# 获取 Aptos 代币

<figure><img src="../.gitbook/assets/how-to-get-bep20-tokens-header.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
本指南涵盖了适合主流代币使用的 Aptos 跨链服务。要在 Aptos 链和 BNB 智能链之间和来回跨链 CAKE，请使用 [PancakeSwap Aptos 跨链桥](https://bridge.pancakeswap.finance/stargate)。
{% endhint %}

Aptos 链的原生代币是 **Aptos Coin (APT)**。&#x20;

在 Aptos Chain 上的大部分操作，您都需要支付矿工费，以 APT 支付。

您还要准备一些在 Aptos 链上用以进行交易或质押的代币。有不少方法可以将您的资产带到 Aptos 链上，以下是我们推荐的方法：

{% tabs %}
{% tab title="🌉 Aptos 跨链桥" %}
[Aptos 跨链桥](https://theaptosbridge.com/bridge) - LayerZero

* Aptos 跨链桥您将主流代币和稳定币跨链到 Aptos&#x20;
* 支持 “发送链支付 gas” - 若 Aptos 链上钱包里无 Aptos 代币 (APT)，将自动由发送链的 gas 中转换少量的 APT ，帮您开始在 Aptos 链上的旅程
* **⚠️ 注意：您的资产将在跨链时被自动封装（wrapped）。（标记为 “LayerZero”）** \
  在您将代币跨链之前，请务必检查代币列表（token list）内对应链上的代币合约，确认您跨过去后目标代币封装版本（wrpped version）为您想交易的版本。
{% endtab %}

{% tab title="🌉cBridge" %}
[cBridge ](https://cbridge.celer.network/)

* cBridge 协助您将主流代币和稳定币跨链到 Aptos&#x20;
* **⚠️ 注意：现在资产在跨链时将被自动封装（wrapped）。（标记为 “Celer”）** \
  在跨链您的代币之前，请务必仔细查看代币列表内目标链上的对应代币合约，以确认您跨链后取得的代币，为您期望取得的代币的封装版本（wrpped version）。

**📖** [**cBridge 教程由 Celer 提供**](https://cbridge-docs.celer.network/tutorial/cross-chain-transfer)
{% endtab %}

{% tab title="🌉Wormhole" %}
[Wormhole - Portal 代币跨链桥 ](https://www.portalbridge.com/#/transfer)

* Portal 代币跨链桥，协助您将主流代币和稳定币跨链到 Aptos 上。&#x20;
* **⚠️ 注意：您的资产将在跨链时被自动封装（wrapped）。（标记为 “Wormhole”）** \
  在您将代币跨链之前，请务必检查代币列表（token list）内目标链上的对应代币合约，确认您跨链后取得的代币，为您期望用以交易的代币的封装版本（wrpped version）。

📖[本教程由 Wormhole 提供](https://docs.wormhole.com/wormhole/video-tutorial-how-to-use-portal)
{% endtab %}

{% tab title="🥞CAKE 跨链" %}
想要在 Aptos 和 BNB 智能链之间跨链 CAKE 代币，请使用[ PancakeSwap Aptos 跨链桥](https://bridge.pancakeswap.finance/aptos)。

请查看[此指南](<cake-kua-lian-zhi-nan (1).md>)以了解如何使用它。
{% endtab %}

{% tab title="💰币安网" %}
[币安网 ](https://www.binance.com/en/)

* 您可以通过您的币安账户在 Aptos 链上提取 Aptos Coin (APT)。&#x20;
* **⚠️ 目前仅支援 Aptos Coin (APT)。如您期望跨链其他资产，请查看前述的其他跨链桥提供的跨链方案。**
* **注意：您需要有一个帐户才能这样操作。**&#x20;

📖 [这是币安为帮助您而制作的快速指南](https://www.binance.com/zh-CN/support/faq/85a1c394ac1d489fb0bfac0ef2fceafd)。
{% endtab %}
{% endtabs %}
