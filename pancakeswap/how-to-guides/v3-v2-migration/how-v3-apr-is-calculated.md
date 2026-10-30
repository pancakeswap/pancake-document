# v3 APR 계산 방식

{% hint style="info" %}
V3 유동성 및 파밍에서는 새로운 대체 불가능(non-fungible) 유동성과 사용자 지정 가격 범위 기능이 도입되어, 각 LP 포지션마다 고유한 LP 수수료 및 CAKE 파밍 APR을 갖습니다.
{% endhint %}

총 APR은 LP 수수료 APR과 CAKE 보상 APR을 합산한 값입니다.

### LP 수수료

이론적으로, 사용자가 추가하려는 가격 범위와 유동성이 주어지면 향후 7일간 예상 수수료를 다음과 같이 추정할 수 있습니다.

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : 최근 7일간 사용자가 지정한 가격 범위에서 발생한 수수료 금액
* $$L_{in}$$: 사용자가 지정한 가격 범위의 현재 유동성
* $$\Delta{L}$$: 사용자가 해당 가격 범위에 추가하려는 유동성

#### 범위 내 수수료

$$fee_{in}$$은 과거 거래량 데이터, 수수료 등급, 과거 가격 데이터를 사용하여 범위 내 가격을 추정합니다.

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: 수수료 등급
* $$V_{7d}$$: 최근 7일간의 총 거래량
* $$T_{in}$$: 지난 7일 동안 가격이 해당 가격 범위 내에 머문 시간(초 단위)
* $$T_{7d}$$: 7일을 초 단위로 환산한 값

### CAKE APR

#### 풀 할당

MC v3에서 업킵(upkeep)을 사용하는 초당 총 CAKE 보상은 `latestPeriodCakePerSecond`로 구할 수 있습니다.

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

각 풀에서는 `poolInfo`를 사용하여 `poolInfo.allocPoint / totalAllocPoint`로 나누어 `poolWeight`를 구할 수 있습니다.

#### 글로벌 CAKE APR

글로벌 APR은 활성 상태로 스테이킹된 유동성의 총량과 풀의 CAKE 보상 배출량을 사용하여 계산합니다.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD`는 MasterChef v3에 스테이킹된 범위 내 모든 포지션 틱으로 구성된, 현재 풀의 활성 스테이킹 유동성을 USD로 나타낸 값입니다.

#### 포지션별 CAKE APR

개별 포지션의 APR은 가격 범위 설정에 따라 달라질 수 있습니다.

$$
APR_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: 풀에서 연간 받는 CAKE 보상의 USD 가치
* $$USD_p$$: 포지션의 총 USD 가치
* $$L_{p}$$: 포지션 유동성
* $$L_{lm}$$: LMPool이 추적하는 총 스테이킹 유동성
