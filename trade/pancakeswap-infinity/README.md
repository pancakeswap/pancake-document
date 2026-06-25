# ♾️ PancakeSwap Infinity

> 如果你是开发者或正在寻找详细的技术文档，请参阅此文档 [https://developer.pancakeswap.finance/](https://developer.pancakeswap.finance/)

**PancakeSwap Infinity** 是 PancakeSwap AMM 的最新版本，旨在让去中心化交易更快速、更便宜、更灵活。它采用模块化设计，支持更多自定义，并支持不同类型的交易资金池和定价模型。

借助 Infinity，开发者可以使用 "hooks"（Hook）更轻松地构建新功能——这些小段代码会在资金池生命周期的关键操作时运行。它们支持诸如自定义预言机、动态费用资金池、高级交易与流动性管理功能等用例。&#x20;

与 PancakeSwap v3 相比，Infinity 更省 gas 且更具前瞻性。通过将记账和交易逻辑等核心功能解耦，它支持无缝集成具备 Hook 能力的新定价曲线——使协议能够在无需重新部署的情况下持续演进。

### ⭐️ 主要功能

1. Singleton
2. Flash Accounting
3. Hooks
4. 原生代币支持
5. 自定义定价曲线
6. ERC-6909
7. `donate()`

{% hint style="success" %}
**开源：** [PancakeSwap Infinity](https://github.com/pancakeswap/infinity-core) 采用开源许可证发布，鼓励开发者自由创新、定制和协作。
{% endhint %}
