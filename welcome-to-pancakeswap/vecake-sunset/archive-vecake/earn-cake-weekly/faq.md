# FAQ

### Tôi đã khóa CAKE hoặc chuyển đổi vị trí CAKE pool của mình. Tại sao tôi vẫn có 0 cổ phần? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Cổ phần được cập nhật sau mỗi lần phân phối hàng tuần vào lúc 00:00 UTC mỗi thứ Năm.

Phần thưởng được tích lũy bất cứ khi nào bạn đã hoàn thành staking trong một epoch đầy đủ.&#x20;

Các epoch là các khoảng thời gian 7 ngày, bắt đầu vào mỗi thứ Năm, UTC 00:00. Ví dụ, nếu bạn staking vào thứ Ba. Epoch đầu tiên của bạn sẽ bắt đầu vào thứ Năm. Sau khi bạn đã hoàn thành staking đến thứ Năm tiếp theo, bạn sẽ có thể nhận phần thưởng từ thứ Năm này đến thứ Năm tiếp theo, tức là epoch 1.

Kiểm tra lại mỗi thứ Năm để xem số phần thưởng cập nhật.

### Tại sao cổ phần/phần thưởng của tôi là 0 mặc dù tôi có vị trí staking đang hoạt động? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Khi tính toán phần thưởng, thời gian khóa còn lại được làm tròn xuống theo tuần. Do đó, để nhận cổ phần, bạn phải đảm bảo vị trí staking của mình mở khóa không sớm hơn thứ Năm 00:00 UTC tiếp theo.

Ví dụ, tuần 1 bắt đầu lúc 00:00 UTC, thứ Năm, ngày 1 tháng 1. Để nhận phần thưởng cho đợt phân phối tuần 1, bạn phải:

* Tham gia trước 00:00 UTC, ngày 1 tháng 1.
* Có vị trí staking veCAKE đang hoạt động, mở khóa bằng hoặc muộn hơn 00:00 UTC, ngày 15 tháng 1. (thứ Năm tuần 3)

Lưu ý rằng nếu vị trí staking của bạn mở khóa lúc 00:00 UTC, ngày 8 tháng 1 (thứ Năm tuần 2), bạn vẫn sẽ nhận 0 phần thưởng cho tuần 1 vì số dư veCAKE của bạn chuyển sang 0 lúc 00:00 UTC, ngày 8 tháng 1.

### Tôi có thể tham gia một kỳ phân phối giữa tuần không? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Không, như đã đề cập, phần thưởng chỉ có thể bắt đầu tích lũy khi bạn đã staking từ đầu epoch. Đó là mỗi tuần vào lúc 00:00 UTC, thứ Năm.&#x20;

### Làm thế nào để tôi nhận được nhiều phần thưởng hơn? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Vì cổ phần của bạn trong các pool được tính dựa trên số dư veCAKE tại thời điểm phân phối, tức là 00:00 UTC thứ Năm tới. Để nhận được nhiều phần thưởng hơn, chỉ cần tăng số dư veCAKE của bạn bằng cách:

* Khóa thêm CAKE vào vị trí staking veCAKE
* Gia hạn vị trí staking của bạn

Lưu ý rằng sau khi thêm CAKE hoặc gia hạn, cổ phần của bạn chỉ được cập nhật sau khi bắt đầu epoch tiếp theo, tức là 00:00 UTC thứ Năm sắp tới.

### Tại sao phần thưởng CAKE được tiêm hàng tuần không khớp 100% với khối lượng hiển thị trên các trình theo dõi khác nhau (như trang Info)? Tại sao phần thưởng CAKE pool hàng tuần không khớp 100% với kết quả bỏ phiếu gauges?

Số lượng phần thưởng CAKE được tiêm hàng tuần có thể không khớp 100% với các con số được tính từ khối lượng hiển thị trên các trình theo dõi khác nhau. Nhiều yếu tố bên ngoài có thể ảnh hưởng đến số lượng phần thưởng CAKE có thể được chuyển đổi:

* Giá token CAKE trong khi phí giao dịch đang được chuyển đổi và xử lý
* Giá tài sản cơ bản trong khi phí giao dịch đang được chuyển đổi và xử lý
* Để tiết kiệm gas và chi phí vận hành, doanh thu từ các blockchain khác ngoài BNB Chain được xử lý hàng tháng. Chúng sẽ được tiêm với độ trễ một tháng với mức trung bình hàng tuần.
* Một số cặp giao dịch có thể có thanh khoản không đủ trong khi xử lý phí giao dịch.
* Một số cặp giao dịch có thể chứa các token với logic tùy chỉnh ngăn phí của chúng được xử lý.
* Độ trễ giao dịch do hiệu suất cơ sở hạ tầng và hệ thống hỗ trợ.

Các đầu bếp đang nỗ lực áp dụng các công cụ và thực hành để đảm bảo nhiều phí giao dịch được tạo ra hơn có thể được xử lý và chuyển đổi thành CAKE.
