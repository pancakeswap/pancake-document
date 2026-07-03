---
description: ワンクリックで流動性を追加する
---

# Zap

### Zapとは <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zapは流動性を簡単に追加できる機能です。Zapを使えば、プールで必要なトークンに関係なく、残高のある任意のトークンで流動性を提供できます。価格レンジを設定し、提供する金額を選択して実行するだけです。トークンは最も効率的な方法で取引されながら、最低限の価格インパクトとスリッページで自動的にバランス調整され、流動性ポジションが形成されます。

### 対応チェーン

* v3 - BNB Chain上のすべてのプール、EthereumおよびArbitrumネットワークの選択されたプール
* Infinity - BNB Chain上のすべてのCLAMMプール（Hookなし）

### 使い方 <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

現在、Zapは以下をサポートしています：

* 🆕 任意のトークン！
* シングルトークンを使用
* 🆕 デュオトークンを使用
* 🆕 または...複数のトークンを使用（ダストコレクターとして使用可能）

#### 開始 <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Zapを使用するには、流動性追加ページにアクセスし、流動性を提供したいトレーディングペア、手数料ティア、価格レンジを選択します。

次に、流動性を提供するトークン数量を選択します。

1つ以上のトークンの残高が不足している場合、Zapのオプションが自動的に表示されます。

リンクをクリックしてZapモーダルを開きます。

#### Zapの開始 <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

新しい「Zap in」モーダル内には、以下のフィールドがあります：

1. Zap（流動性提供）先のトレーディングペア。
2. 預入トークンと預入金額。Zapに使用するトークンは自由に追加・削除できます。
3. 新しいポジションの価格レンジ。矢印をクリックして異なる価格表示を切り替えることもできます。
4. Zap機能が預入トークンをどのように処理するかの詳細な内訳。
5. 以下を含む統計のサマリー：
   1. 新しい流動性ポジションのUSD換算の推定価値。
   2. 新しい流動性ポジションの推定トークン数量。
   3. Zap後のUSD換算の推定残余資金。ほとんどの場合は0になります。流動性プールやトークンの流動性が非常に少ない場合、この値が増加する場合があります。
   4. Zap中のトークンスワップとリバランスに対する価格インパクト。
   5. 流動性追加とポジション構築に対する価格インパクト。
   6. Zap手数料。流動性ペアによって手数料率は異なります。

{% hint style="warning" %}
利用可能な残高に基づいてZap金額を再設定する必要がある場合があります。いずれかのトークンの残高がない場合は、そのトークンを削除してください。
{% endhint %}

{% hint style="info" %}
「V3流動性の追加」からの設定（預入金額や価格レンジの設定を含む）が自動的にZapモーダルに引き継がれることに気づくかもしれません。
{% endhint %}

#### Zapの実行 <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

最後に「Approve」をクリックし、トークン許可のためウォレットポップアップで確認します。

次に「Preview」をクリックして最終確認モーダルを表示します。続行する前に、最終確認モーダルに表示されているすべての統計と見積もりを必ずご確認ください。特に影響の数値と最大スリッページにご注意ください。

最後に「Add Liquidity」をクリックし、ウォレットポップアップで確認します。

トランザクションが確認されると、「マイポジション」ページに新しいポジションが表示されます。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### その他の設定 <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Zapエクスペリエンスをさらにカスタマイズする場合は、右上のギアアイコンをクリックします。設定では以下を設定できます：

* Zap中の最大スリッページ。
* トランザクションデッドラインのタイムライン。
* KyberSwapのアグリゲーテッド流動性を使用してトークンリバランスを実行するかどうか。PancakeSwap Poolsでのみ取引したい場合はオフにしてください。
* Degenモードは非常に高いスリッページのZapを実行するために使用できます。通常の用途には推奨しません。自己責任でご使用ください。

{% hint style="warning" %}
スリッページとデッドラインの設定はSwapおよび流動性ページとは独立していることにご注意ください。
{% endhint %}

#### デュオトークンを使用したZap

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

流動性をデュオトークンでZapできるようになりました。これは、利用可能な残高が価格設定と一致しない場合や、必要なトークン数量と比率に合わない場合に便利です。Zapを使えば、比率が自動的に再調整されます。

#### 複数のトークンを使用したZap

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

ダストトークンコレクターのように機能します。ウォレット内の少額残高を整理し、取引手数料からの収益を得るためのポジションに活用するのに適しています。&#x20;
