# Infinity StableSwap

### 개요

Infinity StableSwap은 [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) 내에서 스테이블코인(예: USDC/USDT)이나 가격이 밀접하게 연동된 자산(예: 래핑 토큰 페어, 유동성 스테이킹 토큰, 유동성 리스테이킹 토큰)처럼 거의 같은 가격으로 거래되어야 하는 자산을 스왑하는 데 최적화된 풀 유형입니다.

Curve의 StableSwap NG 설계에서 영감을 받은, Infinity 아키텍처에서 구동되는 StableSwap 훅(Hooks)을 기반으로 합니다. 현재 BNB 체인에서 이용할 수 있으며, 향후 더 많은 체인으로 확장할 계획입니다.

***

### 작동 방식

Infinity StableSwap은 합 상수와 곱 상수를 혼합한 스테이블 불변 곡선을 사용합니다.

* 페그 근처 → 곡선이 합 상수에 가깝게 작동하여 1:1 근처의 거래에서 슬리피지가 매우 낮습니다.
* 페그에서 멀어질 때 → 곡선이 점진적으로 곱 상수 방식으로 전환되어, 큰 불균형이나 디페깅 상황에서 균형을 회복하고 풀을 보호하는 데 도움이 됩니다.

이 때문에 촘촘한 가격과 낮은 슬리피지가 가장 중요한 스테이블 페어에 특히 효과적입니다.

***

### 주요 특징

페그 근처 스왑에 최적화: 대략 같은 가격으로 거래될 것으로 예상되는 자산 간의 거래에서 슬리피지가 낮습니다.

간편한 유동성 공급: 유동성 공급자(LP)는 CLAMM 풀과 달리 가격 범위를 선택하거나 관리할 필요 없이 두 토큰을 비율에 맞게 예치합니다.

ERC-20 LP 토큰: LP 포지션이 표준 ERC-20 토큰으로 표현되어 일드 프로그램, 포인트 캠페인, 기타 DeFi 프로토콜에서 쉽게 활용할 수 있습니다.

동적 수수료: 풀의 균형 상태에 따라 수수료가 조정될 수 있으며, 풀을 균형으로 되돌리는 거래에는 보상을 주고 불균형을 악화시키는 거래는 억제합니다.

Infinity 라우팅 지원: StableSwap 풀이 최적의 가격을 제공할 때는 거래가 자동으로 해당 풀을 통해 라우팅됩니다. 트레이더가 추가로 할 일은 없습니다.

조정 가능한 증폭(A) 매개변수: 풀 운영자는 시장 상황 변화에 적응하도록 시간에 걸쳐 A 매개변수를 높이거나 낮출 수 있으며, 급격한 변화를 방지하는 안전장치가 마련되어 있습니다.

***

### 풀 매개변수

StableSwap 풀의 동작은 일반적으로 풀 생성 시점에 설정되는 소수의 매개변수로 결정됩니다.

#### 증폭 계수(A)

A 매개변수는 풀이 1:1 가격 페그에 얼마나 가깝게 밀착하는지를 제어합니다.

| A 값   | 효과                                              |
| ----- | ----------------------------------------------- |
| A가 높음 | 페그 근처의 곡선이 촘촘해짐. 1:1 근처에서 슬리피지가 낮아지나 불균형에 더 민감함 |
| A가 낮음 | 곡선이 느슨해짐. 일반적인 곱 상수 풀에 더 가깝게 작동함                |

경험칙: 페그가 강력하고 안정적인 자산(예: USDC/USDT)에는 높은 A를 사용하세요. 페그가 느슨하거나 변동성이 큰 자산(예: 일부 LST 페어)에는 낮은 A를 사용하세요.

A 매개변수는 풀 운영자가 정해진 기간에 걸쳐 점진적으로 높이거나 낮출 수 있습니다. 변경 사항은 조작이나 갑작스러운 가격 변동을 방지하는 안전장치와 함께 점진적으로 적용됩니다.

#### 오프페그 수수료 배수

풀이 균형에서 멀어질 때 유효 수수료를 조정하는 추가 매개변수입니다. 풀의 불균형을 더 키울 수 있는 거래를 억제하고, 시장 스트레스나 디페깅 상황에서 풀을 더 견고하게 만듭니다.

