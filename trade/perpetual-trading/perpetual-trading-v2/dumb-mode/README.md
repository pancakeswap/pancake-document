---
hidden: true
---

# Dumb Mode

### Overview

[**Dumb Mode**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) on PancakeSwap Perpetuals offers a simplified trading experience, ideal for traders who prefer to trade on the minute-by-minute fluctuations of an underlying asset’s value. Dumb Mode simplifies trading by reducing the noise, allowing users to enter and exit short-term positions easily.

### How It Works

Users are given a selection of 5-minute, 15-minute, 30-minute and 1-hour expiration windows with different return-on-investment ratios. Users can choose to long or short an underlying asset.

At the end of the expiration period, if the underlying asset is in a winning position (price greater than open price for long, price lower than open price for short), users will stand to profit.

Each expiration period has a different return-on-investment (ROI). The longer the expiration period, the higher the ROI. Percentages and fees are as follows:<br>

| Expiration Period | Winning ROI (Net of fees)\* | Losing ROI | Fees (on Winning) |
| ----------------- | --------------------------- | ---------- | ----------------- |
| 5 minutes         | 50%                         | -100%      | 6% on collateral  |
| 15 minutes        | 55%                         | -100%      | 6% on collateral  |
| 30 minutes        | 70%                         | -100%      | 6% on collateral  |
| 1 hour            | 83%                         | -100%      | 6% on collateral  |

\*Winning ROI may be adjusted occasionally depending on market conditions. Please check this page for any updates

For example, in the following scenario:

* Position Selected: Long
* Collateral Placed: 100 USDT
* Expiration Period: 60 seconds
* BTCUSD price at open: $50,000
* BTCUSD price after 60s: $50,001

User will profit **100USDT \* 75%= 75USDT**

For more information on how to open a Dumb Mode position, click [here](dumb-mode-guide.md).

### Markets and Margin Assets

Dumb Mode supports trading in the following markets and margin assets on **BNB Chain**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Market</td><td>Margin Assets</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

Dumb Mode supports trading in the following markets and margin assets on **Arbitrum, opBNB and Base Chains**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Market</td><td>Margin Assets</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

Support for more assets/chains is in development.

### Fees

A fee of **6%** of the principal or collateral is charged in case of a winning trade. This is already calculated before ROI.

<br>
