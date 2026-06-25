---
hidden: true
---

# Dumb Mode

### 概述

PancakeSwap 永续合约上的 [**Dumb Mode**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) 提供了简化的交易体验，非常适合那些偏好针对标的资产价值逐分钟波动进行交易的交易者。Dumb Mode 通过减少噪音来简化交易，让用户能够轻松进出短期仓位。

### 工作原理

用户可以从 5 分钟、15 分钟、30 分钟和 1 小时的到期窗口中进行选择，每个窗口具有不同的投资回报率。用户可以选择做多或做空标的资产。

在到期期结束时，如果标的资产处于盈利仓位（做多时价格高于开仓价，做空时价格低于开仓价），用户将获得盈利。

每个到期期都有不同的投资回报率（ROI）。到期期越长，ROI 越高。百分比和费用如下：<br>

| 到期期 | 盈利 ROI（扣除费用后）\* | 亏损 ROI | 费用（盈利时） |
| ----------------- | --------------------------- | ---------- | ----------------- |
| 5 分钟         | 50%                         | -100%      | 抵押品的 6%  |
| 15 分钟        | 55%                         | -100%      | 抵押品的 6%  |
| 30 分钟        | 70%                         | -100%      | 抵押品的 6%  |
| 1 小时            | 83%                         | -100%      | 抵押品的 6%  |

\*盈利 ROI 可能会根据市场状况偶尔调整。请查看本页面以获取任何更新

例如，在以下情境中：

* 选择的仓位：做多
* 投入的抵押品：100 USDT
* 到期期：60 秒
* 开仓时 BTCUSD 价格：$50,000
* 60 秒后 BTCUSD 价格：$50,001

用户将盈利 **100USDT \* 75%= 75USDT**

有关如何开立 Dumb Mode 仓位的更多信息，请点击[此处](dumb-mode-guide.md)。

### 市场和保证金资产

Dumb Mode 支持在 **BNB Chain** 上对以下市场和保证金资产进行交易：

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>市场</td><td>保证金资产</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

Dumb Mode 支持在 **Arbitrum、opBNB 和 Base 链** 上对以下市场和保证金资产进行交易：

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>市场</td><td>保证金资产</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

对更多资产/链的支持正在开发中。

### 费用

在交易盈利的情况下，将收取本金或抵押品的 **6%** 作为费用。此费用已在 ROI 之前计算。

<br>
