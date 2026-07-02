# 🤖 BNB AI Agent Studio

> Руководство для разработчиков, создающих автономных агентов — с помощью [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) или любого фреймворка — которые взаимодействуют с пулами ликвидности и фармами PancakeSwap V3 на BNB Smart Chain.
>
> Ты описываешь стратегию; твой агент исполняет её в сети без участия человека. Эта страница охватывает сторону PancakeSwap: контракты для вызова, безопасный порядок их вызова и полный рабочий пример (автоматический ребалансировщик диапазона V3). Для описания, создания и развёртывания самого агента смотри документацию BNB Agent Studio.

PancakeSwap не требует **никакой интеграции** для этого. Пулы V3 и фармы — это разрешённые смарт-контракты — твой агент вызывает их напрямую, так же как это делает фронтенд PancakeSwap. Всё нижеследующее является публичной поверхностью в сети.

***

### 1. Что агент может делать с PancakeSwap

Сконцентрированная ликвидность (V3) даёт LP гораздо лучшую эффективность капитала, чем V2, но ценой активного управления: позиция зарабатывает комиссии только пока цена находится внутри диапазона тиков, а вознаграждения и доходность постоянно меняются. Именно эти операционные издержки и устраняет агент. Распространённые стратегии:

* **Ребалансировщик диапазона** — наблюдает за позицией LP; когда цена смещается к краю диапазона, выводит и повторно минтит вокруг новой цены, чтобы позиция продолжала зарабатывать комиссии. _(Рабочий пример в разделе 6.)_
* **Роутер APR фарминга** — отслеживает доходность CAKE + комиссии по пулам и перемещает ликвидность в пул с наибольшей суммарной доходностью.
* **Боты для обменов/котировок** — маршрутизируют сделки через Smart Router для лучшего исполнения по V2 + V3.

Всё это — комбинации одного и того же набора вызовов контрактов ниже.

***

### 2. Поверхность контрактов (BNB Smart Chain, chainId 56)

| Контракт                              | Адрес                                        | Твой агент использует для                                                                        |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | Создание/управление LP-позициями — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Выполнение обменов с лучшей маршрутизацией V2+V3                                                 |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Стейкинг NFT позиции для фарминга CAKE — `harvest`, `withdraw`                                   |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Получение котировки обмена перед отправкой                                                       |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Получение адреса пула из `(token0, token1, fee)`                                                 |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Безгазовые/пакетные одобрения токенов для **обменов через Smart Router** (см. §5.1)              |

> ⚠️ **Всегда перепроверяй адреса** в каноническом списке развёртываний PancakeSwap перед отправкой реальных ценностей. Таблица выше — лишь отправная точка.

Пул V3 **идентифицируется** по `(token0, token1, fee)`. Уровни комиссий и их интервалы тиков:

| Комиссия | Значение `fee` | Интервал тиков | Типичное использование    |
| -------- | -------------- | -------------- | ------------------------- |
| 0.01%    | `100`          | 1              | Стейбл-стейбл             |
| 0.05%    | `500`          | 10             | Коррелированные (напр. ETH/BTC) |
| 0.25%    | `2500`         | 50             | Большинство пар           |
| 1.00%    | `10000`        | 200            | Экзотические / волатильные |

**Позиция** V3 — это ERC-721 NFT, хранящийся в NonfungiblePositionManager. Он хранит `tickLower`, `tickUpper`, `liquidity` и накопленные комиссии. Ты ссылаешься на него по `tokenId`.

***

### 3. Инструменты

