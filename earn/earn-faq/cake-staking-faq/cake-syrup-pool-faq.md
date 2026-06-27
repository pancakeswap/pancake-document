---
hidden: true
---

# FAQ về CAKE Syrup Pool

## FAQ

### Chúng tôi có thể chọn thời gian khóa bao lâu?

Bạn có thể chọn từ 1-52 tuần. Bạn thích thế nào?

### Những biến số nào ảnh hưởng đến APR/APY của CAKE Syrup Pool mới (các lựa chọn Flexible và Fixed-Term Staking)?

Vì các tùy chọn flexible staking và fixed-term staking là một phần của cùng một pool, các biến số sau ảnh hưởng đến APR/APY của cả hai:

* Tổng CAKE được stake trong flexible staking và fixed-term staking (tổng của cả hai). CAKE được stake càng nhiều, APR/APY càng thấp.
* Tổng CAKE bị khóa trong fixed-term staking. Khóa CAKE càng nhiều có nghĩa là tăng cường lợi suất nhiều hơn, dẫn đến ít phần thưởng CAKE hơn cho người khác (đặc biệt là flexible staking).
* Thời gian khóa trung bình của tất cả CAKE bị khóa trong fixed-term staking. Nếu thời gian khóa trung bình tăng, APR/APY sẽ giảm.

### Tôi có thể thu hoạch phần thưởng trong thời gian khóa không?

Không. Bạn chỉ có thể thu hoạch phần thưởng khi thời gian khóa kết thúc. Điều này dựa trên lợi suất/lợi nhuận chúng tôi cung cấp cũng như các triển khai kỹ thuật.

### Tôi có thể gia hạn thời gian khóa không?

Có. Gia hạn thời gian khóa sẽ thêm thời gian vào **thời gian khóa ban đầu** của bạn. Khi chọn gia hạn thời gian khóa, lưu ý:

Thời gian khóa gia hạn mới = thời gian khóa ban đầu + thời gian thêm

### Tôi có thể rút CAKE khỏi Fixed-Term staking qua hợp đồng nếu tôi thay đổi ý định không?

Không. CAKE của bạn không thể được rút hoặc lấy ra khỏi fixed-term staking tại bất kỳ thời điểm nào cho đến khi thời gian khóa kết thúc và CAKE của bạn được mở khóa.

### Số tiền "CAKE Locked" là gì?

Số tiền "CAKE Locked" là số dư CAKE ban đầu bị khóa của người dùng cộng với phần thưởng CAKE tính đến nay.&#x20;

CAKE Locked = Số dư CAKE ban đầu bị khóa + Phần thưởng CAKE

Khi thêm CAKE vào fixed-term staking, số tiền "CAKE to be locked" là số dư CAKE ban đầu bị khóa của người dùng, phần thưởng CAKE tính đến nay và CAKE đang được thêm vào.

### APR của CAKE pool Fixed-Term Staking có thể thay đổi sau khi tôi khóa CAKE không?

Có, APR của CAKE pool fixed-term staking là biến động, giống như các CAKE pool cũ. APR của CAKE pool fixed-term staking không cố định và phụ thuộc vào:

* Tổng CAKE được stake trong CAKE pool (tổng của cả Flexible + Fixed-Term Staking).
* Thời gian khóa trung bình của tất cả CAKE bị khóa trong fixed-term staking.
* Tăng cường lợi suất (tương tự như số nhân) được tính từ thời gian khóa ban đầu của người dùng. Khóa CAKE càng lâu, tăng cường lợi suất càng cao.

Ví dụ: nếu bạn khóa CAKE trong 52 tuần, tăng cường lợi suất của bạn sẽ lớn hơn so với nếu bạn khóa CAKE trong 26 tuần. Tăng cường lợi suất tăng tuyến tính theo thời gian bạn khóa CAKE.

