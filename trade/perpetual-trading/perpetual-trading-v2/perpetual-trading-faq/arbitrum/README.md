---
hidden: true
---

# Arbitrum

### Arbitrum에서 PancakeSwap 무기한 선물 V2의 수수료는 얼마인가요?

Arbitrum 출시 시점의 수수료는 **포지션 개시 및 종료 시 0.05%**입니다. 징수된 수수료의 50%는 유동성을 제공하는 ALP 풀과 공유됩니다. 그 외에 실행 수수료, 청산 수수료, 펀딩 수수료가 있습니다. 수수료에 대한 자세한 정보는 [여기](https://blog.pancakeswap.finance/articles/ep-6-4-pancake-swap-perpetuals-v2-fee-structure-a-comprehensive-overview)에서 확인할 수 있습니다.

### ALP란 무엇인가요?

Arbitrum의 무기한 선물 v2에는 Aster 플랫폼의 유동성 공급자 토큰인 $ALP로 구동되는 별도의 유동성 풀인 ALP 풀이 있습니다. ALP 풀은 USDC, USDT, DAI, ETH, BTC 등의 자산으로 구성되며, 사용자는 앞서 언급한 자산 중 하나로 $ALP를 발행(mint)하여 유동성 공급자가 되고 상당한 수익을 얻을 수 있습니다. 포지션 개시/종료 수수료, 실행 수수료, 펀딩 수수료, 청산 수수료 등 다양한 항목을 포함한 플랫폼 전체 수수료 수익의 무려 50%가 ALP 유동성 공급자에게 분배됩니다. ALP 스테이킹 가이드는 [여기](alp-syrup-pool-arbitrum/)에서 확인할 수 있습니다.

### ALP 시럽 풀이란 무엇인가요?

Arbitrum의 새로운 Aster($ALP) 시럽 풀을 통해 사용자는 부스트된 수익을 얻을 수 있습니다. 사용자는 $ALP 토큰을 스테이킹하여 $CAKE 토큰으로 보상을 받을 수 있으며, 출시 시점의 APY는 20%를 넘습니다. PancakeSwap의 ALP 시럽 풀입니다. 배출량과 시작일 및 종료일 등 시럽 풀에 대한 자세한 내용은 [여기](https://pancakeswap.finance/voting/proposal/0x52455da15b4f1ff4d324c1e7645163d6b78b2221a98a4782bff16b27de409ce9)의 제안서를 참고하세요.

### Arbitrum에서 이용 가능한 토큰은 무엇인가요?

Arbitrum One에서 지원되는 거래 페어는 ARBUSD, XRPUSD, DOGEUSD, ETHUSD, BTCUSD입니다. 디젠 모드에서는 ETHUSD와 BTCUSD가 지원됩니다. 앞으로 몇 주 안에 더 많은 페어를 출시할 예정입니다.

### Arbitrum에서 지갑에 USDC를 충전했는데 왜 보이지 않나요?

Arbitrum의 네이티브 USDC([0xaf88d065e77c8cC2239327C5EDb3A432268e5831](https://arbiscan.io/token/0xaf88d065e77c8cC2239327C5EDb3A432268e5831))를 충전하셨을 가능성이 높습니다. 하지만 PancakeSwap 무기한 선물은 유동성이 더 높은 브릿지된 USDC인 USDC.e([0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8](https://arbiscan.io/token/0xff970a61a04b1ca14834a43f5de4533ebddb5cc8))를 지원합니다. USDC를 USDC.e로 [여기](https://pancakeswap.finance/swap?chain=arb\&outputCurrency=0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8\&inputCurrency=0xaf88d065e77c8cC2239327C5EDb3A432268e5831)에서 간편하게 스왑할 수 있습니다. USDC와 USDC.e의 차이에 대한 자세한 내용은 [Circle USDC ](https://www.circle.com/blog/arbitrum-usdc-now-available)보도 자료를 참고하세요.