#### 동적 수수료

각 스왑에 부과되어 유동성 공급자에게 지급되는 수수료입니다. Infinity StableSwap은 동적 수수료를 지원합니다. 즉, 특정 거래의 유효 수수료는 풀의 현재 상태(예: 해당 거래가 균형을 개선하는지 악화시키는지)에 따라 달라질 수 있습니다.

***

### Infinity StableSwap과 Classic StableSwap 비교

기존 PancakeSwap StableSwap을 사용해 보셨다면, 무엇이 바뀌고 무엇이 그대로인지 확인해 보세요.

| <p><br></p>  | Classic StableSwap           | Infinity StableSwap                  |
| ------------ | ---------------------------- | ------------------------------------ |
| 가격 곡선        | 스테이블 불변 곡선 (합 상수 / 곱 상수 혼합)  | 동일한 스테이블 불변 곡선, 페그 근처에서 동일하게 낮은 슬리피지 |
| ERC-20 LP 토큰 | ✅ 예                          | ✅ 예                                  |
| 풀 생성         | 운영 부담이 큼. 팀의 수동 설정이 필요함      | 퍼미션리스 — 누구나 풀을 생성할 수 있음              |
| 스왑 수수료       | 페어별 고정 (예: USDC/USDT는 0.01%) | 동적 수수료 — 거래가 풀 균형에 미치는 영향에 따라 조정됨    |
| 증폭(A) 매개변수   | 고정 — 한 번 설정하면 변경할 수 없음       | 조정 가능 — 시간에 걸쳐 점진적으로 높이거나 낮출 수 있음    |
| 오프페그 수수료 배수  | ❌ 지원 안 함                     | ✅ 지원 — 디페깅 상황에서 풀을 보호하는 데 도움이 됨      |
| 가스 효율성       | 표준                           | 개선됨 — Infinity의 싱글톤과 플래시 회계의 이점을 누림  |

#### 변하지 않는 점

* 핵심 가격 곡선과 페그 근처의 낮은 슬리피지 특성은 그대로입니다.

#### 새롭고 더 나아진 점

* 퍼미션리스 풀 생성: 팀의 수동 설정 없이도 누구나 풀을 생성할 수 있습니다.
* 동적 수수료로 LP 보호: 단일 고정 수수료 대신, 거래가 풀 균형에 도움이 되는지 해가 되는지에 따라 거래별로 수수료가 조정될 수 있어 변동성이 큰 상황에서 풀이 더 탄력적입니다.
* 조정 가능한 A 매개변수: 증폭 계수가 배포 시점에 영원히 고정되는 대신, 시장 상황이 바뀜에 따라 시간에 걸쳐 조정될 수 있습니다.

***

### 자주 묻는 질문 (FAQ)

Infinity StableSwap에 적합한 자산은 무엇인가요?

거의 같은 가격으로 거래될 것으로 예상되는 자산입니다. 스테이블코인(USDC, USDT, BUSD 등), 동일 자산의 래핑 버전(예: WBTC/cbBTC), 그리고 페그 변동성이 낮은 일부 유동성 스테이킹 토큰 / 유동성 리스테이킹 토큰(LST/LRT) 페어가 해당됩니다.

<br>

Infinity StableSwap은 기존 PancakeSwap StableSwap과 어떻게 다른가요?

Infinity StableSwap은 PancakeSwap Infinity의 훅(Hooks)으로 구현되므로, 싱글톤과 플래시 회계를 통한 낮은 가스 비용, 더 유연한 수수료 체계 등 Infinity 인프라의 모든 이점을 그대로 누릴 수 있습니다. 또한 기존 StableSwap에는 없던 동적 수수료와 조정 가능한 증폭 같은 새로운 기능도 지원합니다.

<br>

시간이 지나면서 포지션을 관리해야 하나요?

아니요. CLAMM과 달리 가격 범위를 설정하거나 조정할 필요가 없습니다. 유동성이 곡선 전체에서 항상 활성 상태이므로 포지션이 "범위를 벗어날" 위험이 없습니다.

