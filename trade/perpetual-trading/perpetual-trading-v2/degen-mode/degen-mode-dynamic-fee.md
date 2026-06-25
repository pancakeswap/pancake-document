# Degen Mode 动态费用

PancakeSwap 永续合约 Degen Mode 使用动态费用模型。此费用旨在根据 PnL 收取费用，并保护用户免受损失。\
**它是如何运作的？**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

其中：

* Pnl 是仓位的盈亏
* shareRate 是分成率，即以费用形式支付的名义价值的百分比（默认为 15%）
* Notional 是用于开仓的资金金额
* closeMinRate 是最低平仓费用率，即你平仓所需支付的最低金额（默认为 0.03%）

\
**示例：**

如果你有一个盈利为 $100、分成率为 15%、名义价值为 $600 的仓位，那么平仓费用率为：

平仓费用率 = Max(100 \* 15% / 600, 0.03%) = 0.03%

在这种情况下，平仓费用率为 0.03%，即最低平仓费用率。<br>

注意：

执行费用仅在开仓时收取。它设定为 0.3 USD（BNB Chain）/ 0.2 USD（Arbitrum）/ 0.01 USD（opBNB）/ 0.3 USD（Base），与交易经典永续合约交易对时收取的费用相似。没有开仓费用。

在清算事件中，90% 的流动性损失率包含平仓费用。
