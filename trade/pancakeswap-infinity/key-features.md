# Tính Năng Chính

### 1️⃣ Singleton

Trong PancakeSwap v3, mỗi nhóm thanh khoản có hợp đồng riêng, điều này làm cho việc tạo pool và hoán đổi qua nhiều pool trở nên tốn kém hơn.

Infinity giải quyết điều này bằng cách triển khai mô hình Singleton. Giờ đây, tất cả các pool đều nằm trong một hợp đồng duy nhất gọi là PoolManager. Thay đổi này cắt giảm chi phí gas tạo pool lên đến 99% và làm cho các hoán đổi multi-hop (hoán đổi qua nhiều pool) rẻ hơn nhiều bằng cách tránh chuyển token không cần thiết.

#### ⚙️ **Cách Hoạt Động:**

* Dữ liệu của mỗi pool được lưu trữ trong một hợp đồng chia sẻ sử dụng ID pool duy nhất.
* Tạo pool mới giờ chỉ là cập nhật trạng thái, không phải triển khai hợp đồng đầy đủ.
* Hoán đổi qua các pool nhanh hơn và sử dụng ít gas hơn.<br>

Cách tiếp cận Singleton này, cùng với các tối ưu hóa khác như Flash Accounting và ERC-6909, giúp PancakeSwap Infinity trở thành một trong những nền tảng DEX tiết kiệm gas nhất hiện nay.

***

### ⚡️ Flash Accounting

Flash Accounting là tối ưu hóa mạnh mẽ trong PancakeSwap Infinity giúp giảm phí gas trong các giao dịch phức tạp như hoán đổi multi-hop và thay đổi thanh khoản.

Trong các phiên bản cũ (như v3), token được di chuyển vào và ra khỏi mỗi pool trong mỗi bước của giao dịch. Điều này dẫn đến chi phí gas cao, đặc biệt là cho các hoán đổi multi-hop.

Với Flash Accounting, điều đó không còn cần thiết nữa. Thay vì di chuyển token sau mỗi bước, PancakeSwap Infinity theo dõi tất cả các chuyển động token bên trong và chỉ thực hiện một lần chuyển cuối cùng vào cuối toàn bộ giao dịch. Điều này tiết kiệm rất nhiều gas.

#### ⚙️ **Cách Hoạt Động:**

* Khi bạn tương tác với Infinity (ví dụ: hoán đổi hoặc thêm thanh khoản), hệ thống tính toán số dư ròng của token bạn nợ hoặc nhận.
* Các số dư token ròng này được lưu trữ tạm thời bằng Transient Storage, một tính năng mới được giới thiệu với nâng cấp Cancun của Ethereum (EIP-1153).
* Transient Storage rẻ hơn lưu trữ truyền thống vì nó chỉ tồn tại trong thời gian giao dịch — không cần ghi hay đọc vĩnh viễn.

***

### 🪙 Hỗ Trợ Token Bản Địa

Với sự ra đời của kiến trúc Singleton và Flash Accounting, PancakeSwap Infinity hiện hỗ trợ các gas token bản địa (ví dụ: BNB, ETH) trực tiếp trong các nhóm thanh khoản — không cần gói và bỏ gói nữa.

#### ✅ Điểm Nổi Bật

* **Pool Token Bản Địa Trực Tiếp:** Bạn giờ có thể tạo pool như ETH/USDC, BNB/CAKE mà không cần WETH hay WBNB.
* **Tiết Kiệm Gas:** Chuyển token bản địa rẻ hơn \~50% so với chuyển token ERC-20, dẫn đến chi phí gas thấp hơn cho hoán đổi và các hành động thanh khoản.<br>

**Đã Bị Xóa Trước Đây, Nay Được Kích Hoạt Lại:** Hỗ trợ token bản địa không có trong các phiên bản trước do độ phức tạp triển khai và phân tán thanh khoản.

***

