---
description: veCAKE로 투표하여 CAKE 발행량의 분배 방식을 결정하세요
hidden: true
---

# 게이지 투표

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(11).png" alt=""><figcaption></figcaption></figure>

#### 게이지란 무엇인가요?

게이지 투표를 이해하려면, CAKE 발행량이 필요한 모든 제품을 일련의 게이지로 생각하면 됩니다. 여기에는 파밍, CAKE 주간 보상 풀, 포지션 매니저 볼트 등이 포함됩니다.

이제 veCAKE 보유자는 veCAKE를 투표권으로 사용하여 CAKE의 몇 %가 어떤 제품으로 갈지 결정할 수 있습니다. 게이지 투표를 통해 게이지에 veCAKE가 많이 쌓일수록 해당 유동성 풀 / 포지션 매니저 볼트에 더 많은 CAKE 발행량이 할당됩니다.

{% hint style="info" %}
각 Epoch(E-0)의 투표는 다음 Epoch(E+1)의 CAKE 발행량을 결정하며, 이러한 변경 사항은 현재 Epoch가 종료된 후에만 적용됩니다.
{% endhint %}

#### 게이지 유형

게이지에는 '코어(core)'와 '논코어(non-core)'의 두 가지 유형이 있습니다. 코어 게이지에 대한 CAKE 발행량은 키친이 관리하며, 커뮤니티는 veCAKE로 투표하여 '논코어' 풀에 대한 발행량에 영향을 미칩니다.

1. '코어' 게이지에는 주요 토큰 및 스테이블코인(WBTC, ETH, BNB, USDC, USDT 등)과의 페어가 포함됩니다. 이러한 페어는 프로토콜 수익에 크게 기여하므로 키친이 충분한 CAKE 보상이 제공되도록 관리합니다
2. '논코어' 게이지는 '코어' 게이지로 분류되지 않은 나머지 모든 게이지를 의미합니다

## 투표 방법

### 1 - 투표 일정 이해하기

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(12).png" alt=""><figcaption></figcaption></figure>

게이지 가중치 투표는 2주마다 진행됩니다. 수익 공유와 마찬가지로 Epoch의 시작은 짝수 주 목요일 00:00 UTC입니다.

위 예시에서는 다음과 같습니다.

* Epoch 1은 1주차 1일 목요일 00:00 UTC에 시작합니다.
* Epoch 1은 2주 후인 3주차 15일 목요일 00:00 UTC에 종료됩니다.
* 사용자는 1일부터 14일까지 00:00 UTC 기준으로 투표할 수 있습니다.
* 14일부터 15일까지 00:00 UTC 동안에는 투표를 **할 수 없습니다**. 이 기간에 투표가 조정되고 집계되기 때문입니다.
* 투표 결과는 15일 00:00 UTC, 즉 Epoch 1이 끝나는 시점에 스냅샷으로 기록됩니다.
* 투표 결과는 Epoch 종료 후 72시간 이내에 적용됩니다.

### 2 - 자격 갖추기

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(12).png" alt=""><figcaption></figcaption></figure>

veCAKE는 남은 락업 기간에 따라 점차 감소하므로, 투표 결과는 매 Epoch가 끝나는 시점의 스냅샷으로 집계됩니다. 여기에는 전체 veCAKE 수량과 각 사용자가 보유한 veCAKE가 포함됩니다.

위 예시에서는 다음과 같습니다.

* Epoch 1의 결과는 15일 00:00 UTC의 veCAKE 잔액을 기준으로 합니다.
* veCAKE 포지션이 15일 이전 또는 15일에 언락되는 사용자는 스냅샷 시점에 veCAKE 잔액이 0입니다. 따라서 Epoch 1에서 투표권이 없습니다.

따라서 자격을 갖추려면 현재 Epoch의 종료/스냅샷 시점보다 **나중에** 언락되는 활성 veCAKE 포지션을 보유해야 합니다.

위 예시에서는 다음과 같습니다.

* Epoch 1에서 투표하려면 21일 또는 그 이후, 즉 3주차 목요일에 언락되는 veCAKE 포지션이 있어야 합니다.

### 3 - 현재 투표 결과 확인하기

"CAKE staking"으로 이동해 아래로 스크롤하여 "Gauges Voting" 섹션을 찾은 다음 "Check Gauges"를 클릭하세요.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(13).png" alt=""><figcaption></figcaption></figure>

왼쪽 상단에서 다음을 확인할 수 있습니다.

* 내 veCAKE
* 현재 Epoch의 스냅샷 시간과 투표 종료 시간
* 현재 Epoch의 투표 결과를 기준으로 다음 Epoch에 분배될 CAKE 보상의 총량
* 투표된 veCAKE 표의 총량

오른쪽 상단에는 각 게이지가 받은 비율(%)을 나타내는 원형 차트가 있습니다.

하단에는 모든 투표 대상 게이지의 전체 목록이 있습니다. 각 게이지가 받은 투표 수와 현재 Epoch에서 얻고 있는 예상 가중치(%)가 표시됩니다. 또한 두 가지 중요한 게이지 특성을 나타내는 "boost"와 "caps" 항목이 있습니다. 자세한 내용은 계속해서 읽어보세요.

#### 게이지 부스트와 발행량 상한

