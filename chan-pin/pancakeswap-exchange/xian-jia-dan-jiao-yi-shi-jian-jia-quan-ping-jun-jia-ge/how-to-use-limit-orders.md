# 如何使用限价单？

## 什么是限价订单 ?

限价订单是一种工具，可让用户以指定价格或更优的价格买入或卖出资产，而不是依赖执行时的市场价格。在限价订单中，虽然价格是有保证的，但被执行的订单却没有保证--只有当价格符合订单条件时，限价订单才会被执行。

## 如何设置限价订单？&#x20;

1. 进入兑换页面，点击 "LIMIT " 选择限价订单选项，或使用此链接： [https://pancakeswap.finance/swap/limit ](https://pancakeswap.finance/swap/limit)
2. 选择要交易的 "支出"和 "接收 "的代币。在本例中，我们分别选择了 USDC 和 ETH，这意味着我们想用 USDC 买入 ETH。

<div align="left">

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

</div>

1. 输入您希望交易的金额。注意，限价部分将显示当前市场价格，然后估算目标代币 (ETH) 的输出金额。&#x20;
2. 设置所需的限价。只有当可用市场价格优于或等于限价时，才会执行交易。目标代币输出金额将相应更新。

在下面的例子中，我们希望在价格为 1,900 美元或更优时买入 ETH。收到的 ETH 金额将等于或大于 0.037 ETH。只有出价等于或优于该金额的订单才有资格成交。该金额考虑了 gas 成本和费用。

{% hint style="info" %}
重要提示： 由于费用从输出代币金额中支付，限价包括天然气和交易费用，因此用户在设置价格时应考虑到这一点。例如，一个很小订单的 gas 费用可能占订单输出的很大比例，可能会导致实际限价与现货市场价格相比不具竞争力。
{% endhint %}

3. 点击 "Place order"。仔细检查订单详情，接受免责声明，然后点击 " Confirm order"。

<div align="left">

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

</div>

4. 交易完成后，您就可以在 "未结订单 "下的订单历史记录部分看到您的订单。

<div align="left">

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

</div>

5. 可随时通过展开订单并单击 "取消订单 "按钮取消未结订单。&#x20;

注意事项：

* 如果可用市场价格低于您设定的限价，您的订单可能无法执行。
* 交易以去中心化协议为基础，利用链外吃单者竞争完成订单。这些吃单者有权要求支付费用，协议会从输出代币中为吃单成功的吃单者扣除费用。&#x20;
* 吃单者在设定费用时可能会考虑到您交易的 gas 费用，这可能会导致费用金额的波动。&#x20;
* 指定限价时，用户会在用户界面上看到如果订单成交，他们将收到的目标代币的最低金额。只有出价等于或高于该金额的吃单者才有资格成交订单。该金额考虑了 gas 成本和交易费用。
