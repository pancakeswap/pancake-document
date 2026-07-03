---
description: PancakeSwapでのYield Farmingは簡単です！
---

# ファームの使い方（レガシー）

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-header.png)

ファームでのYield Farmingは、PancakeSwapでCAKE報酬を獲得するための優れた方法です。

シロッププールとは異なり、ファームでは**2つのトークン**をステーキングして流動性を提供し、流動性ポジションNFTまたはLP Tokensを受け取り、それをファームにステーキングして報酬を獲得する必要があります。これにより、他のトークンのポジションを保持しながらCAKEを獲得できます！

{% hint style="warning" %}
Yield farmingはシロッププールよりも高い報酬が得られる場合がありますが、**インパーマネントロス（Impermanent Loss）**のリスクが伴います。思ったほど怖くはありませんが、始める前にこの概念を理解しておくことをお勧めします。

詳しくは、Binance Academyの[インパーマネントロスに関する記事](https://academy.binance.com/en/articles/impermanent-loss-explained)をご覧ください。
{% endhint %}

## Farm V3

### **準備**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2832%29.png)

ファームに参加するには流動性ポジションが必要です。ファームは特定の取引ペアと特定の手数料ティアの流動性ポジションのみ受け付けます。例えば、CAKE-BNB 0.25%ファームはCAKE-BNBの0.25%手数料ティアの流動性ポジションのみ受け付けます。以下は受け付けられません：

* CAKE-BUSDなど他のペア
* 同じペアでも手数料ティアが異なるもの（例：0.05%手数料レートのCAKE-BNB）

正確なLPポジションを作成するには、正しい手数料レートを選択してその取引ペアに流動性を提供する必要があります。CAKE-BNB 0.25% LPポジションを取得するには、まず0.25%手数料ティアを選択してCAKE-BNBペアに流動性を提供する必要があります。

少し複雑に聞こえるかもしれませんが、それほど難しくはありません。ステップごとに見ていきましょう。

### **ファームを見つける**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28239%29.png)

進める前に、ご自身に適したファームを選択してください。[ファームページ](https://pancakeswap.finance/farms)にアクセスすると、利用可能なファームの一覧が表示されます。

現在最も高い報酬レートのファームを探すには、APRなど別の並び替えオプションを選択できます。なお、APRはポジションごとにグローバルで計算されますが、価格レンジの設定によって異なる場合があります。

使用したいファームを見つけたら、後で必要になる場合に備えて取引ペアと手数料レート（例：BNB-CAKEと0.25%）を控えておきましょう。

### **ポジションを作成するために流動性を提供する**

ステーキングするファームを見つけたら、流動性を提供する必要があります：

1 - 利用可能なポジションがない場合は「流動性を追加」ボタンが表示されます。クリックするだけで、ファームページを離れずに「流動性を追加」ウィンドウを開くことができます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2840%29.png)

2 - または、リストから選択したファームの行をクリックすることもできます。詳細が表示されます。カードビューの場合は「詳細」をクリックして詳細を展開します。詳細セクション内の「XXX-YYY LPを追加」リンクをクリックして流動性を追加します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28242%29.png)

### **ポジションをファームにステーキングする**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28124%29.png)

流動性の追加が完了すると、使用したいファームの下にポジションが表示されます。

複数のポジションがある場合は、「すべて表示」をクリックして新しいポップアップウィンドウで確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28198%29.png) ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28151%29.png)

表示されたポジションの「ステーク」をクリックすると、ウォレットで確認を求められます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28229%29.png)

しばらく待つとウィンドウが閉じ、詳細にステーキングされたポジションが表示されます。

上記の手順を繰り返して、異なる価格レンジ設定で複数のポジションを素早くステーキングできます。各ポジションはCAKEを獲得し、個別にハーベストする必要があります。

### **ファーミング報酬のハーベスト**

Farm V3では、同じファームで複数のポジションをステーキングできます。各ステーキングポジションはCAKEを獲得し、個別にハーベストする必要があります。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28230%29.png)

ステーキングされたポジションからCAKE報酬をハーベストするには、ファームページに戻り、ハーベストしたいファームとポジションを見つけます。「ステーク中のみ」トグルを使用して、現在ステーキング中のファームを素早くフィルタリングできます。