### 📈 Đường Cong Định Giá Tùy Chỉnh

PancakeSwap Infinity trao cho nhà phát triển quyền tạo các mô hình định giá tùy chỉnh cho pool — vượt ra ngoài mô hình truyền thống được sử dụng trong hầu hết AMM.

{% hint style="success" %}
#### Nhà phát triển có thể xây dựng các hành vi hoán đổi và mô hình thanh khoản hoàn toàn mới phù hợp với các loại tài sản hoặc chiến lược giao dịch cụ thể.
{% endhint %}

#### 🔧 Đường Cong Định Giá Tùy Chỉnh Là Gì?

Đường cong định giá tùy chỉnh cho phép nhà phát triển:

* Bỏ qua logic pool manager bản địa, tạo các pool với hành vi hoán đổi được định nghĩa tùy chỉnh.
* Thay đổi cách tính toán số lượng token cho hoán đổi hoặc sửa đổi thanh khoản.
* Kết hợp cơ chế phí tùy chỉnh, chẳng hạn như:
  * Phí rút thanh khoản
  * Hoàn tiền hoặc phạt dựa trên chiến lược

Tất cả điều này được thực hiện thông qua callback hook trước/sau hoán đổi, có thể chặn và sửa đổi các tham số hoán đổi động.

#### 🛠 Ví Dụ Trường Hợp Sử Dụng

* **Đường Cong StableSwap:** Thiết kế các đường cong phẳng hơn quanh tỷ lệ giá 1:1, giảm tác động giá giữa các tài sản như USDC và USDT.
* **RWA:** Tạo hành vi tùy chỉnh cho các loại tài sản khác nhau với nguồn cung động.
* **Phí Cấp Hook:** Tính các phí độc đáo khác với phí cấp pool, chẳng hạn như phí nhà phát triển.
* **Mô Hình Rủi Ro Tùy Chỉnh:** Điều chỉnh định giá để phản ánh biến động, dữ liệu oracle hoặc các số liệu bên ngoài.

{% hint style="info" %}
Trong các phiên bản AMM trước (ví dụ: PancakeSwap v2/v3), logic định giá được cố định và cứng nhắc. Kiến trúc của PancakeSwap Infinity mở khóa khả năng xây dựng các pool hiệu quả vốn và được tùy chỉnh hơn.
{% endhint %}

#### 🔍 Linh Hoạt Cho Nhà Phát Triển

* Nhà phát triển có thể triển khai các hợp đồng hook tùy chỉnh để ghi đè logic định giá.
* Các callback hook như beforeSwap và afterSwap cho phép kiểm soát hoàn toàn cách tính toán và áp dụng các delta token.

***

### 🧮 ERC-6909: Kế Toán Đa Token Hiệu Quả

