---
description: Bridge CAKE between EVM chains and Aptos
---

# ブリッジ方法 - EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
以下のガイドでは、EVMチェーンの例としてBNB Chainを使用しています。同じ手順をEthereumにも適用できます。
{% endhint %}

## BNB Smart ChainからAptosへのCAKEのブリッジ

1 - ウォレットがBNB Smart ChainとAptos Mainnetの両方に対応していることを確認するか、ブラウザに両方のウォレットをインストールしてください。

次に[PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)を開きます。

2 - まず、BNB Smart Chainのウォレットを接続する必要があります。

「Connect」をクリックし、「EVM」セクションで希望するウォレットを選択します。次にウォレットのポップアップで確認・承認します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - 次に、Aptosのウォレットを接続する必要があります。

ウォレット接続モーダルで、「Aptos」セクションで希望するウォレットを選択します。次にウォレットのポップアップで確認・承認します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - 上部のトークン選択フィールドの「v」をクリックし、「CAKE」を選択します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - AptosにブリッジしたいCAKEの数量を入力します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Aptosウォレットが新規作成されたばかりでAPT（Aptos Coin）の残高がない場合、「gas on destination」オプションをデフォルトのままにすることをお勧めします。ブリッジは少量のAPTをウォレットに入金します。これはAptos上での活動を開始するためだけでなく、ブリッジされたCAKEの登録とクレームのためのガスにもAPTが必要なためです。

このオプションを変更するとブリッジングが失敗する可能性があります。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - 「Transfer」をクリックしてブリッジングトランザクションを開始し、ウォレットの確認ポップアップで承認します。

BNB Smart ChainウォレットとAptosウォレットの状態によっては、**複数回**のウォレット確認が必要な場合があります。例えば、初めてCAKEをAptosにブリッジする場合、以下が必要になります：

* ブリッジングコントラクトでのCAKEの使用承認（BNB Smart Chainウォレットから）
* CAKEの登録（Aptosウォレットから）

詳細については、[こちらの内訳](aptos.md#bridging-cake-to-aptos-for-the-first-time)をご確認ください。

8 - しばらくお待ちください。数分で完了するはずです。ブリッジングが完了すると、CAKEがAptosウォレットに入金されます。プログレスバーで進行状況を追跡できます。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## 初めてAptosにCAKEをブリッジする場合

AptosウォレットへのCAKEのブリッジングには、登録とクレームのトランザクションが必要です。これはユーザーのセキュリティを強化するためのものであり、Aptos独自の仕様です。

### **ウォレットにAPT（Aptos Coin）がある場合：**

Aptosウォレットにまだ登録されていない場合、CAKEの登録を求めるプロンプトが表示されます。この場合、追加のクレームトランザクションは必要ありません。

### **ウォレットにAPT（Aptos Coin）がない場合：**

ブリッジトランザクションが完了した後、手動でCAKEをクレームする必要があります。クレームのガス代を賄うため、ソースウォレットからAptosウォレットにAPTトークンが送信されます。

これらの登録とクレームの手順は、Aptos上でトークンを初めて操作する場合にのみ適用されます。同じトークンのその後の送金では、これらの操作は必要ありません。

初めてAptosにCAKEをブリッジする前に、AptosアドレスにガスのためのAPTが十分にあることを確認してください。詳細については、Aptosの説明をご確認ください：[https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## AptosからBNB Smart ChainへのCAKEのブリッジ

1 - ウォレットがBNB Smart ChainとAptos Mainnetの両方に対応していることを確認するか、ブラウザに両方のウォレットをインストールしてください。

次に[PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)を開きます。

2 - まず、BNB Smart Chainのウォレットを接続する必要があります。

「Connect」をクリックし、「EVM」セクションで希望するウォレットを選択します。次にウォレットのポップアップで確認・承認します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - 次に、Aptosのウォレットを接続する必要があります。

ウォレット接続モーダルで、「Aptos」セクションで希望するウォレットを選択します。次にウォレットのポップアップで確認・承認します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - 上部のトークン選択フィールドの「v」をクリックして「CAKE」を選択します。次にページ中央のダブルアローボタンをクリックして、ブリッジングの方向を反転させます。

「Aptos」ネットワークが上部フィールドにあることを確認してください。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - BNB Smart ChainにブリッジしたいCAKEの数量を入力します。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - BNB Smart Chainウォレットが新規作成されたばかりでBNB（ガストークン）の残高がない場合、「gas on destination」オプションをデフォルトのままにすることをお勧めします。ブリッジは少量のBNBをウォレットに入金します。BNB Smart Chain上での活動を始め、活気あふれるPancakeSwapエコシステムを探索するのに役立ちます。

7 - 「Transfer」をクリックし、ウォレットのポップアップからトランザクションを承認します。

8 - しばらくお待ちください。数分で完了するはずです。ブリッジングが完了すると、CAKEがBNB Smart Chainウォレットに入金されます。プログレスバーで進行状況を追跡できます。
