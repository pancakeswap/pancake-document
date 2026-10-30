# APR/ROI/IL 계산기

v3 유동성과 파밍에서는 새로운 대체 불가능 유동성과 사용자 지정 가격 범위 기능으로 인해 각 LP 포지션마다 고유한 LP 수수료 및 CAKE 파밍 APR을 갖게 됩니다.

유동성 공급을 더 원활하고 쉽게 만들기 위해, 유동성을 공급하거나 파밍할 때마다 새로운 ROI 계산기와 함께 새로운 자동 APR 표시를 사용할 수 있습니다.

## 자동 APR 계산 및 표시 <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(293).png" alt=""><figcaption></figcaption></figure>

유동성을 공급할 때 자동 APR 표시는 설정 변경에 반응하여 사용자의 설정을 기반으로 APR을 계산합니다.

예를 들어 대부분의 경우 가격 범위 설정을 좁히면 APR이 올라갑니다.

LP 수수료 APR에 대한 참고 사항:

* LP 수수료 보상의 예상 금액은 선택한 수수료 등급에 따라 달라지며, 수수료 보상은 수동으로 수령하고 복리 투자해야 합니다.
* APR 수치는 과거 거래량을 사용하여 계산되며, 이는 Subgraph에 의존하므로 인덱싱 지연이 있을 수 있습니다.

파밍 APR에 대한 참고 사항:

* CAKE 보상의 예상 금액은 파밍에 대한 실시간 CAKE 배출량을 기반으로 합니다. 향후 배출량 조정에 따라 변경될 수 있습니다.

{% hint style="info" %}
수치는 현재 비율과 풀 상태를 기준으로 계산되며 다양한 외부 변수에 따라 변경될 수 있습니다. 이는 편의를 위해 제공되는 추정치일 뿐이며, 어떠한 경우에도 수익을 보장하지 않습니다.
{% endhint %}

이 APR 표시는 다음 위치에서 찾을 수 있습니다.

* "Add Liquidity" 페이지 - LP 수수료 APR 표시
* 기존 각 유동성 포지션의 상세 페이지 - LP 수수료 APR 표시\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(326\).png)
* 파밍 페이지의 각 파밍 아래 포지션 내 - LP 수수료와 CAKE 보상을 합산한 APR 표시\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(138\).png)<br>

## 개선된 ROI 계산기 <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(146).png" alt=""><figcaption></figcaption></figure>

자동 APR 표시가 보일 때마다 클릭하여 새로운 ROI 계산기를 열 수 있습니다. 새로운 ROI 계산기는 v3 집중 유동성 공급과 파밍의 요구에 맞게 여러 기능이 추가되어 재설계되었습니다.

각 섹션을 함께 살펴보겠습니다.

### 예치 금액, "Staked For", "Compounding Every" <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

이 세 가지는 기본 입력값으로, 이전 ROI 계산기에도 있었습니다. 다음을 정의하기 위한 것입니다.

1. 유동성 포지션에 공급하는 자산의 양(USD 기준)
2. 해당 자산을 포지션에 스테이킹할 기간
3. 보상을 포지션에 복리 투자하는 빈도

⓵ **예치 금액**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

USD 금액을 직접 입력하거나, 빠른 실행 버튼을 사용하여 $100, $1000 또는 지갑의 토큰 잔액을 기준으로 허용되는 최대 금액을 빠르게 입력할 수 있습니다.

⓶ **스테이킹 기간**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

1일, 7일, 30일, 1년, 5년 중에서 선택하여 자산을 유동성 포지션에 스테이킹할 기간을 설정할 수 있습니다.

수익은 스테이킹 기간을 기준으로 계산됩니다.

⓷ **복리 투자**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

포지션에서 발생한 보상을 수확하여 포지션에 복리 투자하는 빈도를 선택할 수 있습니다. 12시간, 1일, 7일, 30일 중에서 선택할 수 있습니다.

수익과 APY는 선택에 따라 계산됩니다. 포지션에 복리 투자할 계획이 없다면 왼쪽의 체크박스를 해제하세요.

{% hint style="info" %}
v3에서는 LP 수수료와 획득한 CAKE를 수동으로 수확하고 복리 투자해야 합니다.
{% endhint %}

### ⓸ 과거 가격 <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(305\).png)

선택한 페어의 과거 가격 변동을 참고할 수 있는 보기 전용 섹션입니다.

다양한 기간의 과거 가격 변동을 참고하여 가격이 보통 얼마나 변동하는지 파악하고, 더 높은 APR과 더 낮은 비영구적 손실 위험 사이에서 균형을 이루는 적절한 가격 범위 설정을 정할 수 있습니다.

* MIN - 최저 가격
* MAX - 최고 가격
* AVG - 평균 가격
* CURRENT - 현재 가격

{% hint style="info" %}
가격 차트는 실제 v3 페어의 데이터만 사용합니다. 따라서 v3 배포 이전의 가격 데이터는 제공되지 않습니다. 네 가지 가격 지표는 현재 선택한 기간을 나타내며 선택에 따라 변경됩니다.
{% endhint %}

### ⓹ 가격 범위 <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

이 섹션에서는 다양한 가격 범위에 얼마나 많은 유동성이 예치되어 있는지 확인하고, 유동성을 공급할 가격 범위를 정하고 설정할 수 있습니다.

제목 아래에서 분포 차트를 확인할 수 있습니다. 유동성의 양이 많을수록 차트가 높아집니다.

다음과 같은 방법으로 가격 범위 설정을 변경할 수 있습니다.

* 차트의 두 핸들을 드래그하여 최소 및 최대 가격 한도를 늘리거나 줄입니다.
* 두 핸들 사이의 공간을 사용하여 선택한 범위를 이동합니다.
* 최소 및 최대 가격 필드의 + 및 - 버튼을 클릭합니다.
* 가격 필드의 숫자를 클릭하여 직접 입력합니다.

분포 차트를 탐색하려면 다음을 사용하세요.

1. 플러스 및 마이너스 돋보기 버튼으로 확대 및 축소합니다.
2. X(하단) 축을 드래그하여 좌우로 이동합니다.

전체 가격 범위에 유동성을 공급하려면 "Full Range"를 클릭하세요.

### ⓺ 가격 방향을 전환하여 다른 기준으로 가격 보기 <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

일부 토큰 페어는 특정 기준 토큰으로 가격을 보는 것이 더 쉽고 직관적입니다. 예를 들어 BNB/USDT 페어의 경우 대부분의 사람들은 그 반대보다 "BNB당 USDT 수량"으로 가격을 보는 것을 선호합니다.

가격 표시를 쉽게 전환할 수 있습니다. "View prices in:" 옆의 버튼을 클릭하기만 하면 페어의 두 토큰 간에 기준을 전환할 수 있습니다.

### ⓻ 설정 가져오기 및 내보내기(적용) <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

"Add Liquidity" 창에서 또는 기존 포지션을 보면서 ROI 계산기를 열면 다음 설정이 자동으로 가져와지므로 다시 설정할 필요가 없습니다.

1. 예치하는 자산의 양
2. 가격 범위
3. 선택한 수수료 등급

ROI 계산기에서 설정을 마치면 "Apply Settings"를 클릭하여 계산기의 설정을 "Add Liquidity" 창에 빠르게 적용할 수 있으므로 수동으로 맞출 필요가 없습니다.

### ⓼ 파밍 보상 및 APR 계산 <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

"Farm" 페이지에서 ROI 계산기를 열면 파밍 보상이 계산에 포함됩니다.

상세 섹션을 펼쳐 보상 내역을 확인할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(156).png" alt=""><figcaption></figcaption></figure>
