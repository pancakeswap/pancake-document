---
description: >-
  流動性とファームのステーキングを新しいPancakeSwap ExchangeおよびFarm v3に移行する
---

# マイグレーション方法

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28133%29.png" alt=""><figcaption></figcaption></figure>

2023年4月、PancakeSwapはExchangeとFarmのv3を発表しました。一部のファーミングペアはステーキング報酬を引き続き獲得するためにマイグレーションが必要です。前回同様、スムーズに進めますのでご安心ください。

### マイグレーションが必要かどうかの確認 <a href="#id-4b9e0260-9dee-493b-b0ad-6bdba084cea6" id="id-4b9e0260-9dee-493b-b0ad-6bdba084cea6"></a>

以下の条件に該当する場合はマイグレーションが必要です。

**以下のPancakeSwap v2ファームでファーミングしている場合：**

* BNBチェーン：
  * CAKE-BNB
  * CAKE-BUSD
  * CAKE-USDT
  * BUSD-BNB
  * USDT-BNB
  * BTCB-BUSD
  * BTCB-USDT
  * BTCB-ETH
  * BTCB-BNB
  * ETH-BNB
  * ETH-USDC
  * USDC-USDT
  * BUSD-USDC
  * BUSD-USDT
* Ethereum：
  * ETH-USDC
  * ETH-USDT
  * WBTC-ETH

このリストは今後拡大される可能性があります。最新リストを確認する最も簡単な方法は、[https://pancakeswap.finance/migration](https://pancakeswap.finance/migration)にアクセスしてウォレットを接続することです。

**v2の流動性を提供しており、以下の条件を満たす場合：**

* そのトークンペアの流動性の大部分がv3に移行済み — 詳細はPancakeSwap Infoページ、またはそのトークンプロジェクトのウェブサイトやソーシャルチャンネルをご確認ください。
* そのトークンのプロジェクトチームが流動性をv3に移行すると発表している — 詳細は各プロジェクトのウェブサイトやソーシャルチャンネルをご確認ください。

### マイグレーションの手順 <a href="#c7d7b407-268c-460c-a4f1-be1b771db5e7" id="c7d7b407-268c-460c-a4f1-be1b771db5e7"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28283%29.png" alt=""><figcaption></figcaption></figure>

LiquidityページまたはFarmページのv3マイグレーションバナーをご確認ください。「Proceed」をクリックしてマイグレーションヘルパーページに進みます。



**ステップ1 — v2およびStableSwapファームからアンステーキングする**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28119%29.png" alt=""><figcaption></figcaption></figure>

ステップ1では、ヘルパーがマイグレーションが必要なPancakeSwap v2またはStableSwapファームの一覧を表示します。

各「Unstake All」ボタンをクリックして、ファームからステーキングされているすべてのLPトークンをアンステーキングします。ウォレットで確認を求められます。

リストに表示されたすべてのファームのアンステーキングが完了したら、「Next Steps」をクリックして次に進みます。



**ステップ2 — Exchange v2またはStableSwapから流動性を撤退させる**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28315%29.png" alt=""><figcaption></figcaption></figure>

ステップ2では、ヘルパーがCAKEのイールドファーミング付きでv3に移行できる流動性ポジションの一覧を表示します。

各「Remove」ボタンをクリックして、100%が選択された状態で流動性の撤退モーダルを表示します。&#x20;

「Enable」をクリックし、ウォレットでトランザクションに署名して、「Remove」をクリックします。ウォレットで確認を求められます。

{% hint style="info" %}
他のプロジェクトのトークンの一部もv3に移行していますが、リストには表示されません。詳細は各プロジェクトのウェブサイトやソーシャルチャンネルをご確認ください。手動でマイグレーションするには[Liquidity](https://pancakeswap.finance/liquidity)ページをご利用ください。
{% endhint %}



**ステップ3 — v3の準備をする**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28186%29.png" alt=""><figcaption></figcaption></figure>

操作は不要です。v3の仕組みとv3での流動性提供方法を確認して、理解を深めておきましょう。



**ステップ4 — v3流動性を追加する**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28325%29.png)

このステップでは、新しいExchange v3に流動性を追加します。

「Add Liquidity」をクリックします。以前撤退したv2の流動性がリストに表示されますので、「Add」をクリックしてv3流動性追加のインターフェースを表示します。

追加したいペアが見つからない場合は、「Add Other Pairs」をクリックして2つのトークンを手動で選択してください。

v3での流動性提供に関する詳細チュートリアルは[こちら](../../../earn/pancakeswap-pools/liquidity-guide.md)をご覧ください。

v3で流動性を提供する際にご不明な点がある場合は、[よくある質問 (FAQ)](../../../trade/trading-faq/swap-faq.md)をご確認ください。

{% hint style="warning" %}
Exchange v3では、アクティブな（範囲内の）流動性ポジションのみが取引手数料の報酬を獲得できることにご注意ください。

流動性ポジションの価格範囲を設定する際は慎重にお行いください。
{% endhint %}



**ステップ5 — v3ファームにステーキングする**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2835%29.png" alt=""><figcaption></figcaption></figure>

このステップでは、新しく追加したv3の流動性ポジションを新しいv3ファームにステーキングして、CAKE報酬の獲得を開始します！

ポジションの各「Stake」ボタンをクリックしてファームにステーキングします。ウォレットで確認を求められます。

v3でのファーミングに関する詳細チュートリアルは[こちら](../../../earn/yield-farming/how-to-use-farms/#farm-v3)をご覧ください。

v3ファームで流動性をステーキングする際にご不明な点がある場合は、[よくある質問 (FAQ)](../../../earn/earn-faq/farming-faq.md)をご確認ください。

{% hint style="warning" %}
Farm v3では、アクティブな（範囲内の）流動性ポジションのみがCAKE報酬を獲得できることにご注意ください。

流動性ポジションの価格範囲を設定する際は慎重にお行いください。
{% endhint %}



**完了**

これで完了です。ファームのステーキングと流動性を新しいPancakeSwap v3に移行しました！