複数のステーキングポジションがある場合は、「すべて表示」をクリックして新しいポップアップウィンドウで確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28241%29.png)

ポジションの「ハーベスト」をクリックすると、ウォレットで確認を求められます。しばらく待つと、CAKE報酬がウォレットに送付されます。

### **ファームにステーキング中の流動性の追加または削除**

ファームにステーキング中でも、アンステーキングなしに流動性を追加または削除できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28230%29.png)

その場合は、ファームページに戻り、調整したいファームとポジションを見つけます。「ステーク中のみ」トグルを使用して、現在ステーキング中のファームを素早くフィルタリングできます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28267%29.png)

トークンペア、手数料レート、ポジションID、「>」矢印が記載されたポジションタイトルをクリックすると、ポジション詳細ページに移動します。

「追加」または「削除」ボタンを使用して、ステーキングされたポジションの流動性を調整します。

ポジションを調整する際、未請求のCAKE報酬はすべてハーベストされてウォレットに送付されますのでご注意ください。

### **ファームからポジションをアンステーキングする**

いつでもポジションをアンステーキングできます。

アンステーキングするには、ファームページに戻り、アンステーキングしたいファームとポジションを見つけます。「ステーク中のみ」トグルを使用して、現在ステーキング中のファームを素早くフィルタリングできます。

複数のステーキングポジションがある場合は、「すべて表示」をクリックして新しいポップアップウィンドウで確認できます。

ポジションの「アンステーク」をクリックすると、ウォレットで確認を求められます。しばらく待つと、ポジションNFTが保留中のすべてのCAKE報酬とともにウォレットに返還されます。

## Farm V2

### 準備

Yield Farmingを始めるには少し準備が必要です。

ファームに参加するには「LP Tokens」が必要です。ファームは特定のLP Tokenのみ受け付けます。例えば、CAKE-BNBファームはCAKE-BNB LP Tokensのみ受け付けます。

特定のLP Tokenを取得するには、その取引ペアに流動性を提供する必要があります。CAKE-BNB LP Tokensを取得するには、まずCAKE-BNBペアに流動性を提供する必要があります。

少し複雑に聞こえるかもしれませんが、それほど難しくはありません。ステップごとに見ていきましょう。

### ファームを見つける

進める前に、ご自身に適したファームを選択してください。[ファームページ](https://pancakeswap.finance/farms)にアクセスすると、利用可能なファームの一覧が表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2862%29.png)

現在最も高い報酬レートのファームを探すには、**APR**など別の並び替えオプションを選択できます。

使用したいファームを見つけたら、後で必要になる場合に備えてBNB-CAKEなどの取引ペアを控えておきましょう。

### LP Tokensを取得するために流動性を提供する

ステーキングするファームを見つけたら、LP Tokensを取得するために流動性を追加する必要があります。

1. リストから選択したファームの行をクリックします。詳細が表示されます。
2. 左側にいくつかのリンクが表示されます。**（ペア名）LPを取得**リンクをクリックします。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28131%29.png)

### LP Tokensをファームに入れる

LP Tokensを取得したら、ファームにステーキングして報酬を獲得する準備が整いました！

1 - [ファームページ](https://pancakeswap.finance/farms)に戻り、ファームを見つけます。ペアが表示されている行のどこかをクリックすると、詳細が展開されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28244%29.png)

準備ができたら、**有効化（Enable）**ボタンをクリックして、ウォレットでアクションを確認します。

2 - しばらく待つと、有効化ボタンが**LP をステーク**に変わります。クリックすると新しいウィンドウが表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28171%29.png)

3 - ファーミングに使用するLP Tokensの量をフィールドに入力するか、**最大（Max）**をクリックしてすべてのLP Tokensを使用します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28109%29.png)

4 - 金額を入力すると、**確認（Confirm）**ボタンが有効になります。クリックしてください。ウォレットでアクションの確認が求められます。

5 - しばらく待つとウィンドウが閉じ、詳細にステーキングされた新しいLP Token残高が表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28261%29.png)

{% hint style="info" %}
BNBチェーン以外のEVMブロックチェーンでクロスチェーンファーミングを行う場合、クロスチェーントランザクションの確認に約30分かかります。

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/crosschain-farm-wait.png" alt="" data-size="original">

