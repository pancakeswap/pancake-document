# Máy tính APR/ROI/IL

Trong Thanh khoản và Farms V3, với thanh khoản non-fungible mới và khả năng phạm vi giá có thể tùy chỉnh. Mỗi vị thế LP sẽ có APR phí LP riêng và APR farming CAKE riêng.

Để làm cho việc cung cấp thanh khoản mượt mà và ít thách thức hơn, hiển thị APR tự động mới với máy tính ROI hoàn toàn mới có sẵn để sử dụng bất cứ khi nào bạn cung cấp thanh khoản hoặc farming.

## Tính toán và hiển thị APR tự động <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

Khi bạn cung cấp thanh khoản, hiển thị APR tự động phản ứng với các thay đổi cấu hình và tính toán APR dựa trên cài đặt của bạn.

Ví dụ, trong hầu hết các trường hợp, nếu bạn thu hẹp cài đặt phạm vi giá, APR tăng lên.

Lưu ý đối với APR phí LP:

* Lượng phần thưởng phí LP ước tính thay đổi dựa trên mức phí đã chọn, phần thưởng phí yêu cầu thu hoạch và gộp lãi thủ công.
* Các con số APR được tính bằng khối lượng giao dịch lịch sử, phụ thuộc vào Subgraph và có thể bị trễ lập chỉ mục.

Đối với APR farming:

* Lượng phần thưởng CAKE ước tính dựa trên emissions CAKE trực tiếp vào farms. Chúng có thể thay đổi dựa trên các điều chỉnh emission trong tương lai.

{% hint style="info" %}
Các con số được tính ở mức hiện tại và điều kiện pool và có thể thay đổi dựa trên các biến bên ngoài khác nhau. Chúng là ước tính được cung cấp cho sự tiện lợi của bạn và không đại diện cho lợi nhuận được đảm bảo.
{% endhint %}

Bạn có thể tìm hiển thị APR này trong:

* Trang "Add Liquidity" - hiển thị APR phí LP
* Trang chi tiết của mỗi vị thế thanh khoản hiện có - hiển thị APR phí LP\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* Trang Farm, trong vị thế dưới mỗi farm - hiển thị APR kết hợp với phí LP và phần thưởng CAKE\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## Máy tính ROI cải tiến <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

Bất cứ khi nào bạn thấy hiển thị APR tự động, bạn có thể nhấp và mở máy tính ROI mới. Máy tính ROI mới đã được thiết kế lại với một số tính năng bổ sung để phù hợp với nhu cầu cung cấp thanh khoản tập trung V3 và farming.

Hãy cùng đi qua từng phần:

### Số tiền Nạp, "Đã Stake Trong" và "Gộp lãi Mỗi" <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Ba mục này là các đầu vào cơ bản, cũng có trong máy tính ROI trước. Chúng xác định:

1. Bao nhiêu tài sản được cung cấp cho vị thế thanh khoản, tính bằng USD.
2. Trong bao lâu các tài sản đó sẽ được stake trong vị thế.
3. Bạn sẽ gộp lãi phần thưởng trở lại vị thế bao thường xuyên.



⓵ **Số tiền Nạp**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

Bạn có thể nhập thủ công số tiền bằng USD hoặc sử dụng các nút hành động nhanh để nhanh chóng điền vào $100, $1000 hoặc số tiền tối đa cho phép dựa trên số dư token trong ví của bạn.



⓶ **Thời gian Stake**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

Bạn có thể chọn thời gian tài sản được stake trong vị thế thanh khoản bằng cách chọn giữa: 1 ngày, 7 ngày, 30 ngày, 1 năm và 5 năm.

Số lợi nhuận sẽ được tính dựa trên thời gian stake của bạn.



⓷ **Gộp lãi**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

Bạn có thể chọn tần suất thu hoạch phần thưởng được tạo ra bởi vị thế và gộp lãi chúng trở lại vị thế. Bạn có thể chọn số giữa: 12 giờ, 1 ngày, 7 ngày và 30 ngày.

