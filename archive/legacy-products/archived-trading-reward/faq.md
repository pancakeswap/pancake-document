---
description: FAQ về Trading Reward
---

# FAQ

{% hint style="danger" %}
\[Đã lưu trữ] Trading Reward – Kể từ ngày 23 tháng 8 năm 2024
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## Chung

#### Tại sao khối lượng giao dịch của tôi không được ghi nhận?

* Số liệu khối lượng cần thời gian để cập nhật và có thể bị chậm do SubGraph. Vui lòng kiểm tra lại sau
* Giao dịch của bạn phải được định tuyến qua **đúng** cặp giao dịch đang được nêu bật trên [trang Trading Reward](https://pancakeswap.finance/trading-reward#rewards-breakdown), bao gồm cả bậc phí. Xem [hướng dẫn này](https://docs.pancakeswap.finance/trade/pancakeswap-exchange/fees-and-routes) để biết cách xem các tuyến giao dịch của bạn
* Chỉ các cặp giao dịch V3 mới đủ điều kiện tham gia chương trình này
* Vui lòng dùng cùng một địa chỉ ví đủ điều kiện tham gia chương trình trading reward trên cả Ethereum và BNB Chain
* Nếu khối lượng giao dịch của bạn trong một cặp quá nhỏ, bạn có thể không đủ điều kiện nhận bất kỳ phần thưởng nào
* Sử dụng các trình tổng hợp giao dịch của bên thứ ba có thể khiến giao dịch được định tuyến qua các nhà cung cấp thanh khoản khác và không được ghi nhận

#### Tại sao tôi giao dịch nhiều nhưng chỉ nhận được rất ít phần thưởng

Số phần thưởng trading reward dựa trên phí giao dịch đã trả trong các giao dịch đó.

Nếu giao dịch của bạn được định tuyến qua các cặp có bậc phí thấp, ví dụ 0,01%, bạn đang trả phí rất nhỏ cho giao dịch. Do đó số phần thưởng sẽ thấp tương ứng.

## Chiến dịch Top Traders

#### Tôi có cần giữ thứ hạng yêu cầu trong suốt thời gian để thắng chiến dịch không?

Không, bạn chỉ cần xếp hạng cao hơn thứ hạng yêu cầu **vào cuối chiến dịch**. Tuy nhiên nên xếp hạng cao hơn và duy trì thứ hạng. Và hãy nhớ kiểm tra thường xuyên để đảm bảo bạn không tụt khỏi thứ hạng yêu cầu.

#### Thứ hạng dựa trên con số nào?

Thứ hạng dựa trên số phần thưởng mà mỗi người dùng tích lũy được nhờ giao dịch. Số phần thưởng bằng một % cố định của khoản phí họ trả trong các giao dịch.

## Chiến dịch CAKE Stakers

#### Địa chỉ của tôi đủ điều kiện cho chiến dịch trước. Tại sao lại không đủ điều kiện cho chiến dịch mới nhất?

Mỗi chiến dịch có yêu cầu điều kiện riêng, như ngưỡng tối thiểu của lượng veCAKE tại thời điểm snapshot.

Ngoài ra, thời điểm snapshot được đặt là thời gian kết thúc của mỗi chiến dịch. Do veCAKE giảm dần theo thời gian, số dư veCAKE của bạn có thể xuống dưới ngưỡng cho các chiến dịch sau.

Bạn có thể cần tăng veCAKE của mình. Chỉ cần làm theo hướng dẫn trên trang.

#### Tại sao hệ thống báo tôi có thêm phần thưởng không thể nhận?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

Lượng veCAKE tại thời điểm snapshot sẽ quyết định số phần thưởng tối đa bạn có thể kiếm được từ chiến dịch. Xem chú thích ở phần “Max Reward Cap”.

Trong khi chiến dịch đang diễn ra, bạn có thể tăng veCAKE và nâng mức giới hạn này bất cứ lúc nào.

#### “veCAKE tại thời điểm snapshot” là gì

veCAKE giảm dần theo thời gian khi thời gian khóa còn lại giảm. Do đó, tương tự iCAKE của IFO, số dư veCAKE snapshot - số dư veCAKE tại một thời điểm cụ thể, mang tính tĩnh, phù hợp hơn để dùng làm tiêu chí đánh giá điều kiện.

Trong Trading Reward, thời điểm snapshot là lúc kết thúc mỗi chiến dịch. Do đó, “số dư veCAKE của bạn tại thời điểm snapshot” nghĩa là “số dư veCAKE của bạn vào thời điểm chiến dịch kết thúc”.

#### “veCAKE tại thời điểm snapshot” liên quan thế nào đến chiến dịch

* Số dư veCAKE của bạn tại thời điểm snapshot cao hơn ngưỡng yêu cầu
* Số phần thưởng tối đa bạn có thể kiếm được gắn với y % số dư veCAKE của bạn tại thời điểm snapshot

Ví dụ:

1. Alice khóa 300 CAKE trong 2 năm (104 tuần) vào ngày đầu tiên. Vào ngày đầu tiên, Alice sẽ có số dư veCAKE là `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149` .
2. Một chiến dịch trading reward được khởi chạy vào ngày đầu tiên, với ngưỡng veCAKE là 100 và giới hạn thưởng 1%. Chiến dịch kết thúc sau 30 ngày.
3. Sau 30 ngày, vị thế của Alice sẽ còn khoảng 99,71 tuần thời gian khóa, do đó số dư veCAKE là `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143`.
4. Vì vậy, với chiến dịch này, Alice sẽ có `143` veCAKE tại thời điểm snapshot.
5. 143 lớn hơn 100 nên Alice đủ điều kiện tham gia chiến dịch, cô ấy có thể bắt đầu giao dịch các cặp đủ điều kiện để kiếm trading reward.
6. Với giới hạn thưởng 1%, số CAKE tối đa Alice có thể kiếm được từ chiến dịch này là `143 * 1% = 1.43` CAKE.
7. Alice có thể tăng veCAKE bất cứ lúc nào trước khi chiến dịch kết thúc, bằng cách khóa thêm CAKE hoặc gia hạn vị thế của mình.

#### Làm thế nào để kiểm tra veCAKE tại thời điểm snapshot của tôi trong chiến dịch?

Bạn có thể kiểm tra trên trang Trading Reward.

Trang sẽ cảnh báo bạn khi veCAKE tại thời điểm snapshot của bạn thấp hơn ngưỡng hoặc phần thưởng của bạn hiện đang bị giới hạn bởi nó.

Trong những trường hợp đó, bạn có thể nhấp vào nút “Increase veCAKE” để tăng veCAKE mà không cần rời khỏi trang.

#### Tôi có thể tăng veCAKE trong thời gian chiến dịch không?

Có, bạn có thể tăng veCAKE bất cứ lúc nào trước khi chiến dịch kết thúc. “veCAKE tại thời điểm snapshot” của bạn sẽ được cập nhật tương ứng.
