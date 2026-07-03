# 🔀 クロスチェーンスワップ

クロスチェーンスワップを使用すると、単一のシームレスなトランザクションでチェーン間のトークンスワップが行えます。

クロスチェーンスワップは以下のチェーン間でサポートされています：

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**トランザクションは非常に高速で、通常数秒から1分以内に完了します。**
{% endhint %}

***

### 🔍 仕組み

1. ユーザーが送信元・送信先のチェーンとトークンを選択します
2. PancakeSwapのルーターが最も効率的なルートを計算します
3. 送信元・送信先チェーンのPancakeSwapの流動性プール（v2、v3、Infinity、StableSwap）を使用してスワップが実行されます
4. ブリッジングはパートナープロトコルが担当します：[Across](https://across.to/)（EVM間）、[Relay](https://relay.link/bridge)（SOL〜EVM間）

{% hint style="success" %}
**クロスチェーンスワップは、送信元・送信先チェーンの両方で十分な流動性があれば、あらゆるトークンで利用可能です。**
{% endhint %}

***

### 💸 手数料

* **PancakeSwapはクロスチェーントランザクションに対して手数料を請求しません。**
* 手数料の内訳：
  1. **取引手数料：** 送信元・送信先チェーンの流動性プール内でのスワップで発生します
  2. **ブリッジ手数料：** アセットのブリッジングを行うリレイヤーへの支払いです

***

### 🎯 インテントとは何ですか？

インテントを使用すると、ユーザーは達成方法を気にすることなく望ましい結果を定義できます。

インテントの例：

* 「Base上の1 ETHを、Arbitrum上の少なくとも3000 USDCと交換する」

インテントがない場合、ユーザーは手動で以下の操作が必要です：

* ETHをArbitrumにブリッジする
* ETH → USDCで最良の価格を提供するDEXを探す

{% hint style="success" %}
**インテントを使用すれば、システムがすべてを自動的に処理します。**
{% endhint %}

**インテントベース設計のメリット：**

* シームレスなUX
* 高速なトランザクション処理
* ワンクリックの単一トランザクション

***

### 🔐 監査

クロスチェーンセキュリティ分野の信頼できる機関による複数回の監査を実施しています：

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
