---
description: Bridge CAKE between Ethereum, BNB Chain, Aptos, and many more
---

# 🌉 Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Bridging to/from EVMs（新サイト）: [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Bridging to/from Aptos（V1 Bridge）: [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## クリプトにおけるブリッジングとは？

* ブリッジングとは、異なるブロックチェーンネットワーク間で資産を転送するプロセスのことです。
* 相互運用性を高め、さまざまなネットワーク間でのデータや資産の移転を可能にします。

\
ブリッジングを利用したい理由の例をいくつかご紹介します：

* 異なる暗号通貨トークンを購入する
* 特定のネットワークでのみ利用可能なNFTをミントする
* より安いトランザクションでコストを節約する
* 別のネットワークでのみ利用可能なdappを使用する

***

## CAKE：マルチチェーントークン

マルチチェーン展開により、CAKEはBNBチェーンをネイティブとしながら、Base、Arbitrum、Solana、Ethereum、ZKsync、Linea、opBNB、Aptosでも利用可能なマルチチェーントークンになりました。

他のチェーン上のCAKEは、BNB Smart Chain上のCAKEと同等です。これらのチェーン間で常に1:1の比率でブリッジでき、CAKEの手数料はかかりません。

**CAKEは1種類のみである点にご注意ください。** 異なるチェーンに異なるバージョンのCAKEは存在しません。すべてのブロックチェーンにわたるCAKEの総供給量は、この[投票提案](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5)に記載されているとおり、4億枚に上限が設定されています。

***

## PancakeSwap Bridgeとは？

PancakeSwap Bridgeは、PancakeSwapのインターフェース上で異なるブロックチェーン間で資産を移動できる、便利なアプリ内ツールです。外部のブリッジサイトにアクセスすることなく、BNBチェーン、Ethereum、Base、Arbitrumなどのチェーン間でサポートされているトークンをブリッジできます。すべてが1か所で完結します。

PancakeSwap Bridgeは信頼できるサードパーティプロバイダーによって提供されており、価格・速度・信頼性に基づいて最適なルートを選択する**アグリゲーター**として機能します。

CAKEのブリッジ方法については、以下のセクションのチュートリアルとFAQをご確認ください。

***

## 🔗 仕組み

### アグリゲーターを介したブリッジング

PancakeSwap Bridgeは、信頼できるサードパーティのブリッジプロトコル上のスマートレイヤーとして機能します。ブリッジ送金を開始すると、PancakeSwapは以下を実行します：

* 統合されている複数のブリッジで最適なルートを確認する
* 選択したプロバイダーにトランザクションを送信する

ブリッジングはノンカストディアルです。資産はPancakeSwapの管理下に置かれることはありません。送金はブリッジプロバイダーによって直接処理されます。

### 対応ブリッジプロバイダー

現在、以下と統合しています：

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> 注：各プロバイダーによって、ブリッジングの仕組み、対応チェーン、手数料、上限額が異なります。

***

### 対応チェーンとトークン

#### 現在対応しているチェーン

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (V1サイト)

#### ブリッジング可能なトークン

利用可能なトークンはチェーンとルートによって異なります。一般的にサポートされているトークンには以下が含まれます（これらに限定されません）：

* CAKE
* USDT
* USDC
* ETH

***

#### 制限事項と除外事項

ブリッジの制限や流動性の制約により、一部のトークンはサポートされない場合があります。最良のユーザー体験のため、これらは除外されています。例：

**cBridgeの場合：**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**deBridgeの場合：**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_上記は例です。チェーンごとの実際の利用可能なトークンはBridge UIに直接表示されます。_

***

### 💸 手数料とコスト

#### ブリッジ手数料

* 基盤となるブリッジプロバイダーが請求します
* 通常、送金ごとに少額の手数料が含まれます
* ブリッジを確認する前に明確に表示されます

***

#### ガスコスト

* トランザクションを開始するために**送信元チェーン**のガス手数料をお支払いいただきます
* 一部のプロバイダーは**送信先チェーン**でもガスが必要な場合があります
* **ヒント：** ブリッジの両側にネイティブトークン（ETH、BNBなど）を常に保持しておいてください

***

#### 最小金額と制限

一部のブリッジルートでは以下が適用されます：

* **ブリッジングの最小/最大金額**（例：最小10 USDC）
* **対応するトークンの小数点以下桁数または形式**（例：ERC-20トークンのみ）

UIが無効な送金を自動的に検出して表示します。

***

### ⏳ トランザクション時間と追跡

#### ブリッジングにかかる時間は？

ブリッジ送金は通常、以下の条件によって数**分**で完了します：

* 送信元チェーンと送信先チェーン
* ネットワークの混雑状況
* ブリッジプロバイダーの効率性

#### 送金の追跡

送信後、プロバイダー固有のエクスプローラーでトランザクションのステータスを確認できます：

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

トランザクションが長時間スタックしている場合は、関連するエクスプローラーをご確認いただくか、[ソーシャルチャンネル](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)経由で管理者に[お問い合わせ](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help)ください。

***

### 🧠 ブリッジング前のヒント

* **両方のチェーンにガストークンを保持しておく**（ETH + BNBなど）
* 初めてブリッジングする場合は**少額から始める**
* チェーンの混雑時のブリッジングは避ける（ガス手数料が高くなる可能性があります）
* 両方のチェーンでトークンの互換性を確認する
* 送信元と送信先のネットワークを必ず再確認する

***

### その他：CAKE Omni-chain Fungible Token (OFT) アドレス

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
