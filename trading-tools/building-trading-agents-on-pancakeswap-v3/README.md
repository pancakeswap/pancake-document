# 🤖 BNB AI Agent Studio

> BNB Smart Chain पर PancakeSwap V3 liquidity pools और farms के साथ इंटरैक्ट करने वाले autonomous agents बनाने वाले डेवलपर्स के लिए एक गाइड — [BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio) या किसी भी framework के साथ।
>
> आप एक strategy describe करते हैं; आपका agent उसे ऑन-चेन, बिना निगरानी के निष्पादित करता है। यह पेज PancakeSwap का हिस्सा कवर करता है: कौन से contracts call करने हैं, उन्हें किस सुरक्षित क्रम में call करना है, और एक पूरा worked example (एक automated V3 range rebalancer)। agent को कैसे describe, build और deploy करें, इसके लिए BNB Agent Studio docs देखें।

PancakeSwap को इसके काम के लिए **कोई integration** आवश्यक नहीं है। V3 pools और farms permissionless smart contracts हैं — आपका agent उन्हें सीधे call करता है, उसी तरह जैसे PancakeSwap front end करता है। नीचे सब कुछ public on-chain surface है।

***

### 1. एक agent PancakeSwap के विरुद्ध क्या कर सकता है

Concentrated liquidity (V3) LPs को V2 की तुलना में बहुत बेहतर capital efficiency देता है, सक्रिय management की कीमत पर: एक position तभी fees कमाती है जब price उसके tick range के भीतर हो, और rewards/yields लगातार बदलते रहते हैं। वह operational overhead ही वह है जिसे एक agent हटाता है। सामान्य strategies:

* **Range rebalancer** — एक LP position देखें; जब price range की सीमा की ओर drift करे, तो नई price के चारों ओर withdraw करें और re-mint करें ताकि position fees कमाती रहे। _(§6 में Worked example।)_
* **Farm APR router** — pools में CAKE + fee yield track करें और liquidity को उच्चतम total yield पर ले जाएं।
* **Swap/quote bots** — V2 + V3 में बेहतर execution के लिए Smart Router के माध्यम से trades route करें।

ये सभी नीचे दिए गए उसी handful of contract calls की compositions हैं।

***

### 2. Contract surface (BNB Smart Chain, chainId 56)

