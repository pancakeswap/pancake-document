# Degen 模式动态费用

**它是如何运作的？**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

**其中：**

* Pnl 是仓位的盈利或亏损&#x20;
* shareRate 是份额比率，即支付的费用占名义金额的百分比（默认为 15%）&#x20;
*

**举例说明：**

&#x20;如果您的合约仓位盈利 100 美元，份额比率为 15%，名义金额为 600 美元，那么平仓费率为：&#x20;

平仓费率 = Max(100 \* 15% / 600, 0.03%) = 0.03&#x20;

注意：&#x20;

