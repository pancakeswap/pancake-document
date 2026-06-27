# FAQ

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### Hệ số nhân bCAKE được tính như thế nào?

Bạn có thể nhận thấy rằng bạn nhận được các hệ số nhân boost bCAKE khác nhau khi staking trong các farm khác nhau.

Đó là vì hệ số nhân bCAKE - Farm Booster được tính sử dụng các chỉ số sau khi kích hoạt hoặc làm mới:

* `userLpBalanceInFarm`: Số lượng thanh khoản bạn đang staking trong farm.&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm`: Tổng lượng thanh khoản đang staking trong farm hoặc lượng thanh khoản đang hoạt động hiện tại trong V3 LP pool. bCAKE sẽ chọn số nhỏ hơn giữa hai số này.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)`: Số lượng veCAKE bạn có theo thời gian thực
* `veCAKE.totalSupply`: Tổng cung veCAKE theo thời gian thực

Hệ số nhân được tính bằng phương pháp sau:

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` và `constantB` được thiết lập bởi Kitchen và có thể được điều chỉnh trong tương lai dựa trên phản hồi của cộng đồng và điều kiện thị trường. `constantB` thay đổi giữa các farm khác nhau để bù đắp cho sự chênh lệch giá LP.

`constantA` và `constantB` có thể được truy xuất qua:

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

Nhưng:

{% hint style="info" %}
**TL;DR**

Bạn muốn boost càng nhiều LP (thanh khoản)

Bạn cần khóa càng nhiều CAKE trong thời gian dài hơn
{% endhint %}

### Tại sao hệ số nhân của tôi thay đổi ngay cả sau khi kích hoạt?

Lưu ý rằng **bất kỳ hành động nào của người dùng đối với vị trí farming hoặc pool staking CAKE sẽ tự động cập nhật hệ số nhân boost của bạn** dựa trên dữ liệu và thống kê mới nhất từ các farm và pool staking CAKE, bao gồm nhưng không giới hạn ở:

* Stake/Unstake vị trí vào/từ farm
* Thu hoạch phần thưởng CAKE từ farm
* Gia hạn thời gian staking CAKE của bạn
* Thêm CAKE vào vị trí staking cố định của bạn
* Chuyển đổi vị trí staking CAKE sang linh hoạt

{% hint style="warning" %}
Lưu ý:&#x20;

Để đảm bảo tính công bằng và ngăn chặn lạm dụng và gian lận tiềm ẩn bằng cách sử dụng dữ liệu lỗi thời. Farm booster được thiết kế để không cần quyền và quản trị cộng đồng. Do đó, **bất kỳ ai** cũng có thể gọi hàm `updateLiquidity(address _tokenId)` trên hợp đồng MasterChef V3 để làm mới hệ số nhân boost của bất kỳ ai bằng cách sử dụng dữ liệu mới nhất.

Ngoài ra, Kitchen cũng sẽ giám sát tất cả các vị trí farming được bật bCAKE và sẽ làm mới bất kỳ vị trí nào có hệ số nhân lỗi thời.
{% endhint %}

### Tại sao tôi không thể boost một vị trí

1. Farm booster chỉ có sẵn cho các farm được chọn. Nhiều farm hơn sẽ được cung cấp trong tương lai. Hiện tại, **hãy tìm con số APR màu xanh với biểu tượng tên lửa xanh.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. Do liên quan đến nhiều hợp đồng, một số tương tác hợp đồng yêu cầu nhiều gas token (BNB) hơn một chút. Vì vậy, hãy đảm bảo bạn có đủ BNB trong ví. Nếu lỗi vẫn tiếp diễn, hãy thử tăng thủ công giới hạn gas của giao dịch.

### Hệ số nhân tối đa của bCAKE Boost tôi có thể nhận được là bao nhiêu?

Hiện tại, boost tối đa một người dùng có thể nhận được cho farm booster là 2.5x, mang lại cho họ APR gấp 2.5x so với ban đầu.

Lưu ý rằng boost tối đa bạn có thể nhận được thay đổi theo loại thanh khoản bạn đang cố gắng stake:

* V3: tối đa 2x
* V2, StableSwap: tối đa 2.5x
* Position Manager: tối đa 2.5x

### Làm thế nào để tôi tăng hệ số nhân bCAKE Boost của mình?

* Thêm CAKE vào vị trí staking veCAKE
* Gia hạn hoặc làm mới thời gian staking veCAKE của bạn

Nói đơn giản:

**Stake nhiều CAKE hơn, stake lâu hơn**

[Tìm hiểu thêm về cách tính hệ số nhân boost bCAKE](faq.md#how-are-the-bcake-multipliers-calculated).

### Phần thưởng CAKE được boost thêm từ đâu đến?

**Yên tâm, không có emission bổ sung nào được phân bổ để thực hiện bCAKE.**

Tương tự như CAKE staking veCAKE. bCAKE tăng cường cổ phần của người dùng cá nhân so với những người khác.

Mặc dù APR cơ bản có thể giảm sau khi triển khai bCAKE. Các đầu bếp tin rằng đây là sự đánh đổi tốt vì nó mang lại lợi ích cho những người yêu thích CAKE trung thành bằng cách tăng cường yield farming của họ, tạo ra nhiều nhu cầu hơn cho CAKE, và đóng vai trò là động lực tuyệt vời cho CAKE staking.

### Tại sao hệ số nhân tôi nhận được thấp?&#x20;

bCAKE - farm booster hoạt động bằng cách đánh giá cả vị trí staking veCAKE và vị trí farming thanh khoản của bạn so với những người dùng khác. Nói đơn giản:

> Nếu người dùng muốn boost nhiều thanh khoản hơn trong farm, họ phải khóa nhiều CAKE hơn trong thời gian dài hơn trong pool.

Thiết kế này đảm bảo lợi ích không chỉ được cung cấp cho những người nắm giữ lớn, mà cho bất kỳ người dùng nào có vị trí staking CAKE đáng kể so với vị trí farming.

Tìm hiểu thêm về cách tính hệ số nhân [tại đây](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated).

### Tại sao chỉ có x số farm có thể boost?

Vì bCAKE liên quan đến việc cập nhật một trong những sản phẩm cốt lõi của PancakeSwap, đó là liquidity farming. Các đầu bếp muốn tiếp cận từ từ và ổn định hơn khi ra mắt.

Do đó, trong giai đoạn phát hành sản phẩm ban đầu. Nhiều tham số rất thận trọng. Bao gồm số lượng farm người dùng có thể boost, farm nào người dùng có thể boost, cũng như tham số độ khó trong việc nhận hệ số nhân boost.

**Các đầu bếp sẽ điều chỉnh các tham số dựa trên phản hồi của cộng đồng.**

### **bCAKE V3 có được kiểm toán không?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE đã được kiểm toán bởi cả kiểm toán viên nội bộ và bên ngoài.

Xem các báo cáo kiểm toán tại đây: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