| Contract                              | Address                                      | आपका agent इसे इस्तेमाल करता है                                                                        |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | LP positions बनाना/प्रबंधित करना — `mint`, `increaseLiquidity`, `decreaseLiquidity`, `collect`, `burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | बेहतर V2+V3 routing के साथ swaps निष्पादित करना                                                    |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | CAKE farm करने के लिए position NFT stake करना — `harvest`, `withdraw`                              |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | भेजने से पहले swap quote करना                                                                      |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | `(token0, token1, fee)` से pool address resolve करना                                              |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | **Smart Router swaps** के लिए gasless/batched token approvals (§5.1 देखें)                        |

> ⚠️ **हमेशा addresses को** real value भेजने से पहले canonical PancakeSwap deployment list के विरुद्ध **पुनः confirm करें**। ऊपर की तालिका को starting point मानें।

एक V3 **pool** की पहचान `(token0, token1, fee)` द्वारा होती है। Fee tiers और उनका tick spacing:

| Fee   | `fee` value | Tick spacing | सामान्य उपयोग               |
| ----- | ----------- | ------------ | ------------------------- |
| 0.01% | `100`       | 1            | Stable–stable             |
| 0.05% | `500`       | 10           | Correlated (जैसे ETH/BTC) |
| 0.25% | `2500`      | 50           | अधिकतर pairs              |
| 1.00% | `10000`     | 200          | Exotic / volatile         |

एक V3 **position** एक ERC-721 NFT है जो NonfungiblePositionManager में रखा जाता है। यह `tickLower`, `tickUpper`, `liquidity`, और accrued fees संग्रहीत करता है। आप इसे `tokenId` द्वारा reference करते हैं।

***

### 3. Tooling

आप raw ABIs और किसी भी web3 library के साथ इन contracts से बात कर सकते हैं, लेकिन **`@pancakeswap/v3-sdk`** और **`@pancakeswap/smart-router`** packages आपके लिए कठिन गणित (tick ↔ price, slippage-adjusted minimums, calldata encoding) करते हैं। नीचे के उदाहरण उन्हें [viem](https://viem.sh/) के साथ उपयोग करते हैं।

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

आपका agent बस यही wallet है जो एक schedule या trigger पर transactions execute करता है। wallet Agent Studio द्वारा funded और managed है — BNB docs देखें।

***

### 4. State पढ़ना (हर action से पहले यह करें)

एक agent chain पढ़कर decide करता है कि _कब_ action करना है। तीन reads जो अधिकांश strategies को drive करते हैं:

**Pool price और current tick** — on-chain `slot0` + `liquidity` से एक `Pool` entity build करें:

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddress factory से या computePoolAddress() से resolved
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

**आपकी अपनी position** — `tokenId` द्वारा NonfungiblePositionManager से पढ़ें:

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**क्या position in range है?** वह single boolean एक rebalancer के लिए trigger है। आप इसे "boundary के N ticks के भीतर" तक tight कर सकते हैं ताकि out of range होने से _पहले_ action करें।

***

### 5. Safe transaction sequences

यह वह हिस्सा है जिसे बिल्कुल सही करना है। एक unattended agent के पास कोई human नहीं है जो bad transaction पकड़ सके, इसलिए हर state-changing call को नीचे दिए गए चार guardrails से defend किया जाना चाहिए।

#### 5.1 Approvals

इससे पहले कि एक contract आपके tokens move कर सके, उसे allowance चाहिए। सही mechanism इस पर निर्भर करता है कि आप कौन सा contract call कर रहे हैं — तीनों नीचे permissionless हैं:

* **ERC-20 `approve`** — Smart Router और NonfungiblePositionManager दोनों के लिए काम करता है, किसी भी token के साथ। प्रति token/spender एक tx। सबसे सरल, लेकिन एक standing infinite approval एक standing risk है।
* **`selfPermit` (EIP-2612)** — **NonfungiblePositionManager** liquidity ops के लिए। यदि token EIP-2612 का समर्थन करता है, तो SDK एक signed, amount-scoped permit को `mint`/`increaseLiquidity` के साथ multicall के माध्यम से _inline_ bundle कर सकता है — कोई अलग approve tx नहीं। EIP-2612 के बिना tokens के लिए `approve` पर fall back करता है।
* **Permit2** — **Smart Router** swaps के लिए। Permit2 को प्रति token एक बार approve करें, फिर प्रति swap short-lived, signed, amount-scoped allowances दें।

एक autonomous agent के लिए: हर permit को exact amount और short expiry तक scope करें। **किसी agent wallet से कभी unbounded approval न दें जिसमें meaningful balances हों।**

#### 5.2 Slippage — कभी `amountMin = 0` न भेजें

हर add/remove/swap में एक minimum acceptable output specify करना होगा। इसे हाथ से बनाने के बजाय SDK को tolerance से derive करने दें:

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0.50%

// minting / adding करते समय:
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// removing करते समय:
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

Swaps के लिए, Smart Router `slippageTolerance` apply करता है और आपके लिए `amountOutMinimum` compute करता है (§6, step 0)। **Zero minimum sandwich bots के लिए एक open invitation है** — एक unattended wallet पर इसका मतलब बार-बार, silent नुकसान हो सकता है।

#### 5.3 Deadlines — हमेशा एक सेट करें

हर call एक `deadline` (unix seconds) लेती है। यदि tx उस समय तक pending है तो वह stale price पर execute होने के बजाय revert हो जाती है। एक agent के लिए इसे short रखें:

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5 minutes
```

