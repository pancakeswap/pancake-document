# 자주 묻는 질문 (FAQ)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### bCAKE 배수는 어떻게 계산되나요?

파밍마다 서로 다른 bCAKE 부스트 배수를 받는 것을 볼 수 있습니다.

bCAKE - 파밍 부스터의 배수는 활성화 또는 새로고침 시점에 다음 지표를 사용해 계산되기 때문입니다.

* `userLpBalanceInFarm` : 파밍에 스테이킹한 유동성의 양입니다.
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : 파밍에 스테이킹된 유동성의 총량 또는 V3 LP 풀에서 현재 활성 상태인 유동성의 양입니다. bCAKE는 두 값 중 더 작은 값을 선택합니다.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : 보유한 veCAKE의 실시간 수량입니다.
* `veCAKE.totalSupply` : veCAKE의 실시간 총 공급량입니다.

배수는 다음 방식으로 계산됩니다.

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA`와 `constantB`는 키친이 설정하며, 커뮤니티 의견과 시장 상황에 따라 향후 조정될 수 있습니다. `constantB`는 LP 가격 차이를 보정하기 위해 파밍마다 다릅니다.

`constantA`와 `constantB`는 다음을 통해 조회할 수 있습니다.

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

다만 다음 사항에 유의하세요.

{% hint style="info" %}
**요약**

부스트하려는 LP(유동성)가 많을수록

더 많은 CAKE를 더 오랜 기간 락업해야 합니다
{% endhint %}

### 활성화한 후에도 배수가 바뀌는 이유는 무엇인가요?

**파밍 포지션 또는 CAKE 스테이킹 풀에서 사용자가 어떤 작업을 하면 파밍과 CAKE 스테이킹 풀의 최신 데이터 및 통계를 기준으로 부스트 배수가 자동으로 업데이트된다**는 점에 유의하세요. 다음 작업이 이에 해당하며 이에 한정되지 않습니다.

* 파밍에 포지션 스테이킹/언스테이킹
* 파밍에서 CAKE 보상 수확
* CAKE 스테이킹 기간 연장
* 고정 기간 스테이킹 포지션에 CAKE 추가
* CAKE 스테이킹 포지션을 유연형으로 전환

{% hint style="warning" %}
참고하세요.

오래된 데이터를 이용한 악용과 부정행위를 방지하고 공정성을 보장하기 위해, 파밍 부스터는 퍼미션리스(permissionless)이며 커뮤니티 거버넌스로 운영되도록 설계되었습니다. 따라서 **누구나** MasterChef V3 컨트랙트의 `updateLiquidity(address _tokenId)` 함수를 호출하여 최신 데이터로 다른 사용자의 부스트 배수를 새로고침할 수 있습니다.

이에 더해 키친도 bCAKE가 활성화된 모든 파밍 포지션을 모니터링하며, 배수가 오래된 포지션은 새로고침합니다.
{% endhint %}

### 포지션을 부스트할 수 없는 이유는 무엇인가요?

1. 파밍 부스터는 선택된 파밍에서만 이용할 수 있습니다. 앞으로 더 많은 파밍이 추가될 예정입니다. 현재는 **녹색 로켓 아이콘이 있는 녹색 APR 수치를 찾아보세요.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. 여러 컨트랙트가 관여하기 때문에 일부 컨트랙트 상호작용에는 약간 더 많은 가스 토큰(BNB)이 필요합니다. 지갑에 BNB가 충분한지 확인하세요. 오류가 계속되면 트랜잭션의 가스 한도를 수동으로 늘려 보세요.

### 받을 수 있는 bCAKE 부스트 배수의 최대치는 얼마인가요?

현재 사용자가 파밍 부스터로 받을 수 있는 최대 부스트는 2.5배이며, 이는 원래 APR의 2.5배를 제공합니다.

스테이킹하려는 유동성 유형에 따라 받을 수 있는 최대 부스트가 다르다는 점에 유의하세요.

* V3: 최대 2배
* V2, StableSwap: 최대 2.5배
* 포지션 매니저: 최대 2.5배

### bCAKE 부스트 배수를 높이려면 어떻게 해야 하나요?

* veCAKE 스테이킹 포지션에 CAKE 추가
* veCAKE 스테이킹 포지션의 기간 연장 또는 갱신

간단히 말해 다음과 같습니다.

**더 많은 CAKE를, 더 오래 스테이킹하세요**

[bCAKE 부스트 배수 계산 방식 자세히 알아보기](faq.md#how-are-the-bcake-multipliers-calculated).

### 추가로 부스트된 CAKE 보상은 어디서 나오나요?

**걱정하지 마세요. bCAKE를 가능하게 하기 위해 추가 발행량이 할당되지는 않습니다.**

veCAKE CAKE 스테이킹과 마찬가지로 bCAKE는 개별 사용자의 지분을 다른 사용자 대비 부스트합니다.

bCAKE 도입 이후 기본 APR이 하락할 수 있지만, 셰프들은 이것이 충성도 높은 CAKE 애호가의 파밍 수익을 높여 주고, CAKE 수요를 늘리며, CAKE 스테이킹에 대한 훌륭한 인센티브가 되므로 좋은 절충안이라고 생각합니다.

### 제가 받는 배수가 낮은 이유는 무엇인가요?

bCAKE - 파밍 부스터는 veCAKE 스테이킹 포지션과 유동성 파밍 포지션을 다른 사용자와 비교하여 평가하는 방식으로 작동합니다. 간단히 말해 다음과 같습니다.

> 사용자가 파밍에서 더 많은 유동성을 부스트하려면 풀에 더 많은 CAKE를 더 오랜 기간 락업해야 합니다.

이러한 설계는 큰 보유자뿐 아니라, 파밍 포지션에 비해 상당한 규모의 CAKE 스테이킹 포지션을 가진 모든 사용자에게 혜택이 돌아가도록 보장합니다.

배수 계산 방식에 대한 자세한 내용은 [여기](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated)를 참고하세요.

### 부스터를 이용할 수 있는 파밍이 몇 개뿐인 이유는 무엇인가요?

bCAKE는 PancakeSwap의 핵심 제품 중 하나인 유동성 파밍을 업데이트하는 것이므로, 셰프들은 더 느리고 안정적인 방식으로 출시하고자 합니다.

따라서 초기 제품 출시 단계에서는 많은 파라미터가 매우 보수적으로 설정되어 있습니다. 사용자가 부스트할 수 있는 파밍의 수, 부스트할 수 있는 파밍의 종류, 부스트 배수를 받기 위한 난이도 파라미터 등이 여기에 포함됩니다.

**셰프들은 커뮤니티 의견에 따라 파라미터를 조정할 예정입니다.**

### **bCAKE V3는 감사를 받았나요?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE는 내부 및 외부 감사자 모두에게 감사를 받았습니다.

감사 보고서는 여기에서 확인하세요: [https://docs.pancakeswap.finance/welcome-to-pancakeswap/audits](https://docs.pancakeswap.finance/welcome-to-pancakeswap/audits)
