# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

Yield Farmsでは、LP Tokensをステーキングすることで、PancakeSwapをサポートしながらCAKEを獲得できます。

ファーミングを始めるには、[ファームの使い方ガイド](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms)をご確認ください。

[ファームのスマートコントラクトの確認方法](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
Yield farmingはシロッププールよりも高い報酬が得られる場合がありますが、**インパーマネントロス（Impermanent Loss）**のリスクが伴います。思ったほど怖くはありませんが、始める前にこの概念を理解しておくことをお勧めします。

詳しくは、Binance Academyの[インパーマネントロスに関する記事](https://academy.binance.com/en/articles/impermanent-loss-explained)をご覧ください。
{% endhint %}

## 報酬の計算方法

Yield Farm の APR 計算には以下の両方が含まれます：

* 流動性を提供することで得られる **LP報酬APR**、および
* Farm でLP Tokensをステーキングすることで得られる **ファームベース報酬APR**

なぜ両方含まれるのでしょうか？CAKEを獲得するためにファームでLP tokensをステーキングしている間も、流動性プールに流動性を提供し続けているため、LP報酬も得られるからです！

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

では、これらの数値はどのように計算されるのでしょうか？

### ファームベース報酬APRの計算方法

**ファームベースAPR**は、ファームの乗数とファーム内の総流動性量に基づいて計算されます。これはファームに配分されるCAKEの量に相当します。

### LP報酬APRの計算方法

さらに、ファーマーは流動性を提供することで**LP報酬**を受け取ります。以下は**LP報酬**の計算例です：

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

上記のWBNB/BUSDペアでは、以下の値が確認できます：

**流動性:** $387.42M\
**24時間取引量:** $96.97M\
**7日間取引量:** 709.73M

* 年間手数料の計算
  * 24時間取引量を使用して、プール内の流動性提供者の**手数料シェア**を計算します（0.17%の取引手数料構造に基づく）:\
    $96,970,000\*0.17/100 = **$164,849**
  * 次に、その**手数料シェア**を使用して、プールが獲得する**年間手数料**の見込み額を計算します（現在の24時間取引量に基づく）:\
    $164,849\*365 = **$60,169,885**
* これで年間手数料を使用して**LP報酬APR**を計算できます：**年間手数料**を**流動性**で割った値です：\
  ($60,169,885/$387,420,000)\*100 = **15.53% LP報酬APR**
