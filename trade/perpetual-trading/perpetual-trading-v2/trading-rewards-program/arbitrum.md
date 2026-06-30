# Arbitrum

Vào ngày 31 tháng 8 năm 2023, PancakeSwap Perpetuals sẽ ra mắt Chương Trình Thưởng Giao Dịch V2 trên Arbitrum. Người dùng stake [ALP trong CAKE syrup pool](https://pancakeswap.finance/pools?chain=arb) trên Arbitrum có thể hưởng hệ số nhân tăng cường. Ngoài ra, không có thời gian vesting cho phần thưởng kiếm được trong chương trình này. Người dùng có thể nhận phần thưởng USDC của mình bất cứ lúc nào. Chi tiết như sau:

Thời gian bắt đầu: 31 tháng 8 năm 2023, 08:00 (UTC)

Thời gian hoạt động (Epoch): Mỗi thứ Năm 08:00:00 UTC đến thứ Năm tiếp theo 07:59:59, kéo dài 1 tuần

Thời Gian Phân Phối Thưởng: Mỗi chu kỳ là 00:00 (UTC) đến 23:59 (UTC) hàng ngày. Phần thưởng được phát vào mỗi thứ Năm khoảng 08:00 (UTC). Sau khi cấp bậc của người dùng được cập nhật, phần thưởng sẽ được tính và phân phối. Người dùng phải nhận phần thưởng trong vòng 30 ngày sau khi phần thưởng được phát. Nếu không, nền tảng sẽ thu hồi phần thưởng.&#x20;

Số tiền thưởng: Trong 5 tuần đầu tiên, 25% phí giao dịch (bằng USDC). Pool giải thưởng này sau đó sẽ được phân phối theo cấp bậc.

Quy tắc hoạt động: Người dùng giao dịch trên PancakeSwap Perpetuals V2 trên Arbitrum sẽ đủ điều kiện nhận pool giải thưởng

### Phân Tích Cấp Bậc

Mỗi thứ Năm lúc 08:00:00 UTC, chúng tôi tính toán dữ liệu giao dịch từ thứ Năm tuần trước 08:00:00 UTC đến thứ Năm này lúc 07:59:59 và sau đó cập nhật Cấp Bậc của người dùng theo các quy tắc Cấp Bậc. Các quy tắc Cấp Bậc như sau (cấu hình được hỗ trợ):

<table><thead><tr><th width="161">Cấp Bậc</th><th width="249.33333333333331">Mô Tả</th><th>Trọng Số</th></tr></thead><tbody><tr><td>Diamond</td><td>Khối lượng giao dịch epoch >=1M USD</td><td>5</td></tr><tr><td>Gold</td><td>Khối lượng giao dịch epoch >=500K USD</td><td>3</td></tr><tr><td>Silver</td><td>Khối lượng giao dịch epoch >=250K USD</td><td>1</td></tr></tbody></table>

**Lưu ý: Tiêu chí cấp bậc và trọng số có thể thay đổi dựa trên thanh khoản pool và hoạt động giao dịch tổng thể trên nền tảng**

Phần thưởng sẽ được phân phối đều cho tất cả người dùng đủ điều kiện cho một cấp bậc nhất định

### Công Thức Tính Thưởng Giao Dịch:&#x20;

Vào cuối mỗi chu kỳ thưởng giao dịch, khối lượng giao dịch hiệu quả của người dùng trong chu kỳ đó sẽ được tính để xác định trọng số và số lượng phần thưởng USDC.

Công thức tính số lượng phần thưởng cụ thể là: r = min{R \* W/Sum(Wi), R \* 20%\}, các thông số như sau:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Số lượng phần thưởng USDC sẽ được khai thác bởi người dùng cho epoch hiện tại</td></tr><tr><td>R</td><td>Phần thưởng của epoch hiện tại R=(Giá trị USDC của phí ETH + Giá trị USDC của phí DAI + Giá trị USDC của phí BTC + Phí USDC)*0.25, trong đó cần trừ 1% phí Swap khi quyết toán, ví dụ: khi phí ETH hàng tuần là 1 và Giá ETH là 2.000, giá trị USDC của phí ETH = 1 * 2000 * 0.99</td></tr><tr><td>W</td><td>Trọng số tương ứng với cấp bậc của người dùng</td></tr><tr><td>Sum(Wi)</td><td>Tổng điểm trọng số của tất cả người dùng. Wi đại diện cho trọng số của bất kỳ người dùng nào, và sum(Wi) đại diện cho tổng điểm trọng số của tất cả người dùng.</td></tr></tbody></table>

* Doanh thu tối đa mỗi người dùng được giới hạn ở mức 20% doanh thu dành riêng cho chương trình

Điều Khoản và Điều Kiện

* Do sự khác biệt về phí giao dịch cho mỗi cặp giao dịch trên V2, phần thưởng người dùng nhận có thể khác nhau dù khối lượng giao dịch hiệu quả của họ giống nhau.
* Phần thưởng sẽ phân phối cho mỗi chu kỳ sẽ được lưu trữ trong địa chỉ hợp đồng sau:&#x20;
* PancakeSwap/ApolloX có quyền giải thích cuối cùng cho hoạt động này.



Cảnh Báo Rủi Ro: Giao dịch hợp đồng tương lai crypto mang rủi ro đáng kể. Tất cả các hoạt động giao dịch được thực hiện theo quyết định và rủi ro của riêng bạn. Thông tin ở đây không nên được coi là tư vấn tài chính hoặc đầu tư từ PancakeSwap/ApolloX. PancakeSwap/ApolloX sẽ không chịu trách nhiệm cho bất kỳ tổn thất nào có thể phát sinh từ việc bạn sử dụng PancakeSwap/ApolloX.

<br>
