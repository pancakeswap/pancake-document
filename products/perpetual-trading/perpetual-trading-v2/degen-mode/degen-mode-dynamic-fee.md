# Degen Mode Dynamic Fee

PancakeSwap Perpetuals Degen Mode uses a dynamic fee model. This fee is designed to charge fees by PnL and protect users from losses.\
**How does it work?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

where:

* Pnl is the profit or loss on the position
* shareRate is the share rate, which is the percentage of the notional that is paid in fees (15% as default)
* Notional is the amount of money that is used to open the position
* closeMinRate is the minimum closing fee rate, which is the lowest amount that you can pay to close a position (0.03% as default)

\
**Example:**

If you have a position with a profit of $100, a share rate of 15%, and a notional of $600, then the closing fee rate would be:

Closing fee rate = Max(100 \* 15% / 600, 0.03%) = 0.03%

In this case, the closing fee rate would be 0.03%, the minimum closing fee rate.\


Note:

The execution fee will only be charged when a position is opened. It is set at 0.3 USD (BNB Chain)/ 0.2 USD (Arbitrum)/ 0.01 USD (opBNB)/ 0.3 USD (Base), similar to what is being charged when trading classic perpetual trading pairs. There is no opening position fee.

In the event of liquidation, the 90% liquid lost rate includes close fee.
