# CLAMM 옵션

{% hint style="danger" %}
\[보관됨] 옵션 – 2025년 3월 11일 기준\
아직 출금할 유동성이 있다면 https://www.stryke.xyz/en/trade 를 방문하여 즉시 출금하세요.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM 옵션은 온체인 옵션 거래에 대한 새로운 접근 방식으로, 유동성 공급자에게 PancakeSwap v3 유동성을 활용할 수 있는 플랫폼을 제공합니다. 이를 통해 v3 유동성 풀과 옵션 판매 모두에 유동성을 활용하여 일반적인 AMM 거래 수수료, 옵션 프리미엄 및 추가 보상을 얻을 수 있으며, 트레이더는 이 유동성을 활용하여 다양한 토큰에 대한 아메리칸 스타일 옵션을 매수할 수 있습니다.

Stryke(구 Dopex) 팀이 만든 CLAMM 옵션 프로토콜은 옵션 트레이더(매수자)와 PancakeSwap v3 풀을 위한 효율적인 이중 유동성 공급 시스템을 도입합니다.

CLAMM 옵션의 작동 방식은 다음과 같이 정리할 수 있습니다.

1. CLAMM 옵션에 유동성을 추가하는 LP는 선택한 가격 범위 내에서 지정된 PancakeSwap v3 풀에도 동시에 유동성을 공급합니다.
2. 옵션 트레이더(매수자)가 포지션을 개시하면 옵션 판매를 위해 v3 풀에서 유동성이 추출됩니다. 이에 따라 해당 LP는 옵션 매도자가 되어 프리미엄을 받습니다.
3. 옵션 매수자가 사용하지 않은 유동성은 PancakeSwap v3 풀에 남아 거래 수수료를 얻을 수 있습니다.
4. 옵션 판매와 v3 풀 유동성 공급의 손익은 동일한 비영구적 손실을 반영하므로 사용자는 v3 풀에 유동성을 추가하는 기존 방식에 비해 더 높은 위험에 노출되지 않습니다.
5. LP는 일부 위험을 감수합니다. 옵션 매수 수요가 낮아 유동성이 사용되지 않은 채로 남을 수 있습니다. 또한 유동성이 비활성 범위의 풀에 추가되므로 수수료를 전혀 얻지 못할 수도 있습니다.

PancakeSwap의 아메리칸 스타일 CLAMM 옵션은 Arbitrum 체인에서 출시되며 1시간에서 24시간까지 다양한 만기 기간으로 유연성을 제공합니다.

| **마켓**          | ARB/USDC, ETH/USDC, wBTC/USDC |
| -------------------- | --------------------------------- |
| **옵션 유형**    | 콜 & 풋                        |
| **행사 가격**    | v3 풀 틱 기준            |
| **만기 기간** | 1H, 2H, 6H, 12H, 24H          |

**행사 조건:** 사용자는 인더머니 옵션이 가치 없이 만료되는 것을 방지하기 위해 종료 전에 포지션을 행사할 수 있습니다. 자동 행사를 활성화하면 추가 작업 없이 만기 시 자동으로 수익을 실현할 수 있습니다.

### 단계별 가이드

PancakeSwap CLAMM 옵션을 사용하는 단계별 가이드입니다.

**트레이더용:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**LP용:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
