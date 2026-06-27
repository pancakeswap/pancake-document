# Pancake Gifts FAQ

FAQ này đề cập đến cách Pancake Gifts hoạt động ở phía sau, những gì cần mong đợi trong các tình huống khác nhau, và lý do tại sao một số quyết định thiết kế được đưa ra.

***

## 1. 🔐 Hành vi Mã Quà & Quyền truy cập

### **1.1 Tại sao mã quà không được lưu trữ?**

Chúng tôi **có chủ ý không lưu trữ** mã quà trong:

* Bộ nhớ cục bộ của giao diện người dùng
* Cơ sở dữ liệu backend

Điều này bảo vệ:

* Quyền riêng tư của người dùng
* Bảo mật trước nguy cơ thiết bị bị xâm phạm
* Nhận quà ngoài ý muốn hoặc độc hại

### **1.2 Tôi có thể tạo lại hoặc truy xuất mã quà sau đó không?**

Không. Mã quà:

* Chỉ được hiển thị **một lần** khi tạo
* Được nhúng trong **liên kết** hoặc **mã QR** được tạo ra
* Sẽ **không được hiển thị lại** trong giao diện hoặc lịch sử

{% hint style="warning" %}
Nếu mã bị mất và bạn chưa lưu liên kết hoặc mã QR, quà không thể được nhận thủ công. Thay vào đó, để lấy lại số tiền trong quà, bạn có thể hủy thủ công.
{% endhint %}

### **1.3 Mã quà có còn được nhúng trong liên kết chia sẻ hoặc mã QR không?**

Có:

* Liên kết chia sẻ bao gồm mã quà (ví dụ: `pancakeswap.finance/gift#code=xxxx`)
* Mã QR cũng nhúng mã quà, nhưng **không thể tạo lại sau đó.**&#x20;

{% hint style="success" %}
**Mẹo Hay:** Tải xuống hình ảnh ngay khi được tạo
{% endhint %}

* Nhận quà thủ công yêu cầu mã quà thực tế — không có phương án dự phòng nếu mất liên kết/QR

## 2. 🎁 Trạng thái Quà & Hết hạn

### **2.1 Tôi có thể xem quà đã được nhận, hủy hay hết hạn không?**

Có. Phần **Lịch sử Quà** hiển thị:

* Trạng thái: Đang chờ / Đã nhận / Đã hủy / Hết hạn / Không thể nhận
* Chi tiết quà (token, số lượng, loại, chuỗi, dấu thời gian)

### **2.2 Điều gì xảy ra khi một quà hết hạn?**

Nếu quà không được nhận trong **thời hạn 7 ngày** mặc định:

* **Toàn bộ số tiền quà được hoàn trả** về ví của người tạo
* **Phí gas nhận cố định (\~$0.05) không được hoàn trả**

## 3. 🧠 Logic Nhận & Hạn chế

### **3.1 Người dùng có thể nhận quà trên chuỗi khác với chuỗi đã tạo không?**

Không. Quà **bị ràng buộc với chuỗi**:

* Quà được tạo trên **BSC** phải được nhận trên **BSC**
* Tặng quà xuyên chuỗi hiện không được hỗ trợ

## 4. ⛽ Phí Gas & Thiết kế

### **4.1 Số tiền gas cố định cho việc tạo quà được xác định như thế nào?**

Chúng tôi đặt giá gas cố định dựa trên điều kiện chuỗi BNB hiện tại (\~5 lần số lượng Gas được đề xuất hiện tại).

Khoản dự phòng này:

* Bảo vệ trước sự tăng đột ngột của gas
* Đảm bảo quà vẫn có thể nhận được trong điều kiện biến động bình thường

\
Ví dụ

* **Đề xuất hiện tại: 0.1 Gwei** (xem: [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Do đó, Phí gas nhận cố định = 0.1 Gwei x 5 = 0.5 Gwei**


