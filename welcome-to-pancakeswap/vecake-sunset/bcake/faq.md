# よくある質問 (FAQ)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### bCAKE の倍率はどのように計算されますか？

ファームが異なるとブーストの倍率が変わることにお気づきかもしれません。

これは、bCAKE - Farm Booster の倍率が、有効化または更新の際に以下の指標を使用して計算されるためです。

* `userLpBalanceInFarm` : ファームにステークしている流動性の量
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : ファームにステークされている流動性の総量、または V3 LP プール内の現在アクティブな流動性の量。bCAKE はこの2つのうち小さい方を選択します。
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : 保有しているリアルタイムの veCAKE 数量
* `veCAKE.totalSupply` : veCAKE のリアルタイム総供給量

倍率は以下の方法で計算されます。

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` と `constantB` はキッチンによって設定され、コミュニティのフィードバックや市場状況に基づいて今後調整される場合があります。`constantB` は LP 価格の違いを補うため、ファームによって異なります。

`constantA` と `constantB` は以下で取得できます。

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

ただし：

{% hint style="info" %}
**まとめると**

より多くの LP（流動性）をブーストしたい場合

より長期間、より多くの CAKE をロックする必要があります
{% endhint %}

### 有効化後でも倍率が変わるのはなぜですか？

**ファーミングポジションまたは CAKE ステーキングプールへのユーザー操作は、ファームと CAKE ステーキングプールからの最新データと統計に基づいて、自動的にブースト倍率を更新します**。対象となる操作には以下が含まれますが、これに限りません。

* ファームへのポジションのステーク／アンステーク
* ファームからの CAKE 報酬のハーベスト
* CAKE ステーキング期間の延長
* 固定期間ステーキングポジションへの CAKE の追加
* CAKE ステーキングポジションのフレキシブルへの変換

{% hint style="warning" %}
ご注意ください：

公平性の確保と、古いデータを利用した潜在的な不正使用や不正行為の防止のため、Farm Booster はパーミッションレスかつコミュニティガバナンスで設計されています。そのため、**誰でも** MasterChef V3 コントラクトの `updateLiquidity(address _tokenId)` 関数を呼び出して、誰のブースト倍率でも最新データで更新することができます。

さらに、キッチンもすべての bCAKE 対応ファーミングポジションを監視し、古い倍率のポジションを更新します。
{% endhint %}

### ポジションをブーストできないのはなぜですか？

1. Farm Booster は選択されたファームのみで利用可能です。今後さらに多くのファームが対応予定です。現時点では、**緑のロケットアイコンが付いた緑色の APR 数値を探してください。**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. 複数のコントラクトが関係するため、一部のコントラクト操作では通常より多くのガストークン（BNB）が必要な場合があります。ウォレットに十分な BNB があることをご確認ください。エラーが続く場合は、トランザクションのガスリミットを手動で増やしてみてください。

### bCAKE ブースト倍率の最大値はどれくらいですか？

現在、Farm Booster で得られる最大ブーストは2.5倍で、元の APR の2.5倍を提供します。

ステークする流動性の種類によって得られる最大ブーストが異なることにご注意ください。

* V3：最大2倍
* V2、StableSwap：最大2.5倍
* ポジションマネージャー：最大2.5倍

### bCAKE ブースト倍率を増やすにはどうすればよいですか？

* veCAKE ステーキングポジションに CAKE を追加する
* veCAKE ステーキングポジションの期間を延長または更新する

簡単に言うと：

**より多くの CAKE を、より長期間ステークする**

[bCAKE ブースト倍率の計算方法の詳細はこちら](faq.md#how-are-the-bcake-multipliers-calculated)。

### 追加ブーストされた CAKE 報酬はどこから来るのですか？

**ご安心ください。bCAKE を実現するために追加のエミッションは割り当てられていません。**

veCAKE の CAKE ステーキングと同様に、bCAKE は他のユーザーに対する個々のユーザーのシェアを増加させます。

bCAKE の展開後にベースラインの APR が下がる場合もありますが、忠実な CAKE 愛好者のファーミング収益をブーストし、CAKE の需要を高め、CAKE ステーキングの優れたインセンティブとなるため、キッチンはこれが良いトレードオフであると考えています。

### 受け取れる倍率が低いのはなぜですか？

bCAKE - Farm Booster は、あなたの veCAKE ステーキングポジションとファーミングポジションを他のユーザーと比較して評価する仕組みです。簡単に言うと：

> ファーム内のより多くの流動性をブーストしたい場合、プール内でより長期間、より多くの CAKE をロックする必要があります。

この設計により、大口保有者だけでなく、ファーミングポジションと比較して相応の CAKE ステーキングポジションを持つすべてのユーザーが特典を受けられるようにしています。

倍率の計算方法の詳細は[こちら](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated)をご覧ください。

### ブースト対応ファームの数が限られているのはなぜですか？

bCAKE は PancakeSwap のコアプロダクトである流動性ファーミングの更新に関わるため、キッチンはリリースに対してより慎重で着実なアプローチを取ることにしました。

そのため、初期プロダクトリリース段階では、多くのパラメーターが非常に保守的に設定されています。ユーザーがブーストできるファームの数、ブースト可能なファーム、ブースト倍率を受け取るための難易度パラメーターも同様です。

**キッチンはコミュニティのフィードバックに基づいてパラメーターを調整します。**

### **bCAKE V3 は監査されていますか？** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE は内部および外部の監査人によって監査されています。

監査レポートはこちらでご確認いただけます：[https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
