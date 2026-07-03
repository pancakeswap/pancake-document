---
description: ファームとプールのステーキングを新しいPancakeSwap MasterChefに移行する
---

# ステーキングを移行する

![ICYDK: このバナーに記載されている「チュートリアル」を現在ご覧になっています](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration%20pre%20heat.png)

ステーキング報酬を継続して獲得するには、ファームとプールのステーキングを新しいMasterChefに移行する必要があります。ご安心ください、簡単に進められます。

{% hint style="info" %}
**移行が必要かどうかの確認**

以下に該当する場合はマイグレーションが必要です。

* PancakeSwap **Farm**でファーミングしている。
* PancakeSwap **CAKE Syrup Pool**（Manual、Auto、IFO）でステーキングしている。

\*その他のSyrup Poolは影響を受けません
{% endhint %}

## 移行方法

![移行時に、チェフがプロセスをステップごとにガイドするヘルパーをデプロイします](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration-helper-overview.png)

### 1. マイグレーションヘルパーにアクセスする

[https://pancakeswap.finance/migration](https://pancakeswap.finance/migration)にアクセスし、ウォレットを接続します。

### 2. 旧ファームからアンステーキングする

マイグレーションヘルパーには2つのステップがあります。最初のステップでは、現在ステーキングしている3つのCAKE Syrup Poolとファームのリストが表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration-helper-steps-guide-3.png)

各ファームとプールの「**Unstake All**」をクリックして、すべてのアセットをアンステーキングします。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration-helper-steps-guide-4%20%281%29.png)

アンステーキング後、「**Go to Stake**」をクリックしてステップ2に進みます。

### 3. LPトークンとCAKEを新しいファームとプールにステーキングする

ここでは、全く新しいCAKE Syrup Poolと新しいファームが表示されます。ステーキングの前に、これらを有効化する必要があります。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration-helper-steps-guide-5%20%281%29.png)

各ファームとCAKE Syrup Poolで「**Enable**」をクリックしてステーキングを有効化します。モバイルデバイスをご使用の場合は、「**Enable**」ボタンを探す際に「**v**」（下向き矢印）をクリックしてカードを展開してください。

有効化後、プールとファームでステーキングを開始できます。

{% tabs %}
{% tab title="CAKE Syrup Pool" %}
![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration-helper-steps-guide-7%20%282%29.png)

CAKE Syrup Poolの場合は以下の手順を実行してください。

1. 「Stake CAKE」セクションの「**Flexible**」をクリックします。
2. ステーキングしたいCAKEの量を入力します。
3. 「**Confirm**」をクリックします。



{% hint style="info" %}
ロック（固定期間）ステーキングオプションは、マイグレーションの数日後に利用可能になります。フレキシブルステーキングのポジションをロックに変換することもできます。固定期間ステーキング付きの新しいCAKE Syrup Poolについて詳しくは、[こちらのドキュメント](../../../../archive/legacy-products/new-cake-pool/)をご覧ください。
{% endhint %}
{% endtab %}

{% tab title="Farms" %}
![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration-helper-steps-guide-8.png)

ファームの場合は以下の手順を実行してください。

1. 「**Stake**」をクリックします。
2. ステーキングしたいLPトークンの量を入力します。
3. 「**Confirm**」をクリックします。
{% endtab %}
{% endtabs %}

### 4. 完了！

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/migration-helper-steps-guide-9%20%281%29.png)

新しいMasterChefでステーキングが完了し、CAKE報酬の獲得が継続されます！「**Finish**」をクリックして戻り、PancakeSwapが提供するその他の優れた製品もお楽しみください。

## マイグレーションのタイムライン

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en%20-%20migration%20timeline%20-%202.png)

詳細なタイミングと最新情報については、[Twitter](https://twitter.com/pancakeswap/)または[Telegram](https://t.me/PancakeSwapAnn)アナウンスチャンネルをフォローしてください！サポートが必要な場合は、[こちら](../../../contact-us/#help)でヘルプの求め方をご確認ください。

## よくある質問 (FAQ)

#### **いつ完了しますか？**

マイグレーションには数時間かかりますが、マイグレーションヘルパーページの起動時には完全に完了している予定です。最新情報については[Twitter](https://twitter.com/pancakeswap/)または[Telegram](https://t.me/PancakeSwapAnn)アナウンスチャンネルをフォローしてください！

#### **いつまでに移行する必要がありますか？**

1. いつでも移行できます。期限はありません。&#x20;
2. ファームとプールから引き続き報酬を獲得するために、早めに移行することをお勧めします。

#### マイグレーションヘルパーが表示されません！

スマートコントラクトのデプロイと設定が完了した後にのみデプロイされます。数時間かかる場合があります。最新情報については[Twitter](https://twitter.com/pancakeswap/)または[Telegram](https://t.me/PancakeSwapAnn)アナウンスチャンネルをフォローしてください！

#### ロックステーキングが利用できないのはなぜですか？

近日公開予定です！スムーズなマイグレーションを実現するため、ロック（固定期間）ステーキングはマイグレーションの数日後に有効化されます。

#### マイグレーションヘルパーでファームが見つかりません！

マイグレーション前にファームが終了した可能性があります。以下の手順をお試しください。

1. **Farm**に移動します。
2. ファームリストの上部で「**Finished**」を選択します。
3. 「**Check out v1 farms**」をクリックしてファームを探します。