Số lợi nhuận và APY sẽ được tính dựa trên lựa chọn của bạn. Nếu bạn không có kế hoạch gộp lãi vị thế, hãy bỏ chọn checkbox ở bên trái.

{% hint style="info" %}
Trong V3, phí LP và CAKE kiếm được phải được thu hoạch và gộp lãi thủ công.
{% endhint %}

### &#x20;⓸ Lịch sử Giá <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

Đây là phần chỉ xem để tham khảo biến động giá lịch sử của cặp được chọn.

Bạn có thể tham khảo các biến động giá lịch sử trong các khung thời gian khác nhau, chẳng hạn như giá thường dao động bao nhiêu và sau đó đưa ra cài đặt phạm vi giá phù hợp để cân bằng giữa APR cao hơn và rủi ro tổn thất tạm thời thấp hơn

* MIN - giá tối thiểu
* MAX - giá tối đa
* AVG - giá trung bình
* CURRENT - giá hiện tại

{% hint style="info" %}
Biểu đồ giá chỉ sử dụng dữ liệu từ cặp V3 thực tế. Do đó dữ liệu giá trước khi triển khai V3 không có sẵn. Bốn số liệu giá đại diện cho khung thời gian được chọn hiện tại và sẽ thay đổi dựa trên lựa chọn.
{% endhint %}

### ⓹ Phạm vi Giá <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

Sử dụng phần này, bạn có thể kiểm tra bao nhiêu thanh khoản đã được nạp vào các phạm vi giá khác nhau và đưa ra và đặt phạm vi giá bạn đang cung cấp thanh khoản.

Bạn có thể tìm biểu đồ phân phối bên dưới tiêu đề. Lượng thanh khoản càng lớn, biểu đồ càng cao.

Bạn có thể thay đổi cài đặt phạm vi giá bằng cách:

* Kéo hai tay cầm trên biểu đồ để tăng hoặc giảm giới hạn giá tối thiểu và tối đa.
* Sử dụng khoảng trống giữa hai tay cầm để dịch phạm vi đã chọn.
* Nhấp nút + và - trên các trường giá min và max.
* Nhấp vào số trong các trường giá và nhập thủ công.

Nếu bạn muốn điều hướng biểu đồ phân phối:

1. Sử dụng các nút kính lúp cộng và trừ để phóng to và thu nhỏ
2. Kéo trục X (phía dưới) để dịch sang trái và phải

Nếu bạn muốn cung cấp thanh khoản cho toàn bộ phạm vi giá, nhấp "Full Range"

### ⓺ Lật hướng giá để xem giá với base khác nhau <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

Đối với một số cặp token, sẽ dễ dàng và trực quan hơn khi xem giá với một số token cơ sở nhất định. Ví dụ, đối với cặp BNB/USDT, hầu hết mọi người sẽ thích xem giá theo "bao nhiêu USDT mỗi BNB" hơn là ngược lại.

Bạn có thể dễ dàng lật hiển thị giá. Chỉ cần nhấp nút theo sau "View prices in:" để chuyển đổi base giữa hai token trong cặp.

### ⓻ Import và export (áp dụng) cài đặt của bạn <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

Khi bạn mở máy tính ROI trong cửa sổ "Add Liquidity" hoặc bằng cách xem vị thế hiện có, các cài đặt sau sẽ được tự động import để bạn không cần đặt lại:

1. Số lượng tài sản bạn đang nạp
2. Phạm vi giá
3. Mức phí đã chọn

Khi bạn hoàn thành cấu hình trong máy tính ROI, bạn có thể nhấp "Apply Settings" để nhanh chóng áp dụng cài đặt từ máy tính trở lại cửa sổ "Add Liquidity" để bạn không cần khớp thủ công.

### ⓼ Tính toán phần thưởng farming và APR <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

Phần thưởng farming sẽ được bao gồm trong các tính toán nếu bạn mở máy tính ROI trong trang "Farm".

Bạn có thể mở rộng các phần chi tiết để xem phân tích phần thưởng.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
