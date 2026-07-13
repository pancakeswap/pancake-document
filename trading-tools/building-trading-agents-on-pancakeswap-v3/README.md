# 🤖 BNB AI Agent Studio

> A guide for developers building autonomous agents — with [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) or any framework — that interact with PancakeSwap V3 liquidity pools and farms on BNB Smart Chain.
>
> You describe a strategy; your agent executes it on-chain, unattended. This page covers the PancakeSwap half: the contracts to call, the safe order to call them in, and a complete worked example (an automated V3 range rebalancer). For how to describe, build, and deploy the agent itself, see the BNB Agent Studio docs.

PancakeSwap requires **no integration** for this to work. V3 pools and farms are permissionless smart contracts — your agent calls them directly, the same way the PancakeSwap front end does. Everything below is public on-chain surface.

***

### 1. What an agent can do against PancakeSwap

Concentrated liquidity (V3) gives LPs far better capital efficiency than V2, at the cost of active management: a position only earns fees while the price is inside its tick range, and rewards/yields shift constantly. That operational overhead is exactly what an agent removes. Common strategies:

* **Range rebalancer** — watch an LP position; when price drifts toward the edge of the range, withdraw and re-mint around the new price so the position keeps earning fees. _(Worked example in §6.)_
* **Farm APR router** — track CAKE + fee yield across pools and move liquidity to the highest total yield.
* **Swap/quote bots** — route trades through the Smart Router for best execution across V2 + V3.

All of these are compositions of the same handful of contract calls below.

***

### 2. Contract surface (BNB Smart Chain, chainId 56)

| Contract                              | Address                                      | Your agent uses it to                                                                            |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | Create/manage LP positions — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | Execute swaps with best V2+V3 routing                                                            |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | Stake a position NFT to farm CAKE — `harvest`, `withdraw`                                        |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | Quote a swap before sending it                                                                   |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | Resolve a pool address from `(token0, token1, fee)`                                              |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | Gasless/batched token approvals for **Smart Router swaps** (see §5.1)                            |

> ⚠️ **Always reconfirm addresses** against the canonical PancakeSwap deployment list before sending real value. Treat the table above as a starting point.

A V3 **pool** is identified by `(token0, token1, fee)`. Fee tiers and their tick spacing:

| Fee   | `fee` value | Tick spacing | Typical use               |
| ----- | ----------- | ------------ | ------------------------- |
| 0.01% | `100`       | 1            | Stable–stable             |
| 0.05% | `500`       | 10           | Correlated (e.g. ETH/BTC) |
| 0.25% | `2500`      | 50           | Most pairs                |
| 1.00% | `10000`     | 200          | Exotic / volatile         |

A V3 **position** is an ERC-721 NFT held in the NonfungiblePositionManager. It stores `tickLower`, `tickUpper`, `liquidity`, and accrued fees. You reference it by `tokenId`.

***

### 3. Tooling

