# Infinity CLAMM & LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

CLAMM cho phép nhà cung cấp thanh khoản phân bổ vốn trong **các phạm vi giá cụ thể**. Điều này dẫn đến:

* **Hiệu quả vốn cao hơn**: Nhiều thanh khoản hơn ở các mức giá giao dịch đang hoạt động.
* **Thanh khoản sâu hơn**: Thực hiện tốt hơn cho trader.
* **Quản lý LP chủ động**: LP cần điều chỉnh vị thế khi giá biến động.
* **Tổn thất tạm thời cao hơn** cho các vị thế ngoài phạm vi.

{% hint style="info" %}
CLAMM hoạt động trên công thức tích không đổi (X \* Y = K). Mỗi vị thế thanh khoản là không thể thay thế và được đại diện dưới dạng NFT.
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM hay "Bin Pool")

LBAMM triển khai **các bin giá rời rạc**, mỗi bin giữ thanh khoản ở một mức giá cụ thể. LBAMM tuân theo **công thức tổng không đổi (X + Y = K).**



**Đặc điểm chính:**

* Giao dịch **0 tác động giá** trong một bin.
* **Thanh khoản có thể thay thế** (thanh khoản trong mỗi bin là token ERC-20).
* **Chi phí gas thấp hơn** để điều chỉnh vị thế LP.
* **Hỗ trợ các hình dạng thanh khoản khác nhau** (ví dụ: nghiêng, đồng đều).
* Phù hợp hơn cho **cặp biến động thấp** do đường cong định giá phẳng mỗi bin.

> 🥞 **PancakeSwap là giao thức đầu tiên cung cấp pool LBAMM với hooks.**

{% hint style="success" %}
Cả pool CLAMM và LBAMM đều hỗ trợ **hooks**, cho phép nhà phát triển tùy chỉnh hành vi pool. Các loại pool có thể mở rộng qua các Pool Manager mới, có thể được thêm mà không cần triển khai lại giao thức.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Tính Năng</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Đường Cong Định Giá</strong></td><td>Tích Không Đổi (X * Y = K)</td><td>Tổng Không Đổi (X + Y = K)</td></tr><tr><td><strong>Token Thanh Khoản</strong></td><td>Không thể thay thế (NFT)</td><td>Có thể thay thế (ERC-20 mỗi bin)</td></tr><tr><td><strong>Phù Hợp Nhất</strong></td><td>Cặp biến động cao/thấp</td><td>Cặp biến động thấp</td></tr><tr><td><strong>Ưu Điểm</strong></td><td><ol><li>Hiệu quả vốn</li><li>Tiết kiệm gas ở phạm vi rộng/đầy đủ</li><li>Được áp dụng rộng rãi</li></ol></td><td><ol><li>0 tác động giá trong bin</li><li>Quản lý LP rẻ hơn</li><li>Hình dạng thanh khoản linh hoạt</li></ol></td></tr><tr><td><strong>Hỗ Trợ Hook</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Phí

PancakeSwap Infinity hỗ trợ hệ thống phí linh hoạt và có thể mở rộng thông qua cài đặt phí Tĩnh và Động. Thiết lập này cung cấp cho cả người tạo pool và LP các công cụ mạnh mẽ để tối ưu hóa cho các chiến lược giao dịch và hồ sơ rủi ro khác nhau.

#### 🔁 Phí Động

* Phí Động được xác định theo thời gian thực thông qua các hợp đồng hook.
* Các phí này có thể biến động dựa trên các yếu tố bên ngoài như biến động, khối lượng giao dịch, trạng thái người dùng (ví dụ: nắm giữ CAKE), hoặc bất kỳ logic tùy chỉnh nào được mã hóa trong hook.
* Các pool có phí động phải bật cài đặt này tại thời điểm tạo pool và gắn hook có khả năng sửa đổi phí qua `beforeSwap`.
* Sau khi pool được khởi tạo, loại phí (động hoặc tĩnh) là bất biến.

Phí động cung cấp tính linh hoạt tối đa và tối ưu hóa cấu trúc phí cho cả LP và người hoán đổi dựa trên điều kiện thị trường.

#### 📌 Phí Tĩnh

* Các pool Phí Tĩnh có mức phí cố định được đặt trong quá trình tạo pool.
* Các phí này không thể thay đổi sau khi pool được khởi tạo.
* Phù hợp cho các trường hợp sử dụng đơn giản hơn hoặc khi cần tính dự đoán của cấu trúc phí.<br>

**🔒 Giới Hạn Phí Tối Đa:**

* Pool CLAMM: Lên đến 100% (chủ yếu cho các trường hợp sử dụng chuyên biệt hoặc thử nghiệm)
* Pool LBAMM: Giới hạn ở 10%<br>

**🏛 Phí Giao Thức (cho pool phí tĩnh):**

* PancakeSwap áp dụng phí giao thức trên các pool Infinity
* 33% phí LP, giới hạn ở 0,4%

| **Phí LP**        | **Phí Giao Thức** |
| ----------------- | ----------------- |
| 1%                | 0,33%             |
| 2%                | 0,4% (giới hạn)   |
| Pool Phí Động     | 0%                |

#### 🛠️ Lưu Ý Thiết Lập Cho Người Tạo Pool

* Khi khởi tạo pool qua PoolManager, người tạo phải chọn:
  * Pool sử dụng phí tĩnh hay động
  * Có gắn hợp đồng hook không (bắt buộc cho phí động)

Các cài đặt này là vĩnh viễn và xác định cách pool hoạt động trong suốt vòng đời của nó.
