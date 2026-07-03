---
hidden: true
---

# マーケットメーカー連携

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### EthereumにおけるマーケットメーカーIntegration

PancakeSwapはEthereumおよびBinance Smart Chain上のマーケットメーカーと連携し、トレーダーがより低コストで取引を実行できるよう支援しています。

AMMに加えて、PancakeSwapでの取引は、AMMの現在の価格よりも優れた取引条件を提供する場合、ホワイトリストに登録されたマーケットメーカーにルーティングされるようになりました。このルーティングは[Smart Router](smart-router-v2/)によって自動的に行われ、マーケットメーカーがより良い価格を積極的に提示している場合にのみ、取引がマーケットメーカーにルーティングされます。AMMの方が競争力がある場合は、トレーダーはAMMにルーティングされて実行されます。

PancakeSwapでマーケットメーカーが機能するシナリオは2つあります。

**シナリオ1：既存のAMM流動性プールが存在する場合**

PancakeSwapが特定のトークン（例：WETH/USDC）に対してAMM上の流動性をすでに持っている場合、PancakeSwapは同じ取引についてマーケットメーカーにも見積もりを求めます。PancakeSwapのSmart Routerは、いずれかの流動性ソースがより良い価格を提供しているかに応じて、取引リクエストをAMMまたはマーケットメーカーにルーティングします。

**シナリオ2：AMM流動性プールが存在しない場合**

このシナリオでは、Smart Routerは取引を自動的にマーケットメーカーにルーティングします。ただし、これはプロジェクトが後でAMM流動性プールを設定したり、分散型DEXの流動性を維持するために私たちと協力することを妨げるものではありません。

### 手数料

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwapは、マーケットメーカーによって実行される取引についてトレーダーに一切の手数料を請求しません。ただし、PancakeSwapはホワイトリストに登録されたマーケットメーカーから、マーケットメーカーが実行した取引量に対して**0.05%の取引手数料**を受け取ります。ステーブルコインペア間の取引については、**0.01%の取引手数料**が適用されます。手数料の内訳については以下をご参照ください：<br>

<table><thead><tr><th width="178">取引</th><th width="138">取引手数料</th><th width="182">MMからのPCS手数料</th><th width="147">CAKEバーン</th><th align="center">PancakeSwap Treasury</th></tr></thead><tbody><tr><td>他のネットワークからのブリッジコイン</td><td>N/A</td><td>0.25%</td><td>0.083%</td><td align="center">0.167%</td></tr><tr><td>Ethereum上の非ステーブルコイン（例：ETH/USDC）</td><td>N/A</td><td>0.05%</td><td>0.017%</td><td align="center">0.033%</td></tr><tr><td>BSC上の非ステーブルコイン（例：BNB/USDT）</td><td>N/A</td><td>0.05%</td><td>0.017% </td><td align="center">0.033%</td></tr><tr><td>Ethereum上のステーブルコイン間取引</td><td>N/A</td><td>0.01%</td><td>0.003%</td><td align="center">0.007%</td></tr></tbody></table>

#### 現在サポートされているアセット

以下のアセットが現在サポートされており、マーケットメーカーによって増減する場合があります：

**Ethereum上**

* **主要通貨：** WETH、WBTC
* **ステーブルコイン：** USDT、USDC、DAI、BUSD
* **その他の主要なERC-20アセット：** MATIC、DYDX、CRV、LINK、APE、CVX、STG、LDO、SNX、RNDR、FET

**Binance Smart Chain上：**

* **主要通貨：** BNB、ETH、BTCB
* BNBネイティブ以外のトークン：ARB、OP

AMMとは異なり、マーケットメーカーはあらゆる数量の取引を行えるわけではなく、実行できる数量はマーケットメーカー自身の流動性によって決まります。非常に大きな注文が完全には対応できない場合もあります。各取引がご自身のニーズに合った価格と数量を反映しているか、見積もりを慎重に確認されることをお勧めします。

**マーケットメーカーのダウンタイム**

マーケットメーカーが24時間365日常に見積もりを提供することは求められていません。主要な経済イベントやシステムアップグレードなど、マーケットメーカーが一時的に見積もりを提供できない場合があります。このような期間中は、対象トークンの取引ができない場合がありますので、マーケットメーカーがオンラインに戻るまでしばらくお待ちいただくことをお勧めします。

#### よくある質問（FAQ）

**Q.** マーケットメーカーはAptosにも統合されますか？

**A：** 可能性はありますが、現時点ではより良いユーザー体験のための流動性向上を目的として、EthereumおよびBinance Smart Chainのみでマーケットメーカー連携を開始しています。他のチェーンについては引き続き検討していきます。

**Q.** ユーザーに手数料を請求しない場合、PancakeSwapはどのように収益を得ますか？

**A：** PancakeSwapはユーザーから手数料を徴収しませんが、マーケットメーカーから小額のコミッションを受け取り、CAKEのバイバック・バーンに活用します。

**Q.** 流動性プロバイダーは引き続きLPの手数料を獲得できますか？

**A：** はい、流動性プロバイダーは引き続き0.17%の取引手数料報酬（LP手数料）と、CAKEファームでの収益を獲得できます。

**Q.** マーケットメーカーはAMMに流動性を追加しますか？それによってAPRが下がりますか？

**A：** マーケットメーカーは独自の流動性を維持しており、AMM上での取引からAPRを獲得することはありません。AMM流動性プールへの流動性提供からの手数料とAPRを獲得できるのはLPのみです。

**Q.** EthereumのPancakeSwapで流動性を提供しています。何か操作が必要ですか？

**A：** いいえ、何も操作する必要はありません。AMMを通じて実行された取引のLP手数料を引き続き獲得でき、CAKEでの収益も継続します。

**Q.** マーケットメーカーになるにはどうすればよいですか？

**A：** 私たちは個別にマーケットメーカーを審査し、協力関係を構築しています。ご興味がある場合は、直接または管理者を通じてお問い合わせください。
