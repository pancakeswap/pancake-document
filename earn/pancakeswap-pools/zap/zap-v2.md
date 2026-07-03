---
description: シンプルなワンクリックによる流動性提供
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### Zapとは？ <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zapはシンプルな流動性提供を可能にします。手動でスワップやトークンのバランス調整を行うことなく、1つのトークンとシングルクリックで流動性を追加できます。

* 1つのトークンのみで流動性を追加：トレーディングペアの1つのトークンのみを使用して流動性を追加できます。Zapは提供した1つのトークンを使用して自動的にスワップを実行し、流動性を追加する前にトレーディングペアを50/50の比率に自動的にバランスします。
* 不均衡なトークン数量でのトレーディングペアへの流動性追加：トレーディングペアに提供するトークンの数量がデフォルトのプール比率（50:50）に完全に一致していなくても、流動性を追加できます。例えば30:70。Zapは流動性を追加する前にトークンを50/50に自動的にリバランスします。
* 流動性を削除して受け取りたいトークンを選択：流動性を削除する際、Zapを使えばトレーディングペアの1つのトークンのみを受け取ることができます。Zapはトークンを返す前に自動的にスワップを実行します。

### Zapを有効にする <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

デフォルトでは、すべてのユーザーに対してZap機能がオンになっています。流動性の追加または削除時に新しいZap UIが表示されない場合は、設定パネルで有効にしてください。歯車アイコンをクリックすると設定パネルを開けます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
注意：現在、Zap機能はベータ版です。手数料のあるトークンなど、一部のトークンはサポートされていません。流動性の追加または削除中に問題が発生した場合は、設定パネルで無効にしてください。
{% endhint %}

### Zap In（流動性の追加） <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

[流動性ページ](https://pancakeswap.finance/liquidity)にアクセスし、「Add Liquidity」を選択します。

流動性を提供したいトレーディングペアを2つの入力トークンを選択して選びます。詳細は[流動性ガイド](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide)をご確認ください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

「Add Liquidity」ボタンをクリックして続行します。

流動性を追加しようとしているトレーディングペアのトークンがウォレットに残高があれば、そのトークンのチェックボックスは自動的にチェックされます。両方のトークンの残高がウォレットにある場合、両方のチェックボックスがチェックされます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### 1つのトークンを使用したZap <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

トレーディングペアの1つのトークンのみを使用して流動性を追加できます。使用したいトークンの1つのチェックボックスだけをチェックします。Zapはチェックしたトークンの半分を自動的にトレーディングペアの別のトークンにスワップしてから流動性を追加します。どのトークンが変換されるかを示す警告メッセージが表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
価格インパクトが高すぎる場合、Zapはスリッページによって保護します。「Reduce TOKEN」をクリックして推奨上限まで削減してください。
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### 不均衡な数量の2つのトークンを使用したZap <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

両方のトークンがチェックされているが、入力トークンの数量が50/50の比率に一致しない場合、Zapのバランス調整が適用されます。「一部のトークンAがトークンBに変換されます」というメッセージが表示されます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
流動性を追加する前にZapがトークン数量をバランスしないようにする場合は、「Don't Convert」をクリックします。この場合、Zapはスワップとリバランスを試みる代わりに、50/50の比率に合わせるよう入力トークンの数量を調整します。
{% endhint %}

### Zapを続行する <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

「Supply」をクリックすると、Zapの詳細が表示され、確認を待ちます。

以下が表示されます：

1. 受け取るLPトークンの数量。
2. 入力トークンとコミットするトークン数量。
3. 50/50の比率に合わせるための入力トークンの取引方法。
4. 使用しているスリッページ許容範囲。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap Out（流動性の削除） <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zapを使えば、流動性を削除する際にトレーディングペアの1つのトークンのみを受け取ることもできます。

1. [流動性ページ](https://pancakeswap.finance/swap#/pool)にアクセスします。
2. 「Your Liquidity」の下にある流動性を削除したいペアをクリックします。
3. 「Remove」をクリックします。新しいポップアップが表示されます。

「You Will Receive」セクションで、受け取りたくないトークンのチェックを外します。Zapは流動性を削除する際に、チェックしたトークンにリターンの100%を自動的にスワップ・変換します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
