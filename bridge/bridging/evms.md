---
description: Bridge between EVMs like Ethereum and BNB Chain
---

# EVM間のブリッジ方法

{% hint style="success" %}
**EVM：** EVMチェーンは、Ethereumと互換性のあるスマートコントラクトおよびdAppsを実行するためにEthereum仮想マシンを使用するブロックチェーンです。Ethereum、BNB Smart Chainなどが例として挙げられます。
{% endhint %}

1. [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge) にアクセスします
2. ウォレットが接続されていることを確認します

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%283%29.png" alt=""><figcaption></figcaption></figure>

3. ネットワークセレクターを使って**送信元**と**送信先**のチェーンを選択します

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%283%29.png" alt="" width="375"><figcaption></figcaption></figure>

4. 送金したい金額を入力し、ドロップダウンからトークンを選択します

* **ヒント：** 送信前にトークンのコントラクトアドレスを必ず再確認してください！

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%283%29.png" alt="" width="374"><figcaption></figcaption></figure>

5. **受け取るトークン**を選択します。トークンシンボルが同一の場合（USDC / USDTなど）、バリアントが表示されますので選択してください

* **ヒント：** トークンの上にカーソルを合わせるか、リンクをクリックしてトークン名とアドレスを確認してください

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%282%29.png" alt="" width="375"><figcaption><p>USDC</p></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%285%29%20%282%29.png" alt="" width="375"><figcaption><p>USDC (Wormhole)</p></figcaption></figure>

6. 「受け取り金額」セクションを確認して、すべての詳細が正しいことを確認します

* PancakeSwapは、送信元と送信先チェーンに基づいて複数のブリッジプロバイダーから選択します。
* プロバイダーによって手数料、処理時間、制限が異なります。これらは明確に表示されます。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28385%29.png" alt=""><figcaption></figcaption></figure>

* タグを使用してルートを比較できます：
  * **ベストリターン** = 受け取り金額が最大
  * **最速** = 最短の送金時間

これらのタグを活用して、ニーズに応じた速度と価値のバランスを取ってください。

{% hint style="warning" %}
ブリッジプロバイダーとの**最初のトランザクション**では、トークン転送の承認を求められます（これは1回限りの操作です）

* **2回目のトランザクション**からは、「Send」をクリックするだけでブリッジ送金が開始されます
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29%20%281%29.png" alt=""><figcaption></figcaption></figure>

7. しばらくお待ちください！ほとんどのブリッジ送金は数分で完了します。完了すると、トークンがEthereumアドレスに表示されます。
