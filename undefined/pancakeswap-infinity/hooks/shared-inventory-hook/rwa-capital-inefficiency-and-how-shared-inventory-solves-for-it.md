---
description: '2026-09-04'
---

# RWA 자본 비효율성과 Shared Inventory의 해결 방법

PancakeSwap 사례 연구 실험 (1부: 준비)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(217).png" alt=""><figcaption></figcaption></figure>

이 글은 2부작 사례 연구의 첫 번째 파트입니다. 이번 파트에서는 RWA 자산 발행사가 겪는 실제 자본 효율성 문제를 설명하고, 이를 해결하기 위해 고안된 PancakeSwap의 Shared Inventory Hook(SIH)을 소개하며, 온체인 데이터로 이를 검증하는 라이브 사례 연구 실험을 소개합니다.

앞으로 몇 주 동안 2부: 결과를 공개합니다.

***

### 🧩 자본 효율성 문제란 무엇인가요?

RWA 업계는 한 가지 숫자를 좋아합니다. 바로 **얼마나 많은 자산이 토큰화되었는가**입니다. 거의 모든 보고서의 헤드라인을 장식하는 수치로, 새로운 자산군의 등장, 수십억 달러 규모의 발행, 수백 퍼센트의 성장을 보여 줍니다.

하지만 묻혀 버리는 두 번째 숫자가 있으며, 이쪽이 더 중요한 신호일 수 있습니다. **그중 실제로 거래할 수 있는 것은 얼마인가?**

