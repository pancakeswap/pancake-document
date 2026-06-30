# Bảng Thuật Ngữ Perpetuals V2

**Tại đây bạn sẽ tìm thấy định nghĩa của tất cả các thuật ngữ liên quan đến giao dịch hợp đồng tương lai**

### **Giao Dịch Hợp Đồng Vĩnh Viễn**

&#x20;Hợp đồng vĩnh viễn (perpetuals), hoán đổi vĩnh viễn (perpetual swaps), hay perps là một loại hợp đồng tương lai đặc biệt không có ngày hết hạn.

### **Đòn Bẩy**

Đòn bẩy là một cơ chế giao dịch. Các nhà giao dịch có thể sử dụng nó để tăng mức độ tiếp xúc với thị trường bằng cách cho phép họ thanh toán ít hơn toàn bộ số tiền đầu tư. Nói đơn giản, bạn vay tiền để tận dụng đòn bẩy cho khoản đầu tư của mình.

### Lệnh

**Long (Vị thế dài):** Mở lệnh Long. Trong lệnh này, bạn mua một tài sản và chờ bán khi giá tăng. "Mua" và "long" được sử dụng thay thế cho nhau.

**Short (Vị thế ngắn):** Mở lệnh Short. Trong lệnh này, bạn vay một tài sản, bán nó và hy vọng mua lại khi giá giảm. "Bán" và "short" được sử dụng thay thế cho nhau.

**Lệnh Giới Hạn (Limit Order):** Lệnh giới hạn là mua hoặc bán ở một mức giá cụ thể hoặc tốt hơn. Lệnh giới hạn không được đảm bảo thực thi.

**Lệnh Thị Trường (Market Order):** Lệnh thị trường là lệnh mua hoặc bán ở mức giá hiện tại tốt nhất.

#### Quản Lý Vị Thế

Người dùng có thể kiểm tra chi tiết các vị thế đang mở của mình, chẳng hạn như giá mở, bằng cách nhấp vào "Position" nằm ở cuối trang giao dịch. Họ có thể xem các chi tiết như giá mở, số lượng vị thế, giá mới nhất và giá thanh lý bắt buộc.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Perp5.png" alt=""><figcaption></figcaption></figure>

**Chế Độ Vị Thế**

PancakeSwap sẽ sử dụng chế độ đòn bẩy cô lập cho mỗi cặp giao dịch v2. Các cặp hoạt động độc lập:&#x20;

* Mỗi cặp giao dịch là một vị thế cô lập, người dùng có thể mở nhiều vị thế cô lập
* Mỗi vị thế (cặp giao dịch) hoạt động độc lập. Nếu người dùng cần bổ sung ký quỹ, họ sẽ cần thực hiện thủ công ngay cả khi có tài sản có sẵn trong các vị thế riêng biệt khác (ApolloX sẽ hỗ trợ bổ sung tự động trong tương lai)
* Mỗi vị thế giao dịch cô lập sẽ có tỷ lệ rủi ro và giá thanh lý riêng và sẽ được quyết toán riêng.
* Rủi ro thanh lý được cô lập cho mỗi cặp giao dịch. Nếu một vị thế bị thanh lý, nó không ảnh hưởng đến các vị thế khác.

**Đóng Vị Thế**

Người dùng có thể đóng vị thế của mình bằng cách nhấp vào "Close Position".

#### Phí và Trượt Giá

Vui lòng truy cập [trang của Aster](https://docs.asterdex.com/product/asterex-simple/fees-and-slippage) để biết thêm thông tin về Phí.
