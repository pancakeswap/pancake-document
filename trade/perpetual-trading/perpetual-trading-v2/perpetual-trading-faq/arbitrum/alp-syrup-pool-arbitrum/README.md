# ALP Syrup Pool（Arbitrum）

ALPはPancakeSwap Perpetuals V2の流動性を支えるトークンです。ユーザーはUSDC、USDT、DAI、ETH、BTCなどの担保トークンを使用してALPをミント/購入します。これらのトークンはApolloXが提供するPancakeSwap Perpetualsの取引エンジンに流動性を供給します。ALPトークンは**ウォレット間で転送できず**、**ALPコントラクトを通じてのみミント/売却**でき、**ALPプールにステークできます**。

### ステップバイステップガイド

#### ALPの購入/ミント

1. [PancakeSwap ALP Pool（V2）](https://perp.pancakeswap.finance/en/ALP)ページにアクセスしてウォレットを接続します。
2. ウォレットを接続後、**Buy ALP（ALPを購入）**をクリックします。ALPプールのいずれかの資産でALPを購入できます。
3. 情報を確認し、**Buy ALP（ALPを購入）**をクリックしてトランザクションを完了します。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Buy%20ALP%20Module.png" alt=""><figcaption></figcaption></figure>

**ALPのステーキング（Arbitrum）**

1. Pancake ALPダッシュボードページで**Stake Now（今すぐステーク）**をクリックするか、[こちら](https://pancakeswap.finance/pools?chain=arb)をクリックします。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/png%20%284%29.png" alt=""><figcaption></figcaption></figure>

2. CAKE-ALP Syrup Poolを選択します。
3. ALPを**Enable（有効化）**し、**Stake（ステーク）**をクリックします。
4. ステークするALPの量を選択し、**confirm（確認）**をクリックします。

**ALPの売却**

1. ALP Pool（V2）ページにアクセスしてウォレットを接続します。
2. ウォレットを接続後、**Sell ALP（ALPを売却）**をクリックします。

ALPの売却条件：

* &#x20;ユーザーはALP購入から48時間後に売却できます。
* &#x20;売却可能なALPトークンの量：min\[（流動性プールの価値 - ユーザーのポジション価値）× 50%] / ALP市場価格。例えば、流動性プールの価値が10,000,000 USDT、ユーザーのポジション価値が5,000,000 USDT、ALP市場価格が2 USDTの場合、ALPユーザーが売却できる最大量は1,250,000となります。&#x20;
* 同時に、ユーザーがALPトークンを売却した後に受け取るアセットの量はALP流動性プールを超えることはできません。例えば、流動性プールに1000 USDTしかない場合、ユーザーが受け取る最大USDT量は1000 USDTとなり、残りのALPは他の暗号資産に変えて売却できます。
