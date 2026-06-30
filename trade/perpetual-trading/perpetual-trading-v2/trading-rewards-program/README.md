---
description: ApolloX sẽ ra mắt Chương Trình Thưởng Giao Dịch trên V2
hidden: true
---

# Chương Trình Thưởng Giao Dịch

### Tổng Quan Chương Trình Thưởng

Chi tiết như sau:

Thời gian hoạt động: Ngày tháng thay đổi theo từng chu kỳ và cho các chuỗi khác nhau

Thời Gian Phân Phối Thưởng: Mỗi chu kỳ là 00:00 (UTC) đến 23:59 (UTC) hàng ngày. Phần thưởng được phát vào ngày hôm sau khoảng 03:00 (UTC). Người dùng phải nhận phần thưởng trong vòng 30 ngày sau khi phần thưởng được phát. Nếu không, nền tảng sẽ thu hồi phần thưởng.&#x20;

Số tiền thưởng: Giới hạn ở mức $15.000 USD giá trị APX mỗi ngày

Quy tắc hoạt động: Người dùng giao dịch trên V2 kiếm được từ một pool giải thưởng. Những người stake APX trong DAO để nhận veNFT sẽ được hưởng các hệ số nhân tăng cường tương ứng với giá trị Power được tính từ veNFT.&#x20;

| Giá Trị Power             | Hệ Số Nhân Tăng Cường |
| ------------------------- | --------------------- |
| 50.000 < Power =<100.000  | 1.5                   |
| 100.000 < Power =<300.000 | 2                     |
| Power > 300.000           | 2.5                   |

Công thức tính Thưởng Giao Dịch:&#x20;

Vào cuối mỗi chu kỳ thưởng giao dịch, phí giao dịch hiệu quả và số lượng staking của người dùng trong chu kỳ đó sẽ được tính để xác định trọng số và số lượng phần thưởng APX. Công thức như sau:

r = R\*W / sum(Wi)



Các thông số:

| r       | Phần thưởng APX của người dùng cho chu kỳ này                                                                                                                                                                                                                                                                        |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Được xác định bởi đóng góp phí giao dịch V2 của người dùng vào ngày hôm trước và giá token APX mới nhất                                                                                                                                                                                                            |
| W       | <p>Tổng điểm trọng số cá nhân W=f*w, trong đó;</p><p>f là phí giao dịch hiệu quả do người dùng đóng góp trong chu kỳ này, sẽ được chuyển đổi thành USD.</p><p>w là Hệ Số Nhân Tăng Cường mà người dùng nhận được trong chu kỳ này từ việc stake APX trong DAO. (Tham khảo bảng trên để biết thêm thông tin)</p> |
| sum(Wi) | Tổng điểm của tất cả người dùng. Wi đại diện cho điểm của bất kỳ người dùng cá nhân nào, và sum(Wi) đại diện cho tổng tất cả điểm người dùng                                                                                                                                                                      |

&#x20;

Công thức tính R như sau:

R=Min(Hệ số giá trị USD \* Phí Giao Dịch, Giới hạn giá trị USD)/ Max(Giá Cuối APX, Sàn Giá APX)

* Hệ số giá trị USD: 0.70 epoch này
* Phí Giao Dịch: Giá trị thu nhập phí V2 của ngày hôm trước được chuyển đổi thành USD
* Giới hạn giá trị USD: 15.000 dựa trên cấu hình hệ thống
* Giá Cuối APX: Dựa trên giá token APX mới nhất
* Sàn Giá APX: 0.04 epoch này

Điều Khoản và Điều Kiện

* Sau khi mỗi chu kỳ kết thúc, ApolloX có thể điều chỉnh các quy tắc chương trình theo phản hồi của người dùng và điều kiện thị trường. Phần thưởng sẽ được phát hành không tuyến tính.
* Trong hoạt động, nền tảng sẽ giảm tỷ lệ phần trăm thu nhập phí giao dịch V2 được đưa vào pool ALP từ 50% xuống 20%. 30% còn lại sẽ được sử dụng để mua lại APX.
* Do sự khác biệt về phí giao dịch cho mỗi cặp giao dịch trên V2, phần thưởng người dùng nhận có thể khác nhau dù khối lượng giao dịch hiệu quả của họ giống nhau.
* Phần thưởng sẽ phân phối cho mỗi chu kỳ sẽ được lưu trữ trong địa chỉ hợp đồng sau: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX có quyền giải thích cuối cùng cho hoạt động này.

Cảnh Báo Rủi Ro: Giao dịch hợp đồng tương lai crypto mang rủi ro đáng kể. Tất cả các hoạt động giao dịch được thực hiện theo quyết định và rủi ro của riêng bạn. Thông tin ở đây không nên được coi là tư vấn tài chính hoặc đầu tư từ ApolloX. ApolloX sẽ không chịu trách nhiệm cho bất kỳ tổn thất nào có thể phát sinh từ việc bạn sử dụng ApolloX.

### Nhận Thưởng

Vì chương trình thưởng giao dịch được tổ chức bởi ApolloX, vui lòng thực hiện các bước sau để nhận thưởng của bạn:\
\
Bước 1: Đến [Trang PancakeSwap Perpetuals](https://perp.pancakeswap.finance/en/futures/v2/)

Bước 2: Nhấp vào tab Trading Reward (V2) ở đầu trang

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

Bước 3: Bạn sẽ được chuyển hướng đến trang nhận thưởng của ApolloX để kiểm tra trạng thái thưởng hiện tại. Nhấp "Claim" để nhận thưởng trong thời gian hoạt động.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