#### 5.4 Multicall — multi-step actions को atomic बनाएं

NonfungiblePositionManager और Smart Router `multicall` का समर्थन करते हैं: कई calls को **एक transaction** में bundle करना जो सभी succeed होती हैं या सभी revert हो जाती हैं। यह केवल gas savings नहीं है — यह एक safety property है। एक rebalance जो `decreaseLiquidity` फिर `collect` करती है, कभी half-execute नहीं होनी चाहिए। SDK आपके लिए bundle करता है:

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **कोई atomic "rebalance" function नहीं है।** एक range move करना एक _composed_ sequence है (remove → collect → mint)। Removal और नया mint अलग transactions में होते हैं; बीच में price move हो सकती है। Removal confirm होने के बाद mint के लिए state re-read करें और minimums recompute करें — pre-removal numbers reuse न करें।

#### Guardrail checklist (हर agent action पर apply करें)

* \[ ] Token allowance amount तक scoped (Permit2), infinite नहीं
* \[ ] `amount*Min` / `amountOutMinimum` explicit slippage tolerance से derived, कभी `0` नहीं
* \[ ] हर call पर short `deadline`
* \[ ] Multi-step actions `multicall` के माध्यम से bundled
* \[ ] एक sequence के अलग transactions के बीच State re-read
* \[ ] Moved value पर per-run cap, और action से पहले sanity check कि pool price expected bounds के भीतर है (manipulated/illiquid pool में action के विरुद्ध सस्ती defense)

***

### 6. Worked example — automated V3 range rebalancer

Reference agent। यह एक position देखता है; जब price range boundary के पास आती है, तो liquidity निकालता है और current price के चारों ओर fresh range re-mint करता है। पाँच चरण।

**Trigger:** `pool.tickCurrent` `tickLower`/`tickUpper` के buffer के भीतर है (§4 से)।

#### Step 0 — (optional) token ratio को rebalance करें

Withdraw के बाद, आप token0 और token1 जो भी ratio में old range produce करे, उसे hold करेंगे। एक नया, recentered range आमतौर पर एक अलग ratio चाहता है, इसलिए Smart Router के माध्यम से excess swap करें:

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

#### Step 1–3 — liquidity remove करें, collect करें, burn करें (एक transaction)

