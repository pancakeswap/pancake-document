---
hidden: true
---

# Smart Router (V2)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Smart%20Router.png" alt=""><figcaption></figcaption></figure>

PancakeSwap Smart Router는 AMM과 스테이블스왑(BNB 체인), 그리고 AMM과 마켓 메이커(Ethereum)를 연결하여 더 나은 유동성과 가격을 제공하는 라우팅 알고리즘입니다. 스마트 주문 라우팅 알고리즘을 사용해 여러 풀에 걸쳐 거래를 체결하며 트레이더에게 최적의 가격을 찾아 줍니다. StableSwap에 대한 자세한 내용은 [여기를 클릭](../../stableswap/classic-stableswap.md)하고, 마켓 메이커 통합에 대해서는 [여기를 클릭](../market-maker-integration.md)하세요.

Kitchen 팀은 제품을 추가로 테스트하고 개선하기 위해 StableSwap 페어를 점진적으로 확대해 나갈 예정입니다.

## AMM 스왑에 Smart Router를 사용해야 하는 이유는 무엇인가요?

* 스테이블코인이나 가격이 비슷한 자산 페어를 동일한 거래 단계로 더 효율적으로 스왑할 수 있습니다.
* 일반 PancakeSwap AMM보다 더 좋은 체결을 제공할 수 있는 마켓 메이커를 상대로 스왑할 수 있습니다.
* StableSwap 기능으로 거래 슬리피지가 일반 AMM보다 낮습니다.
* StableSwap 거래 수수료가 일반 AMM보다 저렴합니다.

## 아직 준비 중인 기능

* 결과 화면 UI 개선
* 더 효율적인 거래를 위한 분할 라우팅. 예: 거래 규모와 유동성에 따라 라우터가 페어의 50%를 다른 경로로 보내 수수료를 절약합니다.
