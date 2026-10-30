---
description: 클릭 한 번으로 유동성 추가
---

# Zap

### Zap이란 <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap은 유동성을 손쉽게 추가할 수 있게 해주는 기능입니다. Zap을 사용하면 풀에서 요구하는 토큰과 관계없이 잔액이 있는 어떤 토큰으로도 유동성을 공급할 수 있습니다. 가격 범위를 설정하고, 공급할 수량을 선택한 뒤 실행하기만 하면 됩니다. 토큰이 자동으로 균형을 맞춰 유동성 포지션을 구성하며, 가격 영향과 슬리피지가 가장 낮은 가장 효율적인 방식으로 거래됩니다.

### 지원되는 체인

* v3 - BNB Chain과 Robinhood Chain의 모든 풀, Ethereum 및 Arbitrum 네트워크의 일부 풀
* Infinity - BNB Chain의 모든 CLAMM 풀(훅 없음)

### 사용 방법 <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

현재 Zap은 다음을 지원합니다.

* 🆕 모든 토큰!
* 단일 토큰 사용
* 🆕 두 개의 토큰 사용
* 🆕 또는... 여러 토큰 사용 (네, 먼지 토큰 수집기처럼 쓸 수 있습니다)

#### 시작하기 <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Zap을 사용하려면 유동성 추가 페이지로 이동해 유동성을 공급할 거래 쌍, 수수료 등급, 가격 범위를 선택하세요.

그런 다음 유동성을 공급할 토큰 수량을 선택합니다.

하나 이상의 토큰 잔액이 부족하면 Zap 옵션이 자동으로 표시됩니다.

링크를 클릭하면 Zap 창이 열립니다.

#### Zap 시작 <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

새로운 "Zap in" 창에는 다음 항목이 표시됩니다.

1. Zap(유동성 공급)할 거래 쌍
2. 예치할 토큰과 예치 수량. Zap에 사용할 토큰을 자유롭게 추가하거나 제거할 수 있습니다.
3. 새 포지션의 가격 범위. 화살표를 클릭해 다른 가격 표시 방식으로 전환할 수도 있습니다.
4. Zap 기능이 예치 토큰을 어떻게 처리하는지에 대한 상세 내역
5. 다음을 포함한 통계 요약
   1. 새 유동성 포지션의 USD 추정 가치
   2. 새 유동성 포지션의 추정 토큰 수량
   3. Zap 후 남는 자금의 USD 추정액. 대부분의 경우 0이어야 합니다. 유동성 풀이나 토큰의 유동성이 매우 적으면 이 값이 늘어날 수 있습니다.
   4. Zap 중 토큰 스왑 및 재조정에 따른 가격 영향
   5. 유동성 추가 및 포지션 구성에 따른 가격 영향
   6. Zap 수수료. 유동성 쌍에 따라 수수료율이 다를 수 있습니다.

{% hint style="warning" %}
보유 잔액에 맞춰 Zap할 수량을 다시 설정해야 할 수 있습니다. 토큰 중 하나의 잔액이 없다면 해당 토큰을 제거하세요.
{% endhint %}

{% hint style="info" %}
"V3 유동성 추가"의 설정이 Zap 창에 자동으로 반영되는 것을 볼 수 있습니다. 예치 수량과 가격 범위 설정도 포함됩니다.
{% endhint %}

#### Zap 실행 <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

마지막으로 "Approve"를 클릭하고 지갑 팝업에서 토큰 사용 승인을 확인합니다.

그런 다음 "Preview"를 클릭해 최종 확인 창을 엽니다. 진행하기 전에 최종 확인 창에 표시된 모든 통계와 추정치를 꼼꼼히 검토해 주세요. 특히 가격 영향 수치와 최대 슬리피지를 확인하세요.

마지막으로 "Add Liquidity"를 클릭하고 지갑 팝업에서 확인합니다.

트랜잭션이 확정되면 "My Position" 페이지에서 새로 생성된 포지션을 확인할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### 추가 설정 <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Zap 환경을 더 세부적으로 설정하려면 오른쪽 상단의 톱니바퀴 아이콘을 클릭하세요. 설정에서 다음 항목을 구성할 수 있습니다.

* Zap 중 최대 슬리피지
* 트랜잭션 마감 시간
* 토큰 재조정에 KyberSwap의 애그리게이터 유동성을 사용할지 여부. PancakeSwap 풀에서만 거래하려면 이 옵션을 끄세요.
* Degen 모드는 슬리피지가 매우 높은 Zap을 수행할 때 사용할 수 있습니다. 일반적인 사용 사례에는 권장되지 않으며, 사용에 따른 책임은 본인에게 있습니다.

{% hint style="warning" %}
슬리피지와 마감 시간 설정은 스왑 및 유동성 페이지의 설정과 별개라는 점에 유의하세요.
{% endhint %}

#### 두 개의 토큰으로 Zap in

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

이제 두 개의 토큰으로 유동성을 Zap in 할 수 있습니다. 보유 잔액이 가격 설정과 그에 따라 요구되는 토큰 수량 및 비율과 맞지 않을 때 유용합니다. Zap을 실행하기만 하면 비율이 자동으로 재조정됩니다.

#### 여러 토큰으로 Zap in

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

네, 먼지 토큰 수집기처럼 작동합니다. 지갑에 남은 소액 잔액을 정리하고, 이를 하나의 포지션에 넣어 거래 수수료 수익을 얻기 시작하는 데 적합합니다.&#x20;

