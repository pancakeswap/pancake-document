# Phí Động Degen Mode

PancakeSwap Perpetuals Degen Mode sử dụng mô hình phí động. Phí này được thiết kế để tính phí theo PnL và bảo vệ người dùng khỏi thua lỗ.\
**Cơ chế hoạt động?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

trong đó:

* Pnl là lợi nhuận hoặc lỗ trên vị thế
* shareRate là tỷ lệ chia sẻ, là tỷ lệ phần trăm của giá trị danh nghĩa được thanh toán dưới dạng phí (mặc định là 15%)
* Notional là số tiền được sử dụng để mở vị thế
* closeMinRate là tỷ lệ phí đóng vị thế tối thiểu, là mức thấp nhất bạn có thể trả để đóng vị thế (mặc định là 0.03%)

\
**Ví dụ:**

Nếu bạn có vị thế với lợi nhuận $100, tỷ lệ chia sẻ 15%, và giá trị danh nghĩa $600, thì tỷ lệ phí đóng vị thế sẽ là:

Tỷ lệ phí đóng = Max(100 \* 15% / 600, 0.03%) = 0.03%

Trong trường hợp này, tỷ lệ phí đóng vị thế sẽ là 0.03%, tỷ lệ phí đóng vị thế tối thiểu.<br>

Lưu ý:

Phí thực thi chỉ được tính khi mở vị thế. Phí được đặt ở mức 0.3 USD (BNB Chain)/ 0.2 USD (Arbitrum)/ 0.01 USD (opBNB)/ 0.3 USD (Base), tương tự như mức phí được tính khi giao dịch các cặp hợp đồng vĩnh viễn thông thường. Không có phí mở vị thế.

Trong trường hợp thanh lý, tỷ lệ mất mát thanh lý 90% bao gồm phí đóng vị thế.
