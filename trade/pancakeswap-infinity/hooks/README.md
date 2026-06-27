# Hooks

{% hint style="info" %}
Nếu bạn là nhà phát triển hoặc đang tìm kiếm tài liệu kỹ thuật chi tiết về phát triển hook, vui lòng truy cập [tại đây](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook).
{% endhint %}

Hooks là các tiện ích mở rộng mạnh mẽ cho phép nhà phát triển mở rộng và tùy chỉnh hành vi của các nhóm thanh khoản trong PancakeSwap Infinity. Hãy nghĩ chúng như "plugin" hoặc "widget" bổ sung tính năng mới cho nhóm thanh khoản.

#### 🔍 Hooks Là Gì?

* Hooks là các hợp đồng thông minh bên ngoài được tạo bởi bất kỳ ai — nhà phát triển, giao thức hoặc thành viên cộng đồng — và được gắn vào nhóm thanh khoản để nâng cao hoặc sửa đổi hành vi của chúng.
* Mỗi pool chỉ có thể có một hook được gắn vào, nhưng một hook duy nhất có thể phục vụ nhiều pool.
* Hooks có thể chạy code tùy chỉnh trước hoặc sau các hành động quan trọng như:
  * Khởi tạo pool
  * Hoán đổi
  * Thêm/xóa thanh khoản
  * Đóng góp<br>

**⛓️ Cách Hooks Hoạt Động:**

* Hook được chọn trong quá trình tạo pool và không thể thay đổi sau đó.
* Một hợp đồng hook kích hoạt trên các hành động cụ thể (hoán đổi, thêm thanh khoản, v.v.) và thực thi logic trước hoặc sau các hành động đó như được định nghĩa trong hợp đồng.
* Ví dụ, một hook có thể:
  * Cung cấp chiết khấu phí hoán đổi cho người nắm giữ CAKE
  * Tính phí tùy chỉnh và phân phối phần thưởng
  * Cho phép logic hoán đổi mới như stableswaps hoặc lệnh kiểu TWAMM<br>

#### ⚙️ Callback của Hook

Hooks có thể được kích hoạt trong mười khoảnh khắc cụ thể. Nhà phát triển có thể chọn cái nào họ muốn triển khai:

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

Những điều này cho phép triển khai hành vi có thể tùy chỉnh và mô-đun cao thông qua hooks.

#### 🔧 Hai Loại Hooks

**Loại 1: Không Cần Ủy Quyền**

Những hooks này chạy tự động và không yêu cầu quyền của người dùng. Chúng được kích hoạt bởi các hành động như hoán đổi hoặc thay đổi thanh khoản.



Ví dụ:

* Phí Động: Điều chỉnh phí hoán đổi dựa trên biến động thị trường
* Hoàn Phí: Giảm giá cho người dùng nắm giữ CAKE hoặc giao dịch khối lượng lớn



Ví dụ Luồng (Giảm Phí CAKE):

1. Người dùng khởi tạo hoán đổi.
2. Hook kiểm tra số dư CAKE của họ qua callback hook `beforeSwap`.
3. Nếu người dùng nắm giữ đủ CAKE theo ngưỡng đã định, họ nhận được giảm 50% phí pool.
4. Phần còn lại của giao dịch tiến hành như thường lệ.<br>

{% hint style="success" %}
Những hooks này không cần giao diện người dùng đặc biệt hay tương tác bổ sung. Lợi ích được áp dụng tự động.
{% endhint %}

**Loại 2: Yêu Cầu Ủy Quyền Người Dùng**

Những hooks này yêu cầu người dùng tương tác trực tiếp với chúng, cung cấp ủy quyền và có thể yêu cầu chuyển tiền, thường để tạo hoặc quản lý vị thế.



Ví dụ:

* Lệnh Giới Hạn: Thực hiện hoán đổi chỉ khi đạt mức giá mục tiêu.
* TWAMM: Chia nhỏ các lệnh lớn thành các phần nhỏ hơn để thực hiện tốt hơn.
* Quản Lý Thanh Khoản Chủ Động: Tự động quản lý các vị thế LP để có lợi nhuận tối ưu.



Ví dụ Luồng (Lệnh Giới Hạn Hook):

1. Người dùng tương tác trực tiếp với hợp đồng hook (không phải giao diện hoán đổi thông thường).
2. Họ nhập chi tiết như giá giới hạn, cặp token, số lượng.
3. Hook phát hành token biên nhận đại diện cho lệnh.
4. Sau này, khi giá pool đạt mục tiêu, hook thực hiện lệnh bằng afterSwap.
5. Người dùng có thể trả lại token biên nhận để nhận tài sản đã hoán đổi.

{% hint style="info" %}
Những hooks này thường cần giao diện tùy chỉnh và người dùng phải tin tưởng và phê duyệt hợp đồng hook để giữ tiền của họ.
{% endhint %}

#### 🚀 Trường Hợp Sử Dụng & Đổi Mới

Hooks mở ra vô số khả năng, bao gồm:

* AMM tùy chỉnh (ví dụ: đường cong stablecoin)
* Phần thưởng khai thác thanh khoản
* Chiến lược giao dịch tự động, quản lý thanh khoản
* Lệnh giới hạn trên chuỗi, các loại lệnh khác
* Điều chỉnh định giá và phí động
* Chiến lược LP tăng cường lợi nhuận<br>

Với hooks, nhà phát triển có thể xây dựng trải nghiệm DeFi hoàn toàn mới sử dụng cơ sở hạ tầng hiện có của PancakeSwap Infinity — tăng tốc phát triển và giảm chi phí.