Ты можешь взаимодействовать с этими контрактами с помощью сырых ABI и любой web3-библиотеки, но пакеты **`@pancakeswap/v3-sdk`** и **`@pancakeswap/smart-router`** берут на себя сложную математику (тик ↔ цена, минимумы с поправкой на проскальзывание, кодирование calldata). Примеры ниже используют их с [viem](https://viem.sh/).

```bash
pnpm add @pancakeswap/v3-sdk @pancakeswap/smart-router @pancakeswap/sdk viem
```

```tsx
import { createPublicClient, createWalletClient, http } from 'viem'
import { bsc } from 'viem/chains'
import { privateKeyToAccount } from 'viem/accounts'

const account = privateKeyToAccount(process.env.AGENT_PRIVATE_KEY as `0x${string}`)

const publicClient = createPublicClient({ chain: bsc, transport: http() })
const walletClient = createWalletClient({ chain: bsc, account, transport: http() })
```

Твой агент — это просто этот кошелёк, выполняющий транзакции по расписанию или триггеру. Кошелёк пополняется и управляется через Agent Studio — смотри документацию BNB.

***

### 4. Чтение состояния (делай это перед каждым действием)

Агент решает _стоит ли_ действовать, читая сеть. Три чтения, которые определяют большинство стратегий:

**Цена пула и текущий тик** — строим сущность `Pool` из данных сети `slot0` + `liquidity`:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress получен из фабрики или через computePoolAddress()
const [slot0, liquidity] = await Promise.all([
  publicClient.readContract({ address: poolAddress, abi: pancakeV3PoolABI, functionName: 'slot0' }),
  publicClient.readContract({ address: poolAddress, abi: pancakeV3PoolABI, functionName: 'liquidity' }),
])

const pool = new Pool(
  token0, token1, FeeAmount.MEDIUM,
  slot0[0],      // sqrtPriceX96
  liquidity,
  slot0[1],      // tick
)

console.log('price token0→token1:', pool.token0Price.toSignificant(6))
console.log('current tick:', pool.tickCurrent)
```

**Позиция, которой ты владеешь** — читаем её из NonfungiblePositionManager по `tokenId`:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**Находится ли позиция в диапазоне?** Это одно булево значение — триггер для ребалансировщика. Можно сузить до «в пределах N тиков от границы», чтобы действовать _до_ выхода за пределы диапазона.

***

### 5. Безопасные последовательности транзакций

Здесь нужно всё сделать правильно. У неконтролируемого агента нет человека, который мог бы поймать плохую транзакцию, поэтому каждый вызов, меняющий состояние, должен быть защищён четырьмя барьерами ниже.

#### 5.1 Одобрения

Перед тем как контракт сможет перемещать твои токены, ему нужен allowance. Правильный механизм зависит от того, какой контракт вызывается — все три ниже являются разрешёнными:

* **ERC-20 `approve`** — работает как для Smart Router, так и для NonfungiblePositionManager с любым токеном. Одна транзакция на токен/получателя. Самый простой вариант, но постоянное бесконечное одобрение — постоянный риск.
* **`selfPermit` (EIP-2612)** — для операций ликвидности **NonfungiblePositionManager**. Если токен поддерживает EIP-2612, SDK может встроить подписанный permit с ограниченной суммой _внутрь_ `mint`/`increaseLiquidity` через multicall — без отдельной транзакции approve. Возвращается к `approve` для токенов без EIP-2612.
* **Permit2** — для **обменов через Smart Router**. Одобри Permit2 один раз на токен, затем выдавай краткосрочные подписанные allowance с ограниченной суммой на каждый обмен.

Для автономного агента: ограничивай каждый permit точной суммой и коротким сроком действия. **Никогда не выдавай неограниченное одобрение из кошелька агента, который хранит значимые балансы.**

#### 5.2 Проскальзывание — никогда не отправляй `amountMin = 0`

Каждое добавление/удаление/обмен должны указывать минимально приемлемый выход. Позволь SDK выводить его из допуска, а не задавай вручную:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0.50%

// при минтинге / добавлении:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// при удалении:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Для обменов Smart Router применяет `slippageTolerance` и вычисляет `amountOutMinimum` за тебя (§6, шаг 0). **Нулевой минимум — это открытое приглашение для сэндвич-ботов** — для неконтролируемого кошелька это означает повторяющиеся, незаметные потери.

#### 5.3 Дедлайны — всегда устанавливай их

Каждый вызов принимает `deadline` (секунды unix). Если транзакция всё ещё ожидает в это время, она отменяется вместо исполнения по устаревшей цене. Держи его коротким для агента:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 минут
```

#### 5.4 Multicall — делай многошаговые действия атомарными

NonfungiblePositionManager и Smart Router поддерживают `multicall`: несколько вызовов, объединённых в **одну транзакцию**, которые либо все успешны, либо все отменяются. Это не просто экономия газа — это свойство безопасности. Ребалансировка, которая делает `decreaseLiquidity`, а затем `collect`, никогда не должна выполниться наполовину. SDK объединяет за тебя:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **Нет атомарной функции "rebalance".** Перемещение диапазона — это _составная_ последовательность (удаление → сбор → минтинг). Удаление и новый минт происходят в отдельных транзакциях; между ними цена может измениться. Перечитывай состояние и пересчитывай минимумы для минта после подтверждения удаления — не переиспользуй числа до удаления.

#### Контрольный список барьеров (применяй к каждому действию агента)

* \[ ] Allowance токена ограничен суммой (Permit2), не бесконечный
* \[ ] `amount*Min` / `amountOutMinimum` выведены из явного допуска проскальзывания, никогда не `0`
* \[ ] Короткий `deadline` на каждом вызове
* \[ ] Многошаговые действия объединены через `multicall`
* \[ ] Состояние перечитывается между отдельными транзакциями последовательности
* \[ ] Ограничение на объём перемещаемых средств за один запуск, и проверка что цена пула находится в ожидаемых пределах перед действием (дешёвая защита от действий в манипулированном/неликвидном пуле)

***

### 6. Рабочий пример — автоматический ребалансировщик диапазона V3

Эталонный агент. Он наблюдает за одной позицией; когда цена приближается к границе диапазона, он выводит ликвидность и повторно минтит свежий диапазон, центрированный на текущей цене. Пять шагов.

**Триггер:** `pool.tickCurrent` находится в пределах буфера от `tickLower`/`tickUpper` (из §4).

#### Шаг 0 — (опционально) ребалансировка соотношения токенов

После вывода ты будешь держать token0 и token1 в том соотношении, которое дал старый диапазон. Новый, переcentрированный диапазон обычно требует другого соотношения, поэтому обменяй избыток через Smart Router:

```tsx
import { SmartRouter, SwapRouter } from '@pancakeswap/smart-router'
import { TradeType } from '@pancakeswap/swap-sdk-core' 

const quoteProvider = SmartRouter.createQuoteProvider({ onChainProvider: () => publicClient })                                                                                                     
const trade = await SmartRouter.getBestTrade(amountIn, tokenOut, TradeType.EXACT_INPUT, {
  gasPriceWei: () => publicClient.getGasPrice(),
  maxHops: 2,
  poolProvider: SmartRouter.createStaticPoolProvider(candidatePools),
  quoteProvider,
})

const { calldata, value } = SwapRouter.swapCallParameters(trade, {
  slippageTolerance: new Percent(50, 10_000),
  deadlineOrPreviousBlockhash: deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: SMART_ROUTER_ADDRESS, data: calldata, value: BigInt(value) })
```

#### Шаги 1–3 — удаление ликвидности, сбор, сжигание (одна транзакция)

`removeCallParameters` создаёт весь пакет: `decreaseLiquidity` до нуля, `collect` как выведенного принципала, так и накопленных комиссий, и `burn` теперь пустого NFT — как единый атомарный `multicall`.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — полный выход
  slippageTolerance: new Percent(50, 10_000),     // 0.50% — устанавливает amount0Min/amount1Min
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // ждём — следующий минт зависит от этих токенов
```

> Если позиция **застейкана в MasterChefV3**, не удаляй её из NFPM. Сначала вызови `MasterChefV3.withdraw(tokenId, to)` для анстейкинга (это также собирает ожидаемый CAKE), что возвращает NFT в твой кошелёк — затем выполни удаление выше. См. §7.

#### Шаг 4 — минтинг нового диапазона

Пересчитай тики вокруг _текущей_ цены (перечитай пул — см. §5.4), выровняй их по интервалу тиков уровня комиссий, создай `Position` из токенов, которые у тебя теперь есть, и минти.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* перечитай slot0 + liquidity → новый Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // ширина диапазона определяется стратегией

const tickLower = nearestUsableTick(freshPool.tickCurrent - halfWidth, spacing)
const tickUpper = nearestUsableTick(freshPool.tickCurrent + halfWidth, spacing)

const newPosition = Position.fromAmounts({
  pool: freshPool,
  tickLower,
  tickUpper,
  amount0: balance0,
  amount1: balance1,
  useFullPrecision: true,
})

const { calldata, value } = NonfungiblePositionManager.addCallParameters(newPosition, {
  slippageTolerance: new Percent(50, 10_000), // устанавливает amount0Min/amount1Min для минта
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

Теперь агент держит свежий NFT в диапазоне. Если он был в фарминге, застейкай его снова (§7). Вернись к чтению §4 на следующем тике.

***

### 7. Взаимодействия с фармом (MasterChefV3)

Стейкинг NFT позиции V3 в MasterChefV3 зарабатывает CAKE поверх комиссий за обмены.

> **Только позиции из пулов с активным фармом зарабатывают CAKE.** Управление PancakeSwap регистрирует, какие пулы подходят для фарминга (каждый получает `pid`). Стейкинг позиции, пул которой не зарегистрирован, отменится с ошибкой `InvalidPid`. Это единственное место, где активность агента зависит от списка на стороне PancakeSwap — и это на уровне пула, а не агента: любой кошелёк может застейкать в любой активный фарм. (Управление позицией через NonfungiblePositionManager — минт/сбор/ребалансировка — не требует фарма и работает для каждого пула.)

> **Только позиции из пулов с активным фармом зарабатывают CAKE.** Управление PancakeSwap регистрирует, какие пулы подходят для фарминга (каждый получает `pid`). Стейкинг позиции, пул которой не зарегистрирован, отменится с ошибкой `InvalidPid`. Это _единственное_ место, где активность агента зависит от списка на стороне PancakeSwap — и это на уровне пула, а не агента: любой кошелёк может застейкать в любой _активный_ фарм. Проверь, что у пула есть активный фарм, прежде чем строить вокруг него стратегию фарминга. (Управление позицией через NonfungiblePositionManager — минт/сбор/ребалансировка — не требует фарма и работает для каждого пула.)

* **Стейкинг** — перевод NFT позиции в MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). Теперь фарм хранит NFT.
* **Harvest** — `harvest(tokenId, to)` собирает ожидаемый CAKE без анстейкинга. Используй `batchHarvest` для сбора по нескольким позициям в одной транзакции.
* **Вывод / выход** — `withdraw(tokenId, to)` делает анстейкинг, собирает ожидаемый CAKE и возвращает NFT в твой кошелёк. Ты должен вывести перед тем, как сможешь `decreaseLiquidity`/`burn` (вызовы NFPM в §6 работают только с NFT в твоём кошельке).

Ребалансировщик для **фармящейся** позиции выполняет: `withdraw` → удаление/сбор/сжигание → минтинг → `safeTransferFrom` обратно в MasterChefV3.

***

### 8. Безопасность, ограничения и отказ от ответственности

Прочитай это перед развёртыванием агента, который перемещает реальные средства.

* **Автономность необратима.** Развёрнутый агент подписывает и отправляет транзакции без подтверждения человека. Ошибка, плохой триггер или манипулированный ценовой поток выполняются в реальности. Тестируй на тестовой сети BSC, затем ограничивай воздействие на основной сети (лимиты на одну сделку и в день) перед масштабированием.
* **Проскальзывание и дедлайны обязательны**, а не опциональны (§5). Агент, который их опускает, рано или поздно будет атакован сэндвич-ботами.
* **Защита от манипуляции ценой.** Перед действием проверяй цену пула по независимому источнику и пропускай запуск, если они расходятся — дешёвая страховка от торговли в манипулированный или тонкий пул.
* **Газ и финансирование.** Держи кошелёк агента пополненным BNB для газа; истощённый агент может оставить позицию в середине ребалансировки (удалено, но не перемонтировано). Перечитывание состояния при каждом запуске (§4) позволяет ему восстановиться на следующем тике.
* **Токены с масштабированным UI / RWA.** Некоторые токены BSC (например, Binance Stock Tokens) используют мультипликаторы UI на цепочке (ERC-8056). Необработанные суммы в сети отличаются от отображаемых. Если твой агент торгует ими, выполняй всю математику контракта в необработанных единицах и применяй мультипликатор только для отображения пользователю.
* **Ты несёшь ответственность за своего агента.** Пулы PancakeSwap — это разрешённые контракты; развёртывание автономного агента против них — твоё решение и твой риск. Это руководство является технической справкой, а не финансовым советом, и PancakeSwap не даёт никаких гарантий относительно результатов.

***

### 9. Справочные материалы

* **`@pancakeswap/smart-router`** — маршрутизация + calldata обмена (лучшие примеры в репозитории находятся в его README)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, математика тиков/цен
* **BNB Agent Studio** — описание, создание и развёртывание агента (документация BNB)
* **Адреса развёртывания PancakeSwap** — канонический список контрактов (проверяй перед использованием)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
