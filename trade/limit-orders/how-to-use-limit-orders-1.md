# Cách Sử Dụng Lệnh Giới Hạn

Lệnh giới hạn kiếm phí trên PancakeSwap hoạt động khác với lệnh giới hạn truyền thống. Khi người dùng đặt lệnh giới hạn, về bản chất họ đang cung cấp **thanh khoản một chiều** vào pool PancakeSwap Infinity.

Khi giá thị trường biến động, các giao dịch hoán đổi trong pool có thể sử dụng thanh khoản của người dùng. Khi điều này xảy ra, các token đã ký gửi được chuyển đổi hoàn toàn thành token đầu ra, và người dùng nhận được:

* Các token đầu ra, và
* Phí giao dịch kiếm được từ các giao dịch hoán đổi thực hiện trên thanh khoản của họ.

***

**Ví dụ: Bán BNB lấy USDT**

* **Giá hiện tại trong pool BNB/USDT:** 600 USDT mỗi BNB
* **Giá mục tiêu / giới hạn của người dùng:** 700 USDT mỗi BNB

Quy trình:

1. Người dùng đặt lệnh giới hạn để bán BNB ở mức 700 USDT.
2. BNB của họ được ký gửi vào tick gần nhất với giá 700 USDT mỗi BNB trong pool.
3. Khi giá thị trường bên ngoài đạt 700 USDT, giá pool sẽ điều chỉnh theo (do cơ hội arbitrage / mức giá tốt hơn).
4. Tại thời điểm đó, BNB của người dùng được hoán đổi sang USDT.
5. Trong quá trình này, người dùng kiếm phí từ mỗi giao dịch hoán đổi tiêu thụ thanh khoản của họ.
6. Khi thanh khoản được tiêu thụ hoàn toàn, USDT đã chuyển đổi (cộng với phí) sẽ tự động được rút và gửi đến ví của người dùng.

***

### Hướng dẫn từng bước

Chọn cặp token (ví dụ: BNB/CAKE) và số lượng bạn muốn bán / mua

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Đặt giá mục tiêu / giới hạn của bạn

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Đặt lệnh giới hạn và nhấn "Confirm". Thanh khoản sẽ được đặt thay mặt bạn tại tick gần nhất với giá giới hạn

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Khi giá pool đạt mục tiêu của bạn, lệnh được thực thi. Các token đầu ra mong muốn cùng phí sẽ tự động được rút và gửi đến ví của bạn.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Trạng Thái Lệnh

Bạn có thể xem trạng thái lệnh bằng cách nhấp vào đây

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Lệnh của bạn có thể ở một trong các trạng thái sau:**

| Trạng thái       | Mô tả                                                                                         |
| ---------------- | --------------------------------------------------------------------------------------------- |
| Đang chờ         | Đang chờ giá đạt mục tiêu của bạn                                                            |
| Đã khớp          | Lệnh đã thực thi và tiền đã được gửi đến ví của bạn                                         |
| Khớp một phần    | Chỉ một phần lệnh của bạn được thực thi. Bạn sẽ giữ cả hai token (ví dụ: một phần BNB, một phần USDT) |
| Đã hủy           | Bạn đã hủy lệnh. Toàn bộ tiền của bạn được hoàn trả                                        |

### FAQ

**Hỏi: Tôi có cần trả phí để đặt lệnh giới hạn không?**

Trả lời: Không. Thay vào đó, bạn kiếm 0.1% phí giao dịch khi lệnh được thực thi.

**Hỏi: Tôi có thể đặt lệnh cho bất kỳ cặp nào không?**

Trả lời: Khi ra mắt, chỉ các cặp đã chọn được hỗ trợ. Nhiều cặp hơn sẽ được thêm sau.

**Hỏi: Kích thước lệnh tối thiểu là bao nhiêu?**

Trả lời: $50. Điều này ngăn chặn các lệnh nhỏ có thể dẫn đến phí gas quá cao.&#x20;

**Hỏi: Điều gì xảy ra nếu chỉ một phần lệnh của tôi được khớp?**

Trả lời: Bạn sẽ giữ cả hai token. Bạn có thể hủy bất cứ lúc nào và rút cả hai token cùng phí đã kiếm.

**Hỏi: Lệnh của tôi đã khớp nhưng tôi chưa nhận được tiền trong ví?**

Trả lời: Trong một số trường hợp rất hiếm, điều này có thể xảy ra nhưng tiền của bạn luôn an toàn. Chỉ cần sử dụng nút "Withdraw" trong giao diện chi tiết lệnh để nhận tiền thủ công.
