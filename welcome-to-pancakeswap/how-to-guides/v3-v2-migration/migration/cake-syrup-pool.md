---
description: 新しいCAKE Syrup Poolに移行する
---

# CAKE Syrup Pool

新しいCakePoolは、CakeVault（現在の自動CAKE Pool）をベースに構築された新しい$CAKEステーキングコントラクトで、PancakeSwap MasterChef v2と連携して「$CAKEをステーキングして$CAKEを獲得する」機能を提供しながら、固定期間ステーキングなどの追加機能も備えています。現在の手動CAKE Poolはマイグレーション後に廃止されます。

新しいCakePoolはダミートークンを使用してMasterChef v2から$CAKEをハーベストし、$CAKEをステーキングしているユーザーに報酬を分配します。$CAKEを長期間ロックするユーザーはより多くのシェアを受け取り（期間に基づいて線形にブーストされます）、より高いリターンを享受できます。

### マイグレーションは必要ですか？&#x20;

現在PancakeSwap MasterChef（[0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)）で`enterStaking`と`leaveStaking`を使用している場合は、新しいコントラクトに移行する必要があります。

### 複利計算の廃止

新しいCakePoolでは、報酬はシェアに基づいてすべてのプールユーザーに比例して分配されます。「利付きトークン」やその他のシェアベースモデルと同様に、プールにより多くの報酬が追加されるとユーザーのステーキング残高が増加します。ユーザーはハーベストや複利計算を行う必要はありません。

### 手数料&#x20;

新しいCakePoolでは、すべてのフレキシブルステーキングユーザーに2種類の手数料が適用されます。

#### フレキシブルステーキング報酬の手数料&#x20;

フレキシブルステーキングで発生したすべての報酬に2%の手数料が適用されます。手数料の金額は次回の入金または出金操作時に計算・確定され、ユーザーのシェアから差し引かれます。未確定のパフォーマンス手数料を照会するには、`calculatePerformanceFee(address _user)`を使用してください。

#### 出金手数料&#x20;

最後の入金操作から72時間以内に出金する場合、アンステーキング金額に0.1%の出金手数料が適用されます。出金手数料はCAKEの送金前に最終出金金額から差し引かれます。

### 概要

#### 入金

現在PancakeSwap MasterChefで`enterStaking(uint256 _amount)`を使用している場合は、`deposit(uint256 _amount, uint256 _lockDuration)`に移行する必要があります。フレキシブルステーキングの場合は、`_lockDuration`に「0」を使用してください。

#### ステーキング残高と手数料

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

**CAKEステーキング金額（すべての手数料を差し引く前）**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**パフォーマンス手数料**

コントラクトから照会する場合：

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

手動で計算する場合：

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

**期限超過手数料：（ロックステーキングのみ適用）**

コントラクトから照会する場合：

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

手動で計算する場合：

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

**出金手数料**

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

**CAKEステーキング金額（すべての手数料を差し引いた後）**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### 未払い報酬&#x20;

新しいプールでは複利計算は不要です。報酬はステーキング残高に自動的に追加されます。

ただし、直近の操作以降に獲得したCAKEの量は、現在のステーキング残高（上記参照）と`userInfo.cakeAtLastUserAction`の差を使用して照会できます。

#### 出金

現在PancakeSwap MasterChefで`leaveStaking(uint256 _amount)`メソッドを使用している場合は、`withdraw(uint256 _shares)`に移行する必要があります。

フレキシブルステーキングの出金時には、未払いの報酬手数料が計算されてユーザーのシェア数から差し引かれ、実際に出金されるシェア数は、保有する合計シェアに対する出金するシェアの割合に基づいて再計算されることにご注意ください。以下の例をご参照ください。

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

最終的な受取金額は出金手数料の影響を受けることにご注意ください。出金されるCAKEの最終的な量に処理が大きく依存する場合は、出金操作の前後のCAKE残高の差を使用して計算することを推奨します。

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

または、金額を見積もる際に出金手数料を計算して差し引いてください。

#### 新しいCAKE Poolに配分される1ブロックあたりのCAKEの計算方法

以前、手動CAKE Poolは固定で10 CAKE/ブロックの排出量でした。MasterChef v2と新しいCAKE Poolに移行後は、排出量を調整できるようになりました。

新しいCAKE Poolに配分される1ブロックあたりのCAKEの計算方法は以下の通りです。

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

`cakePool.allocPoint`は`MasterChef.poolInfo(0)`を使用して照会できます。

### **メインネットコントラクトアドレス**

**コントラクト名：** CakePool\
**コントラクトアドレス：** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[BscScanでPancakeSwap: Cake Pool Contractを確認する。](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **テストネット環境**

以下のテストネット環境を使用して、新しいPancakeSwap CAKE Poolとのプロジェクト統合をテストできます。ご質問がある場合は、既存のチャンネルを通じてチームにお問い合わせいただくか、bun@pancakeswap.comにメールでご連絡ください。

**ダミートークン：**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  （`mint(address _to, uint256 _amount) public`を使用してミント可能）
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### FactoryとRouter

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### 新しいCAKE Pool

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
