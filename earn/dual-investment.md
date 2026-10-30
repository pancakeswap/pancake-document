# 🍩 Dual Investment

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201%20%282%29.png" alt=""><figcaption></figcaption></figure>

Dual Investment cho phép bạn cam kết vốn tại một mức giá mục tiêu và nhận phần thưởng cố định, dù thị trường chốt theo hướng nào. Hãy chọn một tài sản, chọn **Buy Low** hoặc **Sell High**, rồi chọn giá mục tiêu và ngày thanh toán. Khi thanh toán, bạn nhận lại tiền gốc cộng phần thưởng, bằng tài sản bạn đã gửi hoặc bằng tài sản được quy đổi theo giá mục tiêu của bạn.

Dual Investment hiện đã hoạt động trên BNB Chain với **BTCB** và **BNB**, cặp với **USDT**.

{% hint style="info" %}
Dual Investment không phải là sản phẩm tiết kiệm. Tùy vào giá thanh toán, vốn của bạn có thể được quy đổi sang một tài sản khác theo giá mục tiêu của bạn, và tài sản đó có thể có giá trị thấp hơn số bạn đã gửi.
{% endhint %}

***

## Dual Investment là gì?

#### **Hai kết quả, một phần thưởng cố định**

Mỗi sản phẩm Dual Investment có một giá mục tiêu và một ngày thanh toán. Khi bạn đăng ký, phần thưởng của bạn được chốt theo APR hiển thị. Khi thanh toán, giá thị trường quyết định bạn nhận một trong hai kết quả:

* **Giá không chạm mục tiêu của bạn.** Bạn nhận lại tài sản ban đầu cộng phần thưởng.
* **Giá chạm mục tiêu của bạn.** Tiền gốc và phần thưởng của bạn được quy đổi sang tài sản còn lại theo giá mục tiêu của bạn.

Bạn nhận được phần thưởng trong cả hai trường hợp. Điều duy nhất thay đổi là loại tài sản bạn nhận.

#### **Buy Low**

Dùng Buy Low khi bạn sẵn lòng mua BTCB hoặc BNB với giá thấp hơn giá hôm nay. Bạn gửi **USDT** và chọn giá mục tiêu thấp hơn giá hiện tại.

| Giá thanh toán          | Bạn nhận được                                                   |
| ----------------------- | --------------------------------------------------------------- |
| Bằng hoặc cao hơn mục tiêu của bạn | USDT (tiền gốc + phần thưởng)                        |
| Thấp hơn mục tiêu của bạn | BTCB hoặc BNB, được mua theo giá mục tiêu của bạn cùng với phần thưởng |

#### **Sell High**

Dùng Sell High khi bạn sẵn lòng bán BTCB hoặc BNB với giá cao hơn giá hôm nay. Bạn gửi **BTCB hoặc BNB** và chọn giá mục tiêu cao hơn giá hiện tại.

| Giá thanh toán          | Bạn nhận được                                          |
| ----------------------- | ------------------------------------------------------ |
| Bằng hoặc thấp hơn mục tiêu của bạn | BTCB hoặc BNB (tiền gốc + phần thưởng)     |
| Cao hơn mục tiêu của bạn | USDT, được bán theo giá mục tiêu của bạn cùng với phần thưởng |

#### **APR hoạt động như thế nào**

APR phụ thuộc vào mức độ gần nhau giữa giá mục tiêu và giá hiện tại, cũng như thời gian chạy của sản phẩm. Các mục tiêu gần giá hiện tại hơn có APR cao hơn vì khả năng bị quy đổi cao hơn. Các mục tiêu xa hơn trả thấp hơn nhưng nhiều khả năng bạn sẽ nhận lại tài sản ban đầu.

Phần thưởng của bạn được tính như sau:

`Reward = Subscription amount × APR × (Days to settlement ÷ 365)`

#### **Ví dụ: Buy Low**

BTCB đang giao dịch ở mức $83,467. Bạn đăng ký 1,000 USDT vào sản phẩm Buy Low 1 ngày với giá mục tiêu $82,000 và APR 14.68%. Phần thưởng của bạn khoảng 0.40 USDT.

| Giá thanh toán   | Bạn nhận được                         |
| ---------------- | ------------------------------------- |
| $82,000 trở lên  | 1,000.40 USDT                         |
| Dưới $82,000     | 0.0122 BTCB (1,000.40 USDT ÷ $82,000) |

Nếu BTCB thanh toán ở mức $78,000, bạn vẫn mua ở mức $82,000. Bạn sẽ nắm giữ 0.0122 BTCB trị giá khoảng 951.60 USDT, thấp hơn số bạn đã gửi.

#### **Ví dụ: Sell High**

BTCB đang giao dịch ở mức $83,467. Bạn đăng ký 0.01 BTCB vào sản phẩm Sell High 1 ngày với giá mục tiêu $84,500 và APR 89.28%. Phần thưởng của bạn khoảng 0.0000245 BTCB.

| Giá thanh toán   | Bạn nhận được                          |
| ---------------- | -------------------------------------- |
| $84,500 trở xuống | 0.0100245 BTCB                        |
| Trên $84,500     | 847.07 USDT (0.0100245 BTCB × $84,500) |

Nếu BTCB thanh toán ở mức $88,000, bạn vẫn bán ở mức $84,500. Bạn sẽ nhận 847.07 USDT cho lượng BTCB lẽ ra có giá trị khoảng 882 USDT.

#### **Ai là đối tác phía bên kia?**

Mỗi sản phẩm được báo giá bởi một market maker, người đứng ở phía đối diện với vị thế của bạn. Market maker đặt một khoản bond để đảm bảo khoản chi trả cho bạn. Nếu market maker vỡ nợ, yêu cầu của bạn sẽ được đảm bảo bằng bond của họ.

