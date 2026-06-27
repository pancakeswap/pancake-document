---
description: Chuyển đổi sang CAKE Syrup Pool mới
---

# CAKE Syrup Pool

CakePool mới là hợp đồng staking $CAKE mới được xây dựng dựa trên CakeVault (pool CAKE tự động hiện tại) và được thiết kế để hoạt động với PancakeSwap MasterChef v2 để cung cấp chức năng "stake $CAKE, kiếm $CAKE" trong khi cung cấp nhiều tính năng hơn như staking có kỳ hạn cố định. Pool CAKE Thủ Công hiện tại sẽ bị ngừng hoạt động sau khi chuyển đổi.

CakePool mới sẽ sử dụng token giả để thu hoạch $CAKE từ MasterChef v2 và thưởng cho người dùng đang staking $CAKE. Người dùng khóa $CAKE lâu hơn sẽ nhận được số lượng share lớn hơn đáng kể (được tăng cường tuyến tính dựa trên thời gian), do đó, tận hưởng lợi suất cao hơn.

### Tôi có cần chuyển đổi không?&#x20;

Nếu bạn hiện đang sử dụng `enterStaking` và `leaveStaking` trên PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), bạn sẽ cần chuyển đổi sang hợp đồng mới.

### Không còn compounding nữa

Với CakePool mới, phần thưởng được phân phối tỷ lệ cho tất cả người dùng pool dựa trên share. Tương tự như "interest-bearing tokens" hoặc các mô hình dựa trên share khác, số dư staking của người dùng sẽ tăng khi có nhiều phần thưởng được đưa vào pool. Người dùng không cần thu hoạch và compound phần thưởng.

### Phí&#x20;

Trong CakePool mới, tất cả người dùng staking linh hoạt sẽ phải chịu hai loại phí.&#x20;

#### Phí trên phần thưởng staking linh hoạt&#x20;

Phí 2% sẽ áp dụng cho tất cả phần thưởng được tạo ra bởi staking linh hoạt. Số tiền phí sẽ được tính toán và thực hiện tại hành động nạp tiền hoặc rút tiền tiếp theo, cắt từ share của người dùng. Để truy vấn số tiền phí hiệu suất chưa được thực hiện, sử dụng `calculatePerformanceFee(address _user)`.&#x20;

#### Phí rút tiền&#x20;

Phí rút tiền 0.1% sẽ áp dụng cho số tiền rút staking nếu bạn rút tiền trong vòng 72 giờ kể từ hành động nạp tiền cuối cùng. Phí rút tiền được cắt từ số tiền rút cuối cùng trước khi chuyển CAKE.

### Tổng quan

#### Nạp tiền

Nếu bạn hiện đang sử dụng `enterStaking(uint256 _amount)` trên PancakeSwap MasterChef hiện tại. Bạn cần chuyển đổi sang `deposit(uint256 _amount, uint256 _lockDuration)`. Đối với staking linh hoạt, chỉ cần sử dụng "0" làm `_lockDuration`.

#### Số dư Staking và Phí

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

**Số tiền staking CAKE (trước khi trừ tất cả phí)**

```
const userInfo. = await CakePoolContract.userInfo(address);
const PricePerFullShare = await CakePoolContract.getPricePerFullShare();
const cakeAmount = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare ;  // cake amount (wei), in flexible staking, userInfo.userBoostedShare should be 0.
```

**Phí Hiệu Suất**

Truy vấn từ hợp đồng:

```
const performanceFeeAmount = await CakePoolContract.calculatePerformanceFee(address);
```

Tính thủ công:

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

**Phí Quá Hạn: (chỉ áp dụng cho staking có khóa)**

Truy vấn từ hợp đồng:

```
const overdueFeeAmount = await CakePoolContract.calculateOverdueFee(address);
```

Tính thủ công:

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

**Phí Rút Tiền**

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

**Số tiền staking CAKE (sau khi trừ tất cả phí)**

```
const user = await CakePoolContract.userInfo(address);
const cakeAmountWithoutFee =  cakeAmount - (!user.locked ? performanceFeeAmount : overdueFeeAmount) - withdrawFeeAmount
```

