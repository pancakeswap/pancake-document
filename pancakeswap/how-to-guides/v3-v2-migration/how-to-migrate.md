---
description: 유동성과 파밍 스테이킹을 새로운 PancakeSwap Exchange 및 Farm V3로 마이그레이션하세요
---

# 마이그레이션 방법

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(133).png" alt=""><figcaption></figcaption></figure>

2023년 4월, PancakeSwap은 Exchange와 Farm의 V3를 발표했습니다. 스테이킹 보상을 계속 받으려면 일부 파밍 페어는 마이그레이션이 필요합니다. 걱정하지 마세요. 지난번처럼 원활하게 진행될 것입니다.

### 잠깐! 마이그레이션이 필요한가요? <a href="#id-4b9e0260-9dee-493b-b0ad-6bdba084cea6" id="id-4b9e0260-9dee-493b-b0ad-6bdba084cea6"></a>

다음 조건에 해당하면 마이그레이션이 필요합니다.

**다음 V2 PancakeSwap 파밍에서 파밍 중인 경우:**

* BNB 체인:
  * CAKE-BNB
  * CAKE-BUSD
  * CAKE-USDT
  * BUSD-BNB
  * USDT-BNB
  * BTCB-BUSD
  * BTCB-USDT
  * BTCB-ETH
  * BTCB-BNB
  * ETH-BNB
  * ETH-USDC
  * USDC-USDT
  * BUSD-USDC
  * BUSD-USDT
* Ethereum:
  * ETH-USDC
  * ETH-USDT
  * WBTC-ETH

이 목록은 앞으로 늘어날 수 있습니다. 최신 목록을 가장 쉽게 확인하려면 [https://pancakeswap.finance/migration](https://pancakeswap.finance/migration)을 방문하여 지갑을 연결하세요.

**V2 유동성을 공급 중이며 다음 조건에 해당하는 경우:**

* 해당 토큰 페어 유동성의 대부분이 V3로 마이그레이션된 경우 - 자세한 내용은 PancakeSwap Info 페이지 또는 해당 토큰 프로젝트의 웹사이트나 소셜 채널을 확인하세요.
* 해당 토큰의 프로젝트 팀이 유동성을 V3로 마이그레이션한다고 발표한 경우 - 자세한 내용은 각 프로젝트의 웹사이트나 소셜 채널을 확인하세요.

### 마이그레이션 방법 <a href="#c7d7b407-268c-460c-a4f1-be1b771db5e7" id="c7d7b407-268c-460c-a4f1-be1b771db5e7"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(283).png" alt=""><figcaption></figcaption></figure>

유동성 또는 파밍 페이지에서 V3 마이그레이션 배너를 찾으세요. 그다음 "Proceed"(진행)를 클릭하여 마이그레이션 도우미 페이지로 이동합니다.

**1단계 - V2 및/또는 StableSwap 파밍에서 언스테이킹**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(119).png" alt=""><figcaption></figcaption></figure>

1단계에서는 마이그레이션이 필요한 모든 PancakeSwap V2 또는 StableSwap 파밍이 도우미에 목록으로 표시됩니다.

각 "Unstake All"(모두 언스테이킹) 버튼을 클릭하여 파밍에 스테이킹된 모든 LP 토큰을 언스테이킹하세요. 지갑에서 확인을 요청합니다.

목록에 있는 모든 파밍의 언스테이킹이 끝나면 "Next Steps"(다음 단계)를 클릭하여 진행하세요.

**2단계 - Exchange V2 또는 StableSwap에서 유동성 제거**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(315).png" alt=""><figcaption></figcaption></figure>

2단계에서는 CAKE 일드 파밍과 함께 V3로 마이그레이션할 수 있는 모든 유동성 포지션이 도우미에 목록으로 표시됩니다.

각 "Remove"(제거) 버튼을 클릭하면 100%가 선택된 유동성 제거 창이 열립니다.

그다음 "Enable"(활성화)을 클릭하고 지갑에서 트랜잭션에 서명한 후 "Remove"를 클릭하세요. 지갑에서 확인을 요청합니다.

{% hint style="info" %}
다른 일부 프로젝트 토큰도 V3로 마이그레이션하지만 이 목록에는 표시되지 않습니다. 자세한 내용은 각 프로젝트의 웹사이트나 소셜 채널을 확인하세요. 그리고 [유동성](https://pancakeswap.finance/liquidity) 페이지를 사용하여 수동으로 마이그레이션하세요.
{% endhint %}

**3단계 - V3 준비하기**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(186).png" alt=""><figcaption></figcaption></figure>

별도의 조치는 필요하지 않습니다. V3의 작동 방식과 V3에서 유동성을 공급하는 방법을 읽고 충분히 숙지하세요.

**4단계 - V3 유동성 추가**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20\(325\).png)

이 단계에서는 새로운 Exchange V3에 유동성을 추가합니다.

"Add Liquidity"(유동성 추가)를 클릭하세요. 이전에 제거한 V2 유동성이 목록에 표시되며, "Add"(추가)를 클릭하면 V3 유동성 추가 화면이 열립니다.

추가하려는 페어가 보이지 않으면 "Add Other Pairs"(다른 페어 추가)를 클릭하고 두 토큰을 직접 선택하세요.

V3에서 유동성을 공급하는 방법에 대한 더 자세한 튜토리얼은 [여기](../../../undefined-2/pancakeswap-pools/liquidity-guide.md)를 참고하세요.

V3에서 유동성을 공급하는 중 궁금한 점이 있다면 [자주 묻는 질문 (FAQ)](../../../undefined/trading-faq/swap-faq.md)을 확인하세요.

{% hint style="warning" %}
Exchange V3에서는 활성(범위 내) 유동성 포지션만 거래 수수료 보상을 받는다는 점에 유의하세요.

유동성 포지션의 가격 범위를 설정할 때 신중하게 결정하세요.
{% endhint %}

**5단계 - V3 파밍에 스테이킹**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(35).png" alt=""><figcaption></figcaption></figure>

이 단계에서는 새로 추가한 V3 유동성 포지션을 새로운 V3 파밍에 스테이킹하여 CAKE 보상을 받기 시작합니다!

포지션의 각 "Stake"(스테이킹) 버튼을 클릭하여 파밍에 스테이킹하세요. 지갑에서 확인을 요청합니다.

V3에서 파밍하는 방법에 대한 더 자세한 튜토리얼은 [여기](../../../undefined-2/yield-farming/how-to-use-farms/#farm-v3)를 참고하세요.

V3 파밍에 유동성을 스테이킹하는 중 궁금한 점이 있다면 [자주 묻는 질문 (FAQ)](../../../undefined-2/earn-faq/farming-faq.md)을 확인하세요.

{% hint style="warning" %}
Farm V3에서는 활성(범위 내) 유동성 포지션만 CAKE 보상을 받는다는 점에 유의하세요.

유동성 포지션의 가격 범위를 설정할 때 신중하게 결정하세요.
{% endhint %}

**완료**

이제 모두 끝났습니다. 파밍 스테이킹과 유동성을 새로운 PancakeSwap V3로 성공적으로 마이그레이션했습니다!
