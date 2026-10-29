---
description: 새로운 CAKE 시럽 풀로 마이그레이션하기
---

# CAKE 시럽 풀

새로운 CakePool은 CakeVault(현재의 Auto CAKE 풀)를 기반으로 구축된 새로운 $CAKE 스테이킹 컨트랙트로, PancakeSwap MasterChef v2와 연동되어 "$CAKE를 스테이킹하고 $CAKE를 받는" 기능을 제공하며 고정 기간 스테이킹과 같은 더 많은 기능도 제공합니다. 현재의 Manual CAKE 풀은 마이그레이션 이후 종료됩니다.

새로운 CakePool은 더미 토큰을 사용하여 MasterChef v2에서 $CAKE를 수확하고, 이를 $CAKE를 스테이킹 중인 사용자에게 보상으로 지급합니다. $CAKE를 더 오래 락업하는 사용자는 (기간에 비례하여 선형적으로 부스트되는) 더 많은 지분을 받으므로 더 높은 수익을 누릴 수 있습니다.

### 마이그레이션이 필요한가요?&#x20;

현재 PancakeSwap MasterChef([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E))에서 `enterStaking`과 `leaveStaking`을 사용 중이라면 새로운 컨트랙트로 마이그레이션해야 합니다.

### 더 이상 복리 재투자가 필요 없습니다

새로운 CakePool에서는 보상이 지분에 비례하여 모든 풀 사용자에게 분배됩니다. "이자 발생 토큰(interest-bearing token)"이나 다른 지분 기반 모델과 유사하게, 풀에 더 많은 보상이 유입될수록 사용자의 스테이킹 잔액이 늘어납니다. 사용자가 직접 보상을 수확하여 재투자할 필요가 없습니다.

### 수수료&#x20;

새로운 CakePool에서는 모든 유연형 스테이킹 사용자에게 두 가지 수수료가 적용됩니다.&#x20;

#### 유연형 스테이킹 보상 수수료&#x20;

유연형 스테이킹으로 발생한 모든 보상에 2%의 수수료가 적용됩니다. 수수료 금액은 다음 예치 또는 출금 시점에 계산 및 확정되며 사용자의 지분에서 차감됩니다. 아직 확정되지 않은 성과 수수료(performance fee)의 금액을 조회하려면 `calculatePerformanceFee(address _user)`를 사용하세요.&#x20;

#### 출금 수수료&#x20;

마지막 예치 후 72시간 이내에 출금하면 언스테이킹 금액에 0.1%의 출금 수수료가 적용됩니다. 출금 수수료는 CAKE가 전송되기 전에 최종 출금 금액에서 차감됩니다.

### 개요

#### 예치

현재 PancakeSwap MasterChef에서 `enterStaking(uint256 _amount)`를 사용 중이라면 `deposit(uint256 _amount, uint256 _lockDuration)`로 마이그레이션해야 합니다. 유연형 스테이킹의 경우 `_lockDuration`에 "0"을 사용하면 됩니다.

#### 스테이킹 잔액 및 수수료

```
Global variables: CakePoolContract // CAKE pool contract
struct UserInfo {
    uint256 shares; // number of shares for a user.
    uint256 lastDepositedTime; // timestamp of the last deposit action
    uint256 cakeAtLastUserAction; // number of CAKE at the last user action
    uint256 lastUserActionTime; // timestamp of the last user action
    uint256 lockStartTime; // timestamp of the start of the lock.
    uint256 lockEndTime; // timestamp of the end of the lock.
    uint256 userBoostedShare; // the amount of shares boosted/added to the user.
    bool locked; // status of the lock
    uint256 lockedAmount; // number of CAKE locked at the start of the lock period.
}
```

**CAKE 스테이킹 수량 (모든 수수료 차감 전)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**성과 수수료**

컨트랙트에서 조회:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

직접 계산:

```
async function calculatePerformanceFeeAmount(_user:address){
    const user = await CakePoolContract.userInfo(address);
    const isFreeFee = await CakePoolContract.freeFeeUsers(_user);  //normal free fee users are some special contracts , so you can set default false

    if(user.shares > 0 && !user.locked && !isFreeFee){
        const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
        uint256 totalAmount = user.shares * PricePerFullShare / 1e18; 
        uint256 earnAmount = totalAmount - user.cakeAtLastUserAction;
        uint256 performanceFee = await  CakePoolContract.performanceFee();
        uint256 currentPerformanceFee = (earnAmount * performanceFee) / 10000;
        return currentPerformanceFee;
    }
    return 0;
}
```

**연체 수수료: (락업형 스테이킹에만 적용)**

컨트랙트에서 조회:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

직접 계산:

