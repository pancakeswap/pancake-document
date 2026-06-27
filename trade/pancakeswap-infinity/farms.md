# Farms

PancakeSwap Infinity farming là cách đơn giản, tiết kiệm gas để người dùng kiếm phần thưởng thanh khoản mà không cần Staking LP token. Sau khi thêm thanh khoản vào pool đủ điều kiện, phần thưởng sẽ tự động bắt đầu tích lũy.

#### ⚙️ Cách Hoạt Động

Đây là tóm tắt nhanh về cách hệ thống theo dõi và phân phối phần thưởng:<br>

**✅ Không Cần Staking**

* Chỉ cần giữ vị thế LP trong ví của bạn.
* Không cần khóa tài sản hoặc tương tác với các hợp đồng thông minh bổ sung.
* Bạn bắt đầu kiếm phần thưởng tự động khi thêm thanh khoản.

#### 📈 Phân Phối Phần Thưởng

* Chỉ các vị thế trong phạm vi (những vị thế đang cung cấp thanh khoản đang hoạt động) mới nhận phần thưởng.
* Phần thưởng tỷ lệ thuận với phí kiếm được bởi vị thế của bạn trong mỗi kỳ, gọi là epoch.

#### ⏳ Epoch Là Gì?

* Một epoch là cửa sổ thời gian cố định — hiện được đặt là 8 giờ.
* Phần thưởng được tính toán và phân phối sau mỗi epoch.
* Các epoch hiện được lên lịch vào 00:00, 08:00 và 16:00 UTC.

***

#### 🔄 Quy Trình Farming & Nhận Thưởng

1. **Theo Dõi Vị Thế:** Hệ thống backend giám sát các vị thế LP của bạn trên tất cả các farm.
2. **Tính Toán Phần Thưởng:** Vào cuối mỗi epoch,
   1. Hệ thống tính toán phần thưởng của bạn dựa trên thanh khoản và phí tạo ra.
   2. Nó xử lý phần thưởng thành Merkle tree và gửi Merkle root lên hợp đồng thông minh.
3. **Thời Gian Tranh Chấp:**
   1. Sau khi Merkle root được công bố, thời gian tranh chấp 1 giờ bắt đầu.
   2. Trong thời gian tranh chấp:
      1. Phần thưởng mới được tính toán không thể được nhận.
      2. Phần thưởng từ các epoch trước vẫn có thể nhận.
      3. Các công cụ xác minh tự động và do cộng đồng vận hành kiểm tra độ chính xác của dữ liệu đã công bố. Nếu phát hiện sai lệch, có thể xảy ra tranh chấp để ngăn chặn phân phối không chính xác.
4. **Nhận Phần Thưởng:**
   1. Sau khi thời gian tranh chấp kết thúc, bạn có thể nhận phần thưởng cho epoch mới nhất.
   2. Tất cả phần thưởng chưa nhận trên tất cả các farm có thể được nhận trong một giao dịch duy nhất, tiết kiệm gas.
5. **Phần Thưởng Chưa Nhận Được Chuyển Tiếp:**
   1. Bất kỳ phần thưởng chưa nhận nào sẽ được chuyển sang các epoch tiếp theo. Mỗi lần cập nhật tích hợp phần thưởng trước đó, đảm bảo không có thu nhập nào bị mất hay hết hạn.

{% hint style="info" %}
Phạm vi thanh khoản hẹp hơn thường dẫn đến thu nhập cao hơn nhưng làm tăng khả năng vị thế ra ngoài phạm vi và không đủ điều kiện nhận phần thưởng.
{% endhint %}

#### 🌱 Tóm Tắt

✅ Không cần staking\
✅ Nhận thưởng tiết kiệm gas\
✅ Cập nhật phần thưởng thường xuyên\
✅ Quy trình tranh chấp công bằng và minh bạch\
✅ Phần thưởng tích lũy cho đến khi bạn sẵn sàng nhận
