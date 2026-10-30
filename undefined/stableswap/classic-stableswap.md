# Classic StableSwap

Classic StableSwap은 Curve Finance의 AMM을 PancakeSwap에 구현한 것입니다. 곱셈 상수 공식(x\*y=k) 위에 선형 불변 합 상수 곡선(x+y=k)을 더하여, 유동성 풀이 극단적으로 불균형하지 않은 한 가격을 더 균등하게 유지합니다. 그 결과 StableSwap은 가격이 비슷한 자산으로 한정되므로 비영구적 손실(IL)은 (극단적인 디페깅 상황을 제외하면) 큰 걱정거리가 아니며, 곱셈 상수 공식만 사용하는 일반 AMM보다 슬리피지가 낮습니다.

StableSwap에서 스왑(거래)을 하면 일반 PancakeSwap AMM의 기본 수수료 0.25%보다 낮은 거래 수수료를 지불합니다. 수수료 배분은 다음과 같습니다.

* 50%는 LP에게 보상으로
* 40%는 CAKE 바이백 및 소각에
* 10%는 PancakeSwap 트레저리에

## Stableswap 수수료

페어별 수수료는 아래 표와 같습니다.

<table><thead><tr><th width="150">스테이블 페어</th><th width="132">거래 수수료</th><th width="118.33333333333331">LP 보상</th><th width="124">CAKE 바이백</th><th>PancakeSwap 트레저리</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-USDT</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>HAY-BUSD</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>HAY-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>axlUSDC-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>BNBx-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>stkBNB-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr></tbody></table>

키친(Kitchen)은 제품을 더욱 테스트하고 개선하기 위해 StableSwap 페어를 점진적으로 출시하고 수수료를 조정할 예정입니다.

## 일반 AMM 스왑 대신 StableSwap을 사용해야 하는 이유는?

* 동일한 거래 단계로 스테이블코인이나 자산 가격이 비슷한 다른 페어를 더 효율적으로 스왑할 수 있습니다
* StableSwap 기능을 사용하면 거래 슬리피지가 일반 AMM보다 낮습니다
* StableSwap 거래 수수료는 일반 AMM보다 저렴합니다
