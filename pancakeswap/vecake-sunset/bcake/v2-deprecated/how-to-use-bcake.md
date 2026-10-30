# bCAKE 사용 방법

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-use-bCAKE.png)

iCAKE 및 vCAKE와 마찬가지로 bCAKE도 CAKE를 고정 기간 CAKE 스테이킹 풀에 락업하는 사용자를 위해 설계된 혜택입니다. 부스트 배수는 스테이킹한 CAKE의 수량, 스테이킹 기간, 그리고 부스트하려는 파밍에 스테이킹한 LP 토큰의 수량을 기준으로 계산됩니다.

## 준비 사항

### 고정 기간 CAKE 스테이킹 포지션 시작하기

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-no-cake-locked.png)

CAKE 스테이킹 풀에 락업한 CAKE가 없다면 "Go to Pool"을 클릭하고 안내에 따라 고정 기간 스테이킹 포지션을 시작하세요.

고정 기간 CAKE 스테이킹 방법에 대해 자세히 알아보려면 [여기](../../../../archive/legacy-products/new-cake-pool/#fixed-term-staking)를 읽어보세요.

### 파밍 부스터 활성화

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-enable-booster.png)

파밍 부스터를 활성화하려면 1회 설정 과정을 완료해야 합니다. "Enable"을 클릭하고 지갑에서 트랜잭션을 확인하면 됩니다.

### 스테이킹 마이그레이션

{% hint style="info" %}
bCAKE를 활성화하려는 파밍에 현재 스테이킹하고 있지 않다면 이 단계를 건너뛰고 해당 파밍에 LP 토큰을 스테이킹하는 것부터 시작하면 됩니다.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-staking-migration-needed.png)

파밍 부스터를 활성화하려는 파밍에 이미 스테이킹하고 있다면 1회 스테이킹 마이그레이션도 필요합니다.

"Migrate"를 클릭하고 단계별 안내에 따라 마이그레이션을 완료하세요. CAKE 보상은 자동으로 수확되어 지갑으로 전송됩니다.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-migration-inprogress.png)

## 부스터 활성화

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-pending-activation%20\(1\).png)

준비가 되면 현재 스테이킹 중인 파밍에 대해 사용 가능한 부스트 배수와 부스트된 APR을 확인할 수 있습니다. bCAKE 배수가 어떻게 계산되는지 자세히 알아보려면 [여기](../faq.md#how-are-the-bcake-multipliers-calculated)를 읽어보세요.

부스트를 활성화하려면 "Boost" 버튼을 클릭하고 지갑에서 트랜잭션을 확인하세요.

{% hint style="info" %}
파밍 또는 CAKE 스테이킹 풀에서 사용자가 어떤 작업을 하면 파밍과 CAKE 스테이킹 풀의 최신 데이터 및 통계를 기준으로 부스트 배수가 자동으로 업데이트됩니다.

자세한 내용은 [여기](../faq.md#why-do-my-multipliers-change-even-after-activation)를 참고하세요.
{% endhint %}

### ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-farm-number-limit.png)

동시에 부스트할 수 있는 파밍의 수에는 제한이 있습니다. 남은 부스터 수를 확인하려면 상단 패널을 참고하세요.

다른 파밍에서 부스터를 활성화하려면 활성화된 부스터를 해제해야 합니다.

## 부스터 해제

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-pending-unset%20\(1\).png)

파밍 부스터를 해제하려면 "Unset" 버튼을 클릭하고 지갑에서 트랜잭션을 확인하세요.

해제 시 획득한 CAKE는 파밍 부스터 컨트랙트로 수확되며, 다음 수확, 입금 또는 출금 시 자동으로 지갑에 전송됩니다. 자세한 내용은 [여기](../faq.md#where-are-my-cake-rewards-after-activating-or-unsetting-the-booster)를 참고하세요.