***

## Cách sử dụng Dual Investment

#### **Truy cập trang Dual Investment**

Truy cập [pancakeswap.finance/dual-investment](https://pancakeswap.finance/dual-investment?chain=bsc) hoặc nhấp vào **Dual Investment** trên thanh điều hướng chính của PancakeSwap.

#### **1. Chọn tài sản mục tiêu**

Chọn **BTCB** hoặc **BNB**. Mỗi thẻ hiển thị giá hiện tại và khoảng APR có sẵn trên tất cả sản phẩm của tài sản đó.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28407%29.png" alt=""><figcaption></figcaption></figure>

#### **2. Chọn hướng giao dịch**

Chọn **Buy Low** để gửi USDT và mua tài sản ở mức giá thấp hơn, hoặc **Sell High** để gửi tài sản và bán ở mức giá cao hơn.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28430%29.png" alt=""><figcaption></figcaption></figure>

#### **3. Chọn ngày thanh toán và giá mục tiêu**

Dùng các bộ lọc thời hạn (**1 Day**, **< 3 Days**, **< 7 Days** và dài hơn) để thu hẹp danh sách. Các sản phẩm được nhóm theo ngày thanh toán. Mỗi hàng hiển thị giá mục tiêu, khoảng cách so với giá hiện tại và APR.

Đồng hồ đếm ngược bên cạnh mỗi ngày thanh toán cho biết bạn còn bao nhiêu thời gian để đăng ký. Việc đăng ký đóng trước thời điểm thanh toán.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28475%29.png" alt=""><figcaption></figcaption></figure>

#### **4. Nhập số tiền đăng ký**

Nhấp **Subscribe** ở mục tiêu bạn muốn, rồi nhập số tiền hoặc nhấn **MAX**. Mỗi sản phẩm có mức tối thiểu và tối đa cho mỗi lần đăng ký, cùng tổng hạn mức cố định. Khi một mục tiêu đã được đăng ký đầy, nó không thể mở lại, nên bạn sẽ cần chọn một giá mục tiêu khác.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28476%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### **5. Xem lại và xác nhận**

Xem lại hướng giao dịch, giá mục tiêu, ngày thanh toán và cả hai kết quả.&#x20;

Tỷ lệ được giữ trong một thời gian ngắn trong lúc bạn xác nhận. Nếu nó hết hạn hoặc thay đổi, trang sẽ lấy tỷ lệ mới và yêu cầu bạn chấp nhận trước khi tiếp tục.

#### **6. Nhận khoản chi trả của bạn**

Sau khi thanh toán, nhấp **Claim** trên một vị thế, hoặc **Claim all** để nhận tất cả vị thế đã thanh toán cùng lúc. Khoản chi trả sẽ được gửi vào ví của bạn bằng tài sản được xác định theo kết quả thanh toán.

***

## FAQ về Dual Investment

#### **Dual Investment là gì?**

Dual Investment là sản phẩm cho phép bạn cam kết vốn tại một mức giá mục tiêu và nhận phần thưởng cố định. Khi thanh toán, bạn nhận tiền gốc cộng phần thưởng, bằng tài sản ban đầu hoặc được quy đổi sang tài sản còn lại theo giá mục tiêu của bạn.

#### **Những tài sản nào được hỗ trợ?**

BTCB và BNB, cặp với USDT, trên BNB Chain.

#### **Buy Low và Sell High khác nhau như thế nào?**

Buy Low cho phép bạn gửi USDT và mua BTCB hoặc BNB ở mức giá mục tiêu thấp hơn giá hiện tại. Sell High cho phép bạn gửi BTCB hoặc BNB và bán ở mức giá mục tiêu cao hơn giá hiện tại.

#### **Tôi có nhận được phần thưởng trong cả hai kết quả không?**

Có. Phần thưởng được cố định khi bạn đăng ký và được trả trong cả hai kết quả. Nó được trả cùng với tiền gốc, bằng loại tài sản bạn nhận khi thanh toán.

#### **Tôi có thể rút trước ngày thanh toán không?**

Không. Sau khi đăng ký, vốn của bạn bị khóa cho đến khi thanh toán và không thể hủy đăng ký.

#### **Tại sao APR giữa các sản phẩm lại khác nhau?**

Các mục tiêu gần giá hiện tại hơn và ngày thanh toán ngắn hơn thường trả APR cao hơn vì có khả năng quy đổi cao hơn. Tỷ lệ được báo giá trực tiếp và có thể thay đổi giữa lúc bạn mở sản phẩm và lúc bạn xác nhận.

#### **Tại sao tỷ lệ thay đổi trong lúc tôi đang đăng ký?**

Tỷ lệ được các market maker báo giá trực tiếp và chỉ được giữ trong thời gian ngắn. Nếu tỷ lệ hết hạn, thay đổi hoặc người dùng khác khớp mức giá đó trước, trang sẽ lấy tỷ lệ mới và yêu cầu bạn chấp nhận trước khi tiếp tục.

#### **Tôi có cần nhận khoản chi trả của mình không?**

Có. Sau khi thanh toán, hãy nhận khoản chi trả từ **Your Holdings**. Bạn có thể nhận từng vị thế một hoặc dùng **Claim all**.

#### **Ai đứng ở phía đối diện với vị thế của tôi?**

Các market maker báo giá cho từng sản phẩm và đứng ở phía đối diện với vị thế của bạn. Họ đặt một khoản bond để đảm bảo khoản chi trả cho bạn, và nếu market maker vỡ nợ, yêu cầu của bạn sẽ được đảm bảo bằng khoản bond đó.

#### **Có thu phí nào không?**

Hoàn toàn miễn phí.
