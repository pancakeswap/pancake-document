---
hidden: true
---

# FAQ về bỏ phiếu Gauges

### Tôi có vị thế hoạt động, tại sao tôi không thể bỏ phiếu? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Vui lòng đảm bảo thời gian mở khóa của bạn bằng hoặc muộn hơn 1 tuần sau thời điểm snapshot của epoch hiện tại.&#x20;

Nếu vị thế của bạn đang mở khóa tại thời điểm snapshot, nghĩa là bạn có 0 veCAKE tại thời điểm snapshot. Do đó bạn không thể bỏ phiếu.



### Có thể bỏ phiếu ngay sau khi thiết lập vị thế veCAKE không?

Có.

Khi vị thế của bạn được thiết lập, bạn có thể sử dụng cake để bỏ phiếu ngay lập tức.

Tuy nhiên:

* Không thể bỏ phiếu trong 24 giờ cuối của một epoch.
* Bạn không thể cập nhật quyết định bỏ phiếu của mình trên một gauge cụ thể thường xuyên hơn 10 ngày.
* Vui lòng đảm bảo vị thế của bạn không mở khóa trước hoặc tại thời điểm snapshot.



### Tôi có thể có thêm veCAKE hoặc phiếu bầu không?

Có, chỉ cần thêm CAKE hoặc gia hạn vị thế khóa.

Lưu ý rằng sau khi có thêm veCAKE bằng cách thêm CAKE hoặc gia hạn thời gian khóa. Bạn cần cập nhật thủ công mọi gauge bằng cách gửi lại yêu cầu bỏ phiếu.



### Tại sao kết quả bỏ phiếu thay đổi sau giai đoạn tổng hợp?

Trong giai đoạn tổng hợp, PancakeSwap Kitchen sẽ bỏ phiếu dựa trên các số liệu khác nhau từ tất cả các gauge.&#x20;

Mục tiêu là:

* Đảm bảo các pool thanh khoản cốt lõi nhận được lợi nhuận cạnh tranh trên các vị thế LP của họ
* Đảm bảo rằng các thỏa thuận đối tác Syrup Pool hiện có được đáp ứng trước khi chuyển hoàn toàn sang hệ thống bỏ phiếu veCAKE gauge
* Đảm bảo rằng bất kỳ farm nhỏ hơn nào không nhận được phiếu bầu nào sau khi khởi chạy veCAKE sẽ nhận được ít nhất một số phân bổ trong đợt triển khai ban đầu, được giới hạn ở mức emission hiện tại của chúng.

Xem đề xuất này để biết thêm chi tiết: [https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c](https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c)



### Tại sao số phiếu bầu của tôi đang giảm?

Vì khi chúng ta bỏ phiếu cho các gauge, chúng ta bỏ phiếu bằng veCAKE. Và số dư veCAKE giảm dần theo thời gian khóa còn lại.&#x20;

Phiếu bầu của bạn sẽ giảm xuống 0 khi vị thế veCAKE của bạn mở khóa.

Để có thêm phiếu bầu, hãy mua thêm veCAKE bằng cách thêm CAKE vào khóa, hoặc gia hạn khóa.



### Sau khi có thêm veCAKE, tại sao tôi không thể bỏ phiếu cho nhiều gauge hơn?

Khi bỏ phiếu cho các gauge, chúng ta bỏ phiếu bằng cách xác định bao nhiêu % veCAKE của chúng ta đi vào mỗi gauge.

Do đó, mặc dù bạn đã có thêm veCAKE. Nếu bạn đã phân bổ 100% veCAKE trong 10 ngày trước, bạn không thể thay đổi quyết định cho đến khi kết thúc giai đoạn cooldown 10 ngày.



### Kết quả bỏ phiếu đã được tổng hợp, tại sao tỷ lệ emission không thay đổi?

Cần khoảng 72 giờ để áp dụng kết quả bỏ phiếu vào các sản phẩm emission khác nhau trên PancakeSwap. Các Chefs sẽ tiếp tục tự động hóa quy trình này để rút ngắn khoảng cách cũng như cải thiện độ chính xác.



### Tại sao gauge tôi bỏ phiếu không nhận được bất kỳ emission CAKE nào trong epoch tiếp theo?

Các gauge được đưa vào danh sách trắng cần nhận phiếu bầu tương ứng với tối thiểu 1 CAKE mỗi ngày trong emissions, trước khi có thể nhận bất kỳ CAKE nào.
