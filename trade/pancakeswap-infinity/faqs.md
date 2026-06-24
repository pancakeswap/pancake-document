# 常见问题解答

1. **Infinity 与 PancakeSwap V3 有何不同？**\
   Infinity 新增了诸如可编程 hooks、更多[资金池类型](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types)（如 LBAMM 和 CLAMM）以及 gas 节省等新功能。不过，除了 LBAMM 资金池在流动性提供方面存在一些细微差异外，核心的兑换和流动性提供机制与 v3 大体相似。\
   <br>
2.  **LBAMM 和 CLAMM 有什么区别？**

    1. **LBAMM（Liquidity Book AMM）：** 使用流动性 bin，每个 bin 在不同价格水平上持有流动性。LP 可以跨多个 bin 提供流动性，兑换在一个 bin 内的单一价格水平上执行。
    2. **CLAMM（Concentrated Liquidity AMM）：** 允许用户像在 PancakeSwap V3 中那样在自定义价格区间内提供流动性。

    \
    如需更多详情，请访问[此处](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types)。\
    <br>
3. **我该如何领取农场奖励，为什么每 8 小时才能领取一次？**\
   你可以通过点击 "Harvest"（收获）按钮来领取流动性头寸的农场奖励。Infinity 支持跨所有活跃农场头寸进行批量领取，从而节省 gas 成本。为了优化 gas 成本和计算，奖励每 8 小时计算和处理一次。\
   \
   有关耕作机制的更多详情，请访问[此处](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms)。\
   <br>
4.  **Infinity 的 hooks 是如何工作的？**\
    Hooks 是可定制的智能合约扩展，为资金池添加额外功能。它们可以在兑换或流动性事件期间触发额外操作——例如，调整费用、提供折扣或应用其他逻辑。<br>

    Hooks 在资金池创建时被附加。在大多数情况下，**用户无需采取任何额外步骤**。只要你像往常一样进行兑换或提供流动性，如果该资金池适用 hook 的逻辑，你便会自动从中受益。<br>

    👉 **你可以在每个资金池页面的 "Pool Features"（资金池功能）部分查看活跃的 hooks 及其详情。**\
    <br>
5.  **为什么我从 LBAMM 资金池提取头寸时没有收到任何费用？**\
    在 LBAMM（Liquidity Book AMM）资金池中，费用会自动添加到你的活跃流动性 bin 中。这意味着：

    1. 当你提取头寸时，你赚取的费用已包含在你提取的代币总量之中。
    2. 与传统 AMM 不同，这里没有单独的 "待领取费用" 余额——它全部捆绑在你头寸的价值之中。

    \
    如果你在提取时没有注意到额外的代币，可能是因为：

    1. 在你持有头寸期间，由于价格变动，你的头寸所产生的无常损失可能超过了所收取的费用。
    2. 你的流动性不在发生交易的活跃 bin 中。
