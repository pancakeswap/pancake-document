# 取引方法

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-trade-on-pancakeswap-header.png)

PancakeSwapでの取引は、ほとんどの取引所と比べて非常に簡単です。複雑なチャートや専門用語に戸惑うことなく、取引ルートや計算はすべてPancakeSwapのSmart Routerが自動で処理してくれます。

**取引の準備**

取引を始める前に、BNB ChainまたはEthereumに対応したウォレットが必要です。取得方法は[こちら](https://docs.pancakeswap.finance/get-started/wallet-guide)でご確認いただけます。また、取引に使用するBEP-20またはERC-20トークンも必要です。取得方法は[こちら](https://docs.pancakeswap.finance/get-started/bep20-guide)でご確認いただけます。

あるいは、Aptos対応ウォレットの取得方法は[こちら](https://docs.pancakeswap.finance/get-started-aptos/wallet-guide)、スワップに使用するAptosコインの取得方法は[こちら](https://docs.pancakeswap.finance/get-started-aptos/aptos-coin-guide)をご参照ください。

## PancakeSwap Exchangeでの取引

1 - [こちら](https://pancakeswap.finance/swap)のExchangeページにアクセスします。



2 - 「Connect **Wallet**」をクリックしてウォレットを接続します（右上の「**Connect**」からも接続できます）。PancakeSwapにウォレットをまだ接続していない場合は、[こちら](https://docs.pancakeswap.finance/get-started/connection-guide)のガイドをご参照ください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28200%29.png)



3 - 上部のドロップダウンメニューから、取引したいトークンを選択します。選択したトークンが十分な量ウォレットに入っていることを確認してください。残高はトークンのドロップダウンメニューの上部に表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2850%29.png)



4 - 同様に、下部のセクションから受け取りたいトークンを選択します。



5 - 次に、上部のセクションにスワップするトークンの数量（送付量）を入力するか、下部のセクションに受け取りたいトークンの数量を入力します。&#x20;

一方のセクションに数量を入力すると、もう一方のセクションの数量が自動的に推定されます。



6 - すべての詳細を確認し、「**Swap**」ボタンをクリックします。

初めてトークンを取引する場合は、最初に「Enable XXX（お使いのトークン）」をクリックして承認が必要になることがあります。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28272%29.png)



7 - 詳細が表示されたウィンドウが開きます。内容が正しいことを確認し、準備ができたら「**Confirm Swap**」ボタンをクリックします。ウォレットでアクションの承認を求められます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2827%29.png)



8 - 完了です！上部に表示されるリンクをクリックすると、ブロックエクスプローラーでトランザクションを確認できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28209%29.png)

## **Smart Router v3とは何ですか？どのように使いますか？**

PancakeSwapのSmart Routerは、v3、v2、StableSwap（BNB Chain）、およびAMMとマーケットメーカー（BNB Chain・Ethereum）を連携させ、常に流動性と価格を提供するルーティングアルゴリズムです。デフォルトでは、複数のプールをまたいで取引を実行し、トレーダーに最良の価格を提供します。

Smart Routerは現在、PancakeSwap Exchange v3のデフォルトルートとなっています。ただし、ユーザーは自分のニーズに合わせてカスタマイズすることも可能です。

取引ルートのカスタマイズ方法については、[こちら](fees-and-routes.md)をご参照ください。&#x20;

StableSwapの詳細については[こちら](/broken/pages/nNPogTZMxocdyFIBYbkE)、マーケットメーカー連携については[こちら](market-maker-integration.md)をご参照ください。

## FAQ

{% hint style="info" %}
このセクションは[こちら](../trading-faq/swap-faq.md)に移動しました。
{% endhint %}
