# CLAMM Options

{% hint style="danger" %}
\[已归档] 期权 – 截至 2025 年 3 月 11 日\
如果你仍有流动性需要提取，请立即前往 https://www.stryke.xyz/en/trade 操作。
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options 为链上期权交易带来了一种全新的方式，为流动性提供者提供了一个平台，让他们可以充分利用 PancakeSwap 上的 v3 流动性。这使他们能够同时将流动性用于 v3 流动性资金池和出售期权，从而赚取标准的 AMM 交易手续费、期权权利金以及额外奖励，而交易者则可以利用这些流动性购买各类代币的美式期权。

CLAMM 期权协议由 Stryke（前身为 Dopex）团队打造，为期权交易者（买方）和 PancakeSwap v3 资金池引入了高效的双重流动性供给系统。

以下是 CLAMM Options 运作方式的结构化说明：

1. 向 CLAMM 期权添加流动性的 LP，会同时在其选定的价格区间内为指定的 PancakeSwap v3 资金池提供流动性。
2. 当期权交易者（买方）建立仓位时，会从 v3 资金池中提取流动性以支持期权出售。相应的 LP 因此成为期权卖方并获得权利金。
3. 期权买方未使用的流动性仍留在 PancakeSwap v3 资金池中，有可能赚取交易手续费。
4. 出售期权与在 v3 资金池中提供流动性的收益结构会产生相同的无常损失，确保用户所面临的风险不会高于以传统方式向 v3 资金池添加流动性。
5. LP 面临一定风险，因为期权买入需求较低时，流动性可能处于闲置状态。此外，由于流动性是在非活跃区间内添加到资金池的，可能无法赚取任何手续费。

PancakeSwap 的美式 CLAMM 期权将首先在 Arbitrum 链上推出，提供灵活的到期时长选择，范围从 1 小时到 24 小时不等。

| **市场**    | ARB/USDC、ETH/USDC 和 wBTC/USDC |
| --------- | ----------------------------- |
| **期权类型**  | 看涨与看跌                         |
| **行权价格**  | 基于 v3 资金池 tick                |
| **到期时长**  | 1H、2H、6H、12H 和 24H            |

**行权条件：** 用户可以在仓位关闭前行权，以避免实值期权到期后作废。你也可以启用自动行权，在到期时自动实现收益，无需再进行其他操作。

### 分步指南

以下是如何使用 PancakeSwap CLAMM Options 的分步指南。

**交易者：** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**LP：** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