PancakeSwap Infinity áp dụng[ ERC-6909](https://eips.ethereum.org/EIPS/eip-6909), một tiêu chuẩn token nhẹ và tiết kiệm gas được thiết kế cho kế toán nội bộ của nhiều token trong một hợp đồng duy nhất. Nó thay thế nhiều hoạt động ERC-20 truyền thống bằng các nguyên thủy mint và burn — dẫn đến tiết kiệm gas đáng kể và luồng giao dịch đơn giản hơn.

#### ⚙️ Cách Hoạt Động

Thay vì di chuyển token vào và ra khỏi giao thức với mỗi tương tác, token ERC-6909 đại diện cho số dư nội bộ:

* Mint: Khi người dùng gửi token hoặc thực hiện giao dịch, họ có thể chọn nhận token ERC-6909 làm yêu cầu.
* Burn: Sau đó, thay vì chuyển lại token ERC-20, người dùng có thể đơn giản đốt các token ERC-6909 này để thanh toán số dư hoặc tài trợ cho các hoạt động mới.

Mô hình này giảm đáng kể nhu cầu chuyển token bên ngoài, thường gánh chịu chi phí gas cao hơn và tương tác với logic bên thứ ba (ví dụ: kiểm tra blacklist của USDC).

#### 🪙 Lợi Ích Của ERC-6909

<table><thead><tr><th width="262.9921875">Tính Năng</th><th width="497.7421875">Lợi Ích</th></tr></thead><tbody><tr><td>✅ Yêu Cầu Số Dư Nội Bộ</td><td>Không cần chuyển token nhiều lần giữa người dùng và hợp đồng</td></tr><tr><td>✅ Mint/Burn Tiết Kiệm Gas</td><td>Chi phí cố định bất kể token, không cần gọi hợp đồng bên ngoài</td></tr><tr><td>✅ Đơn Giản Hơn ERC-1155</td><td>Kích thước code nhỏ hơn, không có callback, không có yêu cầu chuyển theo lô</td></tr><tr><td>✅ Hỗ Trợ Đa Token</td><td>Một hợp đồng có thể theo dõi nhiều loại token với số dư độc lập</td></tr><tr><td>✅ Liền Mạch Với PoolManager</td><td>Loại bỏ phê duyệt và chuyển ERC-20 dư thừa</td></tr></tbody></table>

#### 🚀 Trường Hợp Sử Dụng

* **Trader tần số cao:** Tránh chuyển tốn gas và tương tác trực tiếp sử dụng số dư nội bộ.
* **Nhà quản lý thanh khoản:** Mở và đóng vị thế hiệu quả hơn mà không cần chuyển token quá mức.

#### 💡 Lưu Ý Chính

* Người dùng tự nguyện tham gia vào luồng ERC-6909 khi họ không cần thanh toán chuyển token ngay lập tức.
* Số dư nội bộ có thể được hợp nhất và thanh toán ròng sau, mang lại cho người dùng cao cấp quyền kiểm soát và linh hoạt lớn hơn.

***

### 💸 Phương Thức Donate

Phương thức `donate()` cho phép người dùng trực tiếp khuyến khích các nhà cung cấp thanh khoản trong phạm vi trong một pool bằng cách đóng góp token. Phương thức này dựa vào hệ thống kế toán phí của pool để thực hiện các khoản thanh toán, đảm bảo chỉ token pool được hỗ trợ.

#### 🔹 Tính Năng Chính:

* **Thanh Toán Trực Tiếp Cho LP:** Đóng góp được thực hiện trực tiếp cho các nhà cung cấp thanh khoản, thưởng cho những người duy trì thanh khoản trong phạm vi hoạt động của pool.
* **Chỉ Hỗ Trợ Token Pool:** Phương thức `donate()` chỉ hỗ trợ đóng góp bằng token của pool, vì nó tận dụng hệ thống kế toán phí để đảm bảo phân phối đúng cách.
* **Mở Cho Tất Cả Người Dùng:** Bất kỳ người dùng nào cũng có thể gọi phương thức `donate()`, cho phép bất kỳ ai khuyến khích việc cung cấp thanh khoản đang hoạt động.



Mặc dù phương thức `donate()` là công cụ mạnh mẽ để khuyến khích LP, người đóng góp cần biết rằng các khoản đóng góp của họ có thể bị chạy trước bởi người dùng khác. Điều này có thể xảy ra khi người dùng nhanh chóng thêm thanh khoản vào pool ngay trước khi đóng góp được thực hiện, nhận được một phần tiền đóng góp.

Để ngăn chặn việc chạy trước, người đóng góp có thể cần xem xét các chiến lược bổ sung khi thiết kế cơ chế đóng góp, chẳng hạn như:

* Đảm bảo rằng các khoản đóng góp xảy ra theo cách giảm thiểu khả năng bị chạy trước cơ hội.
* Thêm độ trễ thời gian hoặc điều kiện cụ thể (sử dụng callback hook before/after donate) đảm bảo các khoản đóng góp không bị khai thác theo cách này.