#### Phần Thưởng Đang Chờ&#x20;

Xin lưu ý rằng pool mới không yêu cầu bất kỳ compounding nào. Phần thưởng được đưa vào số dư staking của bạn tự động.

Tuy nhiên, bạn có thể truy vấn số lượng CAKE kiếm được kể từ hành động cuối cùng, sử dụng sự chênh lệch giữa số dư staking hiện tại (được đề cập ở trên) và số từ `userInfo.cakeAtLastUserAction`.

#### Rút Tiền

Nếu bạn đang sử dụng phương thức `leaveStaking(uint256 _amount)` trên PancakeSwap MasterChef hiện tại. Bạn cần chuyển đổi sang `withdraw(uint256 _shares)`.

Khi thực hiện staking linh hoạt. Xin lưu ý rằng khi rút tiền, các phí phần thưởng đang chờ sẽ được tính và cắt từ số share của người dùng, số share thực tế đang được rút sẽ được hiệu chỉnh lại, dựa trên tỷ lệ phần trăm share bạn đang rút so với tổng share bạn có. Xem ví dụ bên dưới:

```
// the number of CAKE being withdrawn can be calculated by:
withdrawPercentage = _sharesToWithdraw / userInfo.shares
stakingBalance = userInfo.shares * PricePerFullShare / 1e18 - userInfo.userBoostedShare - !userInfo.locked ? calculatePerformanceFee(_userAddress) : calculateOverdueFee(_userAddress)
finalWithdrawAmount = withdrawPercentage * stakingBalance
```

Xin lưu ý rằng số tiền nhận được cuối cùng sẽ bị ảnh hưởng bởi phí rút tiền. Nếu hàm của bạn phụ thuộc quan trọng vào số CAKE cuối cùng được rút, chúng tôi khuyến nghị tính toán điều đó bằng cách sử dụng sự chênh lệch trong số dư CAKE trước và sau hành động rút tiền:

```
cakeBalPrev = CAKE.balanceOf(address(this))
CakePool.withdraw(_sharesToWithdraw)
cakeBalNew = CAKE.balanceOf(address(this))
cakeWithdrawn = cakeBalNew - cakeBalPrev
```

Hoặc, tính và trừ phí rút tiền khi ước tính số tiền.

#### Cách tính CAKE mỗi block được phân phối cho CAKE pool mới?

Trước đây, pool CAKE thủ công có phát thải cố định 10 CAKE/block. Sau khi chuyển đổi sang MasterChef v2 và pool CAKE mới, chúng ta có thể điều chỉnh phát thải của nó.

Và đây là cách bạn có thể tính CAKE mỗi block được phân phối cho pool CAKE mới:

`cakePerBlockToPool = MasterChef.cakePerBlock(false) * (cakePool.allocPoint / MasterChef.totalSpecialAllocPoint)`

Bạn có thể truy vấn `cakePool.allocPoint` bằng cách sử dụng `MasterChef.poolInfo(0)`

### **Địa Chỉ Hợp Đồng Mainnet**

**Tên hợp đồng:** CakePool\
**Địa chỉ hợp đồng:** `0x45c54210128a065de780C4B0Df3d16664f7f859e`

[Xem PancakeSwap: Cake Pool Contract trên BscScan.](https://bscscan.com/address/0x45c54210128a065de780C4B0Df3d16664f7f859e)

### **Môi Trường Testnet**

Bạn có thể sử dụng môi trường testnet sau để kiểm tra tích hợp dự án của bạn với CAKE Pool PancakeSwap mới. Nếu bạn có câu hỏi, vui lòng liên hệ nhóm của chúng tôi qua các kênh hiện có, hoặc liên hệ bun@pancakeswap.com qua Email.

**Token Giả:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (có thể mint bằng cách sử dụng `mint(address _to, uint256 _amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory và Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`

#### CAKE Pool Mới

`0x683433ba14e8F26774D43D3E90DA6Dd7a22044Fe`
