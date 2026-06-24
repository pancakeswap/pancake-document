---
description: 迁移到新的 CAKE 糖浆池
---

# CAKE 糖浆池

新的 CakePool 是一个全新的 $CAKE 质押合约，基于 CakeVault（当前的自动 CAKE 池）构建，旨在与 PancakeSwap MasterChef v2 协同工作，提供“质押 $CAKE，赚取 $CAKE”的功能，同时提供更多特性，例如固定期限质押。当前的手动 CAKE 池将在迁移后停用。

新的 CakePool 将使用一个虚拟代币（dummy token）从 MasterChef v2 收取 $CAKE，并将其奖励给正在质押 $CAKE 的用户。锁定 $CAKE 时间更长的用户将获得更多的份额（根据时长线性加成），因此能享受更高的收益。

### 我需要迁移吗？&#x20;

如果你当前正在 PancakeSwap MasterChef（[0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)）上使用 `enterStaking` 和 `leaveStaking`，则你需要迁移到新合约。

### 不再有复利

在新的 CakePool 中，奖励会根据份额按比例分配给所有矿池用户。与“计息代币”或其他基于份额的模型类似，当更多奖励被投入矿池时，用户的质押余额会增长。用户无需收取并复投他们的奖励。

### 手续费&#x20;

在新的 CakePool 中，所有灵活质押用户都将受到两组手续费的约束。&#x20;

#### 灵活质押奖励手续费&#x20;

所有由灵活质押产生的奖励都将收取 2% 的手续费。该手续费的金额将在下一次存款或取款操作时计算并实现，从用户的份额中扣除。要查询尚未实现的绩效费数额，请使用 `calculatePerformanceFee(address _user)`。&#x20;

#### 取款手续费&#x20;

如果你在上一次存款操作后的 72 小时内取款，则取消质押的金额将收取 0.1% 的取款手续费。该取款手续费在 CAKE 转账之前从最终取款金额中扣除。

### 概述

#### 存款

如果你当前正在当前的 PancakeSwap MasterChef 上使用 `enterStaking(uint256 _amount)`，你需要迁移到 `deposit(uint256 _amount, uint256 _lockDuration)`。对于灵活质押，只需将 `_lockDuration` 设为“0”即可。

#### 质押余额和手续费

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

**CAKE 质押金额（扣除所有手续费之前）**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**绩效费**

从合约查询：

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

手动计算：

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

**逾期费：（仅适用于锁定质押）**

从合约查询：

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

手动计算：

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

**取款手续费**

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

**CAKE 质押金额（扣除所有手续费之后）**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### 待领取奖励&#x20;

请注意，新池不需要任何复投。奖励会自动计入你的质押余额。

不过，你可以使用当前质押余额（如上所述）与 `userInfo.cakeAtLastUserAction` 数值之间的差额，来查询自上次操作以来赚取的 CAKE 数量。

#### 取款

如果你正在当前的 PancakeSwap MasterChef 上使用 `leaveStaking(uint256 _amount)` 方法，你需要迁移到 `withdraw(uint256 _shares)`。

在进行灵活质押时，请注意，取款时，待领取的奖励手续费将被计算并从用户份额数量中扣除，实际被取出的份额数量将根据你要取出的份额占你持有总份额的百分比重新校准。参见下方示例：

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

请注意，最终收到的金额将受取款手续费影响。如果你的函数关键性地依赖于最终取出的 CAKE 数量，我们建议使用取款操作前后的 CAKE 余额差额来计算：

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

或者，在估算金额时计算并减去取款手续费。

#### 如何计算分配给新 CAKE 池的每区块 CAKE 数量？

此前，手动 CAKE 池有固定的每区块 10 CAKE 释放量。在迁移到 MasterChef v2 和新的 CAKE 池后，我们现在可以调整其释放量。

以下是计算分配给新 CAKE 池的每区块 CAKE 数量的方法：

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

你可以使用 `MasterChef.poolInfo(0)` 查询 `cakePool.allocPoint`

### **主网合约地址**

**合约名称：** CakePool\
**合约地址：** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[在 BscScan 上查看 PancakeSwap: Cake Pool 合约。](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **测试网环境**

你可以使用以下测试网环境来测试你的项目与新 PancakeSwap CAKE 池的集成。如果你有任何问题，请通过现有渠道联系我们的团队，或通过电子邮件联系 bun@pancakeswap.com。

**虚拟代币：**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  （可通过 `mint(address _to, uint256 _amount) public` 铸造）
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory 和 Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: 手动 CAKE
  * pid4: 用于 MasterChef v2 的虚拟池
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### 新 CAKE 池

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
