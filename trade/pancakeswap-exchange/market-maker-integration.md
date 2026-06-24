---
hidden: true
---

# Market Maker Integration

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Ethereum 上的 Market Maker 集成

PancakeSwap 已与 Ethereum 和 Binance Smart Chain 上的 Market Maker 集成，以帮助交易者以更低的成本执行交易。

除了 AMM 之外，PancakeSwap 上的交易现在可以路由到指定的白名单 Market Maker，前提是它们提供的交易执行价格优于 AMM 当前的价格。此路由由 [Smart Router](smart-router-v2/) 自动完成，因此只有当 Market Maker 积极报出更优价格时，交易才会被路由到它们。在 AMM 更具竞争力的地方，交易者将被路由到 AMM 进行执行。

Market Maker 在 PancakeSwap 上有 2 种运作情形。

**情形 1：现有的 AMM 流动性池**

如果 PancakeSwap 在 AMM 中已经拥有某个代币（例如 WETH/USDC）的流动性，PancakeSwap 将就同一笔交易向 Market Maker 询价。然后，PancakeSwap 的 Smart Router 将根据在任意给定时刻哪个流动性来源提供最优价格，把交易请求路由到 AMM 或 Market Maker。

**情形 2：没有现有的 AMM 流动性池**

在这种情形下，Smart Router 将自动把交易路由到 Market Maker。但是，这并不妨碍项目方随后建立自己的 AMM 流动性池，并与我们合作以维持去中心化的 DEX 流动性。

### 费用

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

对于通过我们路由并由 Market Maker 执行的交易，PancakeSwap 不向交易者收取任何费用。但是，PancakeSwap 会就 Market Maker 执行的交易量从白名单 Market Maker 处收取 **0.05%** 的**交易手续费**。如果执行的交易是在稳定币对之间，PancakeSwap 收取较低的 **0.01%** **交易手续费**。请参阅下方的费用分配：<br>

<table><thead><tr><th width="178">交易</th><th width="138">交易手续费</th><th width="182">PCS 从 MM 收取的费用</th><th width="147">Cake 销毁</th><th align="center">Pancakeswap 国库</th></tr></thead><tbody><tr><td>从其他网络桥接的代币</td><td>N/A</td><td>0.25%</td><td>0.083%</td><td align="center">0.167%</td></tr><tr><td>Ethereum 上的非稳定币（例如 ETH/USDC）</td><td>N/A</td><td>0.05%</td><td>0.017%</td><td align="center">0.033%</td></tr><tr><td>BSC 上的非稳定币（例如 BNB/USDT）</td><td>N/A</td><td>0.05%</td><td>0.017% </td><td align="center">0.033%</td></tr><tr><td>Ethereum 上稳定币兑稳定币</td><td>N/A</td><td>0.01%</td><td>0.003%</td><td align="center">0.007%</td></tr></tbody></table>

#### 当前支持的资产

以下资产目前受支持，并可能根据 Market Maker 的情况增加/减少：

**在 Ethereum 上**

* **主流币：** WETH, WBTC
* **稳定币：** USDT, USDC, DAI, BUSD
* **其他热门 ERC-20 资产：** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**在 Binance Smart Chain 上：**

* **主流币：** BNB, ETH, BTCB
* 非原生 BNB 代币：ARB, OP

请注意，与 AMM 不同，Market Maker 无法在任意金额下进行交易，它们愿意执行的金额将取决于其自身的流动性。有时非常大的订单无法被完全成交并不罕见。我们建议用户仔细审查报价，以确保每笔交易都符合其需求的价格和数量。

**Market Maker 停机时间**

Market Maker 不一定全天候报价。在某些情况下（例如重大经济事件、系统升级），Market Maker 可能会暂时无法提供报价。请注意，在这些时段，这些代币将根本无法交易，我们建议用户等待一段时间，直到 Market Maker 重新上线。

#### 常见问题解答

**问：** Market Maker 会在 Aptos 上集成吗？

**答：** 有可能，我们目前仅在 Ethereum 和 Binance Smart Chain 上推出 Market Maker 集成，以提升流动性、带来更好的用户体验。我们将继续关注其他链。

**问：** 如果 PancakeSwap 不向用户收取费用，它将如何创造收入？

**答：** PancakeSwap 不会向用户收取任何费用，但 PancakeSwap 将从 Market Maker 处获得一小笔佣金，并用其资助 CAKE 回购和销毁。

**问：** 流动性提供者会继续赚取 LP 费用吗？

**答：** 是的，流动性提供者将继续赚取 0.17% 的交易手续费奖励（LP 费用）以及 CAKE 农场的收益。

**问：** Market Maker 会向 AMM 添加流动性吗？这会导致 APR 下降吗？

**答：** Market Maker 维护自己独立的流动性，因此不会从 AMM 上的交易中赚取任何 APR。只有 LP 才能从向 AMM 池提供流动性中赚取费用和 APR。

**问：** 我正在 Ethereum PancakeSwap 上提供流动性。我需要做任何事情吗？

**答：** 不需要，您无需做任何事情。您将继续为通过 AMM 执行的交易赚取 LP 费用，并继续获得 CAKE 收益。

**问：** 如何成为 Market Maker？

**答：** 我们以个案方式筛选并与 Market Maker 合作。如果您有兴趣与我们合作，请直接或通过我们的管理员与我们联系。