핵심은 이 두 숫자 사이의 격차에 있습니다. 대표적인 트래커인 [rwa.xyz](http://rwa.xyz)에서 온체인에 _표현된_ 가치의 양은 특정 시점에 실제로 _거래할 수 있는_ 양을 훨씬 웃돕니다. 데이터에 따르면 락업, 참조, 유통되는 가치는 **거래 가능한 오더북에 있는 가치보다 한 자릿수 이상 큽니다.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(380).png" alt=""><figcaption></figcaption></figure>

_출처: app.rwa.xyz/stocks_

RWA 발행사에게 이것은 함정입니다. 주식, ETF, 국채를 토큰화하는 것은 쉬운 부분이며, 이를 촘촘하고 안정적으로 거래되게 만드는 것이 과제이자 자본 효율성이 좌우되는 지점입니다. 궁극적인 목표는 트레이더가 토큰화 자산을 쉽고 저렴하게 \_실제로 거래\_할 수 있게 하는 것이며, 결국 거래량과 수수료는 여기서 나옵니다.

그리고 이것이 단순한 유동성 문제가 아니라 특히 _자본 효율성_ 문제인 이유는 다음과 같습니다.

#### 호가를 제시하는 모든 풀은 자체 전용 USDT 스택을 요구합니다

기존의 집중 유동성(CLAMM) 풀에서 하나의 RWA 페어를 거래 가능하게 만들려면, 발행사는 구매자가 매도할 수 있도록 전용 호가 자산인 USDT를 풀에 넣어 두어야 합니다. 열 개의 페어를 상장하면 CLAMM 모델은 페어마다 하나씩, 서로 도울 수 없는 **열 개의 별도 USDT 스택**을 충전해야 합니다. 그래서 호가 자본이 전용 사일로로 잘게 쪼개집니다.

저희는 자체 오더북에서 이를 측정했습니다. PancakeSwap에서 운영 중인 **7개의 토큰화 주식 풀**(각각 기존 V3 CLAMM 풀로 운영)을 대상으로 전용 USDT를 집계했습니다.

스냅샷: **2026년 9월 2일**

<table data-search="false"><thead><tr><th>페어</th><th>풀 내 전용 USDT</th><th>풀 TVL</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>합계</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

전용으로 할당된 USDT가 **약 $745k**에 달합니다.

그리고 이것은 오더북이 있는 종목만 집계한 것입니다.

SNXXB, KORUB, SOXSB, DJTB는 CLAMM USDT 오더북이 아예 없습니다. 토큰화는 되었지만 거래하기 어렵습니다.

***

### 🎯 발행사는 무엇을 최적화해야 할까요?

메커니즘을 걷어내고 나면, RWA 발행사가 핵심적으로 해결해야 할 것은 세 가지입니다.

1. **자산이 실제로, 효율적으로 거래 가능할 것** — 대표 토큰뿐 아니라 모든 자산에서 촘촘한 호가.
2. **가능한 한 적은 자본이 묶일 것** — 호가 자산은 비쌉니다. 열 개의 USDT 스택을 전용으로 충전하는 것은 그리 효율적이지 않습니다.
3. **트레이딩 데스크를 운영하지 않을 것 —** 매일 유동성 인프라를 운영하지 않고도 자산을 발행할 수 있어야 합니다.

그렇다면 질문은 유동성을 다르게 구조화할 수 있느냐는 것이며, PancakeSwap의 Shared Inventory Hook이 바로 이를 해결하도록 설계되었습니다.

***

### 🥞 Shared Inventory Hook (SIH)

**SIH는 RWA 발행사가 페어마다 전용 스택을 두는 대신 하나의 공유 USDT 풀로 여러 페어를 뒷받침할 수 있게 해 주는 PancakeSwap Infinity Hook입니다.**

SIH는 JIT(Just-in-time) 방식으로 유동성을 제공하여 다음을 가능하게 합니다.

* 페어의 더 깊은 호가
* 특히 대규모 거래에서 더 낮은 가격 영향
* 더 적은 자본으로 더 많은 페어에 호가를 제시하므로 RWA 발행사의 자본 확보

이러한 주장을 실제로 살펴보겠습니다.

같은 **2026년 9월 2일** 스냅샷 기준, SIH는 단일 Hook에 **$635,028**의 인벤토리를 보유하고, **$180,467**의 공유 USDT로 **11개 페어**에 호가를 제시하며 \*\*87.7%\*\*의 활용률로 운영되고 있습니다. 이를 통해 SIH는 **17,299건의 트랜잭션에서 $3.56M**을 처리했습니다.

즉 **약 $700k의 단일 공유 USDT 잔액이 약 11개 페어에 호가를 제시하는 반면, 약 $745k는 7개 페어에만 호가를 제시**합니다.

같은 일을 하되, 자본이 중복되지 않도록 설계했을 뿐입니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(381).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(395).png" alt=""><figcaption></figcaption></figure>

발행사가 중요하게 여기는 점에 대응시키면 다음과 같습니다.

* 기존에는 N개의 전용 USDT 잔액 → ✅ SIH에서는 하나의 공유 풀
* 발행은 되었지만 거래 불가 → ✅ 거래 가능\
  실시간 가격 주변에 JIT로 투입되는 공유 인벤토리 덕분에, V3 USDT 오더북이 없는 토큰도 단순히 발행만 되는 것이 아니라 호가를 제시할 수 있습니다.
* 데스크 운영 → ✅ 권한이 부여된 운영자\
  발행사는 인벤토리를 공급하고, Hook과 운영자가 호가 제시를 처리합니다.

***

### 🔬 Shared Inventory 시뮬레이터 체험하기

인터랙티브 비교 도구로 SIH가 어떻게 작동하는지 직관적으로 이해해 보세요 **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(406).png" alt=""><figcaption></figcaption></figure>

이것은 SIH를 기존 CLAMM 오더북과 비교한 **높은 수준의 정규화된 비교**이며, 자본 효율성 메커니즘을 명확하게 분리해 보여 주기 위해 여러 현실 요소를 양쪽에서 동일하게 고정했습니다. 이해를 돕기 위한 모델이며 손익 계산서가 아닙니다.

세 개의 탭이 있습니다.

* **시뮬레이터 탭** - 인벤토리, 밴드 폭, 거래 흐름을 조정하며 다양한 조건에서 SIH가 비슷한 CLAMM 풀 대비 어떤 성능을 _낼 수 있는지_ 확인합니다.
* **비교 탭** - 동일한 풀에서 SIH를 **PancakeSwap V3 CLAMM** 오더북과 직접 비교하여, 공유 USDT 풀과 전용 USDT 간의 투입 자본 및 커버리지 차이를 나란히 확인할 수 있습니다.
* **라이브 데이터 탭** — 이 연구를 뒷받침하는 온체인 쿼리를 바탕으로 SIH가 지금 _실제로_ 어떤 성능을 내고 있는지 측정합니다.

시뮬레이터는 Shared Inventory Hook이 어떻게 작동하는지 보여 주기 위한 것입니다. 직접 사용해 보고, 앞으로 몇 주 안에 공개할 실제 결과와 비교해 보세요.

***

### 🧪 실험

**앞으로 몇 주 동안** SIH를 실제로 운영하며 온체인 소스를 사용해 위의 자본 효율성 주장에 대해 측정합니다. 매주 SIH 성능과 아키텍처에 대한 새로운 정보를 공개합니다.

**연구에 포함된 라이브 RWA 페어:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_참고: SNXXB, KORUB, SOXSB, DJTB는 기존 CLAMM 오더북이 아예 없습니다._

**결과는 앞으로 몇 주에 걸쳐 PancakeSwap의** [**Twitter**](https://x.com/PancakeSwap)**에 공개됩니다.**

공개될 결과에는 다음이 포함됩니다.

* **전체 성능 데이터셋 -** 앞으로 몇 주간의 모든 SIH 데이터를 하나의 그림으로 종합합니다.
* **자본 배분 문제 -** SIH가 RWA 발행사의 자본을 실제로 얼마나 절약했는지.
* **기대 충족/미달 -** SIH가 기대를 넘어선 부분과 개선이 필요한 부분.
* **결론 -** SIH가 RWA 자본 효율성에 실제로 얼마나 효과적인지에 대한 근거 있는 결론.

_데이터 관련 안내: 여기에 제시된 수치는 라이브 온체인 쿼리와 공개 페어 데이터에서 가져온 것이며 본문에 출처를 표기했습니다. 일부 비교는 서로 다른 기간을 사용하므로 이를 표시해 두었습니다. 이 연구는 이번 소개글이 질문을 제기하는 데 그쳤던 부분에서 동일 조건 비교를 측정하도록 설계되었습니다._

***

### 자산에 SIH를 활성화하고 싶으신가요?

RWA 발행사이고 호가를 제시하는 모든 풀마다 별도의 USDT 스택을 충전하는 데 지치셨다면, 이 내용은 바로 여러분을 위한 것입니다.

현재 RWA 발행사를 온보딩하고 있습니다. 이 구글 양식을 작성해 주시면 자산을 SIH에서 호가 제시하도록 안내해 드리겠습니다 - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

읽어 주셔서 감사합니다! 최신 소식은 [X](https://x.com/PancakeSwap)에서 확인하시고, [Telegram](https://t.me/PancakeSwap)과 [Discord](https://discord.gg/pancakeswap)에서 대화에 참여해 주세요.

함께 만들어 가요,\
The Chefs 🥞

***

_면책 조항: 이 콘텐츠는 일반적인 정보 및 교육 목적으로만 제공되며, 금융, 법률 또는 기타 전문적인 조언으로 해석되어서는 안 됩니다. 디지털 자산 가격은 변동성이 클 수 있습니다. 투자 가치는 하락하거나 상승할 수 있습니다._
