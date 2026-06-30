---
hidden: true
---

# FAQ về Chia sẻ doanh thu

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### Cổ phần (rCAKE) được tính như thế nào? <a href="#id-50b7c683-feb0-47f6-809f-39c1a0976bb5" id="id-50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

Với mỗi lần phân phối hàng tuần, cổ phần của mỗi người dùng được tính lại dựa trên:

1. Lượng CAKE bị khóa của họ
2. Thời gian khóa còn lại của CAKE bị khóa làm tròn xuống tuần và thời gian khóa tối đa được phép (hiện tại là 52 tuần)

Ví dụ:

Nếu người dùng có 50 CAKE bị khóa và thời gian khóa còn lại là 10,3 tuần, thì người dùng có `50 * (10 / 52 ) ~= 9.61` cổ phần.

### Tôi đã cập nhật vị thế của mình; tại sao tôi vẫn có 0 cổ phần? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Cổ phần (rCAKE) được cập nhật với mỗi lần phân phối hàng tuần lúc 23:59 UTC mỗi thứ Tư. Hãy kiểm tra lại sau lần phân phối hàng tuần tiếp theo để xem cổ phần đã cập nhật của bạn.

### Tại sao cổ phần của tôi bằng 0 mặc dù có vị thế staking đang hoạt động? <a href="#id-9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="id-9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Khi tính cổ phần (rCAKE), thời gian khóa còn lại được làm tròn xuống tuần. Do đó để nhận cổ phần, bạn phải đảm bảo vị thế staking của mình mở khóa không sớm hơn lần phân phối tiếp theo.

Ví dụ: để nhận cổ phần cho tuần phân phối 1. Bạn phải:

* Tham gia trước 23:59 UTC, ngày 2 tháng 8.
* Có vị thế fixed-term CAKE staking đang hoạt động mở khóa muộn hơn 23:59 UTC, ngày 9 tháng 8.

Nếu vị thế staking của bạn mở khóa trước 23:59 UTC, ngày 9 tháng 8, bạn sẽ nhận được 0 cổ phần cho tuần 1.

### Tôi có thể tham gia vào giữa tuần của giai đoạn phân phối không? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Không, như đã đề cập, cổ phần được tính vào đầu giai đoạn phân phối lúc 23:59 UTC vào thứ Tư mỗi tuần. Do đó bạn sẽ nhận cổ phần bắt đầu từ lần phân phối tiếp theo và bắt đầu tích lũy phần thưởng từ thời điểm đó.

### Làm thế nào để nhận thêm cổ phần? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Vì cổ phần được tính dựa trên số lượng CAKE và thời gian khóa còn lại, để nhận thêm cổ phần, bạn có thể:

* Khóa thêm CAKE
* Gia hạn vị thế staking của bạn

Lưu ý rằng sau khi thêm CAKE hoặc gia hạn, cổ phần KHÔNG được cập nhật theo thời gian thực và chỉ được cập nhật với mỗi lần phân phối hàng tuần của tuần.

### Tôi có cần cập nhật vị thế staking khi thêm CAKE hoặc gia hạn staking không? <a href="#id-71d1d397-ac1c-454b-abd9-15492860f05c" id="id-71d1d397-ac1c-454b-abd9-15492860f05c"></a>

Không, bạn chỉ cần đăng ký một lần. Tất cả các hoạt động pool CAKE staking tiếp theo sẽ tự động thông báo cho pool chia sẻ doanh thu và cập nhật cổ phần của bạn trong mỗi lần phân phối hàng tuần.

### Tại sao phần thưởng được nạp hàng tuần không khớp 100% với khối lượng được hiển thị trên các tracker khác nhau (như trang Info)?

Số lượng phần thưởng CAKE được nạp hàng tuần có thể không khớp 100% với các con số được tính từ khối lượng hiển thị trên các tracker khác nhau. Nhiều yếu tố bên ngoài có thể ảnh hưởng đến số lượng phần thưởng CAKE có thể được chuyển đổi:

* Giá token CAKE khi phí giao dịch đang được chuyển đổi và xử lý
* Giá tài sản cơ bản khi phí giao dịch đang được chuyển đổi và xử lý
* Để tiết kiệm gas và chi phí vận hành. Doanh thu từ các blockchain khác ngoài BNB Chain được xử lý hàng tháng. Chúng sẽ được nạp với độ trễ một tháng với mức trung bình hàng tuần.
* Một số cặp giao dịch có thể thiếu thanh khoản khi xử lý phí giao dịch.
* Một số cặp giao dịch có thể chứa các token với logic tùy chỉnh ngăn phí của chúng bị xử lý.

Các Chefs đang nỗ lực áp dụng các công cụ và thực tiễn để đảm bảo nhiều phí giao dịch được tạo ra có thể được xử lý và chuyển đổi thành CAKE hơn.
