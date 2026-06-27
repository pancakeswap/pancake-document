# 🎁 Pancake Gifts

### 🎯 Pancake Gifts là gì?

**Pancake Gifts** cho phép bất kỳ ai gửi token — bao gồm cả gas tùy chọn — đến bạn bè, người dùng hoặc cộng đồng chỉ bằng một **liên kết** hoặc **mã QR**. Đây là trải nghiệm đơn giản, an toàn và không tốn gas cho người nhận.

Được xây dựng để giúp việc bắt đầu sử dụng tiền điện tử dễ dàng như gửi một tin nhắn — không cần nạp tiền vào ví, không cần kết nối chuỗi, không cần phí trước.

### 🤝 Lý do chúng tôi xây dựng Pancake Gifts

Việc bắt đầu sử dụng Web3 vẫn còn nhiều rào cản. Người dùng mới thường bỏ cuộc trước khi họ kịp bắt đầu vì:

* **Không có gas trong ví** → Không thể thực hiện bất kỳ hành động onchain nào
* **Không có tiền trên chuỗi đúng** → Cần kết nối chuỗi trước khi sử dụng dApp
* **Phải mua tiền điện tử chỉ để bắt đầu** → Cần đăng ký CEX hoặc nạp tiền pháp định

Pancake Gifts loại bỏ những rào cản này bằng cách:

* ✅ **Bao gồm token gas gốc** trong quà tặng để người nhận có thể tương tác ngay lập tức
* ✅ **Tài trợ phí gas trước** (người gửi trả một khoản phí nhỏ)
* ✅ **Cho phép nhận qua liên kết hoặc QR đơn giản** — không cần quy trình phức tạp



Đây là công cụ dành cho cả:

* Người dùng mới bắt đầu onchain
* Cộng đồng Web3 muốn **thúc đẩy việc áp dụng, thưởng cho người dùng hoặc chạy các chiến dịch** theo cách thân thiện hơn

***

### ⚙️ Tóm tắt Tính năng

| Tính năng                    | Mô tả                                                                     |
| ---------------------------- | ------------------------------------------------------------------------- |
| **Hỗ trợ Chuỗi**             | BNB Chain (ra mắt ban đầu)                                                |
| **Loại Mã Quà**              | Liên kết **hoặc** Mã QR                                                   |
| **Sử dụng một lần**          | Mỗi mã chỉ có thể được nhận một lần                                       |
| **Hỗ trợ Token**             | Tối đa 2 token: 1 BEP-20 (bắt buộc), 1 token gas gốc (tùy chọn)         |
| **Số lượng Tùy chỉnh**       | Đặt giá trị khác nhau cho mỗi token                                       |
| **Phí Gas Nhận Quà**         | Người gửi trả trước gas (\~$0.05 bằng BNB)                               |
| **Lịch sử Quà**              | Người dùng có thể xem tất cả quà đã gửi, trạng thái nhận, thời hạn       |
| **Kiểm tra Bảo mật**         | Các token có phí chuyển nhượng và logic phức tạp đều bị chặn              |

### 🚫 Hạn chế

1. **Một quà cho một mã** — Gửi quà hàng loạt chưa được hỗ trợ.
2. **Quà không thể khôi phục** — Một khi đã hủy hoặc hết hạn, chúng không thể tái sử dụng.
3. **Token không được hỗ trợ bị chặn** — Token có phí chuyển nhượng hoặc logic đặc biệt sẽ hiển thị lỗi khi tạo.
4. **Các lần nhận không thành công sẽ được thử lại** — Hệ thống sẽ thử lại vài lần. Nếu vẫn thất bại, quà sẽ được đánh dấu là **không thể nhận** và phải hủy thủ công để lấy lại tiền.
5. **Quà phải được nhận trên cùng chuỗi** — ví dụ: quà ETH phải được nhận trên Ethereum. Nhận quà xuyên chuỗi chưa được hỗ trợ.

***

### 🕒 Logic Hủy & Hết hạn

Quà tuân theo vòng đời được xác định dựa trên trạng thái và thời gian:

#### Hủy Thủ công

* **Người tạo** có thể hủy bất kỳ quà nào vẫn còn **chưa được nhận** và **trong thời hạn hết hạn**.
* Token (trừ Phí Gas Nhận Quà ban đầu) sẽ được hoàn trả cho người gửi.
* Quà đã hủy **không thể** được kích hoạt lại hoặc tái sử dụng.

#### Tự động Hết hạn

* Quà **tự động hết hạn** sau khoảng thời gian do người dùng xác định (mặc định: 7 ngày).
* Token chưa được nhận sẽ được **tự động hoàn trả** về ví của người gửi.
* Quà hết hạn cũng không thể tái sử dụng.

***

### 🔄 Trạng thái Quà & Ý nghĩa

| Trạng thái        | Mô tả                                                                         |
| ----------------- | ----------------------------------------------------------------------------- |
| **Đang chờ**      | Quà đã được tạo và đang chờ được nhận                                         |
| **Đã nhận**       | Quà đã được người nhận nhận thành công                                        |
| **Đã hủy**        | Quà đã bị người gửi hủy thủ công                                              |
| **Hết hạn**       | Quà đã qua thời gian hết hạn mà không được nhận                               |
| **Không thể nhận**| Số lần thử lại vượt quá giới hạn; quà cần được hủy để lấy lại tiền           |

***

### ⚠️ Xử lý Lỗi & Các Trường hợp Biên

1. **Token Không được Hỗ trợ**
   * Việc tạo quà bị chặn đối với các token có phí chuyển nhượng hoặc logic đặc biệt.
2. **Không khớp Gas**
   * Nếu **chi phí gas thực tế khi nhận ≥** phí người gửi đã trả trước, việc nhận sẽ tự động thất bại để ngăn chặn lạm dụng. Hệ thống sẽ thử lại khi mức phí gas nằm trong phạm vi cho phép.
3. **Các Lần Nhận Thất bại**
   * Sẽ thử lại khi lần nhận đầu tiên không thành công.
   * Nếu vẫn không thành công:
     * Người nhận thấy trạng thái "Không thể nhận"
     * Người gửi phải hủy quà thủ công để lấy lại tiền và người nhận sẽ phải yêu cầu mã quà mới.
