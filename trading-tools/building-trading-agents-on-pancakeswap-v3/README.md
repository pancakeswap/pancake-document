# 🤖 在 PancakeSwap V3 上构建交易代理

本页提供概览，更多信息请访问 [pancakeswap.ai](https://pancakeswap.ai)

> 这是一份面向开发者的指南，帮助你构建与 BNB Smart Chain 上 PancakeSwap V3 流动性资金池和农场交互的自主代理，可使用 [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) 或任何框架。
>
> 你描述一个策略，你的代理就会在链上无人值守地执行它。本页涵盖 PancakeSwap 这一半：要调用的合约、安全的调用顺序，以及一个完整的实战示例（自动化 V3 区间再平衡器）。关于如何描述、构建和部署代理本身，请参阅 BNB Agent Studio 文档。

PancakeSwap **无需任何集成**即可实现这一点。V3 资金池和农场是无需许可的智能合约——你的代理可以直接调用它们，方式与 PancakeSwap 前端相同。下面的一切都是链上公开的接口。

***

### 1. 代理可以用 PancakeSwap 做什么

集中流动性（V3）为 LP 带来了远高于 V2 的资金效率，代价是需要主动管理：头寸只有在价格处于其 tick 区间内时才会赚取手续费，而奖励/收益也在不断变化。这种运营负担，正是代理可以消除的。常见策略：

* **区间再平衡器** — 监控一个 LP 头寸；当价格漂向区间边缘时，撤出并围绕新价格重新铸造，使头寸持续赚取手续费。_（实战示例见 §6。）_
* **农场 APR 路由器** — 跟踪各资金池的 CAKE + 手续费收益，并将流动性转移到总收益最高的资金池。
* **兑换/报价机器人** — 通过 Smart Router 路由交易，在 V2 + V3 之间获得最佳成交。

所有这些都是由下面同样那几个合约调用组合而成的。

***

### 2. 合约接口（BNB Smart Chain，chainId 56）

| 合约                                    | 地址                                           | 你的代理用它来                                                                                   |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | 创建/管理 LP 头寸 — `mint`、`increaseLiquidity`、`decreaseLiquidity`、`collect`、`burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | 以 V2+V3 最佳路由执行兑换                                                            |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | 质押头寸 NFT 以赚取 CAKE — `harvest`、`withdraw`                                        |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | 在发送兑换前先获取报价                                                                   |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | 根据 `(token0, token1, fee)` 解析资金池地址                                              |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | 为 **Smart Router 兑换**提供免 gas/批量的代币授权（见 §5.1）                            |

> ⚠️ **在发送真实资产之前，请务必对照 PancakeSwap 官方部署列表再次确认地址。** 请将上表仅视为起点。

一个 V3 **资金池**由 `(token0, token1, fee)` 标识。费率档位及其 tick 间距：

| 费率   | `fee` 值 | Tick 间距 | 典型用途               |
| ----- | ----------- | ------------ | ------------------------- |
| 0.01% | `100`       | 1            | 稳定币–稳定币             |
| 0.05% | `500`       | 10           | 相关性资产（如 ETH/BTC） |
| 0.25% | `2500`      | 50           | 大多数交易对              |
| 1.00% | `10000`     | 200          | 小众 / 高波动             |

一个 V3 **头寸**是由 NonfungiblePositionManager 持有的 ERC-721 NFT。它存储 `tickLower`、`tickUpper`、`liquidity` 以及累积的手续费。你通过 `tokenId` 引用它。

***

### 3. 工具

你可以使用原始 ABI 和任意 web3 库与这些合约交互，但 **`@pancakeswap/v3-sdk`** 和 **`@pancakeswap/smart-router`** 包会替你完成繁琐的数学运算（tick ↔ 价格、考虑滑点的最小值、calldata 编码）。下面的示例搭配 [viem](https://viem.sh/) 使用它们。

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

你的代理其实就是这个钱包按计划或触发条件执行交易。该钱包由 Agent Studio 注资和管理——请参阅 BNB 文档。

***

### 4. 读取状态（每次操作前都要做）

代理通过读取链上数据来决定_是否_行动。驱动大多数策略的三项读取：

**资金池价格和当前 tick** — 用链上的 `slot0` + `liquidity` 构建 `Pool` 实体：

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress resolved from the factory or computePoolAddress()
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

**你持有的头寸** — 通过 `tokenId` 从 NonfungiblePositionManager 读取：

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**头寸是否在区间内？** 这个单一的布尔值就是再平衡器的触发条件。你可以把它收紧为"距离边界不超过 N 个 tick"，以便在它脱离区间_之前_就采取行动。

***

### 5. 安全的交易序列

这是必须做到万无一失的部分。无人值守的代理没有人来拦截错误交易，因此每一次改变状态的调用都必须由下面四道防护来保护。

#### 5.1 授权

合约在转移你的代币之前需要获得授权额度。正确的机制取决于你调用的是哪个合约——以下三种都是无需许可的：

* **ERC-20 `approve`** — 适用于 Smart Router 和 NonfungiblePositionManager，支持任何代币。每个代币/被授权方需要一笔交易。最简单，但长期有效的无限授权是一种长期风险。
* **`selfPermit`（EIP-2612）** — 用于 **NonfungiblePositionManager** 的流动性操作。如果代币支持 EIP-2612，SDK 可以通过 multicall 将一个已签名、限定额度的 permit _内嵌_到 `mint`/`increaseLiquidity` 中——无需单独的 approve 交易。对于不支持 EIP-2612 的代币，则回退到 `approve`。
* **Permit2** — 用于 **Smart Router** 兑换。每个代币对 Permit2 授权一次，然后为每次兑换授予短期、已签名、限定额度的授权。

对于自主代理：把每个 permit 都限定在确切的金额和较短的有效期内。**切勿从持有可观余额的代理钱包授予无限授权。**

#### 5.2 滑点 — 永远不要发送 `amountMin = 0`

每一次添加/移除/兑换都必须指定可接受的最小输出。让 SDK 根据容忍度推导它，而不是手动计算：

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0.50%

// when minting / adding:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// when removing:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

对于兑换，Smart Router 会应用 `slippageTolerance` 并替你计算 `amountOutMinimum`（§6，步骤 0）。**最小值为零等于向三明治机器人发出邀请**——在无人值守的钱包上，这可能意味着反复、悄无声息的损失。

#### 5.3 截止时间 — 始终设置

每次调用都带有一个 `deadline`（unix 秒）。如果交易到该时间仍处于待处理状态，它会回滚，而不是以过时的价格执行。对代理来说应将其设得较短：

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minutes
```

#### 5.4 Multicall — 让多步操作具有原子性

NonfungiblePositionManager 和 Smart Router 支持 `multicall`：把多个调用打包进**一笔交易**，要么全部成功，要么全部回滚。这不只是节省 gas——它是一项安全属性。先 `decreaseLiquidity` 再 `collect` 的再平衡绝不能只执行一半。SDK 会替你打包：

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **不存在原子的"再平衡"函数。** 移动区间是一个_组合式_序列（移除 → 收取 → 铸造）。移除和新的铸造发生在不同的交易中；价格可能在两者之间变动。移除确认后，请重新读取状态并为铸造重新计算最小值——不要复用移除之前的数字。

#### 防护清单（适用于代理的每一次操作）

* \[ ] 代币授权额度限定在所需金额（Permit2），而非无限
* \[ ] `amount*Min` / `amountOutMinimum` 由明确的滑点容忍度推导，绝不为 `0`
* \[ ] 每次调用都设置较短的 `deadline`
* \[ ] 多步操作通过 `multicall` 打包
* \[ ] 序列中各独立交易之间重新读取状态
* \[ ] 设置每次运行的转移价值上限，并在行动前对资金池价格是否在预期范围内做合理性检查（以低成本防范在被操纵/流动性不足的资金池中操作）

***

### 6. 实战示例 — 自动化 V3 区间再平衡器

这是参考代理。它监控一个头寸；当价格接近区间边界时，撤出流动性，并重新铸造一个以当前价格为中心的新区间。共五步。

**触发条件：** `pool.tickCurrent` 距离 `tickLower`/`tickUpper` 在缓冲范围之内（来自 §4）。

#### 步骤 0 —（可选）重新平衡代币比例

撤出后，你持有的 token0 和 token1 的比例就是旧区间产生的比例。重新居中的新区间通常需要不同的比例，因此请通过 Smart Router 兑换多余部分：

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

#### 步骤 1–3 — 移除流动性、收取、销毁（一笔交易）

`removeCallParameters` 会构建完整的打包调用：它将流动性 `decreaseLiquidity` 至零，`collect` 撤出的本金和累积的手续费，并 `burn` 已清空的 NFT——全部作为一个原子的 `multicall`。

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — full exit
  slippageTolerance: new Percent(50, 10_000),     // 0.50% — sets amount0Min/amount1Min
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // wait — the next mint depends on these tokens
```

> 如果头寸**已质押在 MasterChefV3** 中，则无法从 NFPM 中移除。请先调用 `MasterChefV3.withdraw(tokenId, to)` 取消质押（这也会领取待收的 CAKE），NFT 会返回你的钱包——然后再执行上面的移除操作。见 §7。

#### 步骤 4 — 铸造新区间

围绕_当前_价格重新计算 tick（重新读取资金池——见 §5.4），将其对齐到该费率档位的间距，用你现在持有的代币构建一个 `Position`，然后铸造。

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* re-read slot0 + liquidity → new Pool (§4) */
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // strategy-defined range width

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
  slippageTolerance: new Percent(50, 10_000), // sets amount0Min/amount1Min for the mint
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

代理现在持有一个全新的区间内 NFT。如果之前在做农场，请重新质押它（§7）。在下一个 tick 回到 §4 的读取步骤继续循环。

***

### 7. 农场交互（MasterChefV3）

将 V3 头寸 NFT 质押到 MasterChefV3 中，可在兑换手续费之外额外赚取 CAKE。

> **只有来自有活跃农场的资金池的头寸才能赚取 CAKE。** PancakeSwap 治理会登记哪些资金池可以开农场（每个资金池会分配一个 `pid`）。质押一个其资金池未登记的头寸会以 `InvalidPid` 回滚。这是代理活动唯一依赖 PancakeSwap 一侧列表的地方——而且它是资金池层面的，而非代理层面的：任何钱包都可以质押到任何活跃的农场。（通过 NonfungiblePositionManager 管理头寸——铸造/收取/再平衡——不需要农场，对所有资金池都适用。）

> **只有来自有活跃农场的资金池的头寸才能赚取 CAKE。** PancakeSwap 治理会登记哪些资金池可以开农场（每个资金池会分配一个 `pid`）。质押一个其资金池未登记的头寸会以 `InvalidPid` 回滚。这是代理活动_唯一_依赖 PancakeSwap 一侧列表的地方——而且它是资金池层面的，而非代理层面的：任何钱包都可以质押到任何_活跃的_农场。在围绕某个资金池构建农场策略之前，请先确认它有一个正在运行的农场。（通过 NonfungiblePositionManager 管理头寸——铸造/收取/再平衡——不需要农场，对所有资金池都适用。）

* **质押** — 将头寸 NFT 转移到 MasterChefV3（`safeTransferFrom(owner, masterChefV3, tokenId)`）。此后农场会托管该 NFT。
* **收获** — `harvest(tokenId, to)` 在不取消质押的情况下领取待收的 CAKE。使用 `batchHarvest` 可在一笔交易中跨多个头寸领取。
* **提取 / 退出** — `withdraw(tokenId, to)` 取消质押、领取待收的 CAKE，并将 NFT 返回你的钱包。你必须先提取，才能执行 `decreaseLiquidity`/`burn`（§6 中的 NFPM 调用只对你的钱包所持有的 NFT 有效）。

因此，对**已开农场**的头寸进行再平衡的流程是：`withdraw` → 移除/收取/销毁 → 铸造 → 通过 `safeTransferFrom` 转回 MasterChefV3。

***

### 8. 安全、限制与免责声明

在部署会转移真实资金的代理之前，请先阅读本节。

* **自主性是不可逆的。** 已部署的代理会在没有人工确认的情况下签名并发送交易。一个漏洞、一次错误的触发或一个被操纵的价格源都会真实执行。请先在 BSC 测试网上测试，然后在扩大规模之前限制主网敞口（每笔和每日限额）。
* **滑点和截止时间是强制性的**，而非可选（§5）。省略它们的代理迟早会被三明治攻击。
* **防范价格操纵。** 行动之前，请将资金池价格与独立的参考价格做合理性检查，如果两者出现偏差则跳过本次运行——这是防止在被操纵或流动性稀薄的资金池中交易的低成本保险。
* **Gas 与资金。** 请让代理钱包持有足够的 BNB 用于 gas；资金枯竭的代理可能让头寸停在再平衡的中途（已移除但尚未重新铸造）。每次运行都重新读取状态（§4）可以让它在下一个 tick 恢复。
* **Scaled-UI / RWA 代币。** 一些 BSC 代币（例如 Binance Stock Tokens）使用链上 UI 乘数（ERC-8056）。链上原始数量与显示数量不同。如果你的代理交易这些代币，请使用原始单位完成所有合约运算，仅在面向用户的显示中应用该乘数。
* **你要对你的代理负责。** PancakeSwap 资金池是无需许可的合约；针对它们部署自主代理是你的决定，风险由你承担。本指南是技术参考，不构成财务建议，PancakeSwap 对结果不作任何保证。

***

### 9. 参考资料

* **`@pancakeswap/smart-router`** — 路由 + 兑换 calldata（仓库内最佳示例见其 README）
* **`@pancakeswap/v3-sdk`** — `Pool`、`Position`、`NonfungiblePositionManager`、`Multicall`、tick/价格运算
* **BNB Agent Studio** — 描述、构建和部署代理（BNB 文档）
* **PancakeSwap 部署地址** — 官方合约列表（使用前请核实）
* **ERC-8056（Scaled UI Amount）** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
