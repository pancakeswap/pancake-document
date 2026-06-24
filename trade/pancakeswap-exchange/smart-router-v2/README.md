---
hidden: true
---

# Smart Router (V2)

<figure><img src="../../../.gitbook/assets/Smart Router.png" alt=""><figcaption></figcaption></figure>

PancakeSwap Smart Router 是一种路由算法，它连接 AMM 和 StableSwap（BNB Chain）以及 AMM 和 Market Maker（Ethereum），以提供更好的流动性和定价。它使用一种智能订单路由算法，跨多个池执行交易，为交易者找到最优价格。有关 StableSwap 的更多信息，[请点击此处](/broken/pages/nNPogTZMxocdyFIBYbkE)；有关 Market Maker 集成，[请点击此处](../market-maker-integration.md)。

厨房将逐步推出 StableSwap 交易对，以进一步测试和改进该产品。

## 我为什么应该在 AMM 兑换中使用 Smart Router？&#x20;

* 以相同的交易步骤更高效地兑换您的稳定币或其他资产价格相近的交易对。
* 与 Market Maker 进行交易，它们在交易上可能提供比普通 PancakeSwap AMM 更优的执行。
* 借助 StableSwap 功能，交易滑点低于普通 AMM。
* 与普通 AMM 相比，StableSwap 的交易手续费更低。

## 仍在烹饪中&#x20;

* 更好的输出 UI。
* 用于更高效交易的拆分路由。例如，根据交易规模和流动性，路由将交易对的 50% 发送到不同的路由以节省费用。&#x20;
