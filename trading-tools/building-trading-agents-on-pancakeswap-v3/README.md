# 🤖 BNB AIエージェントスタジオ

> BNB Smart Chain上のPancakeSwap V3流動性プールおよびFarmと連携する自律型エージェントを、[BNB Agent Studio](https://www.bnbchain.org/en/bnb-agent-studio)またはその他のフレームワークを使用して構築する開発者向けガイドです。
>
> 戦略を記述すると、エージェントがオンチェーンで自律的に実行します。このページではPancakeSwapの部分（呼び出すべきコントラクト、安全な呼び出し順序、完全な実例（自動V3レンジリバランサー））を説明します。エージェント自体の記述、構築、デプロイについては、BNB Agent Studioのドキュメントをご覧ください。

このために**PancakeSwapへの統合は必要ありません**。V3プールとFarmはパーミッションレスのスマートコントラクトであり、エージェントはPancakeSwapのフロントエンドと同じように直接呼び出すことができます。以下のすべては公開のオンチェーンサーフェスです。

***

### 1. エージェントがPancakeSwapに対してできること

集中型流動性（V3）はV2よりもLPにとってはるかに優れた資本効率を提供しますが、積極的な管理が必要です。ポジションは価格がティック範囲内にある間のみ手数料を稼ぎ、報酬/利回りは常に変化します。この運用上のオーバーヘッドこそがエージェントが解消するものです。一般的な戦略：

* **レンジリバランサー** — LPポジションを監視し、価格が範囲の端に近づいたときに流動性を引き出して新しい価格中心に再ミントし、ポジションが手数料を稼ぎ続けるようにします。_（§6に実例があります。）_
* **Farm APRルーター** — プール全体のCAKE+手数料利回りを追跡し、最高の合計利回りに流動性を移動します。
* **Swap/クォートボット** — V2+V3にわたって最良の執行のために Smart Routerを通じてトレードをルーティングします。

これらはすべて以下の同じ少数のコントラクト呼び出しの組み合わせです。

***

### 2. コントラクトサーフェス（BNB Smart Chain、chainId 56）

| コントラクト                              | アドレス                                      | エージェントの用途                                                                            |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **NonfungiblePositionManager** (NFPM) | `0x46A15B0b27311cedF172AB29E4f4766fbE7F4364` | LPポジションの作成/管理 — `mint`、`increaseLiquidity`、`decreaseLiquidity`、`collect`、`burn` |
| **SmartRouter**                       | `0x13f4EA83D0bd40E75C8222255bc855a974568Dd4` | V2+V3ルーティングで最良のSwapを実行                                                            |
| **MasterChefV3**                      | `0x556B9306565093C855AEA9AE92A594704c2Cd59e` | ポジションNFTをステークしてCAKEを Farm — `harvest`、`withdraw`                                        |
| **V3 Quoter**                         | `0xB048Bbc1Ee6b733FFfCFb9e9CeF7375518e25997` | 送信前にSwapの見積もりを取得                                                                   |
| **PancakeV3Factory**                  | `0x0BFbCF9fa4f9C56B0F40a671Ad40E0805A091865` | `(token0, token1, fee)`からプールアドレスを解決                                              |
| **Permit2**                           | `0x31c2F6fcFf4F8759b3Bd5Bf0e1084A055615c768` | **Smart Routerのスワップ**のためのガスレス/バッチトークン承認（§5.1参照）                            |

> ⚠️ **実際の資産を送信する前に**、正規のPancakeSwapデプロイリストに対してアドレスを**必ず再確認**してください。上記の表は出発点として扱ってください。

V3 **プール**は`(token0, token1, fee)`で識別されます。手数料ティアとティック間隔：

| 手数料   | `fee`値 | ティック間隔 | 代表的な用途               |
| ----- | ----------- | ------------ | ------------------------- |
| 0.01% | `100`       | 1            | ステーブル-ステーブル             |
| 0.05% | `500`       | 10           | 相関ペア（例：ETH/BTC） |
| 0.25% | `2500`      | 50           | ほとんどのペア                |
| 1.00% | `10000`     | 200          | エキゾチック/ボラティル         |

V3 **ポジション**はNonfungiblePositionManagerに保持されるERC-721 NFTです。`tickLower`、`tickUpper`、`liquidity`、および発生した手数料を格納します。`tokenId`で参照します。

***

### 3. ツール

これらのコントラクトに生のABIとあらゆるweb3ライブラリで接続できますが、**`@pancakeswap/v3-sdk`**と**`@pancakeswap/smart-router`**パッケージが困難な計算（ティック↔価格、スリッページ調整済み最小値、コールデータのエンコード）を代わりに行ってくれます。以下の例では[viem](https://viem.sh/)と共に使用します。

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

エージェントはスケジュールまたはトリガーに基づいてトランザクションを実行するこのウォレットです。ウォレットはAgent Studioによって資金提供・管理されます。BNBのドキュメントをご覧ください。

***

### 4. 状態の読み取り（すべてのアクションの前に実行）

エージェントはチェーンを読み取ることで_行動するかどうか_を決定します。ほとんどの戦略を駆動する3つの読み取り：

**プールの価格と現在のティック** — オンチェーンの`slot0` + `liquidity`から`Pool`エンティティを構築：

```tsx
import { Pool, FeeAmount } from '@pancakeswap/v3-sdk'

// poolAddressはファクトリーまたはcomputePoolAddress()から解決
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

**所有するポジション** — `tokenId`でNonfungiblePositionManagerから読み取り：

```tsx
const p = await publicClient.readContract({
  address: NFPM_ADDRESS, abi: nfpmABI, functionName: 'positions', args: [tokenId],
})
// p.tickLower, p.tickUpper, p.liquidity, p.tokensOwed0, p.tokensOwed1, ...
const inRange = pool.tickCurrent >= p.tickLower && pool.tickCurrent < p.tickUpper
```

**ポジションは範囲内か？** この単一のブール値がリバランサーのトリガーです。境界の「Nティック以内」に締め付けることで、範囲外になる_前_に行動できます。

***

### 5. 安全なトランザクションシーケンス

ここが正確に理解する必要がある部分です。無人のエージェントには不正なトランザクションを捕捉する人間がいないため、状態を変更するすべての呼び出しは以下の4つのガードレールで保護する必要があります。

#### 5.1 承認

コントラクトがトークンを移動するには、許可（allowance）が必要です。適切なメカニズムは呼び出すコントラクトによって異なります。以下の3つはすべてパーミッションレスです：

* **ERC-20 `approve`** — Smart RouterとNonfungiblePositionManagerの両方で、任意のトークンで機能します。トークン/スペンダーごとに1回のトランザクション。最もシンプルですが、無限の無期限承認はリスクがあります。
* **`selfPermit`（EIP-2612）** — **NonfungiblePositionManager**の流動性操作用。トークンがEIP-2612をサポートしている場合、SDKはmulticall経由で`mint`/`increaseLiquidity`に_インライン_で署名済み・金額限定のpermitをバンドルできます。EIP-2612のないトークンの場合は`approve`にフォールバックします。
* **Permit2** — **Smart Router**のスワップ用。トークンごとに1回Permit2を承認し、スワップごとに短期間の署名済み・金額限定の許可を付与します。

自律型エージェントの場合：すべてのpermitを正確な金額と短い有効期限に限定してください。**意味のある残高を保持するエージェントウォレットから無制限の承認を絶対に付与しないでください。**

#### 5.2 スリッページ — `amountMin = 0`は絶対に送信しない

すべてのadd/remove/swapは許容可能な最小出力を指定する必要があります。許容誤差から導出するためにSDKを使用してください：

```tsx
import { Percent, Position } from '@pancakeswap/v3-sdk'

const slippage = new Percent(50, 10_000) // 0.50%

// ミント/追加時：
const { amount0: amount0Min, amount1: amount1Min } =
  position.mintAmountsWithSlippage(slippage)

// 削除時：
const { amount0: amount0Min, amount1: amount1Min } =
  position.burnAmountsWithSlippage(slippage)
```

スワップの場合、Smart Routerは`slippageTolerance`を適用して`amountOutMinimum`を計算してくれます（§6、ステップ0）。**ゼロの最小値はサンドイッチボットへの公開招待**です。無人のウォレットでは、これは繰り返しのサイレントな損失を意味する可能性があります。

#### 5.3 デッドライン — 常に設定する

すべての呼び出しは`deadline`（Unixの秒単位）を受け取ります。その時刻にトランザクションがまだ保留中の場合、古い価格で実行されるのではなくrevertします。エージェントでは短く設定してください：

```tsx
const deadline = BigInt(Math.floor(Date.now() / 1000) + 60 * 5) // 5分
```

#### 5.4 Multicall — マルチステップのアクションをアトミックに

NonfungiblePositionManagerとSmart Routerは`multicall`をサポートしています：複数の呼び出しを**1つのトランザクション**にバンドルし、すべて成功するかすべてrevertします。これはガス節約だけでなく、安全性の特性です。`decreaseLiquidity`の後に`collect`を行うリバランスは、半分の状態で実行されてはいけません。SDKがバンドルしてくれます：

```tsx
import { Multicall } from '@pancakeswap/v3-sdk'
const calldata = Multicall.encodeMulticall([decreaseCalldata, collectCalldata, burnCalldata])
```

> **アトミックな「リバランス」関数はありません。** レンジの移動は_合成された_シーケンス（削除→収集→ミント）です。削除と新しいミントは別のトランザクションで発生します。その間に価格が動く可能性があります。削除確認後にミントの状態を再読み取りして最小値を再計算してください。削除前の数値を再利用しないでください。

#### ガードレールチェックリスト（すべてのエージェントアクションに適用）

* \[ ] トークン許可は金額に限定（Permit2）、無制限ではない
* \[ ] `amount*Min` / `amountOutMinimum`は明示的なスリッページ許容値から導出、絶対に`0`ではない
* \[ ] すべての呼び出しに短い`deadline`
* \[ ] マルチステップのアクションは`multicall`でバンドル
* \[ ] シーケンスの別トランザクション間に状態を再読み取り
* \[ ] ラウンドごとの移動価値の上限、および操作/流動性の低いプールへの行動前のプール価格が期待範囲内かどうかのサニティチェック（操作されたプールへの取引に対する安価な防御）

***

### 6. 実例 — 自動V3レンジリバランサー

リファレンスエージェント。1つのポジションを監視し、価格がレンジの境界に近づいたとき、流動性を引き出して現在の価格を中心とした新しいレンジを再ミントします。5つのステップ。

**トリガー：** `pool.tickCurrent`が`tickLower`/`tickUpper`のバッファ内にある場合（§4から）。

#### ステップ0 — （オプション）トークン比率のリバランス

引き出した後、古いレンジが生成した比率でtoken0とtoken1を保持します。新しい中心のレンジには通常異なる比率が必要なため、Smart Routerを通じて余剰分をスワップします：

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

#### ステップ1〜3 — 流動性の削除、収集、バーン（1つのトランザクション）

`removeCallParameters`がバンドル全体を構築します：`decreaseLiquidity`をゼロにし、引き出した元本と発生した手数料の両方を`collect`し、今は空のNFTを`burn`します。すべて1つのアトミックな`multicall`として。

```tsx
import { NonfungiblePositionManager, Percent } from '@pancakeswap/v3-sdk'

const { calldata, value } = NonfungiblePositionManager.removeCallParameters(oldPosition, {
  tokenId,
  liquidityPercentage: new Percent(1),            // 100% — 完全退出
  slippageTolerance: new Percent(50, 10_000),     // 0.50% — amount0Min/amount1Minを設定
  deadline,
  collectOptions: {
    expectedCurrencyOwed0: feesOwed0,
    expectedCurrencyOwed1: feesOwed1,
    recipient: account.address,
  },
})

const hash = await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
await publicClient.waitForTransactionReceipt({ hash }) // 待機 — 次のミントはこれらのトークンに依存します
```

> ポジションが**MasterChefV3にステークされている**場合、NFPMから削除しません。まず`MasterChefV3.withdraw(tokenId, to)`を呼び出してアンステーク（これにより保留中のCAKEも収穫されます）し、NFTをウォレットに戻してから、上記の削除を実行します。§7を参照してください。

#### ステップ4 — 新しいレンジのミント

_現在の_価格周辺のティックを再計算し（プールを再読み取り — §5.4参照）、手数料ティアの間隔にスナップし、現在保有しているトークンから`Position`を構築してミントします。

```tsx
import { Position, NonfungiblePositionManager, nearestUsableTick } from '@pancakeswap/v3-sdk'

const freshPool = /* slot0 + liquidityを再読み取り → 新しいPool（§4）*/
const spacing = freshPool.tickSpacing
const halfWidth = 10 * spacing // 戦略定義のレンジ幅

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
  slippageTolerance: new Percent(50, 10_000), // ミントのamount0Min/amount1Minを設定
  deadline,
  recipient: account.address,
})
await walletClient.sendTransaction({ to: NFPM_ADDRESS, data: calldata, value: BigInt(value) })
```

エージェントは新しい範囲内のNFTを保持します。Farmしていた場合は再ステークします（§7）。次のティックで§4の読み取りに戻ります。

***

### 7. Farm操作（MasterChefV3）

V3ポジションNFTをMasterChefV3にステークすると、スワップ手数料に加えてCAKEを獲得できます。

> **アクティブなFarmを持つプールのポジションのみCAKEを獲得します。** PancakeSwapのガバナンスはどのプールがFarmable（各プールに`pid`が付与）かを登録します。登録されていないプールにポジションをステークすると`InvalidPid`でrevertします。これはエージェントの活動がPancakeSwap側のリストに依存する唯一の場所ですが、プールレベルであってエージェントレベルではありません。どのウォレットもアクティブなFarmにステークできます。（NonfungiblePositionManager経由でポジションを管理 — mint/collect/rebalance — はFarmを必要とせず、すべてのプールで機能します。）

> **アクティブなFarmを持つプールのポジションのみCAKEを獲得します。** PancakeSwapのガバナンスはどのプールがFarmable（各プールに`pid`が付与）かを登録します。登録されていないプールにポジションをステークすると`InvalidPid`でrevertします。これはエージェントの活動がPancakeSwap側のリストに依存する_唯一の_場所ですが、プールレベルであってエージェントレベルではありません。どのウォレットも_アクティブな_Farmにステークできます。Farming戦略を構築する前に、プールにライブのFarmがあることを確認してください。（NonfungiblePositionManager経由でポジションを管理 — mint/collect/rebalance — はFarmを必要とせず、すべてのプールで機能します。）

* **ステーク** — ポジションNFTをMasterChefV3に転送します（`safeTransferFrom(owner, masterChefV3, tokenId)`）。FarmがNFTを管理します。
* **ハーベスト** — `harvest(tokenId, to)`でアンステークせずに保留中のCAKEを請求します。複数のポジションにわたって1つのトランザクションで請求するには`batchHarvest`を使用します。
* **引き出し/終了** — `withdraw(tokenId, to)`でアンステーク、保留中のCAKEのハーベスト、NFTのウォレットへの返却を行います。`decreaseLiquidity`/`burn`（§6のNFPM呼び出し）の前に引き出す必要があります（NFPM呼び出しはウォレットが保有するNFTにのみ機能します）。

**Farm済みの**ポジションのリバランサーは次のように実行します：`withdraw` → remove/collect/burn → mint → MasterChefV3に`safeTransferFrom`で戻す。

***

### 8. 安全性、制限、免責事項

実際の資金を移動するエージェントをデプロイする前に必ずお読みください。

* **自律性は不可逆です。** デプロイされたエージェントは人間の確認なしにトランザクションに署名して送信します。バグ、不正なトリガー、または操作された価格フィードは実際に実行されます。BSCテストネットでテストし、スケールアップ前にメインネットのエクスポージャーを制限してください（取引ごとおよび日次の上限）。
* **スリッページとデッドラインは必須**であり、オプションではありません（§5）。省略したエージェントは最終的にサンドイッチ攻撃を受けます。
* **価格操作の防御。** 行動する前に、独立した参照に対してプール価格をサニティチェックし、乖離する場合は実行をスキップします。操作された、または薄いプールへの取引に対する安価な保険です。
* **ガスと資金調達。** エージェントウォレットにガスのためのBNBを十分に保持してください。エージェントのガス不足により、ポジションがリバランスの途中（削除されたが再ミントされていない）で止まる可能性があります。各実行での状態の再読み取り（§4）により、次のティックで回復できます。
* **スケールドUI / RWAトークン。** 一部のBSCトークン（例：Binanceストックトークン）はオンチェーンのUIマルチプライヤー（ERC-8056）を使用します。オンチェーンの生の量は表示量と異なります。エージェントがこれらを取引する場合、コントラクトの計算はすべて生の単位で行い、人間向けの表示にのみマルチプライヤーを適用してください。
* **エージェントについてはあなたが責任を負います。** PancakeSwapのプールはパーミッションレスのコントラクトです。自律型エージェントをデプロイしてそれらに対して使用することはあなたの決断とリスクです。このガイドは技術的なリファレンスであり、財務的なアドバイスではなく、PancakeSwapは結果について何ら保証しません。

***

### 9. リファレンス

* **`@pancakeswap/smart-router`** — ルーティング + スワップのコールデータ（最良のリポジトリ内の例はREADMEにあります）
* **`@pancakeswap/v3-sdk`** — `Pool`、`Position`、`NonfungiblePositionManager`、`Multicall`、ティック/価格計算
* **BNB Agent Studio** — エージェントの記述、構築、デプロイ（BNBのドキュメント）
* **PancakeSwapのデプロイアドレス** — 正規のコントラクトリスト（使用前に確認してください）
* **ERC-8056（スケールドUI量）** — [https://github.com/bnb-chain/BEPs/pull/677](https://github.com/bnb-chain/BEPs/pull/677)