<br>

토큰 하나만으로 유동성을 공급할 수 있나요?

네, 단일 토큰 예치를 지원합니다.

<br>

동적 수수료는 어떻게 작동하나요?

Infinity StableSwap에서는 거래가 풀의 균형에 미치는 영향에 따라 스왑 수수료가 거래마다 달라질 수 있습니다. 풀을 균형으로 되돌리는 데 도움이 되는 거래는 더 낮은 유효 수수료를 내고, 불균형을 악화시키는 거래는 더 높은 수수료를 낼 수 있습니다. 이는 LP를 보호하고 더 건전한 풀 상태를 유지하도록 설계되었습니다.

***

## Infinity StableSwap 풀 생성하기

Infinity StableSwap 풀은 퍼미션리스입니다. PancakeSwap 팀의 승인 없이 누구나 생성할 수 있습니다.

<br>

### 단계별 가이드

1\. Farm/Liquidity 페이지로 이동하여 Create Pool을 클릭합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. 풀 유형 옵션에서 StableSwap Pool을 선택합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20(1).png" alt=""><figcaption></figcaption></figure>

<br>

3\. 풀에 사용할 토큰 페어를 선택합니다(예: USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20(2).png" alt=""><figcaption></figcaption></figure>

<br>

4\. 풀 매개변수

| 매개변수                  | 기능                                                               |
| --------------------- | ---------------------------------------------------------------- |
| Swap Fee              | 각 스왑에 부과되어 LP에게 지급되는 수수료. 촘촘한 스테이블 페어의 기본값은 0.01%입니다.            |
| A (Amplification)     | 곡선이 페그에 얼마나 밀착하는지를 제어합니다. 높을수록 1:1 근처에서 슬리피지가 낮아지나 불균형에 더 민감합니다. |
| Offpeg Fee Multiplier | 풀이 균형에서 멀어질 때 수수료를 높여, 불균형을 악화시키는 거래를 억제합니다.                     |
| Moving Average Time   | 동적 수수료 조정을 위한 이동평균 가격을 계산하는 데 사용되는 시간 구간입니다.                     |

⚠️ 매개변수를 신중하게 설정하세요. 잘못된 매개변수, 특히 페그가 느슨한 자산에 매우 높은 A를 설정하면 LP의 위험이 커질 수 있습니다. 확신이 서지 않으면 자산 유형에 맞는 프리셋을 사용하고 Advanced 설정은 변경하지 마세요.

<br>

풀 매개변수 프리셋을 선택하세요. 자산 유형에 맞는 권장 매개변수가 자동으로 설정됩니다. Advanced 토글을 통해 직접 조정할 수도 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20(3).png" alt=""><figcaption></figcaption></figure>

| 프리셋                                                | A    | Offpeg Fee Multiplier | Moving Average Time (초) |
| -------------------------------------------------- | ---- | --------------------- | ----------------------- |
| Fiat Redeemable Stablecoins(법정화폐 상환형 스테이블코인)       | 1000 | 10                    | 600                     |
| Crypto Collateralized Stablecoins(암호화폐 담보형 스테이블코인) | 100  | 12.5                  | 600                     |
| Liquid Restaking Tokens(유동성 리스테이킹 토큰)              | 500  | 10                    | 600                     |

<br>

어떤 것을 골라야 할지 모르겠나요?

* USDC/USDT 같은 페어에는 Fiat Redeemable Stablecoins를 사용하세요
* 알고리즘 또는 암호화폐 담보 스테이블코인에는 Crypto Collateralized Stablecoins를 사용하세요
* stkBNB/WBNB 같은 LRT 페어에는 Liquid Restaking Tokens를 사용하세요.

<br>

5\. 초기 유동성을 공급할 예치 수량을 입력합니다. 두 토큰의 수량이 같아야 합니다(예: 1 USDC와 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20(4).png" alt=""><figcaption></figcaption></figure>

<br>

6\. Preview Pool을 클릭하고 설정을 검토한 뒤 확인 체크박스를 선택하고 Create Pool을 클릭합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20(5).png" alt=""><figcaption></figcaption></figure>
