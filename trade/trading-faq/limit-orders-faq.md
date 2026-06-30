# FAQ

{% hint style="info" %}
Sử dụng thanh bên để nhanh chóng tìm câu trả lời cho câu hỏi của bạn!
{% endhint %}

## Lệnh Giới Hạn và TWAP

Vui lòng tham khảo FAQ được cung cấp bởi Orbs:

[https://www.orbs.com/dtwap-and-dlimit-faq/](https://www.orbs.com/dtwap-and-dlimit-faq/)

## Limit V2 (Đã Ngừng Hỗ Trợ)

### Tại sao tôi không tìm thấy lệnh của mình?

Lệnh giới hạn V2 hiện đã ngừng hỗ trợ, vui lòng truy cập bằng liên kết này:

[https://pancakeswap.finance/limit-orders](https://pancakeswap.finance/limit-orders)

### Tại sao lệnh của tôi không được thực thi?

Lệnh giới hạn được thực thi khi đạt đến mức giá mong muốn, tuy nhiên, do biến động phí gas, giá thực thi thực tế có thể khác với giá bạn đã chỉ định trên giao diện. Thông thường, giá thực thi và giá mong muốn phải gần giống nhau, tuy nhiên, nếu bạn đã gửi lệnh đặc biệt nhỏ (\~<1000$), giá thực thi có thể hơi cao hơn để tính phí.&#x20;

Do đó, lệnh của bạn có thể không được thực thi vì:

* Không thể khớp toàn bộ lệnh ở mức giá và số lượng mong muốn do tác động giá.
* Một trong các token trong lệnh giới hạn có phí khi chuyển nhượng (xem bên dưới).

**Trước khi gửi lệnh, vui lòng tham khảo giao diện hiển thị giá thực thi thực tế.**

{% hint style="info" %}
Lưu ý: bảng lịch sử lệnh lấy dữ liệu từ Subgraph và có thể hiển thị thông tin bị trễ đôi chút.
{% endhint %}

### Tôi có thể gửi lệnh giới hạn cho các token có phí khi chuyển nhượng không?

**Không.** Các token có phí khi chuyển nhượng không nên được sử dụng với lệnh giới hạn. Hãy tự chịu rủi ro nếu tiến hành.

### Làm thế nào để đặt trượt giá khi sử dụng lệnh giới hạn?

Trượt giá không liên quan đến lệnh giới hạn. Bạn chỉ định số lượng đầu vào (ví dụ: 1000 CAKE) và số lượng đầu ra (ví dụ: 20 BNB), Lệnh giới hạn đảm bảo bạn sẽ nhận không ít hơn số lượng đầu ra đã chỉ định (20 BNB) cho số lượng đầu vào của bạn (1000 CAKE) nếu giá cho cặp đạt mức giá mong muốn. **Lưu ý rằng các token có phí khi chuyển nhượng không nên được sử dụng với lệnh giới hạn** (đọc bên trên)

### Giá thực thi thực tế hiển thị "never executes" (không bao giờ thực thi). Điều này có nghĩa là gì?

Về cơ bản điều này có nghĩa là bạn đang cố gắng hoán đổi một lượng token rất nhỏ do đó không có đủ token để tính phí gas. Nhìn chung, bạn cần tăng lượng token trong trường "input" để loại bỏ lỗi này.&#x20;

### Lệnh giới hạn của tôi có ngày hết hạn không?

Các lệnh đang mở có ngày hết hạn là 90 ngày. Sau khi lệnh hết hạn, nó có thể không bao giờ được thực thi. Vui lòng hủy lệnh khi đã hết hạn.&#x20;

Tính năng ngày hết hạn tùy chỉnh đang được lên kế hoạch cho tương lai gần.

### Tại sao tôi không thể tạo lệnh giới hạn dưới giá thị trường?

Để bán dưới giá thị trường, bạn cần **Lệnh Stop Limit**, không phải lệnh giới hạn. Tính năng Lệnh Stop Limit sẽ sớm ra mắt.

### Tôi đã đặt lệnh nhưng nó không hiển thị trong bảng lệnh hoặc bị kẹt ở trạng thái "pending".

Lịch sử lệnh đến từ subgraph và do đó có thể hiển thị thông tin bị trễ đôi chút. Thông thường, các độ trễ không dài hơn vài phút trong trường hợp xấu nhất. Vui lòng tham khảo chỉ báo subgraph ở góc dưới bên phải của bảng lịch sử lệnh.
