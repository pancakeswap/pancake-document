# 🤖 BNB AI Agent Studio

> Una guía para desarrolladores que crean agentes autónomos — con [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) o cualquier framework — que interactúan con pools de liquidez y farms de PancakeSwap V3 en BNB Smart Chain.
>
> Tú describes una estrategia; tu agente la ejecuta on-chain, sin supervisión. Esta página cubre la parte de PancakeSwap: los contratos a los que llamar, el orden seguro para hacerlo y un ejemplo completo (un rebalanceador automatizado de rango V3). Para saber cómo describir, construir e implementar el agente en sí, consulta la documentación de BNB Agent Studio.

PancakeSwap **no requiere ninguna integración** para que esto funcione. Los pools y farms de V3 son contratos inteligentes sin permisos — tu agente los llama directamente, de la misma manera que lo hace el frontend de PancakeSwap. Todo lo que se describe a continuación es superficie on-chain pública.

***

### 1. Qué puede hacer un agente contra PancakeSwap

La liquidez concentrada (V3) ofrece a los LPs una eficiencia de capital mucho mayor que V2, a costa de una gestión activa: una posición solo genera comisiones mientras el precio está dentro de su rango de ticks, y las recompensas/rendimientos cambian constantemente. Esa carga operativa es exactamente lo que un agente elimina. Estrategias comunes:

* **Rebalanceador de rango** — monitorea una posición LP; cuando el precio se acerca al límite del rango, retira y vuelve a abrir alrededor del nuevo precio para que la posición siga generando comisiones. _(Ejemplo práctico en §6.)_
* **Enrutador de APR de Farm** — rastrea el rendimiento de CAKE + comisiones en todos los pools y mueve la liquidez al mayor rendimiento total.
* **Bots de intercambio/cotización** — enruta las operaciones a través del Smart Router para la mejor ejecución entre V2 + V3.

Todas estas son composiciones del mismo conjunto reducido de llamadas de contratos que se describen a continuación.

***

### 2. Superficie de contratos (BNB Smart Chain, chainId 56)

| Contrato                              | Dirección                                    | Tu agente lo usa para                                                                            |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | Crear/gestionar posiciones LP — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Ejecutar intercambios con el mejor enrutamiento V2+V3                                            |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Hacer staking de un NFT de posición para farmear CAKE — `harvest`, `withdraw`                    |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Cotizar un intercambio antes de enviarlo                                                         |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Resolver una dirección de pool a partir de `(token0, token1, fee)`                               |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Aprobaciones de tokens sin gas/en lote para **intercambios con Smart Router** (ver §5.1)         |

> ⚠️ **Siempre reconfirma las direcciones** contra la lista canónica de implementaciones de PancakeSwap antes de enviar valor real. Trata la tabla anterior como punto de partida.

Un **pool** V3 se identifica por `(token0, token1, fee)`. Niveles de comisión y su espaciado de ticks:

| Comisión | Valor `fee` | Espaciado de ticks | Uso típico                |
| -------- | ----------- | ------------------ | ------------------------- |
| 0.01%    | `100`       | 1                  | Stable–stable             |
| 0.05%    | `500`       | 10                 | Correlacionados (ej. ETH/BTC) |
| 0.25%    | `2500`      | 50                 | La mayoría de pares       |
| 1.00%    | `10000`     | 200                | Exóticos / volátiles      |

Una **posición** V3 es un NFT ERC-721 almacenado en el NonfungiblePositionManager. Guarda `tickLower`, `tickUpper`, `liquidity` y las comisiones acumuladas. La referencias por `tokenId`.

***

### 3. Herramientas

