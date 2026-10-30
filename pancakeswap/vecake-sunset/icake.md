---
description: veCAKE 스테이킹과 IFO 할당
hidden: true
---

# iCAKE

### **새로운 iCAKE란 무엇인가요?**

veCAKE로 전환된 이후, 새로운 iCAKE는 veCAKE 잔액을 기준으로 합니다

* 기존 iCAKE와 마찬가지로 PancakeSwap IFO 공개 판매에서 CAKE를 커밋할 수 있는 최대 한도를 결정합니다. 예를 들어 iCAKE가 200이라면 IFO 공개 판매에서 200 CAKE를 커밋할 수 있습니다.
* 새로운 iCAKE 수치는 각 IFO가 끝나는 시점의 veCAKE 잔액으로 계산됩니다. 따라서 IFO마다 iCAKE 수치가 다를 수 있습니다.
* veCAKE 잔액은 남은 락업 기간에 따라 점차 감소합니다. 따라서 이후 IFO에서의 iCAKE도 veCAKE 잔액과 함께 감소합니다. iCAKE 수치를 유지하려면 스테이킹에 CAKE를 더 추가하거나 락업을 갱신/연장하세요.

**iCAKE는 새로운 토큰이 아니며, PancakeSwap IFO 시스템에서 사용하는 수치 지표입니다.**

### iCAKE는 어떻게 계산되나요?

보유한 iCAKE 수량은 각 IFO가 끝나는 시점의 veCAKE 잔액에 사전에 정해진 비율을 곱한 값입니다.

veCAKE는 락업한 CAKE의 양과 락업의 남은 시간을 기준으로 동적으로 계산되는 값입니다. veCAKE가 어떻게 계산되는지 자세히 알아보려면 [여기](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef)를 확인하세요.

veCAKE 잔액에는 추가 비율이 적용되며, 이 비율은 각 IFO마다 키친이 조정합니다. 예를 들어 비율이 2배이고 다음 IFO가 끝나는 시점에 1 veCAKE를 보유하고 있다면 최대 2 CAKE를 커밋할 수 있습니다.

예시:

* 100 CAKE를 2년간 락업했습니다.
  * 남은 락업 시간은 `2 * 52 * 7 * 24 * 60 * 60 = 62899200` (초)입니다
  * 최대 락업 시간은 `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (초)입니다
  * 현재 시점에서 보유한 veCAKE는 `100 * (62899200 / 126403199) ~= 49.76`입니다
* 바로 다음 IFO가 예정되어 있으며, 종료 시간은 현재 시점으로부터 정확히 1주 후인 `604800`초 뒤입니다.
  * 그 시점에 남은 락업 시간은 `62899200 - 604800 = 62294400` (초)입니다
  * 그 시점에 보유한 veCAKE는 `100 * (62294400 / 126403199) ~= 49.28`입니다
* 이번 IFO의 비율은 `3x`로 설정되었습니다
* 따라서 이번 IFO에서 보유한 iCAKE는 `49.28 * 3 = 147.84`이며, 이는 공개 판매에서 최대 147.84 CAKE를 커밋할 수 있다는 의미입니다.

### 보유한 iCAKE 수량은 어떻게 확인하나요?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(9).png" alt="" width="375"><figcaption></figcaption></figure>

IFO 페이지 [여기](https://pancakeswap.finance/ifo)에서 보유한 iCAKE 수량을 확인할 수 있습니다.

예정된 IFO가 없을 때는 실시간 veCAKE 잔액으로 iCAKE가 계산되며, 이는 초 단위로 점차 감소한다는 점에 유의하세요.

예정된 IFO가 있을 때는 IFO 종료 시점인 스냅샷 시점의 veCAKE 잔액으로 iCAKE가 계산됩니다. IFO가 끝날 때까지 iCAKE는 감소하거나 변하지 않습니다.

### **iCAKE 수량은 어떻게 늘리나요?**

[CAKE 스테이킹 페이지](https://pancakeswap.finance/cake-staking)에서 언제든지 다음 방법으로 iCAKE 수량을 늘릴 수 있습니다.

* veCAKE 스테이킹 포지션에 CAKE 추가
* veCAKE 스테이킹 포지션 연장

### iCAKE 계산에서 "비율"이란 무엇인가요?

비율은 iCAKE를 계산할 때 veCAKE 잔액에 추가로 적용되는 조절 계수입니다.

예를 들어 비율이 2배이고 다음 IFO가 끝나는 시점에 1 veCAKE를 보유하고 있다면 최대 2 CAKE를 커밋할 수 있습니다.

각 IFO 사이에 키친은 다양한 지표를 기반으로 "비율"을 최적화합니다. 조정 내용은 모든 소셜 채널에 공지됩니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20(10).png" alt="" width="375"><figcaption></figcaption></figure>

[IFO 페이지](https://pancakeswap.finance/ifo)에서 iCAKE 계산에 사용되는 현재 "비율" 수치를 확인할 수 있습니다.