You can talk to these contracts with raw ABIs and any web3 library, but the **`@pancakeswap/v3-sdk`** and **`@pancakeswap/smart-router`** packages do the hard math (tick ↔ price, slippage-adjusted minimums, calldata encoding) for you. The examples below use them with [viem](https://viem.sh/).

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

Your agent is just this wallet executing transactions on a schedule or trigger. The wallet is funded and managed by Agent Studio — see the BNB docs.

***

### 4. Reading state (do this before every action)

An agent decides _whether_ to act by reading the chain. The three reads that drive most strategies:

**Pool price and current tick** — build a `Pool` entity from on-chain `slot0` + `liquidity`:

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

**A position you own** — read it from the NonfungiblePositionManager by `tokenId`:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**Is the position in range?** That single boolean is the trigger for a rebalancer. You can tighten it to "within N ticks of the boundary" to act _before_ it goes out of range.

***

### 5. Safe transaction sequences

This is the part to get exactly right. An unattended agent has no human to catch a bad transaction, so every state-changing call must be defended with the four guardrails below.

#### 5.1 Approvals

Before a contract can move your tokens it needs an allowance. The right mechanism depends on which contract you're calling — all three below are permissionless:

* **ERC-20 `approve`** — works for both the Smart Router and the NonfungiblePositionManager, with any token. One tx per token/spender. Simplest, but a standing infinite approval is a standing risk.
* **`selfPermit` (EIP-2612)** — for **NonfungiblePositionManager** liquidity ops. If the token supports EIP-2612, the SDK can bundle a signed, amount-scoped permit _inline_ with `mint`/`increaseLiquidity` via multicall — no separate approve tx. Falls back to `approve` for tokens without EIP-2612.
* **Permit2** — for **Smart Router** swaps. Approve Permit2 once per token, then grant short-lived, signed, amount-scoped allowances per swap.

For an autonomous agent: scope every permit to the exact amount and a short expiry. **Never grant an unbounded approval from an agent wallet that holds meaningful balances.**

#### 5.2 Slippage — never send `amountMin = 0`

Every add/remove/swap must specify a minimum acceptable output. Let the SDK derive it from a tolerance instead of hand-rolling it:

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

For swaps, the Smart Router applies `slippageTolerance` and computes `amountOutMinimum` for you (§6, step 0). **A zero minimum is an open invitation to sandwich bots** — on an unattended wallet that can mean repeated, silent losses.

#### 5.3 Deadlines — always set one

Every call takes a `deadline` (unix seconds). If the tx is still pending at that time it reverts instead of executing at a stale price. Keep it short for an agent:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minutes
```

#### 5.4 Multicall — make multi-step actions atomic

The NonfungiblePositionManager and Smart Router support `multicall`: several calls bundled into **one transaction** that all succeed or all revert. This is not just gas savings — it's a safety property. A rebalance that does `decreaseLiquidity` then `collect` must never half-execute. The SDK bundles for you:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **There is no atomic "rebalance" function.** Moving a range is a _composed_ sequence (remove → collect → mint). Removal and the new mint happen in separate transactions; the price can move between them. Re-read state and recompute minimums for the mint after the removal confirms — don't reuse pre-removal numbers.

#### Guardrail checklist (apply to every agent action)

* \[ ] Token allowance scoped to the amount (Permit2), not infinite
* \[ ] `amount*Min` / `amountOutMinimum` derived from an explicit slippage tolerance, never `0`
* \[ ] Short `deadline` on every call
* \[ ] Multi-step actions bundled via `multicall`
* \[ ] State re-read between separate transactions of a sequence
* \[ ] A per-run cap on value moved, and a sanity check that the pool price is within expected bounds before acting (cheap defense against acting into a manipulated/illiquid pool)

***

### 6. Worked example — automated V3 range rebalancer

The reference agent. It watches one position; when price approaches the range boundary, it pulls liquidity out and re-mints a fresh range centered on the current price. Five steps.

**Trigger:** `pool.tickCurrent` is within a buffer of `tickLower`/`tickUpper` (from §4).

#### Step 0 — (optional) rebalance the token ratio

After you withdraw, you'll hold token0 and token1 in whatever ratio the old range produced. A new, recentered range usually needs a different ratio, so swap the excess via the Smart Router:

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

#### Step 1–3 — remove liquidity, collect, burn (one transaction)

`removeCallParameters` builds the whole bundle: it `decreaseLiquidity` to zero, `collect`s both the withdrawn principal and accrued fees, and `burn`s the now-empty NFT — as a single atomic `multicall`.

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

> If the position is **staked in MasterChefV3**, you don't remove from the NFPM. Call `MasterChefV3.withdraw(tokenId, to)` first to unstake (this also harvests pending CAKE), which returns the NFT to your wallet — then run the removal above. See §7.

#### Step 4 — mint the new range

Recompute ticks around the _current_ price (re-read the pool — see §5.4), snap them to the fee tier's spacing, build a `Position` from the tokens you now hold, and mint.

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

The agent now holds a fresh in-range NFT. If it was farming, re-stake it (§7). Loop back to the §4 read on the next tick.

***

### 7. Farm interactions (MasterChefV3)

Staking a V3 position NFT in MasterChefV3 earns CAKE on top of swap fees.

> **Only positions from pools with an active farm earn CAKE.** PancakeSwap governance registers which pools are farmable (each gets a `pid`). Staking a position whose pool isn't registered reverts with `InvalidPid`. This is the _one_ place agent activity depends on a PancakeSwap-side list — and it's pool-level, not agent-level: any wallet can stake into any _active_ farm. Check the pool has a live farm before building a farming strategy around it. (Managing a position via the NonfungiblePositionManager — mint/collect/rebalance — needs no farm and works for every pool.)

* **Stake** — transfer the position NFT to MasterChefV3 (`safeTransferFrom(owner, masterChefV3, tokenId)`). The farm now custodies the NFT.
* **Harvest** — `harvest(tokenId, to)` claims pending CAKE without unstaking. Use `batchHarvest` to claim across several positions in one tx.
* **Withdraw / exit** — `withdraw(tokenId, to)` unstakes, harvests pending CAKE, and returns the NFT to your wallet. You must withdraw before you can `decreaseLiquidity`/`burn` (the NFPM calls in §6 only work on an NFT your wallet holds).

A rebalancer for a **farmed** position therefore runs: `withdraw` → remove/collect/burn → mint → `safeTransferFrom` back into MasterChefV3.

***

### 8. Safety, limits & disclaimers

Read this before deploying an agent that moves real funds.

* **Autonomy is irreversible.** A deployed agent signs and sends transactions with no human confirmation. A bug, a bad trigger, or a manipulated price feed executes for real. Test on BSC testnet, then cap mainnet exposure (per-trade and per-day limits) before scaling.
* **Slippage and deadlines are mandatory**, not optional (§5). An agent that omits them will eventually be sandwiched.
* **Price-manipulation defense.** Before acting, sanity-check the pool price against an independent reference and skip the run if they diverge — cheap insurance against trading into a manipulated or thin pool.
* **Gas and funding.** Keep the agent wallet funded with BNB for gas; a starved agent can leave a position mid-rebalance (removed but not re-minted). Re-reading state on each run (§4) lets it recover on the next tick.
* **Scaled-UI / RWA tokens.** Some BSC tokens (e.g. Binance Stock Tokens) use on-chain UI multipliers (ERC-8056). On-chain raw amounts differ from displayed amounts. If your agent trades these, do all contract math in raw units and only apply the multiplier for human-facing display.
* **You are responsible for your agent.** PancakeSwap pools are permissionless contracts; deploying an autonomous agent against them is your decision and your risk. This guide is technical reference, not financial advice, and PancakeSwap makes no warranty as to outcomes.

***

### 9. Reference

* **`@pancakeswap/smart-router`** — routing + swap calldata (best in-repo examples are in its README)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, tick/price math
* **BNB Agent Studio** — describing, building, and deploying the agent (BNB docs)
* **PancakeSwap deployment addresses** — canonical contract list (verify before use)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
