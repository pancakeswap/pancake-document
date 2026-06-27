# CLAMM 期权

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28392%29.png" alt=""><figcaption></figcaption></figure>

CLAMM 期权提供了一种新颖的链上期权的交易方法，为流动性提供者提供了一个利用 PancakeSwap 上 v3 流动性的平台。这使他们既能利用 v3 流动性池的流动性，又能出售期权，这样既可以赚取经典的 AMM 交易费、还可以赚取期权溢价和额外奖励，而交易者则可以利用这种流动性购买各种代币的美式期权。

CLAMM 期权协议由 Stryke（前 Dopex）团队精心设计，为期权交易者（买方）和 PancakeSwap v3 池引入了高效的双重流动性供给系统。&#x20;

以下是 CLAMM 期权如何运作的结构性细分：&#x20;

1. 为 CLAMM 期权增加流动性的 LP 同时在其选择的价格范围内向指定的 PancakeSwap v3 池提供流动性。&#x20;
2. 当期权交易者（买方）开设头寸时，流动性将从 v3 池中提取，以促进期权卖出。相应的 LP 因此成为期权卖方并收取期权费。&#x20;
3. 期权买方未使用的流动性则留在 PancakeSwap v3 池中，有可能赚取交易费。&#x20;
4. 卖出期权和在 v3 池中提供流动性的回报反映的是同样的无常损失，确保用户不会面临比向 v3 池添加流动性的传统方法更高的风险。&#x20;
5. LPs 会面临一些风险，因为流动性可能会由于期权购买需求降低而未被调用。此外，由于流动性是在不活跃的范围内加入池中的，因此可能无法赚取任何手续费用。

PancakeSwap 的美式 CLAMM 期权将在 Arbitrum 链首次亮相，提供从 1 小时到 24 小时不等的不同到期时间的期权，具有灵活性。

| **市场**   | ARB/USDC, ETH/USDC,以及 wBTC/USDC |
| -------- | ------------------------------- |
| **类型**   | 看涨与看跌                           |
| **触发价**  | 基于 v3 流动性池价格刻度                  |
| **到期时间** | 1 小时、2 小时、6 小时、12 小时和 24 小时     |

**执行条件**： 用户可以在平仓前行使头寸，以避免价内期权到期一文不值。可以启用自动行权功能，在到期时自动实现盈利，跳过进一步的操作。

### 分步指南&#x20;

以下是如何使用 PancakeSwap CLAMM 期权的分步指南。&#x20;

**交易者:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
&#x20;**LPs:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
