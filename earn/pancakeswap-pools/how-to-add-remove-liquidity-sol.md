# 유동성 추가 / 제거 방법 (SOL)

"유동성"은 PancakeSwap 거래소가 작동하는 핵심 요소입니다. 유동성 페이지에서 두 토큰을 모두 스테이킹하여 어떤 토큰 쌍에도 유동성을 추가할 수 있습니다.

유동성을 추가하면 해당 쌍의 거래 수수료와 (해당되는 경우) 파밍 보상을 받게 됩니다.

PancakeSwap V3에서는 **집중 유동성**을 공급할 수 있습니다. 즉, 유동성이 활성화되는 가격 범위를 직접 선택합니다. 이를 통해 자본을 어떻게 사용할지 더 세밀하게 제어하고 효율을 높일 수 있습니다.

{% hint style="warning" %}
**참고:** 이 가이드에 표시된 이미지는 설명을 위한 것이며 실시간 데이터나 현재 풀 통계를 반영하지 않을 수 있습니다.
{% endhint %}

***

## 유동성 추가

유동성을 추가하는 방법은 두 가지입니다.

* **옵션 1:** 기존 풀에 추가
* **옵션 2:** 이미 만든 포지션에 토큰 추가

***

### 옵션 1: 기존 풀에 추가

#### 1단계: 풀 목록 페이지로 이동

여기에서 Solana의 모든 활성 V3 풀을 확인할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28386%29.png" alt=""><figcaption></figcaption></figure>

#### 2단계: 필터를 사용해 풀 찾기

페이지 상단의 필터를 사용해 다음을 할 수 있습니다.

*   특정 토큰 쌍 **검색**<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28387%29.png" alt=""><figcaption></figcaption></figure>
*   **레이아웃 보기 변경** (그리드/리스트)<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28388%29.png" alt=""><figcaption></figcaption></figure>
*   TVL, 거래량, 수수료, APR 기준으로 **풀 정렬**<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28389%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
풀을 생성한 직후에 바로 표시되지 않는다면 최대 5분까지 기다려 주세요. TVL, 거래량, 수수료, APR 통계는 풀에서 스왑이 이루어지는 동안 약 15분마다 업데이트됩니다.
{% endhint %}

#### 3단계: 유동성 추가 방법 선택

다음 중 한 가지 방법으로 시작할 수 있습니다.

*   풀 카드에서 **"Deposit"** 클릭<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28390%29.png" alt=""><figcaption></figcaption></figure>
*   또는 "My Positions" 아래의 **"Create New Position"** 클릭<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28391%29.png" alt=""><figcaption></figcaption></figure>

#### 4단계: 가격 범위 설정

V3 풀이므로 유동성의 가격 범위를 선택해야 합니다.

*   **빠른 프리셋 범위**(예: +- 25%)를 사용하거나 직접 범위를 설정하세요<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28392%29.png" alt=""><figcaption></figcaption></figure>
*   **가격 방향 전환 토글**로 기준/상대 토큰 보기를 전환하세요<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28393%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
다음과 같은 경우 **경고**를 확인하세요.

* 선택한 범위가 시장 가격과 멀리 떨어져 있는 경우
* 풀의 유동성이 낮은 경우
{% endhint %}

#### 5단계: 예치 수량 입력

공급할 토큰 수량을 입력합니다

\*\* 두 토큰의 수량을 모두 입력해야 APR이 표시됩니다

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28394%29.png" alt=""><figcaption></figcaption></figure>

#### 6단계: 미리보기 및 확인

*   **"Add Liquidity"** 클릭

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28396%29.png" alt=""><figcaption></figcaption></figure>
*   미리보기 창에서 포지션을 검토합니다<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28397%29.png" alt=""><figcaption></figcaption></figure>

확인하면 트랜잭션이 제출되고 포지션이 생성됩니다!

***

### 옵션 2: 기존 포지션에 유동성 추가

#### 1단계: "My Positions"로 이동

여기에서 모든 활성 V3 유동성 포지션을 확인할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28398%29.png" alt=""><figcaption></figcaption></figure>

#### 2단계: "+" 버튼 클릭

현재 가격 범위에 토큰을 더 추가할 수 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28399%29.png" alt=""><figcaption></figcaption></figure>

#### 3단계: 예치 수량 입력

원하는 토큰 수량을 입력하고 **"Confirm"**을 클릭합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28400%29.png" alt=""><figcaption></figcaption></figure>

확인하면 성공 메시지가 표시됩니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28401%29.png" alt=""><figcaption></figcaption></figure>

***

## 유동성 제거

**My Positions** 탭에서 바로 활성 포지션의 유동성을 제거할 수 있습니다.

#### 1. **My Positions**로 이동

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28402%29.png" alt=""><figcaption></figcaption></figure>

#### 2. 유동성을 제거할 포지션 선택

포지션 옆의 **"−"** 아이콘을 클릭합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28403%29.png" alt=""><figcaption></figcaption></figure>

#### 3. 제거할 수량 입력

다음 중 한 가지를 선택할 수 있습니다.

* 토큰 수량을 직접 입력
* **또는** **슬라이더**를 사용해 현재 포지션의 비율 선택

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28404%29.png" alt=""><figcaption></figcaption></figure>

#### 4. (선택 사항) 유동성 제거 후에도 포지션 유지

유동성의 **100%**를 제거할 때 **"Keep my position open"**을 선택하면:

* 토큰은 출금됩니다
* 하지만 포지션의 내역과 처음 설정한 가격 범위는 **My Positions**에 **그대로 표시됩니다**

가격 범위 표시를 포함해 포지션을 **완전히 닫으려면**:

* **"X"** 아이콘을 클릭하세요

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28408%29.png" alt=""><figcaption></figcaption></figure>

#### 5. 동일한 가격 범위 재사용

처음 유동성을 추가했을 때와 같은 단계를 따라 나중에 동일한 가격 범위에 **유동성을 더 추가**할 수도 있습니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28409%29.png" alt=""><figcaption></figcaption></figure>
