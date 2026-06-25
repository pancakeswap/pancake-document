---
description: >-
  我们理解你可能对我们最新的升级有疑问。我们整理了这份全面的常见问题解答，以解答你的所有疑问。让我们开始吧：
---

# PancakeSwap Infinity 常见问题解答

**Q1 PancakeSwap Infinity 将如何让交易者和流动性提供者受益？**

**答：** PancakeSwap Infinity 为交易者和流动性提供者带来了诸多优势：

**1. 简化的操作和 Gas 节省：** 通过 Singleton 和 Flash Accounting 等功能，PancakeSwap Infinity 大幅降低了 gas 费。Singleton 将所有池整合到一个合约中，将部署成本削减 99%。Flash Accounting 通过计算交易的净余额来优化记账流程，最大限度地减少 gas 消耗。

**2. 高级功能带来的直接好处：** hooks 的集成允许实现动态手续费、自定义订单类型和主动流动性管理模块。流动性提供者可以享受减轻的无常损失 (IL)、MEV 保护以及访问各种手续费档位，确保更有利可图和更安全的交易体验。

\
**3. AMM 设计的灵活性：** PancakeSwap Infinity 支持多种池类型，包括 CLAMM 和 LBAMM，允许交易者和 LP 选择不同的池类型。这种包容性的方法还能支持任何未来需要新定价曲线的资产。查看此博客[了解更多](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-15 at 16.16.56.png" alt=""><figcaption></figcaption></figure>

**Q2** PancakeSwap Infinity 将如何让开发者和 defi 协议受益？

**答：** PancakeSwap Infinity 为开发者和 DeFi 协议开启了一个充满可能性的世界。&#x20;

**1. 无尽的定制可能性：** 借助 PancakeSwap Infinity，开发者可以构建 Hooks 来引入自定义功能；从动态手续费到链上限价单和自定义预言机。PancakeSwap Infinity 支持部署新的池类型（CLAMM、LBAMM 以及未来任何其他池类型），提高资本效率和交易灵活性。

**2. 访问强大的流动性和用户群：** 凭借超过 180 万活跃用户和 21 亿美元的流动性，开发者和 DeFi 协议拥有无与伦比的机会来接触庞大而活跃的社区，促进产品开发和采用。

**3. 收入生成机会：** 开发者可以通过 hook 手续费建立稳定的收入来源，允许他们为使用其 hooks 设定费用。通过用手续费将其创新货币化，开发者可以为 PancakeSwap 生态系统的发展和壮大做出贡献。查看此博客[了解更多](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-15 at 09.40.42.png" alt=""><figcaption></figcaption></figure>

**Q3** 与 v3 相比，PancakeSwap Infinity 带来了哪些改进？

**答：** PancakeSwap Infinity 引入了无需重新实现核心协议即可使用自定义功能增强流动性池功能的能力。它还支持随时实现任何定价曲线，并为用户提供大量的 gas 节省。

**Q4** PancakeSwap Infinity 中用户界面或用户体验会有任何变化吗？

**答：** 用户可以通过 PancakeSwap 的兑换页面在 Infinity 上进行兑换，就像往常友好的体验一样。交易者和流动性提供者有多种选择，可以在支持的池类型（包括 CLAMM 和 LBAMM）中添加流动性。

**Q5** 社区如何参与 PancakeSwap Infinity 的测试或提供反馈？

**答：** 如果你是社区成员，欢迎通过我们的社交媒体 [Telegram](https://t.me/PancakeSwapAnn)、[Discord](https://discord.com/channels/897834609272840232/1207724381212770315) 和 [Twitter](https://twitter.com/PancakeSwap) 分享你的反馈。如果你是开发者，请加入我们的开发者 Discord 社区并分享你的想法。

**Q6** 用户在哪里可以找到有关 PancakeSwap Infinity 的更多信息并随时了解其开发进度？

**答：** 访问我们的官方[网站](https://pancakeswap.finance/v4?utm_source=v4announcementblog\&utm_medium=blog\&utm_campaign=v4announcementblog\&utm_id=v4announcementblog)，阅读我们的[白皮书](https://github.com/pancakeswap/pancake-v4-core/blob/main/docs/whitepaper-en.pdf)，并在社交媒体上关注我们以获取最新的更新和动态。如果你是开发者，请加入我们的开发者 Discord 社区。\
\
**Q7** PancakeSwap Infinity 的许可机制是什么？

**答：** PancakeSwap Infinity 致力于开源原则。我们的代码将在开源许可下发布，让开发者能够自由创新。然而，作为我们[联盟计划](https://forum.pancakeswap.finance/t/discussion-on-pancakeswap-affiliates-a-multichain-expansion-strategy/395)的一部分，分叉 PancakeSwap 的 DeFi 协议将受到 Kitchen 的热烈欢迎和正式认可。\
\
**Q8** PancakeSwap Infinity 如何降低 gas 费？

**答：** PancakeSwap Infinity 利用 Singleton 和 Flash accounting 机制显著降低 gas 费。通过将所有池整合到一个合约 (singleton) 中，多池交易得以简化，使其更具成本效益。Flash Accounting 用净余额取代单独的转账，在每笔交易结束时统一计算，从而大幅节省 gas。ERC-6909 进一步降低了频繁用户的 gas，让用户可以将资金保留在协议内并在需要时使用，从而无需在钱包之间进行转账。\
\
**Q9** PancakeSwap Infinity 中的 Hooks 是什么，它们如何促进创新？

**答：** Hooks 是可定制的附加组件，可增强流动性池功能，允许开发者引入自定义功能和手续费管理选项。Hooks 在外部部署，可以在关键的池操作期间执行预定义的逻辑，提供无尽的可能性，包括动态手续费、订单类型、自定义预言机和主动流动性管理策略。查看此博客[了解更多](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks)\
\
**Q10** PancakeSwap Infinity 为开发者带来了哪些机会？

**答：** 开发者可以构建创新解决方案，通过 hook 手续费产生收入，并接触 PancakeSwap 庞大的用户群和深厚的流动性。阅读我们关于开发者为何应在 PancakeSwap 上构建的专门[博客文章](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks)。

**Q11** PancakeSwap Infinity 如何为更广泛的 DeFi 生态系统做出贡献？

**答：** PancakeSwap Infinity 旨在解决当前 AMM 的不足，提升 DEX 体验，并在我们开源方法的支持下发展成为功能最强大的 DeFi 平台。阅读我们的主厨 Chef Mochi 对 [Infinity 的愿景](https://blog.pancakeswap.finance/articles/chef-mochi-s-vision-for-pancake-swap-v4-a-leap-forward-in-de-fi-innovation)了解更多。\
\
**Q12** 我们在哪里可以找到 hook 模板仓库？

**答：** Hooks 模板可以在 [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) 找到，示例 hooks 可以在 [https://github.com/pancakeswap/infinity-hooks](https://github.com/pancakeswap/infinity-hooks) 找到。\
\
**Q13** 你能解释一下 hooks 的生命周期及其示例吗？

**答：** Hooks 可以在 5 个关键操作之前/之后实现，即 initialize、swap、addLiquidity、removeLiquidity、donate。例如，当用户发起兑换时，PoolManager 合约会检查是否存在 beforeSwap hook 回调。如果存在，则执行 hook 合约中 beforeSwap 方法下的逻辑；否则，兑换照常进行。兑换完成后，afterSwap 回调会发生相同的过程。\
\
**Q14：** 我们需要进行地址挖掘以确保 hooks 部署在特定地址吗？\
**答：** Hooks 可以像其他合约一样部署在任何地址上。回调权限在 PoolKey 处设置。有关更多信息，请参阅此处的 hooks 常见问题解答&#x20;

[https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook](https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook)\
\
**Q15：** 我们如何在 etherscan 上验证 hook 合约？&#x20;

**答：** 如果你使用 foundry，可以参考此处的 foundry 指南 [https://book.getfoundry.sh/reference/forge/forge-verify-contract](https://book.getfoundry.sh/reference/forge/forge-verify-contract) \
或者，如果你使用 hardhat，请参考此处的 hardhat 指南 [https://hardhat.org/hardhat-runner/docs/guides/verifying](https://hardhat.org/hardhat-runner/docs/guides/verifying)\
\
**Q16：** 我们应该使用 foundry 还是 hardhat 进行 hook 开发？

**答：** 模板 [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) 基于 foundry；因此，我们建议使用 foundry。除此之外，foundry 的人气也在不断增长！&#x20;

**Q17：** 什么是 pool keys？&#x20;

**答：** PoolKey 是描述每个池的结构体。在[此处](https://developer.pancakeswap.finance/contracts/infinity/overview/amm-layer-poolmanager)查看更多。\
\
\
PancakeSwap Infinity 代表了 DeFi 领域的一个重要里程碑，为交易者、开发者、流动性提供者和更广泛的社区提供了无与伦比的好处。我们很高兴与你一起踏上这段旅程，并期待共同塑造 DeFi 的未来。我们希望这份常见问题解答已回答了你关于 PancakeSwap Infinity 的疑问。如果你有任何进一步的问题，欢迎通过（[Twitter](https://twitter.com/PancakeSwap)、[Discord](https://discord.com/channels/897834609272840232/1207724381212770315) 和 [Telegram](https://t.me/PancakeSwap)）与我们联系，或查看我们的开发者[文档](https://developer.pancakeswap.finance)。
