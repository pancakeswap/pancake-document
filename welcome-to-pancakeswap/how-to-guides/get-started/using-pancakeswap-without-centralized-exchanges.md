---
description: >-
  PancakeSwap を使い始めるのに、Binance、Coinbase、Kraken、Huobi、OKEx などの
  中央集権型取引所のアカウントは必要ありません！
hidden: true
---

# 中央集権型取引所を使わずに PancakeSwap を利用する

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-pancakeswap-without-cex-header.png)

PancakeSwap は分散型アプリケーションです。Binance などの中央集権型プラットフォームとは異なり、アカウント登録不要で利用できます。必要なのは暗号資産ウォレットだけです。では、中央集権型取引所を使わずに PancakeSwap へ暗号資産を送るにはどうすればよいでしょうか？

このチュートリアルでは、「クロスチェーンブリッジ」を使って資産を BNB Smart Chain ウォレットに移し、PancakeSwap を使い始めるまでの手順を説明します。

### **他のブロックチェーンから BNB Smart Chain へ資産を移動する**

さまざまなクロスチェーンブリッジを使って、Ethereum などのネットワークから BNB Smart Chain へトークンを移動することができます。

以下のチュートリアルでは、3 種類のクロスチェーンブリッジを使って、さまざまなブロックチェーンから USDT を BNB Smart Chain に移動する手順を説明します。

{% tabs %}
{% tab title="🥞🌉 Pancake Bridge（推奨）" %}
![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28168%29.png)

[**PancakeSwap Bridge**](http://bridge.pancakeswap.finance) — Stargate を利用したネイティブアセットのクロスチェーンブリッジです。

このブリッジを使うと、ステーブルコインをシームレスに BNBチェーン へ移動させ、活発な PancakeSwap コミュニティや BNB エコシステム全体に参加することができます。

📖 [使い方を見る](https://medium.com/pancakeswap/launching-pancakeswap-bridge-a-partnership-with-stargate-21c1c9f491a8)
{% endtab %}

{% tab title="AnySwap" %}
AnySwap を使って、Polygon (MATIC) ブロックチェーンから BSC へ USDT を移動する方法をご紹介します。

1. Polygon (MATIC) ウォレットに USDT と、ガス代用の MATIC を用意します。
2. AnySwap がサポートしているのは MetaMask、OKEx Wallet、Coin98 Wallet のみです。他のウォレットアプリをご利用の場合は、MetaMask にウォレットをインポートすることをおすすめします。
3. [https://anyswap.exchange/#/router](https://anyswap.exchange/#/router) にアクセスします。
4. ウォレットを接続し、ネットワークを Polygon (MATIC) Mainnet に切り替えます。
5.  「From」に MATIC mainnet の USDT、「To」に BSC mainnet の USDT を選択します。移動したい USDT の金額を入力します。

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-055554AM-Google%20Chrome_AnySwap%20-%20Cross%20Chain%20Protocol.png" alt="" data-size="original">
6. 「Approve USDT」をクリックして USDT を承認します。
7. 別の BSC アドレスへ USDT を送金したい場合は「+ Send To」ボタンをご利用ください。
8. 「Swap」をクリックし、クロスチェーン取引を完了させます。
9. ネットワークの混雑状況によりますが、全体の処理には約 10〜30 分かかります。
10. 完了後、BSC ウォレットに資金が届きます。これで PancakeSwap を使って BNB Smart Chain 上のトークンをスワップする準備が整いました。
{% endtab %}

{% tab title="O3 Hub" %}
⚠️ **O3 Swap はベータ版です。ご自身の責任においてご利用ください。**

O3 Hub を使って ERC-20 ブロックチェーンから BNB Smart Chain へ USDT を移動する方法をご紹介します。

1. ERC-20（Ethereum Mainnet）ウォレットに USDT と、ガス代用の ETH を用意します。
2. O3 Hub がサポートしているのは MetaMask と O3 Wallet のみです。他のウォレットアプリをご利用の場合は、MetaMask にウォレットをインポートすることをおすすめします。
3. [https://o3swap.com/hub](https://o3swap.com/hub) にアクセスします。
4.  ETH と BSC 両方で MetaMask または O3 ウォレットを接続します。MetaMask のネットワークを Ethereum Mainnet に切り替えます。

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-054852AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
5.  「You pay」に ERC-20 USDT、「You will receive」に BEP-20 USDT を選択します。移動したい USDT の金額を入力します。

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-053358AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
6.  「To」フィールドに接続済みの正しい BNB Smart Chain ウォレットアドレスが表示されているか確認します。

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-053441AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
7. 内容に問題がなければ「Swap」をクリックします。
8. 画面の指示に従って USDT を承認し、最終的なクロスチェーン取引を完了させます。
9.  ネットワークの混雑状況によりますが、全体の処理には約 10〜30 分かかります。履歴タブで進捗を確認できます。

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-054520AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
10. 完了後、BSC ウォレットに資金が届きます。これで PancakeSwap を使って BNB Smart Chain 上のトークンをスワップする準備が整いました。

詳細については、O3 Swap の[ユーザーガイド](https://docs.o3swap.com/o3-swap-user-guide/hub#2.-hub-swap)もご参照ください。
{% endtab %}
{% endtabs %}
