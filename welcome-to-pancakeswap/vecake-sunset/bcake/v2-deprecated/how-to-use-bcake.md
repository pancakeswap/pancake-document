# bCAKE の使い方

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-use-bCAKE.png)

iCAKE や vCAKE と同様に、bCAKE は固定期間 CAKE ステーキングプールで CAKE をロックするユーザーのために設計された特典です。ブースト倍率は、ステークしている CAKE の量、ステーキング期間、およびブーストしたいファームにステークしている LP トークンの量に基づいて計算されます。

## 事前準備

### 固定期間 CAKE ステーキングポジションを開始する

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-no-cake-locked.png)

CAKE ステーキングプールにまだ CAKE をロックしていない場合は、「Go to Pool」をクリックして手順に従い、固定期間ステーキングポジションを開始してください。

固定期間 CAKE ステーキングの方法については、[こちら](../../../../archive/legacy-products/new-cake-pool/#fixed-term-staking)をご参照ください。

### Farm Booster を有効化する

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-enable-booster.png)

Farm Booster を有効化するには、一度限りのセットアップが必要です。「Enable」をクリックして、ウォレットからトランザクションを承認するだけです。

### ステーキングを移行する

{% hint style="info" %}
bCAKE を有効化したいファームにまだステークしていない場合は、このステップをスキップして、ファームで LP トークンをステークするところから始めてください。
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-staking-migration-needed.png)

Farm Booster を有効化したいファームにすでにステークしている場合は、一度限りのステーキング移行も必要です。

「Migrate」をクリックして、ステップバイステップのガイドに従って移行を完了してください。CAKE 報酬は自動的にハーベストされ、ウォレットに送られます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-migration-inprogress.png)

## ブースターを有効化する

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-pending-activation%20%281%29.png)

準備が整うと、現在ステーキング中のファームの利用可能なブースト倍率とブーストされた APR が表示されます。bCAKE 倍率の計算方法については、[こちら](../faq.md#how-are-the-bcake-multipliers-calculated)をご参照ください。

ブーストを有効化するには、「Boost」ボタンをクリックして、ウォレットからトランザクションを承認してください。

{% hint style="info" %}
ファームまたは CAKE ステーキングプールへのユーザー操作は、ファームと CAKE ステーキングプールからの最新データと統計に基づいて、自動的にブースト倍率を更新します。

詳細は[こちら](../faq.md#why-do-my-multipliers-change-even-after-activation)をご覧ください。
{% endhint %}

### ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-farm-number-limit.png)

同時にブーストできるファーム数には上限があります。残りのブースター数を確認するには、上部のパネルをご参照ください。

他のファームのブースターを有効化するには、アクティブなブースターを解除する必要があります。

## ブースターを解除する

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-pending-unset%20%281%29.png)

Farm Booster を解除するには、「Unset」ボタンをクリックして、ウォレットからトランザクションを承認してください。

解除時に獲得された CAKE は Farm Booster コントラクトにハーベストされ、次のハーベスト、デポジット、または引き出し時に自動的にウォレットに送られます。詳細は[こちら](../faq.md#where-are-my-cake-rewards-after-activating-or-unsetting-the-booster)をご覧ください。
