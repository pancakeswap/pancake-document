---
description: 一键添加流动性
---

# Zap

### **什么是 Zap?**

Zap 是一项可以让您轻松添加流动性的功能。使用 Zap，您只需使用流动性池中的一种代币即可提供 V3 流动性。只需设置价格范围，选择要提供的金额，然后执行即可。您的代币将自动平衡以形成流动性仓位，同时以最有效的方式进行交易，并将价格影响和滑点降至最低。

### **如何使用？**

使用之前请注意，目前 Zap 只支持

* 某些流动性对（即将支持更多币对）

{% hint style="info" %}
USDT-WBNB 0.05%, USDT-USDC 0.05%, USDT-USDC 0.01%, ETH-BTCB 0.25%, USDT-BTCB 0.05%, Cake-WBNB 0.25%, BTCB-WBNB 0.05%, ETH-BTCB 0.05%, Cake-USDT 0.25%, USDT-WBNB 0.01%, ETH-WBNB 0.05%, USDT-BNX 0.05%, USDT-BUSD 0.01%, ETH-WBNB 0.25%, BTCB-WBNB 0.25%, SOL-WBNB 0.25%, ETH-USDT 0.05%, TUSD-USDT 0.01%, USDC-WBNB 0.01%, XRP-WBNB 0.25%输入单
{% endhint %}

* 输入单一代币
* BNB 链

**开始**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="563"><figcaption></figcaption></figure>

要使用 Zap，只需进入“添加 V3 流动性”页面，选择您要提供流动性的交易对、手续费等级和价格范围。

然后选择要提供流动性的代币数量。&#x20;

当一个或多个代币余额不足时，将自动出现 Zap 选项。&#x20;

点击超链接，弹出 V3 Zap 模式。

**启动 Zap**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt=""><figcaption></figcaption></figure>

在新的“Zap in”弹窗中，您会看到以下字段：

* 您正在 Zap 的交易对（即提供流动性的交易对）。
* 存款代币及存款金额。您可以点击箭头在两个池中的代币之间切换。
* 新仓位的价格范围。您也可以点击箭头在不同的价格显示之间切换。
* Zap 功能将如何处理您的存款代币的详细说明。
* 统计摘要包括：
  * 新流动性仓位的预计价值（以 USD 计算）。
  * 新流动性仓位中的预计代币数量。
  * Zap 后剩余资金的预估值（以 USD 计）。在大多数情况下，该值应为 0。如果流动性池或代币流动性很小，此值可能会增加。
  * Zap  时代币兑换和重新平衡时的价格影响。
  * 添加流动性和建立仓位时的价格影响。
  * Zap 手续费。根据流动性对的不同，手续费率可能有所不同。

{% hint style="info" %}
您可能会注意到，“添加 V3 流动性 ”中的设置会自动转到 Zap 模式。包括存款金额和价格范围设置。
{% endhint %}

**开始 Zap**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="375"><figcaption></figcaption></figure>

最后，点击“Approve”（批准）并在钱包弹窗中确认代币授权。&#x20;

接着，点击“Preview”（预览）以显示最终确认弹窗。继续操作前，请仔细查看最终确认弹窗中显示的所有统计数据和预估，特别是价格影响和最大滑点。&#x20;

最后，点击“Add Liquidity”（添加流动性）并在钱包弹窗中确认。&#x20;

交易确认后，您将在“我的仓位”页面看到您新的头寸。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="375"><figcaption></figcaption></figure>

**更多设置**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="375"><figcaption></figcaption></figure>

如果您想进一步自定义您的 Zap 体验，只需点击右上角的齿轮图标。在设置中，您可以配置：

* Zapping 时的最大滑点。
* 交易截止时间。
* 是否使用 KyberSwap 的聚合流动性进行代币重新平衡。如果您只想在 PancakeSwap 池中交易，可以将其关闭。
* “Degen 模式”可以用于执行超高滑点的 Zap。不建议用于正常情况下，请自行承担风险。

{% hint style="warning" %}
请注意，这里的滑点和截止设置独立于流动性页面和兑换页面的设置
{% endhint %}
