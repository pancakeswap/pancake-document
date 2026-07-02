---
description: Миграция на MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 — это новый основной контракт стейкинга для Farms, предоставляющий большую гибкость для управления эмиссией $CAKE, включая CAKE пул, сжигание и другие продукты PancakeSwap.

### Нужно ли мне выполнять миграцию?

Если ты сейчас используешь PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), тебе нужно мигрировать на новый контракт ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)).

### Обзор

#### Депозит

Если ты сейчас используешь `enterStaking(uint256 _amount)` в текущем PancakeSwap MasterChef, тебе нужно перейти на новый контракт CAKE pool. Ознакомься с соответствующей документацией [здесь](../cake-syrup-pool.md).

Функция депозита для пулов ферм не изменилась. Однако тебе нужно будет обновить адрес MasterChef и `pid` — смотри [список ферм](list-of-farms.md) для новых `pid` в MasterChef v2.

#### Типы пулов

MasterChef v2 имеет 2 типа пулов: обычные фермерские пулы и специальные фермерские пулы. Ты можешь использовать `poolInfo(_pid).isRegular` для запроса типа пула. Они используют разные `totalAllocPoint`, образуя два независимых набора пулов.

Специальные фермерские пулы: только адреса из белого списка могут вносить депозиты. Обычно они используются внутренними продуктами PancakeSwap для распределения вознаграждений.

Обычные фермерские пулы: стандартные фермы LP-токенов. Например, CAKE-BNB, BNB-BUSD и т.д.

#### Вывод

Если ты сейчас используешь `leaveStaking(uint256 _amount)` в текущем PancakeSwap MasterChef, тебе нужно перейти на новый контракт CAKE pool. Ознакомься с соответствующей документацией [здесь](../cake-syrup-pool.md).

Функция вывода для пулов ферм не изменилась. Однако тебе нужно будет обновить адрес MasterChef и `pid` — смотри [список ферм](list-of-farms.md) для новых `pid` в MasterChef v2.

#### Баланс стейкинга

Используй `userInfo[_pid][_user].amount` для запроса баланса стейкинга.

#### Токен стейкинга

Обрати внимание, что новая структура `PoolInfo` **не** содержит поля адреса LP-токена — тебе нужно использовать `lpToken(_pid)` для запроса токена стейкинга любого пула.

#### Общие доли/суммы стейкинга

Используй `lpToken.balanceOf(MasterChef.address)` для получения общей суммы стейкинга для любого фермерского пула.

Однако в MasterChef v2 доли пользователей могут быть усилены (скоро). Поэтому вознаграждения рассчитываются с использованием нового поля `totalBoostedShare` в `PoolInfo` в качестве общих долей каждого пула. Например, если в пуле 0 есть 2 пользователя — user1 стейкирует 100 LP (без буста), user2 стейкирует 100 (с `boostMultiplier` равным 1.05), то `totalBoostedShare` станет равным 205, что приведёт к получению user2 большего количества вознаграждений.

#### CakePerBlock

Ты можешь использовать `cakePerBlock(bool _isRegular)` для запроса вознаграждения CAKE за блок, которое идёт на все фермы PancakeSwap.

### Адрес контракта в основной сети

**Название контракта:** MasterChef v2\
**Адрес контракта:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[Посмотреть PancakeSwap: Main Staking Contract v2 на BscScan.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Тестовая среда

Ты можешь использовать следующую тестовую среду для проверки интеграции своего проекта с новым PancakeSwap MasterChef v2. Если у тебя есть вопросы, обращайся к нашей команде через существующие каналы или по электронной почте bun@pancakeswap.com.

**Тестовые токены:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (можно создавать с помощью `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (можно создавать с помощью `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory и Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP Pairs

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
