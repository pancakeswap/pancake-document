# 流動性の追加/削除方法 (EVM)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-add-remove-liquidity-header.png)

「流動性」はPancakeSwapのExchangeの仕組みの中心です。流動性ページでトークンペアのステーキングを行うことで、任意のトークンペアに流動性を追加できます。

流動性を追加することで、そのペアの取引手数料を受け取り、NFTまたはLPトークンを受け取ることができます。これらは[Farms](https://pancakeswap.finance/farms)でステーキングしてCAKE報酬を獲得できます！

## Exchange V3

流動性を提供するには、好みのトークンペアの数量をコミットする必要があります。2つのトークンのうちUSD価値が低い方が、提供できる流動性の上限となります。

必要なトークンは簡単に取引で入手できます。必要な場合は[PancakeSwapでのトレード方法](https://docs.pancakeswap.finance/get-started/trade-guide)ガイドをご確認ください。

この例では、ETHとUSDCを使用してV3流動性を追加します。



1 - [流動性](https://pancakeswap.finance/liquidity)ページにアクセスします。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28243%29.png" alt=""><figcaption></figcaption></figure>

2 - 「Add Liquidity」ボタンをクリックします。



3 - 左上の入力フィールドを使用して、流動性を追加したいトレーディングペアの2つのトークンを選択します。ここでは例としてETHとUSDCを使用します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28126%29.png)



4 - インターフェースが自動的に最も人気のある取引手数料ティアを選択し、価格レンジを設定します。



5 - 「V3 LP - x% fee tier」の表示を確認することで、提供している流動性プールのバージョンと手数料ティアを確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2843%29.png)

* 手数料ティアをカスタマイズする場合は、「More」をクリックして希望の手数料ティアを選択してください。
* 最も人気のある手数料ティアに流動性を提供することを常にお勧めします。



6 - 右側の表示で価格レンジを確認・調整できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2822%29.png)

* チャートはすべての価格レンジの流動性レベルを表示します。拡大縮小ボタンでズームイン・ズームアウトできます。下部のX軸をドラッグしてパンおよびナビゲートできます。
* 価格レンジをカスタマイズする場合は、ハンドルをドラッグするか、2つの価格の「+」「-」ボタンをクリックするか、2つの価格数値をクリックして手動で入力してください。
* 推奨はしませんが、「Full Range」ボタンをクリックして全価格レンジに流動性を提供することも可能です。



7 - 「Deposit Amount」欄のいずれかのトークンに金額を入力します。もう一方のトークンは自動的に計算されて入力されます。どちらかのトークンの残高が不足している場合は、エラーが表示されてボタンがグレーアウトします。より少ない金額を入力するか、「MAX」ボタンを使用して最大利用可能金額を入力してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2847%29.png)



8 - 「Enable USDC」ボタンをクリックします。ETH以外のトークンに対して流動性を追加する場合、ペアの各トークンに対してenableを2回クリックする必要がある場合があります。ウォレットが操作の確認を求めます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2898%29.png)



9 - 「Add」ボタンが点灯します。クリックして続行します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2826%29.png)



10 - 流動性ポジションのプレビューを表示する新しいポップアップウィンドウが表示されます。すべて問題なければ、「Add」をもう一度クリックして続行します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2838%29.png)



11 - ウォレットが確認を求めます。ウォレットからトランザクションを確認してください。



12 - 間もなく、「マイ流動性」ページに新しい流動性ポジションが表示されます。ポジションをクリックして詳細を確認できます。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28211%29.png" alt=""><figcaption></figcaption></figure>

### **流動性の削除**

流動性を削除するには。

1 - [流動性](https://pancakeswap.finance/liquidity)ページにアクセスします。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28191%29.png" alt=""><figcaption></figcaption></figure>



2 - 「Your Liquidity」の下にある流動性を削除したいポジションをクリックします。フィルターを使用してすべてのV3流動性ポジションをすばやく確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28251%29.png)



3 - 「Remove」をクリックします。新しいウィンドウが表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28286%29.png)



4 - ボタンまたはスライダーを使用して、削除したい流動性の量を選択します。このペアの流動性をすべて削除するには「MAX」を選択します。

5 - 「Remove」をクリックして続行します。

6 - 受け取るトークン数量を表示するウィンドウが表示されます。「Remove」をもう一度クリックします。ウォレットが操作の確認を求めます。

7 - トランザクションが確認された後、ペアの2つのトークンを受け取ります。流動性をすべて削除していない場合は、残りの流動性の価値が流動性ページで更新されます。



## Exchange V2

### 流動性の追加

この例では、BNBとCAKEを使用してV2流動性を追加します。

{% hint style="warning" %}
この例はあくまで説明目的のものであり、CAKE/BNBトレーディングペアはV3に移行済みです。基礎となるトークンのいずれかがExchange V3をサポートしていない場合や、トークンペアの流動性の大部分が移行されていない場合を除き、常にV3流動性を提供してください。
{% endhint %}

1. [流動性](https://pancakeswap.finance/liquidity)ページにアクセスします。
2. 「Add Liquidity」ボタンをクリックします。
3. 左上の入力フィールドを使用して、流動性を追加したいトレーディングペアの2つのトークンを選択します。ここでは例としてBNBとCAKEを使用します。
4. インターフェースはデフォルトでV3流動性の追加になりますが、以下の場合は例外があります：
   1. トレーディングペアにアクティブなPancakeSwap V2 Farmがある場合、デフォルトでV2流動性の追加になります。
   2. トレーディングペアに既存のV2流動性プールがある場合、「Add V2 Liquidity」リンクが表示されます。クリックするだけでV2流動性の追加に切り替えられます。
5. 「V2 LP - 0.25 fee tier」の表示を確認して、V2流動性を追加していることを確認してください。
6. 「Deposit Amount」欄のいずれかのトークンに金額を入力します。もう一方のトークンは自動的に計算されて入力されます。どちらかのトークンの残高が不足している場合は、エラーが表示されてボタンがグレーアウトします。より少ない金額を入力するか、「MAX」ボタンを使用して最大利用可能金額を入力してください。
7. 「Enable CAKE」ボタンをクリックします。BNB以外のトークンに対して流動性を追加する場合、ペアの各トークンに対してenableを2回クリックする必要がある場合があります。ウォレットが操作の確認を求めます。
8. 「Add」ボタンが点灯します。クリックして続行します。
9. ウォレットが確認を求めます。ウォレットからトランザクションを確認してください。
10. 間もなく、流動性ページにLPトークン残高が表示されます。V3やStableSwapのその他の流動性ポジションと並んで表示されます。

### **流動性の削除**

流動性を削除するには。

1\. [流動性ページ](https://exchange.pancakeswap.finance/#/pool)にアクセスします。

2\. 「Your Liquidity」の下にある流動性を削除したいペアをクリックします。フィルターを使用してすべてのV2流動性ポジションをすばやく確認できます。

3\. 「Remove」をクリックします。新しいモーダルが表示されます。

4\. ボタンまたはスライダーを使用して、削除したい流動性の量を選択します。このペアの流動性をすべて削除するには「MAX」を選択します。

5\. 「Enable」をクリックします。ウォレットが操作への署名を求めます。

6\. 「Remove」ボタンが点灯します。クリックして続行します。

7\. 受け取るトークン数量を表示するウィンドウが表示されます。「Confirm」をクリックします。ウォレットが操作の確認を求めます。

8\. トランザクションが確認された後、ペアの2つのトークンを受け取ります。流動性をすべて削除していない場合は、残りの流動性の価値が流動性ページで更新されます。<br>