CAKE 보상이 가장 생산적인 게이지로 가도록, 각 게이지에는 부스트 및/또는 발행량 상한이 적용될 수 있습니다. 두 특성은 동시에 존재할 수 있습니다.

게이지 부스트는 게이지가 받은 투표 수에 적용되는 배수로, 1배에서 2.5배까지입니다(V3 풀의 게이지는 최대 2배). 이는 중요한 거래 페어에 대한 투표와 유동성을 장려하기 위한 것입니다.

발행량 상한은 게이지가 받을 수 있는 가중치(%)의 최대 한도로, 2%에서 20%까지입니다. 이는 분배의 공정성을 높이고 게이지 시스템의 악용을 방지하기 위한 것입니다.

예를 들어 다음과 같습니다.

* 어떤 게이지가 10표, 2배 부스트, 15% 상한을 가지고 있고 전체 투표 수는 100표입니다.
* 부스트를 적용하면 이 게이지는 20표가 되어 전체(100)에 대한 가중치가 20%가 됩니다.
* 그러나 15% 상한이 있으므로, 다음 Epoch에서 이 게이지가 받는 최종 CAKE 보상 비율은 15%로 조정됩니다.

#### 게이지 부스트와 발행량 상한은 어떻게 결정되나요?

게이지 신청 과정에서 신청자에게 해당 게이지에 지정하려는 부스트 배수와 발행량 상한(%) 값을 제안하도록 요청합니다. 이 값은 게이지 신청 전체와 함께 veCAKE 보유자의 투표를 거쳐야 합니다.

모든 게이지의 기본 옵션은 1.00배 배수와 5% 발행량 상한이며, 향후 제안을 통해 변경될 수 있습니다.

{% hint style="info" %}
투표 결과는 매주 업데이트된다는 점에 유의하세요. 수치는 다가오는 목요일 00:00 UTC의 veCAKE 잔액을 기준으로 계산됩니다.
{% endhint %}

### 4 - 투표할 게이지 추가하기

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(14).png" alt=""><figcaption></figcaption></figure>

게이지에 투표하려면 아래로 스크롤하여 "My Votes" 섹션을 찾고 "Add Gauge"를 클릭하세요.

팝업 창에서 파란색 "+" 아이콘을 클릭하여 투표 목록에 게이지를 추가할 수 있습니다. 목록에서 부스트 및 상한과 함께 현재 투표 결과를 확인할 수 있습니다.

게이지를 빠르게 찾으려면 블록체인, 수수료 등급, 유동성 유형별로 필터링하거나 검색 필드에 토큰 티커를 입력하세요.

### 5 - 각 게이지에 투표할 veCAKE 비율(%) 선택하기

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(15).png" alt=""><figcaption></figcaption></figure>

게이지를 추가한 후에는 보유한 veCAKE의 몇 %를 각 게이지에 배분할지 선택할 수 있습니다.

그 이유는 다음과 같습니다.

* veCAKE는 남은 락업 기간에 따라 점차 감소합니다. 투표할 정확한 veCAKE 수량을 추정하고 계산하는 것은 현실적이지 않습니다.
* 다가오는 모든 Epoch마다 다시 투표하는 것은 번거롭습니다. 따라서 게이지 투표는 새로 투표할 때까지 이후 모든 Epoch에 투표 결정이 그대로 이어지도록 설계되었습니다.

위 예시에서는 다음과 같습니다.

* 현재 저는 2.62 veCAKE를 보유하고 있습니다.
* CAKE-BNB에 80%를 배분하기로 했으며, 현재 기준 2.10 veCAKE입니다.
* USDC-ETH에는 20%를 배분했으며, 마찬가지로 현재 기준 0.52 veCAKE입니다.
* 제 총 veCAKE는 남은 락업 기간에 따라 점차 감소합니다. 스냅샷 시점에는 veCAKE가 더 적을 수 있지만, 80% - 20% 배분이라는 결정은 최종 결과에 그대로 적용됩니다.
* 게다가 이 80% - 20% 결정은 새 투표 요청으로 업데이트하거나 언락으로 veCAKE가 0이 될 때까지 이후 모든 Epoch에 적용됩니다.

결정을 확인했다면 "Submit vote"를 클릭하고 지갑에서 확인하세요.

### 6 - 투표 업데이트하기

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(17).png" alt=""><figcaption></figcaption></figure>

투표를 제출하면 투표가 "Current Votes"로 업데이트되고 남은 veCAKE도 갱신됩니다.

각 게이지에 대한 투표 결정은 10일마다 한 번만 업데이트할 수 있다는 점에 유의하세요. 투표 요청을 제출하면 투표한 모든 게이지에 10일의 쿨다운 기간이 적용되며, 이후에야 업데이트 요청을 다시 제출할 수 있습니다.

투표 결정을 업데이트하려면 비율(%)을 변경하고 다시 제출하세요.

{% hint style="info" %}
CAKE를 추가하거나 락업 기간을 연장하여 veCAKE가 늘어난 경우, 투표 요청을 다시 제출하여 모든 게이지를 직접 업데이트해야 한다는 점에 유의하세요.

비율 결정을 변경했는지 여부와 관계없이 10일의 쿨다운 기간은 계속 적용됩니다.
{% endhint %}
