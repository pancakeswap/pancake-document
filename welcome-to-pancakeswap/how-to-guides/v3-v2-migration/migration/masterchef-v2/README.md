---
description: Chuyển đổi sang MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 là hợp đồng staking chính mới cho Farms trong khi cung cấp tính linh hoạt hơn để điều chỉnh phát thải $CAKE, bao gồm CAKE pool, đốt token và các sản phẩm PancakeSwap khác.

### Tôi có cần chuyển đổi không?

Nếu bạn hiện đang sử dụng PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), bạn sẽ cần chuyển đổi sang hợp đồng mới ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)).

### Tổng quan

#### Nạp tiền&#x20;

Nếu bạn hiện đang sử dụng `enterStaking(uint256 _amount)` trên PancakeSwap MasterChef hiện tại. Bạn cần chuyển đổi sang hợp đồng CAKE pool mới. Xem tài liệu liên quan [tại đây](../cake-syrup-pool.md).

Hàm nạp tiền cho các farm pool không thay đổi. Tuy nhiên, bạn sẽ cần nâng cấp địa chỉ MasterChef và `pid`, xem [danh sách farm](list-of-farms.md) để biết danh sách `pid` mới trên MasterChef v2.

#### Loại Pool

MasterChef v2 có 2 loại pool: Regular farm pools và Special farm pools, bạn có thể sử dụng `poolInfo(_pid).isRegular` để truy vấn loại pool. Chúng chia sẻ `totalAllocPoint` khác nhau, làm cho chúng trở thành hai bộ pool độc lập.

Special farm pools: chỉ các địa chỉ được phép mới có thể nạp tiền. Chúng thường được sử dụng bởi các sản phẩm PancakeSwap nội bộ để phân phối phần thưởng.

Regular farm pools: các farm LP token thông thường. Ví dụ CAKE-BNB, BNB-BUSD, v.v.…

#### Rút Tiền

Nếu bạn hiện đang sử dụng `leaveStaking(uint256 _amount)` trên PancakeSwap MasterChef hiện tại. Bạn cần chuyển đổi sang hợp đồng CAKE pool mới. Xem tài liệu liên quan [tại đây](../cake-syrup-pool.md).

Hàm rút tiền cho các farm pool không thay đổi. Tuy nhiên, bạn sẽ cần cập nhật địa chỉ MasterChef và `pid`, xem [danh sách farm](list-of-farms.md) để biết danh sách `pid` mới trên MasterChef v2.

#### Số Dư Staking

Sử dụng `userInfo[_pid][_user].amount` để truy vấn số dư staking.

#### Token Staking&#x20;

Lưu ý rằng cấu trúc `PoolInfo` mới **không** chứa trường địa chỉ lp token, bạn sẽ cần sử dụng `lpToken(_pid)` để truy vấn token staking của bất kỳ pool nào.&#x20;

#### Tổng Share/Số Tiền Staking

Sử dụng `lpToken.balanceOf(MasterChef.address)` để lấy tổng số tiền staking cho bất kỳ farm pool nào.

Tuy nhiên, trong MasterChef v2, share của người dùng có thể được tăng cường (sắp ra). Do đó, phần thưởng được tính bằng trường `totalBoostedShare` mới trong `PoolInfo` làm tổng share của mỗi pool. Ví dụ: nếu pool 0 có 2 người dùng, user1 staking 100 LP (không boost), user2 staking 100 (với `boostMultiplier` là 1.05), thì `totalBoostedShare` sẽ trở thành 205. Dẫn đến user2 nhận được nhiều phần thưởng hơn.

#### CakePerBlock

Bạn có thể sử dụng `cakePerBlock(bool _isRegular)` để truy vấn phần thưởng CAKE mỗi block đi đến tất cả các farm PancakeSwap.

### Địa Chỉ Hợp Đồng Mainnet

**Tên hợp đồng:** MasterChef v2\
**Địa chỉ hợp đồng:** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[Xem PancakeSwap: Main Staking Contract v2 trên BscScan.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### Môi Trường Testnet

Bạn có thể sử dụng môi trường testnet sau để kiểm tra tích hợp dự án của bạn với PancakeSwap MasterChef v2 mới. Nếu bạn có câu hỏi, vui lòng liên hệ nhóm của chúng tôi qua các kênh hiện có, hoặc liên hệ bun@pancakeswap.com qua Email.

**Token Giả:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (có thể mint bằng cách sử dụng `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (có thể mint bằng cách sử dụng `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory và Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP Pairs

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
