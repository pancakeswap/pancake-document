---
hidden: true
---

# Arbitrum

### ArbitrumでのPancakeSwap Perpetuals V2の手数料はいくらですか？

Arbitrumへのローンチにあたり、手数料は**取引の開設・クローズで0.05%**となります。徴収された手数料の50%は流動性提供のためにALPプールに分配されます。その他の手数料には実行手数料、清算手数料、ファンディングフィーが含まれます。手数料の詳細については[こちら](https://blog.pancakeswap.finance/articles/ep-6-4-pancake-swap-perpetuals-v2-fee-structure-a-comprehensive-overview)をご参照ください。

### ALPとは何ですか？

ArbitrumのPerpetuals v2では、Asterプラットフォームの流動性プロバイダートークン$ALPを活用した独立した流動性プールであるALPプールが採用されています。USDC、USDT、DAI、ETH、BTCなどの資産で構成されるALPプールにより、ユーザーは上記のいずれかの資産で$ALPをミントすることで流動性プロバイダーになり、大きなイールドを得ることができます。プラットフォームの総手数料収益の50%がALP流動性プロバイダーに分配されます。これには開設・クローズ手数料、実行手数料、ファンディングフィー、清算手数料などが含まれます。ALP Stakingのガイドは[こちら](alp-syrup-pool-arbitrum/)をご参照ください。

### ALP Syrup Poolとは何ですか？

Arbitrumの新しいAster（$ALP）Syrup Poolにより、ユーザーは強化されたイールドを得ることができます。ユーザーは$ALPトークンをステークしてCAKEトークンを報酬として受け取ることができ、ローンチ時のAPYは20%以上です。PancakeSwapのALP Syrup Pool。シロッププールの詳細（エミッションや開始・終了日など）については、[こちら](https://pancakeswap.finance/voting/proposal/0x52455da15b4f1ff4d324c1e7645163d6b78b2221a98a4782bff16b27de409ce9)のプロポーザルをご参照ください。

### Arbitrumで利用可能なトークンは何ですか？

Arbitrum Oneでサポートされている取引ペアはARBUSD、XRPUSD、DOGEUSD、ETHUSD、BTCUSDです。デジェンモードではETHUSDとBTCUSDがサポートされています。今後数週間でさらに多くのペアを追加する予定です。

### ArbitrumでUSDCをウォレットにトップアップしたのに表示されません。なぜですか？

ArbitrumのネイティブUSDC（[0xaf88d065e77c8cC2239327C5EDb3A432268e5831](https://arbiscan.io/token/0xaf88d065e77c8cC2239327C5EDb3A432268e5831)）をトップアップした可能性が高いです。しかし、PancakeSwap PerpetualはよりPancakeSwap高い流動性を持つブリッジ版USDC（USDC.e）（[0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8](https://arbiscan.io/token/0xff970a61a04b1ca14834a43f5de4533ebddb5cc8)）をサポートしています。USDC.eへのSwapは[こちら](https://pancakeswap.finance/swap?chain=arb\&outputCurrency=0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8\&inputCurrency=0xaf88d065e77c8cC2239327C5EDb3A432268e5831)からシームレスに行えます。USDCとUSDC.eの違いについては、[Circle USDC](https://www.circle.com/blog/arbitrum-usdc-now-available)プレスリリースをご参照ください。
