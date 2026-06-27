# PancakeSwap v4

_如果您是开发人员或正在查找详细的技术文档，请参阅本文档_ [_https://developer.pancakeswap.finance/_](https://developer.pancakeswap.finance/)

**1.什么是 PancakeSwap v4？**&#x20;

PancakeSwap v4 是 PancakeSwap 协议的最新版本，采用模块化自动做市商 (AMM) 架构。该版本通过Hooks 引入了增强的池功能，支持多种定价曲线，并优先考虑用户的 gas 效率。其目的是为用户提供无缝的 DeFi 体验，并为开发人员提供一个可以自由创新的平台。

&#x20;**2. PancakeSwap v4 有哪些功能？**&#x20;

**i) Hooks**

PancakeSwap v4 中的 Hooks 是外部部署的合约，作为可定制的附加组件来增强流动性池的功能。开发人员和协议可以部署这些合约，以便在池运行的关键操作过程中执行预定义的逻辑。Hooks 为流动性池带来了新的定制化功能，允许动态费用、自定义预言机、有效的流动性管理等。

**Hooks** 的好处：&#x20;

* **动态费用**： 交易者可以体验更多样的费用结构，最低费用为 0%。&#x20;
* **高级交易工具**： Hooks 的引入使限价订单、止盈订单、TWAMM（时间加权平均做市）等高级交易工具以及交易费用返还等其他奖励计划成为可能。&#x20;
* **开发人员的收入流**： 开发人员可通过 Hooks 费用获得稳定的收入流，从而激励创新。

<figure><img src="../../.gitbook/assets/image (387) (1).png" alt=""><figcaption></figcaption></figure>

阅读我们的[博客文章](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)来了解 v4 对于开发者，交易者，流动性提供者以及 Defi 协议的好处。

**ii) 多种池类型**&#x20;

PancakeSwap v4 支持多种池类型，包括：

&#x20;**a) 带 Hooks 的 CLAMM（集中流动性自动做市商）**：PancakeSwap v4 支持带 Hooks 的集中流动性自动做市商（CLAMM）模型，允许流动性提供者在特定价格范围内供应资产。 Hooks 的集成为 CLAMM 池提供了自定义选项。&#x20;

**b) 带 Hooks 的 LBAMM（订单簿 AMM）**：首个带 Hooks 的订单簿 AMM 模型在每个 Bin 内按常数和公式运行。该模型消除了单个 bin 内 LP 的无常损失，并实现了零价格影响交易。 Hooks 为订单簿 AMM 池带来了定制的可能性。&#x20;

**c) 任何其他带有 Hooks 的未来可能出现的新的池类型**：PancakeSwap v4 的设计灵活且面向未来，允许使用 Hooks 实施新的 AMM 设计。开发人员可以探索创新的池类型来满足不断变化的市场需求。每种资金池类型都具有独特的优势，并允许多种交易策略和流动性配置选项。&#x20;

**iii) 捐赠**&#x20;

捐赠功能使利益相关者能够直接激励范围内的流动性提供者，提高 LPs 的回报和参与度。

&#x20;**iv) Singleton**

Singleton 合约设计将所有池合并到一个合约中。这显着降低了池的创建成本（高达 99%），并最大限度地降低了多跳交换的 Gas 成本。

**v) Flash Accounting**&#x20;

Flash Accounting 是一种 Gas 优化技术，通过计算一批交易的净余额并对其进行集体结算，优化了记账流程， 与以前的模型相比，这种方法减少了 Gas 消耗，以前的模型在每次用户操作后都会将资产转入和转出池。

**vi) ERC6909**&#x20;

PancakeSwap v4 采用 ERC-6909 多代币标准进行记账。 该标准允许在单个智能合约中创建和管理可替代和不可替代的代币。 ERC-6909 提高了效率，降低了交易频繁的用户的成本，并提供了其他代币标准的简化替代方案。

**vii) 支持原生 Gas 代币**

&#x20;**PancakeSwap v4 支持原生 Gas 代币**，允许与原生 Gas 代币直接组成交易对，降低用户的 Gas 成本。&#x20;

**开源许可**：PancakeSwap v4 代码将在开源许可下发布，鼓励开发人员自由创新、定制和协作。&#x20;

**开发者计划**：PancakeSwap 正在启动一项价值 500,000 美元的开发者计划，以支持和激励开发者。 这包括增长活动、黑客马拉松、开发者大使计划和 CAKE 排放补助计划。 请在[此处](https://blog.pancakeswap.finance/articles/introducing-pancake-swap-s-500-k-developer-program-and-cake-emissions-grant-program)阅读有关开发者计划的更多信息。

PancakeSwap v4 的推出代表了 DeFi 协议发展的一个重要里程碑。 其模块化架构、可定制功能和 Gas 优化技术为用户提供了更高效、灵活和有意义的体验。

无论您是寻求构建自定义功能的开发人员、寻求高级工具的交易者，还是为了在获得最佳回报的流动性提供商，PancakeSwap v4 都能满足您的独特需求。 欢迎加入我们，我们将于今年第三季度在以太坊主网和 BNB 链上推出。

点此访问[代码库](https://github.com/pancakeswap/pancake-v4-core)，代码库是对开发人员是开源的，详细的技术文档请访问[这里](https://developer.pancakeswap.finance/)。
