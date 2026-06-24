# 手续费和路由

<figure><img src="../../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

在 Exchange V3 中，默认情况下，PancakeSwap Smart Router 将利用来自 V3、V2、StableSwap（BNB Chain）以及 AMM 和 Market Maker（BNB Chain 和 Ethereum）的流动性来执行交易，并为交易者找到最优价格。

但是，用户始终可以通过选择路由应利用哪些流动性来源，以及启用或禁用多跳（multihops）和拆分路由（split routing），来自定义自己的交易。

### **查看当前应用的费率和费用金额**

![](<../../.gitbook/assets/image (182).png>)

要查看您当前的兑换将收取多少交易费用，请查看兑换详情部分中的 “Fee” 部分。

![](<../../.gitbook/assets/image (296).png>)

要查看您的交易当前路由所经过的池类型和费率档位，请查看 “Route” 部分。

![](<../../.gitbook/assets/image (265).png>)

要了解更多详情，请点击放大镜图标以调出完整的交易路由显示。



### **自定义流动性来源**

![](<../../.gitbook/assets/image (289).png>)

在 “Customize Routing” 界面的顶部，您可以选择路由在为您的交易进行路由时应使用哪些流动性来源。要调出此界面，您可以：

* 点击交易路由显示底部的 “Customize Routing”。
* 点击兑换界面中的齿轮图标，然后点击底部的 “Customize Routing”。

默认情况下，所有流动性来源均已启用，Smart Router 将充分利用 PancakeSwap 内所有可用的流动性。

请注意，路由不会在 AMM 流动性池和 MM Market Maker 之间进行交易路由。当您的交易由 MM Market Maker 执行时，它不会经过任何 AMM 流动性池。

![](<../../.gitbook/assets/image (199).png>)

您可以点击右上角的 “Reset” 按钮将配置重置为默认值。



### **自定义路由偏好**

![](<../../.gitbook/assets/image (129).png>)

在 “Customize Routing” 界面的底部，您可以通过启用或禁用多跳和拆分路由来自定义您的路由偏好。

多跳允许代币在多个流动性池之间通过多次跳转进行兑换，以达成最优交易。关闭它将把交易限制为直接兑换，这可能导致更高的滑点甚至资金损失。

拆分路由使代币兑换能够被拆分为多个路由，以达成最优交易。关闭它将限制交易只能通过单一路由执行，这可能导致效率低下或更高的滑点。

{% hint style="warning" %}
当您的交易由于自定义的交易配置而无法执行时，将出现一条警告，您可以点击 “Check your settings” 快速调出 “Customize Routing” 界面。或者选择 “Reset to default” 快速将您的配置重置为默认值。
{% endhint %}