```
async function calculateOverdueFee(_user:address){
    const user = await CakePoolContract.userInfo(address);
    const isFreeFee = await CakePoolContract.freeFeeUsers(_user); //normal free fee users are some special contracts , so you can set default false
    const UNLOCK_FREE_DURATION = 1 week seconds (or you can get from smart contract,  const UNLOCK_FREE_DURATION = await CakePoolContract.UNLOCK_FREE_DURATION())
    const DURATION_FACTOR_OVERDUE = 180 * 24 * 3600; // 180 days, in order to calculate overdue fee. you can get it from contract too.

    if (
        user.shares > 0 &&
        user.locked &&
        !isFreeFee &&
        ((user.lockEndTime + UNLOCK_FREE_DURATION) < block.timestamp)
    ) {
        const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
        uint256 currentAmount = user.shares * PricePerFullShare / 1e18 - user.userBoostedShare;
        uint256 earnAmount = currentAmount - user.lockedAmount;
        uint256 overdueDuration = block.timestamp - user.lockEndTime - UNLOCK_FREE_DURATION;  //  you can use UTC timestamp to replace current block.timestamp.
        if (overdueDuration > DURATION_FACTOR_OVERDUE) {
            overdueDuration = DURATION_FACTOR_OVERDUE;
        }
        // Rates are calculated based on the user's overdue duration.
        uint256 overdueWeight = (overdueDuration * overdueFee) / DURATION_FACTOR_OVERDUE;
        uint256 currentOverdueFee = (earnAmount * overdueWeight) / PRECISION_FACTOR;
        return currentOverdueFee;
    }
    return 0;
}
```

**출금 수수료**

```
const user = await CakePoolContract.userInfo(address);
const withdrawFee = await  CakePoolContract.withdrawFee();
const isFreeFee = await CakePoolContract.freeFeeUsers(_user); //normal free fee users are some special contracts , so you can set default false
let WithdrawFeeAmount = 0;
// you can use UTC timestamp to replace current block.timestamp.
// withdrawFeePeriod = 72 * 3600 (S)
// _amount : withdraw amount
if (!isFreeFee && (block.timestamp < user.lastDepositedTime + withdrawFeePeriod)) {
     WithdrawFeeAmount = _amount * withdrawFee;
}
```

**CAKE 스테이킹 수량 (모든 수수료 차감 후)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### 대기 중인 보상&#x20;

새로운 풀에서는 복리 재투자가 필요하지 않다는 점에 유의하세요. 보상은 스테이킹 잔액에 자동으로 추가됩니다.

다만 현재 스테이킹 잔액(위에서 설명)과 `userInfo.cakeAtLastUserAction`의 값의 차이를 이용하여 마지막 작업 이후 획득한 CAKE 수량을 조회할 수 있습니다.

#### 출금

현재 PancakeSwap MasterChef에서 `leaveStaking(uint256 _amount)` 메서드를 사용 중이라면 `withdraw(uint256 _shares)`로 마이그레이션해야 합니다.

유연형 스테이킹의 경우, 출금 시 대기 중인 보상 수수료가 계산되어 사용자의 지분 수량에서 차감되며, 실제로 출금되는 지분 수량은 보유한 전체 지분 대비 출금하려는 지분의 비율에 따라 재조정된다는 점에 유의하세요. 아래 예시를 참고하세요.

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

최종 수령 금액은 출금 수수료의 영향을 받는다는 점에 유의하세요. 함수가 최종 출금되는 CAKE 수량에 크게 의존한다면, 출금 전후의 CAKE 잔액 차이를 이용하여 계산하는 것을 권장합니다.

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

또는 수량을 추정할 때 출금 수수료를 계산하여 차감하세요.

#### 새로운 CAKE 풀에 분배되는 블록당 CAKE는 어떻게 계산하나요?

이전에 Manual CAKE 풀은 블록당 10 CAKE로 고정된 배출량을 가졌습니다. MasterChef v2와 새로운 CAKE 풀로 마이그레이션한 후에는 배출량을 조정할 수 있습니다.

새로운 CAKE 풀에 분배되는 블록당 CAKE는 다음과 같이 계산할 수 있습니다.

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

`cakePool.allocPoint`는 `MasterChef.poolInfo(0)`를 사용하여 조회할 수 있습니다.

### **메인넷 컨트랙트 주소**

**컨트랙트 이름:** CakePool\
**컨트랙트 주소:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[BscScan에서 PancakeSwap: Cake Pool Contract 보기.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **테스트넷 환경**

다음 테스트넷 환경을 사용하여 프로젝트와 새로운 PancakeSwap CAKE 풀의 연동을 테스트할 수 있습니다. 궁금한 점이 있다면 기존 채널을 통해 팀에 문의하거나 bun@pancakeswap.com으로 이메일을 보내주세요.

**더미 토큰:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (`mint(address _to, uint256 _amount) public`를 사용하여 민팅 가능)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### 팩토리 및 라우터

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChef 목록

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### 새로운 CAKE 풀

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