### Tôi có thể tham gia IFO nếu CAKE của tôi bị khóa trong Fixed-Term Staking pool không, hay tôi cần mua thêm CAKE?

Không, cần có một lượng CAKE riêng biệt. Tuy nhiên, locked-staking cung cấp quyền đăng ký cho các đợt bán công khai IFO. Xem [iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md).

### Tôi có thể bỏ phiếu nếu CAKE của tôi bị khóa trong Fixed-Term Staking pool không?

Có! Xem [vCAKE](../../../welcome-to-pancakeswap/vecake-sunset/archive-vecake/vecake.md).

### Tôi có thể sử dụng cả Flexible Staking CAKE pool và Fixed-Term Staking CAKE pool cùng một lúc không?

Có, khi bạn đang thực hiện fixed-term CAKE staking. Một side-pool flexible CAKE staking sẽ tự động xuất hiện để bạn chọn.

### Có phí nào khi chuyển đổi Flexible Staked CAKE sang Fixed-Term Staked CAKE không?

Không. Không có phí bổ sung nào khi chuyển CAKE từ flexible staking sang fixed-term staking, chỉ có phí gas.

### Điều gì xảy ra khi kết thúc thời gian khóa? "After Burning" là gì?

{% hint style="warning" %}
**After Burning sẽ đốt phần thưởng CAKE tương lai và phần thưởng CAKE đã kiếm được.** Để tránh mất bất kỳ phần thưởng CAKE nào bạn đã kiếm được, chúng tôi khuyên bạn nên bắt đầu một thời gian fixed-term staking mới hoặc chuyển đổi CAKE sang flexible staking khi kết thúc thời gian staking khóa.
{% endhint %}

Khi thời gian fixed-term staking của bạn kết thúc và CAKE của bạn được mở khóa, bạn có 7 ngày để hoàn thành một trong hai lựa chọn:

* Khóa CAKE để bắt đầu thời gian fixed-term staking mới\
  hoặc
* Chuyển đổi CAKE đã stake sang flexible staking (không có phí rút 72 giờ).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20before%20after%20burning.png)

Trong 7 ngày này, bạn vẫn sẽ kiếm được CAKE.

Sau 7 ngày, nếu bạn chưa thực hiện một trong hai lựa chọn, CAKE đã stake của bạn sẽ vào trạng thái gọi là "After Burning". **Với "After Burning", phần thưởng CAKE của bạn (bao gồm cả phần thưởng đã kiếm được) sẽ bắt đầu bị gửi để đốt.** % phần thưởng CAKE bị gửi để đốt sẽ tăng tuyến tính trong 90 ngày "After Burning" cho đến khi đạt 100%, nghĩa là tất cả phần thưởng CAKE bị đốt.

Vì vậy, để tránh mất phần thưởng CAKE, chúng tôi khuyên bạn nên bắt đầu một thời gian fixed-term staking mới hoặc chuyển đổi CAKE sang flexible staking khi kết thúc thời gian staking khóa.

Đây là một ví dụ:

> John đã stake 100 CAKE trong 52 tuần, anh ấy đã kiếm được 50 CAKE trong thời gian staking, và bây giờ thời gian staking đã hết hạn.&#x20;
>
> Sau đó anh ấy không thực hiện bất kỳ hành động nào và vị thế của anh ấy chuyển sang chế độ "After Burning".
>
> Trong 90 ngày After Burning, toàn bộ 50 CAKE anh ấy đã kiếm được sẽ dần bị đốt cùng với bất kỳ CAKE mới nào kiếm được.&#x20;
>
> Sau 90 ngày, phần thưởng anh ấy thực sự kiếm được sẽ trở thành 0. Tuy nhiên, 100 CAKE anh ấy ban đầu gửi vào sẽ không bị ảnh hưởng.
>
> Hãy bắt đầu một thời gian fixed-term staking mới hoặc chuyển sang flexible staking, và đừng như John.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20after%20burning%20started.png)
