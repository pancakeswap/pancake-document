# 手数料とルート

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

Exchange v3では、デフォルトでPancakeSwapのSmart Routerがv3、v2、StableSwap（BNB Chain）、およびAMMとマーケットメーカー（BNB Chain・Ethereum）の流動性を活用して取引を実行し、トレーダーに最良の価格を提供します。

ただし、ユーザーはルーターが使用する流動性ソースを選択したり、マルチホップやスプリットルーティングを有効または無効にしたりすることで、取引をカスタマイズすることができます。

### **現在適用されている手数料率と手数料額の確認方法**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

現在のスワップに対してどれだけの取引手数料がかかるかを確認するには、スワップ詳細セクションの「Fee」セクションをご覧ください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

取引が現在どのプール種別および手数料ティアにルーティングされているかを確認するには、「Route」セクションをご覧ください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

詳細を確認するには、虫眼鏡アイコンをクリックして取引ルートの全詳細表示を開いてください。



### **流動性ソースのカスタマイズ**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

「Customize Routing」インターフェースの上部では、取引をルーティングする際に使用する流動性ソースを選択できます。このインターフェースを開くには：

* 取引ルート詳細の下部にある「Customize Routing」をクリックします。
* スワップインターフェースの歯車アイコンをクリックし、下部の「Customize Routing」をクリックします。

デフォルトでは、すべての流動性ソースが有効になっており、Smart RouterはPancakeSwap内のすべての利用可能な流動性を最大限に活用します。

ルーターはAMM流動性プールとMMマーケットメーカーの間で取引をルーティングすることはありません。取引がMMマーケットメーカーによって実行される場合、どのAMM流動性プールも経由しません。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

右上の「Reset」ボタンをクリックすると、設定をデフォルトにリセットできます。



### **ルーティング設定のカスタマイズ**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

「Customize Routing」インターフェースの下部では、マルチホップとスプリットルーティングを有効または無効にすることで、ルーティング設定をカスタマイズできます。

マルチホップは、複数の流動性プールを経由して最良の取引条件を達成するためにトークンをスワップすることを可能にします。無効にすると取引は直接スワップに限定されるため、スリッページが高くなったり、場合によっては資金が失われる可能性があります。

スプリットルーティングは、最良の取引条件を達成するためにトークンスワップを複数のルートに分割することを可能にします。無効にすると取引は単一ルートでの実行に限定されるため、効率が低下したりスリッページが高くなる可能性があります。

{% hint style="warning" %}
カスタマイズされた取引設定により取引が実行できない場合、警告が表示されます。「Check your settings」をクリックすると「Customize Routing」インターフェースをすぐに開けます。または「Reset to default」を選択して設定を素早くデフォルトにリセットできます。
{% endhint %}
