# 如何通过智能路由进行交易？

## 通过智能路由进行交易&#x20;

智能路由在兑换页面上默认是开启的。它类似于使用现有的 PancakeSwap AMM。&#x20;

在开始之前，它需要一个与 BNB 链兼容的钱包和 BNB 代币作为 gas 费。请查看我们的[钱包指南](../../../get-started/wallet-guide.md)了解更多细节。

1. 导航到[兑换页面](https://pancakeswap.finance/swap#/swaphttps://pancakeswap.finance/swap#/swap)。&#x20;
2. 选择您想交易的代币对。在发布此功能时，由于滑点问题，通过智能路由的交易输入代币框内只接受输入整数。
3. 输入你想交易的代币的数量。勾选 "**使用 StableSwap 可以获得更划算的费用** "方框。

<div align="left">

<figure><img src="../../../.gitbook/assets/Smart Router 1.png" alt=""><figcaption></figcaption></figure>

</div>

4. 在底部一行，点击路由字段右侧的放大镜图标，以查看检查新的交易路径。好了一切就绪！之后的兑换流程和平时的兑换一样。如果你是第一次使用兑换功能，请查看这里的[指南](../ru-he-jin-hang-jiao-yi.md)。

{% hint style="info" %}
请注意，当您第一次使用智能路由通过 StableSwap 兑换时将需要重新对代币进行批准（授权）。如上图中所示，将需要重新批准 CAKE。
{% endhint %}

### 关闭智能路由

禁用智能路由后，所有交易都将通过 V2 交易路径进行，不会通过 StableSwap 进行交易。

1. 点击兑换页面右上方的**齿轮图标**打开设置界面。&#x20;
2. 在弹出的窗口中对应字段 (Smart Router) ，点击右边按钮以**禁用智能路由**。

<div align="left">

<figure><img src="../../../.gitbook/assets/Smart Router 3 EN original.png" alt=""><figcaption></figcaption></figure>

</div>

3. 关闭设置页面。
