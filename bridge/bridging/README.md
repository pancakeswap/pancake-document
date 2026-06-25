---
description: 在以太坊、BNB 链、Aptos 等众多网络之间跨链转移 CAKE
---

# 🌉 跨链桥

<figure><img src="../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
跨链至/自 EVM 网络（新版网站）：[https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

跨链至/自 Aptos（V1 跨链桥）：[https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## 加密货币中的跨链是什么？

* 加密货币中的跨链是指在不同区块链网络之间转移资产的过程。
* 它增强了互操作性，允许在各种网络之间转移数据和资产。

\
以下是你可能想要进行跨链的一些原因：

* 购买不同的加密货币代币
* 铸造仅在特定网络上提供的 NFT
* 通过更便宜的交易节省费用
* 使用仅在另一个网络上提供的 dapp

***

## CAKE，一种多链代币

随着我们的多链扩展和部署，CAKE 现在成为一种多链代币，它原生于 BNB 链，同时也可在 Base、Arbitrum、Solana、Ethereum、ZKsync、Linea、opBNB 和 Aptos 上使用。

其他任何链上的 CAKE 都等同于 BNB 智能链上的 CAKE。它始终可以在这些链之间以 1:1 的比例跨链转移，且不收取任何 CAKE 费用。

**请注意，CAKE 只有一种。** 不同链上不存在不同版本的 CAKE。所有区块链上 CAKE 的总供应量上限为 4 亿，正如此[投票提案](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5)所述。

***

## 什么是 PancakeSwap 跨链桥？

PancakeSwap 跨链桥是一款便捷的应用内工具，让你可以直接通过 PancakeSwap 界面在不同区块链之间转移资产。你无需访问外部跨链桥网站，即可在 BNB 链、Ethereum、Base、Arbitrum 等链之间跨链转移受支持的代币——所有操作集于一处。

PancakeSwap 跨链桥由受信任的第三方提供商提供支持，并作为**聚合器**运作——根据价格、速度和可靠性选择最佳路由。

要了解如何跨链转移 CAKE，请查看以下章节中的教程和常见问题解答。

***

## 🔗 运作方式

### 通过聚合器跨链

PancakeSwap 跨链桥充当受信任的第三方跨链桥协议之上的智能层。当你发起跨链转账时，PancakeSwap 会：

* 检查多个集成的跨链桥以获得最优路由
* 将你的交易发送至所选的提供商

跨链是非托管的——你的资产不会进入 PancakeSwap 的托管。转账由跨链桥提供商直接处理。

### 受支持的跨链桥提供商

我们目前集成了：

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> 注意：每个提供商都有不同的跨链机制、受支持的链、费用和限额。

***

### 受支持的链和代币

#### 当前受支持的链

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos（V1 网站）

#### 可用于跨链的代币

可用代币因链和路由而异。常见的受支持代币包括（但不限于）：

* CAKE
* USDT
* USDC
* ETH

***

#### 限制与排除项

由于跨链桥的限制或流动性约束，某些代币可能不受支持。为了提供最佳用户体验，这些代币已被过滤掉。例如：

**对于 cBridge：**

* Wrapped BNB（BNB Chain）
* USDT（Arbitrum）
* USDC.e（Arbitrum）

**对于 deBridge：**

* cUSDCv3（Ethereum）
* cUSDCv3（Polygon）
* cUSDCv3（Arbitrum）

_以上为示例。每条链上实际可用的代币会直接显示在跨链桥 UI 中。_

***

### 💸 费用与成本

#### 跨链桥费用

* 由底层跨链桥提供商收取
* 通常每笔转账包含一笔小额费用
* 在你确认跨链之前会清楚显示

***

#### Gas 成本

* 你需在**源链**上支付 gas 费以发起交易
* 某些提供商可能还要求在**目标链**上支付 gas
* **提示：** 始终在跨链桥的两端都保留原生代币（例如 ETH、BNB）

***

#### 最低金额与限制

某些跨链路由会强制执行：

* **最低/最高跨链金额**（例如最低 10 USDC）
* **受支持的代币精度或格式**（例如仅限 ERC-20 代币）

UI 会自动检测并显示无效的转账。

***

### ⏳ 交易时间与追踪

#### 跨链需要多长时间？

跨链转账通常会在几**分钟**内完成，具体取决于：

* 源链和目标链
* 网络拥堵情况
* 跨链桥提供商的效率

#### 追踪你的转账

提交后，你可以通过提供商特定的浏览器查看交易状态：

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

如果某笔交易长时间卡住，请检查相关浏览器，或通过[社交渠道](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts)联系我们的管理员寻求[帮助](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help)。

***

### 🧠 跨链前的提示

* **在两条链上都保留 gas 代币**（例如 ETH + BNB）
* 如果这是你第一次跨链，请**从小额开始**
* 避免在链上活动高峰期跨链（可能导致更高的 gas 费）
* 在两条链上确认代币兼容性
* 始终仔细核对源网络和目标网络

***

### 附加：CAKE 全链同质化代币（OFT）地址

1. **BNB Chain**
   * `cake`：`0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82`（[链接](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82)）
   * `cakeOFTProxy`：`0xb274202daBA6AE180c665B4fbE59857b7c3a8091`（[链接](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code)）
2. **Ethereum**
   * `cakeOFT`：`0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898`（[链接](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898)）
3. **Aptos**
   * `cakeOFT`：`0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6`（[链接](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet)）
4. **Arbitrum**
   * `cakeOFT`：`0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c`（[链接](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c)）
5. **zkSync**
   * `cakeOFT`：`0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD`（[链接](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract)）
6. **Linea**
   * `cakeOFT`：`0x0D1E753a25eBda689453309112904807625bEFBe`（[链接](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe)）
7. **Base**
   * `cakeOFT`：`0x3055913c90Fcc1A6CE9a358911721eEb942013A1`（[链接](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code)）
8. **opBNB**
   * `cakeOFT`：`0x2779106e4F4A8A28d77A24c18283651a2AE22D1C`（[链接](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1)）
