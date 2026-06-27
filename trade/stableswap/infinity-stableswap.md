# Infinity StableSwap

### Tổng Quan

Infinity StableSwap là một loại pool trong [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) được tối ưu hóa để hoán đổi các tài sản nên giao dịch gần cùng mức giá — như stablecoin (ví dụ: USDC/USDT) hoặc các tài sản được gắn chặt (ví dụ: cặp token wrapped, token staking lỏng và token restaking lỏng).

Nó được hỗ trợ bởi một StableSwap hook chạy trên kiến trúc Infinity, lấy cảm hứng từ thiết kế StableSwap NG của Curve. Hiện đang khả dụng trên BNB Chain, với kế hoạch mở rộng sang các chuỗi bổ sung trong tương lai.

***

### Cách Hoạt Động

Infinity StableSwap sử dụng đường cong hằng số ổn định — kết hợp giữa tổng không đổi và tích không đổi:

* Gần điểm neo → đường cong hoạt động gần với tổng không đổi, dẫn đến trượt giá rất thấp cho các giao dịch quanh 1:1.
* Xa điểm neo → đường cong dần chuyển sang tích không đổi, giúp khôi phục cân bằng và bảo vệ pool trong các sự kiện mất cân bằng lớn hoặc mất neo.

Điều này làm cho nó đặc biệt hiệu quả cho các cặp ổn định nơi định giá chặt chẽ và trượt giá thấp là quan trọng nhất.

***

### Tính Năng Chính

Tối ưu hóa cho hoán đổi gần điểm neo: Trượt giá thấp cho các giao dịch giữa các tài sản dự kiến giao dịch ở mức giá gần bằng nhau.

Cung cấp thanh khoản đơn giản: Nhà cung cấp thanh khoản (LP) gửi cả hai token theo tỷ lệ mà không cần chọn hay quản lý phạm vi giá — không giống pool CLAMM.

Token LP ERC-20: Vị thế LP của bạn được đại diện dưới dạng token ERC-20 tiêu chuẩn, giúp dễ dàng sử dụng với các chương trình yield, chiến dịch điểm và các giao thức DeFi khác.

Phí động: Phí có thể điều chỉnh dựa trên điều kiện cân bằng pool, thưởng cho các giao dịch giúp khôi phục pool về trạng thái cân bằng và ngăn cản những giao dịch làm trầm trọng thêm sự mất cân bằng.

Hỗ trợ định tuyến Infinity: Giao dịch được định tuyến tự động qua pool StableSwap khi chúng cung cấp giá tốt nhất — không cần thêm bước nào cho trader.

Thông số Khuếch Đại (A) có thể điều chỉnh: Người vận hành pool có thể tăng hoặc giảm thông số A theo thời gian để thích ứng với điều kiện thị trường thay đổi, với các biện pháp bảo vệ để ngăn chặn thay đổi đột ngột.

***

### Thông Số Pool

Hành vi pool StableSwap được điều chỉnh bởi một tập hợp nhỏ các thông số, thường được đặt tại thời điểm tạo pool.

#### Hệ Số Khuếch Đại (A)

Thông số A kiểm soát mức độ chặt chẽ của pool theo tỷ lệ giá 1:1.

| Giá Trị A | Hiệu Ứng                                                                                     |
| --------- | --------------------------------------------------------------------------------------------- |
| A cao hơn | Đường cong chặt hơn quanh điểm neo; trượt giá thấp hơn gần 1:1; nhạy cảm hơn với mất cân bằng |
| A thấp hơn | Đường cong lỏng hơn; hoạt động giống pool tích không đổi tiêu chuẩn hơn                    |

Quy tắc kinh nghiệm: Sử dụng A cao hơn cho các tài sản có neo mạnh, đáng tin cậy (ví dụ: USDC/USDT). Sử dụng A thấp hơn cho các tài sản có neo lỏng hơn hoặc biến động hơn (ví dụ: một số cặp LST).

Thông số A có thể được tăng dần hoặc giảm dần bởi người vận hành pool trong một khoảng thời gian xác định. Các thay đổi được áp dụng dần dần với các biện pháp bảo vệ để ngăn chặn thao túng hoặc biến động giá đột ngột.

