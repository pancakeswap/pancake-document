---
hidden: true
---

# Arbitrum

### Arbitrum 上 PancakeSwap 永续合约 V2 的费用是多少？

在我们于 Arbitrum 上线时，费用为 **开仓和平仓交易各 0.05%**。所收取费用的 50% 将与提供流动性的 ALP 池共享。其他费用包括执行费、清算费和资金费。有关费用的更多信息，请查看[此处](https://blog.pancakeswap.finance/articles/ep-6-4-pancake-swap-perpetuals-v2-fee-structure-a-comprehensive-overview)。

### 什么是 ALP？

Arbitrum 上的永续合约 v2 设有一个独立的流动性池，即 ALP 池，由 Aster 平台的流动性提供者代币 $ALP 提供支持。ALP 池由 USDC、USDT、DAI、ETH 和 BTC 等资产组成，允许用户使用上述任何资产铸造 $ALP，从而成为流动性提供者并赚取可观的收益。平台总费用收入的高达 50% 将分配给 ALP 流动性提供者，涵盖开仓/平仓费用、执行费用、资金费用和清算费用等各种组成部分。质押 ALP 的指南可在[此处](alp-syrup-pool-arbitrum/)找到。

### 什么是 ALP 糖浆池？

Arbitrum 上新推出的 Aster（$ALP）糖浆池允许用户赚取提升后的收益。用户可以质押 $ALP 代币以赚取 $CAKE 代币奖励，上线时 APY 超过 20%。PancakeSwap 上的 ALP 糖浆池。有关糖浆池的更多详细信息，包括产出量以及开始和结束日期，请参阅[此处](https://pancakeswap.finance/voting/proposal/0x52455da15b4f1ff4d324c1e7645163d6b78b2221a98a4782bff16b27de409ce9)的提案。

### Arbitrum 上有哪些可用代币？

Arbitrum One 上支持的交易对为 ARBUSD、XRPUSD、DOGEUSD、ETHUSD 和 BTCUSD。对于 Degen 模式，支持 ETHUSD 和 BTCUSD。我们将在未来几周内推出更多交易对。

### 我在 Arbitrum 上用 USDC 给钱包充值了；为什么我看不到它？

很可能你充值的是 Arbitrum 上的原生 USDC（[0xaf88d065e77c8cC2239327C5EDb3A432268e5831](https://arbiscan.io/token/0xaf88d065e77c8cC2239327C5EDb3A432268e5831)）。然而，PancakeSwap 永续合约支持桥接 USDC，即 USDC.e（[0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8](https://arbiscan.io/token/0xff970a61a04b1ca14834a43f5de4533ebddb5cc8)），因为它具有更高的流动性。你可以在[此处](https://pancakeswap.finance/swap?chain=arb\&outputCurrency=0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8\&inputCurrency=0xaf88d065e77c8cC2239327C5EDb3A432268e5831)将 USDC 无缝兑换为 USDC.e。有关 USDC 和 USDC.e 之间区别的更多信息，请参阅 [Circle USDC ](https://www.circle.com/blog/arbitrum-usdc-now-available)新闻稿。
