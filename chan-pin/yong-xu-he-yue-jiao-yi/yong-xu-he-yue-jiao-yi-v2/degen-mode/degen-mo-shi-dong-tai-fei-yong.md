# Degen 模式动态费用

PancakeSwap Perpetuals Degen Mode uses a dynamic fee model. This fee is designed to charge fees by PnL and protect users from losses.\
**它是如何运作的？**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

**其中：**

* Pnl 是仓位的盈利或亏损&#x20;
* shareRate 是份额比率，即支付的费用占名义金额的百分比（默认为 15%）&#x20;
* notional 是名义值，指用于开仓的金额
* closeMinRate 是最低平仓费率，即平仓时需支付的最低金额（默认为 0.03%）

**举例说明：**

如果您的合约仓位盈利 100 美元，份额比率为 15%，名义金额为 600 美元，那么平仓费率为：&#x20;

平仓费率 = Max(100 \* 15% / 600, 0.03%) = 0.03&#x20;

在这种情况下，平仓费率为 0.03%，即最低平仓费率。

注意：&#x20;

执行费仅在开仓时收取。执行费设定为 0.3 USD (BNB Chain) / )/ 0.2 USD (Arbitrum) )/ 0.01 USD (opBNB)/ 0.3 USD (Base)，类似于交易经典永续合约代币对时收取的费用。没有开仓位费用。&#x20;

清算时，90% 的资产的流失率包括平仓费。