#### Hệ Số Nhân Phí Ngoài Điểm Neo

Một thông số bổ sung điều chỉnh phí hiệu dụng khi pool rời khỏi trạng thái cân bằng. Nó giúp ngăn cản các giao dịch có thể làm mất cân bằng pool thêm và làm cho pool bền vững hơn trong giai đoạn căng thẳng thị trường hoặc sự kiện mất neo.

#### Phí Động

Phí được tính trên mỗi hoán đổi, được trả cho nhà cung cấp thanh khoản. Infinity StableSwap hỗ trợ phí động — nghĩa là phí hiệu dụng trên một giao dịch nhất định có thể thay đổi tùy thuộc vào trạng thái hiện tại của pool (ví dụ: giao dịch có cải thiện hay làm xấu đi sự cân bằng hay không).

***

### Infinity StableSwap vs. StableSwap Cổ Điển

Nếu bạn đã từng sử dụng StableSwap hiện có của PancakeSwap, đây là những gì thay đổi — và những gì vẫn giữ nguyên.

| <p><br></p>                   | StableSwap Cổ Điển                                                  | Infinity StableSwap                                                                              |
| ----------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Đường cong định giá           | Hằng số ổn định (kết hợp tổng không đổi / tích không đổi)          | Cùng đường cong hằng số ổn định, cùng trượt giá thấp gần điểm neo                               |
| Token LP ERC-20               | ✅ Có                                                                 | ✅ Có                                                                                             |
| Tạo pool                      | Nặng về vận hành; yêu cầu thiết lập thủ công bởi nhóm               | Không cần cấp phép — bất kỳ ai cũng có thể tạo pool                                             |
| Phí hoán đổi                  | Cố định theo cặp (ví dụ: 0,01% cho USDC/USDT)                       | Phí động — điều chỉnh dựa trên cách giao dịch ảnh hưởng đến cân bằng pool                      |
| Thông số Khuếch Đại (A)       | Tĩnh — đặt một lần, không thể thay đổi                               | Có thể điều chỉnh — có thể được tăng hoặc giảm dần theo thời gian                               |
| Hệ số nhân phí ngoài điểm neo | ❌ Không hỗ trợ                                                      | ✅ Hỗ trợ — giúp bảo vệ pool trong các sự kiện mất neo                                          |
| Hiệu quả gas                  | Tiêu chuẩn                                                           | Cải thiện — được hưởng lợi từ Singleton và Flash Accounting của Infinity                        |

#### Những gì giữ nguyên

* Đường cong định giá cốt lõi và hành vi trượt giá thấp gần điểm neo không thay đổi.

#### Những gì mới và tốt hơn

* Tạo Pool Không Cần Cấp Phép: Pool có thể được tạo mà không cần thiết lập thủ công của nhóm.
* Phí động bảo vệ LP: Thay vì một mức phí cố định duy nhất, phí có thể điều chỉnh theo từng giao dịch dựa trên việc giao dịch có giúp hay làm hại cân bằng pool — làm cho pool bền vững hơn trong điều kiện biến động.
* Thông số A có thể thích ứng: Hệ số khuếch đại có thể được tinh chỉnh theo thời gian khi điều kiện thị trường thay đổi, thay vì bị khóa tại thời điểm triển khai mãi mãi.

***

### Câu Hỏi Thường Gặp

Những tài sản nào phù hợp với Infinity StableSwap?

Các tài sản dự kiến giao dịch gần cùng mức giá: stablecoin (USDC, USDT, BUSD, v.v.), tương đương wrapped của cùng tài sản (ví dụ: WBTC/cbBTC), và một số cặp token staking lỏng / token restaking lỏng (LST/LRT) nơi biến động neo thấp.

<br>

Infinity StableSwap khác StableSwap cũ của PancakeSwap như thế nào?

Infinity StableSwap được triển khai như một hook trên PancakeSwap Infinity, có nghĩa là nó kế thừa tất cả lợi ích cơ sở hạ tầng của Infinity, bao gồm chi phí gas thấp hơn qua Singleton và Flash Accounting, và hệ thống phí linh hoạt hơn. Nó cũng hỗ trợ các khả năng mới như phí động và khuếch đại có thể điều chỉnh mà StableSwap cũ không cung cấp.