Puedes interactuar con estos contratos usando ABIs en bruto y cualquier librería web3, pero los paquetes **`@pancakeswap/v3-sdk`** y **`@pancakeswap/smart-router`** hacen los cálculos complejos (tick ↔ precio, mínimos ajustados por deslizamiento, codificación de calldata) por ti. Los ejemplos a continuación los usan con [viem](https://viem.sh/).

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

Tu agente es simplemente esta billetera ejecutando transacciones según un horario o disparador. La billetera está financiada y gestionada por Agent Studio — consulta la documentación de BNB.

***

### 4. Lectura del estado (hacerlo antes de cada acción)

Un agente decide _si_ actuar leyendo la cadena. Las tres lecturas que impulsan la mayoría de estrategias:

**Precio del pool y tick actual** — construye una entidad `Pool` a partir de los datos on-chain `slot0` + `liquidity`:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress resuelto desde la factory o computePoolAddress()
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

console.log('precio token0→token1:', pool.token0Price.toSignificant(6))
console.log('tick actual:', pool.tickCurrent)
```

**Una posición que posees** — léela desde el NonfungiblePositionManager por `tokenId`:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**¿Está la posición en rango?** Ese único booleano es el disparador para un rebalanceador. Puedes ajustarlo a "dentro de N ticks del límite" para actuar _antes_ de que salga del rango.

***

### 5. Secuencias de transacciones seguras

Esta es la parte que hay que hacer bien. Un agente sin supervisión no tiene a un humano que pueda corregir una transacción incorrecta, por lo que cada llamada que cambie el estado debe estar protegida con las cuatro salvaguardas a continuación.

#### 5.1 Aprobaciones

Antes de que un contrato pueda mover tus tokens, necesita un permiso (allowance). El mecanismo correcto depende del contrato al que llames — los tres siguientes son sin permisos:

* **ERC-20 `approve`** — funciona tanto para el Smart Router como para el NonfungiblePositionManager, con cualquier token. Una tx por token/gastador. La más simple, pero una aprobación infinita permanente es un riesgo permanente.
* **`selfPermit` (EIP-2612)** — para operaciones de liquidez en el **NonfungiblePositionManager**. Si el token soporta EIP-2612, el SDK puede incluir un permit firmado con alcance de cantidad _en línea_ con `mint`/`increaseLiquidity` vía multicall — sin tx de aprobación separada. Recurre a `approve` para tokens sin EIP-2612.
* **Permit2** — para intercambios con el **Smart Router**. Aprueba Permit2 una vez por token, luego otorga permisos firmados de corta duración con alcance de cantidad por cada intercambio.

Para un agente autónomo: limita cada permit a la cantidad exacta y una caducidad corta. **Nunca otorgues una aprobación ilimitada desde una billetera agente que contenga saldos significativos.**

#### 5.2 Deslizamiento — nunca envíes `amountMin = 0`

Cada operación de añadir/retirar/intercambiar debe especificar un resultado mínimo aceptable. Deja que el SDK lo derive a partir de una tolerancia en lugar de calcularlo manualmente:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0.50%

// al hacer mint / añadir:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// al retirar:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Para intercambios, el Smart Router aplica `slippageTolerance` y calcula `amountOutMinimum` por ti (§6, paso 0). **Un mínimo de cero es una invitación abierta a los bots de ataque sándwich** — en una billetera sin supervisión, eso puede significar pérdidas repetidas y silenciosas.

#### 5.3 Plazos límite — siempre establece uno

Cada llamada acepta un `deadline` (segundos unix). Si la tx sigue pendiente en ese momento, revierte en lugar de ejecutarse a un precio obsoleto. Mantenlo corto para un agente:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minutos
```

#### 5.4 Multicall — haz que las acciones de varios pasos sean atómicas

El NonfungiblePositionManager y el Smart Router soportan `multicall`: varias llamadas agrupadas en **una sola transacción** que todas tienen éxito o todas revierten. Esto no es solo un ahorro de gas — es una propiedad de seguridad. Un rebalanceo que hace `decreaseLiquidity` y luego `collect` nunca debe ejecutarse a medias. El SDK agrupa por ti:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **No existe una función atómica de "rebalanceo".** Mover un rango es una secuencia _compuesta_ (retirar → cobrar → crear nueva posición). La retirada y la nueva posición ocurren en transacciones separadas; el precio puede moverse entre ellas. Vuelve a leer el estado y recalcula los mínimos para el mint después de que se confirme la retirada — no reutilices los números previos a la retirada.

#### Lista de verificación de salvaguardas (aplicar a cada acción del agente)

* \[ ] Permiso de token limitado a la cantidad (Permit2), no infinito
* \[ ] `amount*Min` / `amountOutMinimum` derivados de una tolerancia de deslizamiento explícita, nunca `0`
* \[ ] `deadline` corto en cada llamada
* \[ ] Acciones de varios pasos agrupadas vía `multicall`
* \[ ] Estado releído entre transacciones separadas de una secuencia
* \[ ] Un límite de valor movido por ejecución, y una verificación de cordura de que el precio del pool está dentro de los límites esperados antes de actuar (defensa económica contra actuar en un pool manipulado/ilíquido)

***

### 6. Ejemplo práctico — rebalanceador automatizado de rango V3

El agente de referencia. Monitorea una posición; cuando el precio se acerca al límite del rango, retira la liquidez y crea una nueva posición centrada en el precio actual. Cinco pasos.

**Disparador:** `pool.tickCurrent` está dentro de un margen de `tickLower`/`tickUpper` (del §4).

#### Paso 0 — (opcional) rebalancear el ratio de tokens

Después de retirar, tendrás token0 y token1 en cualquier ratio que produjera el antiguo rango. Un nuevo rango recentrado normalmente necesita un ratio diferente, así que intercambia el exceso a través del Smart Router:

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

#### Pasos 1–3 — retirar liquidez, cobrar, quemar (una transacción)

`removeCallParameters` construye todo el paquete: hace `decreaseLiquidity` a cero, `collect` tanto el principal retirado como las comisiones acumuladas, y `burn` el NFT ahora vacío — como un solo `multicall` atómico.

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — salida completa
  slippageTolerance: new Percent(50, 10_000),     // 0.50% — establece amount0Min/amount1Min
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // esperar — el siguiente mint depende de estos tokens
```

> Si la posición está **en staking en MasterChefV3**, no la retiras del NFPM. Primero llama a `MasterChefV3.withdraw(tokenId, to)` para hacer unstaking (esto también cosecha el CAKE pendiente), lo que devuelve el NFT a tu billetera — luego ejecuta la retirada anterior. Ver §7.

#### Paso 4 — crear la nueva posición

Recalcula los ticks alrededor del precio _actual_ (vuelve a leer el pool — ver §5.4), ajústalos al espaciado de la comisión del pool, construye una `Position` con los tokens que tienes ahora y crea la posición.

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* vuelve a leer slot0 + liquidity → nuevo Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // ancho de rango definido por la estrategia

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
  slippageTolerance: new Percent(50, 10_000), // establece amount0Min/amount1Min para el mint
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

El agente ahora tiene un NFT nuevo dentro del rango. Si estaba farmeando, vuelve a hacer staking (§7). Regresa a la lectura del §4 en el siguiente tick.

***

### 7. Interacciones con farms (MasterChefV3)

Hacer staking de un NFT de posición V3 en MasterChefV3 genera CAKE además de las comisiones de intercambio.

> **Solo las posiciones de pools con un farm activo generan CAKE.** La gobernanza de PancakeSwap registra qué pools son farmeables (cada uno tiene un `pid`). Hacer staking de una posición cuyo pool no está registrado revierte con `InvalidPid`. Este es el único lugar donde la actividad del agente depende de una lista del lado de PancakeSwap — y es a nivel de pool, no de agente: cualquier billetera puede hacer staking en cualquier farm activo. (Gestionar una posición a través del NonfungiblePositionManager — mint/collect/rebalanceo — no requiere farm y funciona para cada pool.)

> **Solo las posiciones de pools con un farm activo generan CAKE.** La gobernanza de PancakeSwap registra qué pools son farmeables (cada uno tiene un `pid`). Hacer staking de una posición cuyo pool no está registrado revierte con `InvalidPid`. Este es el _único_ lugar donde la actividad del agente depende de una lista del lado de PancakeSwap — y es a nivel de pool, no de agente: cualquier billetera puede hacer staking en cualquier farm _activo_. Verifica que el pool tiene un farm activo antes de construir una estrategia de farming a su alrededor. (Gestionar una posición a través del NonfungiblePositionManager — mint/collect/rebalanceo — no requiere farm y funciona para cada pool.)

* **Staking** — transfiere el NFT de posición a MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). El farm ahora custodia el NFT.
* **Harvest** — `harvest(tokenId, to)` reclama el CAKE pendiente sin hacer unstaking. Usa `batchHarvest` para reclamar en varias posiciones en una sola tx.
* **Withdraw / salir** — `withdraw(tokenId, to)` hace unstaking, cosecha el CAKE pendiente y devuelve el NFT a tu billetera. Debes hacer withdraw antes de poder ejecutar `decreaseLiquidity`/`burn` (las llamadas NFPM del §6 solo funcionan en un NFT que tu billetera posee).

Un rebalanceador para una posición **farmeada** ejecuta por tanto: `withdraw` → retirar/cobrar/quemar → crear nueva posición → `safeTransferFrom` de vuelta a MasterChefV3.

***

### 8. Seguridad, límites y avisos legales

Lee esto antes de implementar un agente que mueva fondos reales.

* **La autonomía es irreversible.** Un agente implementado firma y envía transacciones sin confirmación humana. Un error, un disparador incorrecto o un feed de precios manipulado se ejecuta de verdad. Prueba en la testnet de BSC y luego limita la exposición en mainnet (límites por operación y por día) antes de escalar.
* **El deslizamiento y los plazos son obligatorios**, no opcionales (§5). Un agente que los omita eventualmente sufrirá un ataque sándwich.
* **Defensa contra manipulación de precios.** Antes de actuar, verifica el precio del pool contra una referencia independiente y omite la ejecución si divergen — seguro económico contra operar en un pool manipulado o con poca liquidez.
* **Gas y financiación.** Mantén la billetera del agente financiada con BNB para gas; un agente sin fondos puede dejar una posición a medias en el rebalanceo (retirada pero sin nueva posición). Volver a leer el estado en cada ejecución (§4) le permite recuperarse en el siguiente tick.
* **Tokens Scaled-UI / RWA.** Algunos tokens de BSC (ej. Binance Stock Tokens) usan multiplicadores UI on-chain (ERC-8056). Las cantidades brutas on-chain difieren de las cantidades mostradas. Si tu agente opera con estos tokens, haz todos los cálculos de contratos en unidades brutas y aplica el multiplicador solo para la visualización orientada al usuario.
* **Eres responsable de tu agente.** Los pools de PancakeSwap son contratos sin permisos; implementar un agente autónomo contra ellos es tu decisión y tu riesgo. Esta guía es referencia técnica, no asesoramiento financiero, y PancakeSwap no ofrece ninguna garantía sobre los resultados.

***

### 9. Referencia

* **`@pancakeswap/smart-router`** — enrutamiento + calldata de intercambio (los mejores ejemplos en el repositorio están en su README)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, matemática de ticks/precios
* **BNB Agent Studio** — descripción, construcción e implementación del agente (documentación de BNB)
* **Direcciones de implementación de PancakeSwap** — lista canónica de contratos (verifica antes de usar)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
