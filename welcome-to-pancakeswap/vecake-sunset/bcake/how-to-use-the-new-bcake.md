---
description: veCAKE ステーキングとファーミングブースト
---

# 新しい bCAKE の使い方

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2887%29.png" alt=""><figcaption></figcaption></figure>

iCAKE や vCAKE と同様に、bCAKE は忠実な CAKE ホルダーのために設計された veCAKE ステーキングの特典です。CAKE をロックすることで veCAKE が得られ、それによって自動的に bCAKE が付与されます。選択されたファームからの収益を最大2.5倍にブーストできます。

ブースト倍率は veCAKE 残高と、ブーストしようとしているファーム内の流動性の量に基づいて計算されます。

## 事前準備 <a href="#id-9ad80126-6efe-49c2-b203-3590093b92d6" id="id-9ad80126-6efe-49c2-b203-3590093b92d6"></a>

#### **固定期間 veCAKE ステーキングポジションを開始する** <a href="#id-3e485cf0-a9c5-408d-ab19-3ad2a7852589" id="id-3e485cf0-a9c5-408d-ab19-3ad2a7852589"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2878%29.png)

veCAKE プールにまだ CAKE をロックしていない場合は、「Go to Pool」をクリックして手順に従い、固定期間ステーキングポジションを開始してください。

veCAKE ステーキングポジションの開始方法については、[こちら](https://docs.pancakeswap.finance/products/syrup-pool/new-cake-pool#fixed-term-staking)をご参照ください。

#### ブーストしたいファームとポジションを探す <a href="#cf04ee3e-9678-4fc4-bf79-dcc5620a83fd" id="cf04ee3e-9678-4fc4-bf79-dcc5620a83fd"></a>

bCAKE が有効なファームからのみ収益をブーストできます。対象のファームを探すには、APR セクションで緑のロケットアイコンが付いた緑色の APR 数値を確認してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2883%29.png)

または、「Farm Types」セレクター内の「Booster Available」フィルターを使用して、bCAKE 対応ファームを素早く絞り込むこともできます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2876%29.png)

#### ポジションをステークする

bCAKE を有効化するには、ポジションがファームにステークされている必要があります。

* V3 の場合：「Stake」をクリックして LP ポジションをステークします。
* V2 および StableSwap の場合：「Add LP」をクリックして LP トークンをステークします。
* ポジションマネージャーの場合：「Add Liquidity」をクリックして流動性を追加します。

Yield Farming の詳細については、[こちら](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms)のチュートリアルをご覧ください。

#### bCAKE を有効化する <a href="#b3a80f22-5043-4e4b-afae-93b4abec504e" id="b3a80f22-5043-4e4b-afae-93b4abec504e"></a>

bCAKE の有効化は完全に自動化されました。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%20883379190.png" alt="" width="174"><figcaption><p>V3 Farm</p></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Connected%20-%20Has%20LP%20-%20Has%20veCAKE%20-%20Boosted%20automatically.png" alt="" width="174"><figcaption><p>V2、StableSwap</p></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Connected%20-%20Has%20liquidity%20-%20Has%20veCAKE%20-%20Boosted%20automatically.png" alt="" width="174"><figcaption><p>ポジションマネージャー</p></figcaption></figure>

ステーク後、現在ステーキング中のファームに適用されたブースト倍率が表示されます。bCAKE 倍率の計算方法については、[こちら](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#why-do-my-multipliers-change-even-after-activation)をご参照ください。

{% hint style="info" %}
ファーミングポジションまたは veCAKE ステーキングへのユーザー操作は、ファームと CAKE ステーキングプールからの最新データと統計に基づいて、自動的にブースト倍率を更新します。

詳細は[こちら](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#why-do-my-multipliers-change-even-after-activation)をご覧ください。
{% endhint %}

同時にブーストできるファーミングポジションの数に制限はなくなりました。veCAKE ステーキングポジションがアクティブであれば、無制限の数のファームおよびポジションマネージャーのポジションをブーストできます。

#### bCAKE を解除する <a href="#id-6fa438f5-eea6-4d66-9b56-24780cedd273" id="id-6fa438f5-eea6-4d66-9b56-24780cedd273"></a>

bCAKE の解除も完全に自動化されました。

bCAKE ブーストを解除するには、単に流動性を引き出してください。

* V3 の場合：「Unstake」をクリックして LP ポジションをアンステークします。
* V2 および StableSwap の場合：「-」マイナスボタンをクリックして LP トークンをアンステークします。
* ポジションマネージャーの場合：「-」マイナスボタンをクリックして流動性を引き出します。