<br>

Tôi có cần quản lý vị thế theo thời gian không?

Không. Không giống CLAMM, bạn không cần đặt hoặc điều chỉnh phạm vi giá. Thanh khoản của bạn luôn hoạt động trên toàn bộ đường cong, vì vậy không có nguy cơ vị thế của bạn "ngoài phạm vi".

<br>

Tôi có thể cung cấp thanh khoản chỉ với một token không?

Có, hỗ trợ gửi một token.

<br>

Phí động hoạt động như thế nào?

Trong Infinity StableSwap, phí hoán đổi có thể thay đổi theo từng giao dịch dựa trên cách giao dịch ảnh hưởng đến cân bằng pool. Các giao dịch giúp đưa pool trở lại trạng thái cân bằng có thể trả phí hiệu dụng thấp hơn, trong khi các giao dịch làm xấu đi sự mất cân bằng có thể trả phí cao hơn. Điều này được thiết kế để bảo vệ LP và duy trì điều kiện pool lành mạnh hơn.



***



## Tạo Pool Infinity StableSwap



Pool Infinity StableSwap không cần cấp phép — bất kỳ ai cũng có thể tạo mà không cần phê duyệt từ nhóm PancakeSwap.

<br>

### Từng Bước

1\. Truy cập trang Farm/Thanh Khoản và nhấp Tạo Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Chọn Pool StableSwap từ các lựa chọn loại pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Chọn cặp token cho pool của bạn (ví dụ: USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Thông Số Pool

| Thông Số                | Tác Dụng                                                                                                            |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Phí Hoán Đổi            | Phí tính trên mỗi hoán đổi, được trả cho LP. Mặc định là 0,01% cho các cặp ổn định chặt chẽ.                       |
| A (Khuếch Đại)          | Kiểm soát mức độ chặt chẽ của đường cong theo điểm neo. Cao hơn = trượt giá thấp hơn gần 1:1, nhưng nhạy cảm hơn với mất cân bằng. |
| Hệ Số Nhân Phí Ngoài Neo | Tăng phí khi pool rời khỏi trạng thái cân bằng, ngăn cản các giao dịch làm xấu đi sự mất cân bằng.               |
| Thời Gian Trung Bình Động | Cửa sổ thời gian được dùng để tính giá trung bình động cho điều chỉnh phí động.                                   |

⚠️ Đặt thông số cẩn thận. Thông số không chính xác — đặc biệt là A rất cao trên tài sản được neo lỏng — có thể làm tăng rủi ro cho LP. Nếu không chắc, sử dụng preset cho loại tài sản của bạn và tránh thay đổi cài đặt Nâng Cao.

<br>

Chọn Preset Thông Số Pool — điều này tự động đặt các thông số được khuyến nghị cho loại tài sản của bạn. Bạn vẫn có thể điều chỉnh thủ công chúng qua nút Nâng Cao.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Preset                                    | A    | Hệ Số Nhân Phí Ngoài Neo | Thời Gian Trung Bình Động (giây) |
| ----------------------------------------- | ---- | ------------------------ | -------------------------------- |
| Stablecoin Có Thể Đổi Fiat                | 1000 | 10                       | 600                              |
| Stablecoin Được Thế Chấp Bằng Crypto      | 100  | 12,5                     | 600                              |
| Token Restaking Lỏng                      | 500  | 10                       | 600                              |

<br>

&#x20; Không chắc chọn cái nào?&#x20;

* Sử dụng Stablecoin Có Thể Đổi Fiat cho các cặp như USDC/USDT
* Sử dụng Stablecoin Được Thế Chấp Bằng Crypto cho stablecoin algo hoặc được thế chấp bằng crypto
* Sử dụng Token Restaking Lỏng cho các cặp LRT như stkBNB/WBNB.

<br>

5\. Nhập số lượng tiền gửi để cung cấp thanh khoản ban đầu. Cả hai số lượng token phải bằng nhau (ví dụ: 1 USDC và 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Nhấp Xem Trước Pool, xem lại cài đặt của bạn, đánh dấu vào ô xác nhận, sau đó nhấp Tạo Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