`removeCallParameters` पूरा bundle build करता है: यह `decreaseLiquidity` को zero करता है, withdrawn principal और accrued fees दोनों `collect` करता है, और अब empty NFT `burn` करता है — एक single atomic `multicall` के रूप में।

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — full exit
  slippageTolerance: new Percent(50, 10_000),     // 0.50% — amount0Min/amount1Min सेट करता है
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // wait — अगला mint इन tokens पर निर्भर है
```

> यदि position **MasterChefV3 में staked है**, तो आप NFPM से नहीं हटाते। पहले `MasterChefV3.withdraw(tokenId, to)` call करें unstake करने के लिए (यह pending CAKE भी harvest करता है), जो NFT आपके wallet में वापस करता है — फिर ऊपर दिया removal run करें। §7 देखें।

#### Step 4 — नया range mint करें

_Current_ price के चारों ओर ticks recompute करें (pool re-read करें — §5.4 देखें), उन्हें fee tier की spacing पर snap करें, अब आपके पास जो tokens हैं उनसे एक `Position` build करें, और mint करें।

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* slot0 + liquidity re-read → new Pool (§4) */
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
  slippageTolerance: new Percent(50, 10_000), // mint के लिए amount0Min/amount1Min सेट करता है
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

Agent के पास अब एक fresh in-range NFT है। यदि यह farming था, तो इसे re-stake करें (§7)। अगले tick पर §4 read पर वापस loop करें।

***

### 7. Farm interactions (MasterChefV3)

MasterChefV3 में V3 position NFT stake करने से swap fees के ऊपर CAKE मिलती है।

> **केवल active farm वाले pools की positions CAKE earn करती हैं।** PancakeSwap governance register करता है कि कौन से pools farmable हैं (प्रत्येक को एक `pid` मिलता है)। किसी ऐसी position को staking करना जिसका pool registered नहीं है, `InvalidPid` के साथ revert होगा। यह एकमात्र जगह है जहाँ agent activity एक PancakeSwap-side list पर निर्भर है — और यह pool-level है, agent-level नहीं: कोई भी wallet किसी भी active farm में stake कर सकता है। (NonfungiblePositionManager के माध्यम से position manage करना — mint/collect/rebalance — किसी farm की आवश्यकता नहीं है और हर pool के लिए काम करता है।)

* **Stake** — position NFT को MasterChefV3 में transfer करें (`safeTransferFrom(owner, masterChefV3, tokenId)`)। Farm अब NFT की custody करता है।
* **Harvest** — `harvest(tokenId, to)` unstaking के बिना pending CAKE claim करता है। एक tx में कई positions में claim करने के लिए `batchHarvest` उपयोग करें।
* **Withdraw / exit** — `withdraw(tokenId, to)` unstakes, pending CAKE harvest करता है, और NFT आपके wallet में वापस करता है। `decreaseLiquidity`/`burn` से पहले आपको withdraw करना होगा (§6 में NFPM calls केवल तब काम करती हैं जब आपका wallet NFT hold करे)।

एक **farmed** position के लिए rebalancer इसलिए चलता है: `withdraw` → remove/collect/burn → mint → `safeTransferFrom` MasterChefV3 में वापस।

***

### 8. Safety, limits और disclaimers

Real funds move करने वाला agent deploy करने से पहले यह पढ़ें।

* **Autonomy irreversible है।** एक deployed agent बिना human confirmation के transactions sign और send करता है। एक bug, bad trigger, या manipulated price feed real के लिए execute होता है। BSC testnet पर test करें, फिर mainnet exposure (per-trade और per-day limits) cap करें scaling से पहले।
* **Slippage और deadlines mandatory हैं**, optional नहीं (§5)। एक agent जो उन्हें छोड़ता है वह eventually sandwiched होगा।
* **Price-manipulation defense।** Action करने से पहले, pool price को एक independent reference के विरुद्ध sanity-check करें और यदि वे diverge हों तो run skip करें — manipulated या thin pool में trading के विरुद्ध सस्ता insurance।
* **Gas और funding।** Agent wallet को gas के लिए BNB से funded रखें; एक starved agent position को mid-rebalance (removed लेकिन re-minted नहीं) छोड़ सकता है। प्रत्येक run पर state re-reading (§4) इसे अगले tick पर recover करने देता है।
* **Scaled-UI / RWA tokens।** कुछ BSC tokens (जैसे Binance Stock Tokens) on-chain UI multipliers (ERC-8056) उपयोग करते हैं। On-chain raw amounts displayed amounts से differ करते हैं। यदि आपका agent इन्हें trade करता है, तो सभी contract math raw units में करें और multiplier केवल human-facing display के लिए apply करें।
* **आप अपने agent के लिए जिम्मेदार हैं।** PancakeSwap pools permissionless contracts हैं; उनके विरुद्ध autonomous agent deploy करना आपका निर्णय और आपका जोखिम है। यह गाइड technical reference है, financial advice नहीं, और PancakeSwap outcomes के बारे में कोई warranty नहीं देता।

***

### 9. Reference

* **`@pancakeswap/smart-router`** — routing + swap calldata (सर्वोत्तम in-repo examples इसके README में हैं)
* **`@pancakeswap/v3-sdk`** — `Pool`, `Position`, `NonfungiblePositionManager`, `Multicall`, tick/price math
* **BNB Agent Studio** — agent describe, build, और deploy करना (BNB docs)
* **PancakeSwap deployment addresses** — canonical contract list (उपयोग से पहले verify करें)
* **ERC-8056 (Scaled UI Amount)** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
