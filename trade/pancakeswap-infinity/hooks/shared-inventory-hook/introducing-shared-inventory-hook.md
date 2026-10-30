---
description: '2026-08-21'
---

# Shared Inventory Hook 소개

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

다섯 개의 페어에 호가를 제시하는 데 다섯 배의 자본이 들어서는 안 됩니다. 하지만 온체인에서는 모든 자산 발행사가 그런 조건을 받아들여야 합니다. 유동성이 각 페어에 묶여 있기 때문에 새 페어를 추가할 때마다 또 한 덩어리의 자본을 투입해야 하고, 그 대부분은 정확히 그 페어가 정확한 가격 범위 안에서 거래될 때까지 아무 수익도 내지 못한 채 그저 놓여 있습니다. 새 페어에 호가를 제시하고 싶을 때마다 새로운 자본을 LP로 공급해야 하며, 그 자본은 해당 페어 하나에 묶여 다른 곳에서는 사용할 수 없습니다.

Shared Inventory Hook(SIH)은 이 연결 고리를 끊습니다. PancakeSwap Infinity의 최신 Hook이며, 자본 효율성을 위해 만들어진 최초의 Hook입니다.

_💡 요약: Hook은 Infinity 풀에 연결되어 스왑 도중 커스텀 로직을 실행하는 스마트 컨트랙트(애드온과 같은 것)입니다. 새로운 거래 장소를 따로 만들 필요가 없습니다._

그렇다면 어떻게 작동할까요?

모든 풀에 별도의 자금을 묶어 두는 대신, RWA 자산 발행사는 **하나의 공유 인벤토리**를 충전하고, Shared Inventory Hook은 스왑이 일어나는 바로 그 순간에 그 인벤토리에서 현재 거래 중인 페어로 JIT 방식으로 깊이를 제공합니다. 요리마다 별도의 창고를 두는 대신, 하나의 창고가 주방의 모든 요리에 재료를 공급한다고 생각해 보세요. 하나의 잔액이 여러 잔액의 역할을 합니다.

이 단순한 전환이 SIH를 자본 효율적으로 만드는 핵심이며, 세 가지 방식으로 나타납니다.

* **자본이 계속 활성 상태로 일합니다.** Hook 인벤토리의 유동성은 스왑 시 JIT 방식으로 투입되므로, 유휴 상태로 놓여 있는 대신 적극적으로 일하며 수수료를 벌어 줍니다.
* **하나의 잔액으로 여러 페어에서 수수료 기회를 얻습니다.** 하나의 인벤토리가 서비스하는 모든 페어에서 수익을 내므로, 훨씬 적은 자본으로 수수료 흐름을 확보할 수 있습니다.
* **더 낮은 가격 영향.** 스왑 시점에 제시되는 유동성이 더 깊기 때문에, SIH가 최선의 가격을 제시할 때는 대규모 거래의 가격 영향이 낮아집니다.
* **자본 효율성 향상.** 한 번만 충전하면 동일한 자본이 SIH가 활성화된 모든 페어의 깊이를 뒷받침합니다. 또한 추가 자본 없이 새 페어에 SIH를 활성화할 수 있습니다.

> \*\*이미 마음이 정해지셨나요? 자본 효율적인 방식으로 자산을 온체인에 올려 보세요. 다음 양식을 작성해 주세요 → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**증거는 온체인에 있습니다**

SIH는 올해 8월 bStocks와 함께 출시되었으며, 가장 중요한 수치는 그 자본이 얼마나 열심히 일하느냐입니다. 최신 Hook 스냅샷(2026년 8월 21일) 기준, 공유 인벤토리의 75%가 세 개의 페어에 걸쳐 활발히 배치되어 있습니다(Hook 인벤토리 약 $297K, 활성 약 $224K). 성숙한 두 페어인 CRCLB와 MUB의 활용률은 약 99%(98.96% / 98.95%)입니다. 기존 V3 CLAMM 풀이라면 유휴 상태로 남아 있었을 자본이 여기서는 범위 안에서 호가를 제시하고 있습니다.

출시 후 첫 몇 주(8월 21일까지) 동안 세 개의 페어는 약 $297K의 공유 인벤토리로 5,713건의 스왑에서 약 $710K를 거래했으며, 0.25% 수수료 등급으로 LP 수수료를 벌어들였습니다.

_**출처:** 내부 Dune 대시보드_ **라이브 풀:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**앞으로의 방향**

이 모델은 확장을 위해 만들어졌습니다. 더 많은 페어, 24시간 거래되는 수천 개의 시장에 걸쳐 확장되는 하나의 공유 잔액입니다. 뒷받침하는 자본을 늘리지 않고도 토큰의 전체 페어 라인업을 온체인에 올릴 수 있는, 지금까지 본 중 가장 빠른 방법입니다.

라이브 SIH 풀은 [PancakeSwap Earn 페이지](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001)에 있습니다. **Infinity**를 열고 풀 기능에서 **Shared Inventory**를 찾아보세요. SIH는 현재 CRCLB / USDT, MUB / USDT, GMEB / USDT에서 활성화되어 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_참고: 일반 LP는 이미 Earn에서 이 풀들에 유동성을 추가할 수 있습니다. 해당 예치금은 풀에 상주하는 유동성이 되며, 공유 인벤토리와는 별도로 보관됩니다._

_**중요:**_

_SIH는 인벤토리가 스왑 순간에만 활용되기 때문에 일반 LP 포지션보다 가격 변동에 덜 노출됩니다. 그렇다고 위험이 없는 것은 아닙니다. 운영자는 여전히 시장에 따라 움직이는 인벤토리를 보유합니다. 모든 온체인 전략과 마찬가지로 결과는 거래량, 인벤토리, 헤징, 시장 상황에 따라 달라집니다._

자본 효율성을 극대화할 준비가 되셨나요? 지금 토큰 페어에 SIH를 활성화하세요 → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, The Chefs 🥞

***

_면책 조항: 이 콘텐츠는 일반적인 정보 및 교육 목적으로만 제공되며, 금융, 법률 또는 기타 전문적인 조언으로 해석되어서는 안 됩니다. 디지털 자산 가격은 변동성이 클 수 있습니다. 투자 가치는 하락하거나 상승할 수 있습니다._