クロスチェーンファーミングトランザクションの進捗を追跡するには、ステーキング残高の横にある円形アイコンをクリックするか、右上の「最近のトランザクション」セクションを確認してください。
{% endhint %}

{% hint style="warning" %}
BNBチェーン以外のEVMブロックチェーンで初めてクロスチェーンファーミングを行う場合、初回セットアップには少量のネイティブトークン（例：EthereumではETH）が必要です。そのため、最初のトランザクションは若干費用がかかります。
{% endhint %}

### ファームへのLP Tokensの追加または削除

後でファームにLP Tokensを追加したい場合や、ファームから一部を取り出したい場合があります。いつでも簡単に行うことができます。

1. [Yield Farmsページ](https://pancakeswap.finance/farms)に戻ります。ページ上部に**ステーク中のみ（Staked only）**トグルが表示されます。トグルをクリックします。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28240%29.png)

リストにLP Tokensを持っているペアのみが表示されるようになり、ファームを見つけやすくなります。

1. LP Tokensを持っているファームを見つけ、行をクリックして詳細を表示します。右側に**-**と**+**ボタンが表示されます。LP Tokensを削除するには**-**をクリックし、さらに追加するには**+**をクリックします。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28102%29.png)

1. 最初にLP Tokensをステーキングした際に使用したものと似たウィンドウが開きます。前回と同様に、アンステーキング/ステーキングする量を入力するか、**最大（Max）**をクリックして利用可能なすべてのLP Tokensを削除/追加します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2879%29.png)

1. 情報が正しいことを確認します。準備ができたら、**確認（Confirm）**ボタンをクリックしてウォレットでアクションを確認します。
2. しばらく待つと、LP Tokenペアの詳細セクションに新しいステーキング残高が表示されます。LP Tokensをアンステーキングした場合、未ハーベストの報酬は自動的に回収されます。

### ファーミング報酬の回収

ファーミングにより時間とともにCAKE報酬が蓄積されます。これらの報酬を回収して、より多くのLP Tokensの取得、シロッププールへのステーキング、宝くじへの参加など、さまざまな用途に使用できます。

### ファームに戻ってハーベストする

ホームページからファームとシロッププールの報酬をまとめてハーベストできます。ファーミング報酬のみを回収したい場合は、以下の手順に従ってください。

報酬を回収するには、選択したファームにアクセスして待機しているCAKEを回収する必要があります。

1 - [ファームページ](https://pancakeswap.finance/farms)に戻ります。

2 - LP Tokensをステーキングしたファームを見つけ、行をクリックして詳細を表示します。「CAKE獲得済み」の下に報酬の見込み額が表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28181%29.png)

3 - **ハーベスト（Harvest）**ボタンをクリックしてウォレットでアクションを確認します。しばらく待つと、CAKEがウォレットにクレームされ、自由に使用できます。

{% hint style="info" %}
BNBチェーン以外のEVMブロックチェーンでクロスチェーンファーミングを行う場合、ファーミング報酬をハーベストするには常にBNB Smart Chainに切り替える必要があります。

ウォレットがチェーン切り替えをサポートしていない場合、LP tokensのステーキングまたはアンステーキングを行うと常にCAKEがハーベストされます。なお、ハーベストされたCAKEはBNB Smart Chain上に配布されます。

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28164%29.png" alt="" data-size="original">
{% endhint %}

## 報酬はどのくらいの頻度でハーベストすればよいですか？

報酬をハーベストする頻度はご自身で決めていただけますが、ハーベストには小額の手数料が発生することを覚えておくと役立ちます。

**ハーベスト**をクリックした後、ウォレットで確認する際にこの手数料を確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28281%29.png)

これはMetaMaskウォレットに表示されるハーベスト手数料の例です。ウォレットによって表示方法が若干異なる場合があります。手数料をあまり頻繁に支払わないよう、しばらく報酬を積み立てることをご検討ください。

以上で完了です！[PancakeSwap シロッププールの使い方](https://docs.pancakeswap.finance/get-started/syrup-pool-guide)も確認して報酬を獲得してみてください。

楽しいファーミングを！
