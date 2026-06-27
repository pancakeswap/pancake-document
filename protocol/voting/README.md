# 📔 Quản trị

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Là một phần của [nâng cấp Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3), trang này đã được cập nhật vào ngày 15 tháng 5 năm 2025
{% endhint %}

Bỏ phiếu trao tiếng nói cho cộng đồng PancakeSwap, cho phép cộng đồng có ý kiến trong việc phát triển PancakeSwap trong tương lai.

Hãy xem [cổng bỏ phiếu gốc của PancakeSwap](https://pancakeswap.finance/voting) và trang [Diễn đàn](https://forum.pancakeswap.finance/) của chúng tôi.

## Cơ chế bỏ phiếu

:notebook\_with\_decorative\_cover:Tóm tắt - Những thay đổi (sau [Cập nhật Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3))

<table><thead><tr><th width="200.6015625">Thành phần quản trị</th><th width="218.01953125">Trước Tokenomics 3.0</th><th width="205.1796875">Sau Tokenomics 3.0</th><th>Trạng thái<select><option value="q1dVFsCri7zA" label="✅ Changed" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Unchanged" color="blue"></option></select></th></tr></thead><tbody><tr><td>Quyền bỏ phiếu</td><td>1 veCAKE = 1 quyền bỏ phiếu</td><td>1 CAKE = 1 quyền bỏ phiếu</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Ủy quyền</td><td>Được phép (thông qua cơ chế veCAKE)</td><td>Không cho phép ủy quyền</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Ngưỡng gửi đề xuất</td><td>Snapshot yêu cầu 100K veCAKE</td><td>Snapshot yêu cầu 100K CAKE</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Đề xuất Core vs Cộng đồng</td><td>Vai trò và mục đích được xác định rõ cho từng loại đề xuất</td><td>Không thay đổi</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Thời gian bỏ phiếu</td><td>Cộng đồng: Cố định<br>Core: Linh hoạt</td><td>Không thay đổi</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Thời điểm Snapshot</td><td>Tại block khi đề xuất được đăng</td><td>Không thay đổi</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Quorum</td><td>Không có quorum tối thiểu</td><td>Không thay đổi</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr></tbody></table>

### 1. **Quyền bỏ phiếu (Đã thay đổi)**

* **Tất cả người nắm giữ CAKE đều có quyền bỏ phiếu trực tiếp.**
* **Quyền bỏ phiếu tương ứng trực tiếp với số lượng CAKE nắm giữ trong địa chỉ ví tại thời điểm snapshot**
  * **1 CAKE = 1 quyền bỏ phiếu**
  * **CAKE được staking trong Syrup Pool không được tính** vào quyền bỏ phiếu của bạn, vì nó không thuộc số dư ví của bạn tại thời điểm snapshot
  * Số dư snapshot = Cùng block khi đề xuất được đăng
* **Ủy quyền không còn được hỗ trợ.** Mỗi người nắm giữ CAKE phải bỏ phiếu riêng lẻ.

### 2. **Gửi đề xuất (Không thay đổi)**

* **Cách gửi đề xuất**
  * Gửi tại [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)
  * Phải bao gồm:
    * Tiêu đề
    * Nội dung
    * Mô tả
    * Hành động on-chain (nếu cần)
    * Thời gian bỏ phiếu
* Các loại đề xuất
  1.  Đề xuất Core

      * Chỉ có thể được đề xuất bởi **Đội ngũ Core PancakeSwap**.
      * Yêu cầu bỏ phiếu từ người nắm giữ CAKE.
      * Nếu được thông qua, sẽ được đội ngũ PancakeSwap triển khai.

      Ví dụ

      1. Điều chỉnh giao thức (thay đổi sản phẩm, thay đổi phí)
      2. Sử dụng đáng kể quỹ Phát triển Hệ sinh thái không được bao gồm trong các đề xuất trước
  2. Đề xuất Cộng đồng
     * Các đề xuất **Cộng đồng** được đăng bởi cộng đồng PancakeSwap. Chúng được dùng để đề xuất ý tưởng và thể hiện quan điểm của cộng đồng. Đây là những **gợi ý không ràng buộc** từ cộng đồng.
     * Bất kỳ ai có **100.000 CAKE (số dư snapshot)** đều có thể gửi.
     * Đội ngũ PancakeSwap có thể tiếp thu các đề xuất mạnh và đưa vào Đề xuất Core trong tương lai
     * Thành viên cộng đồng cũng có thể sử dụng [Diễn đàn](https://forum.pancakeswap.finance/) của chúng tôi để cung cấp phản hồi và đề xuất với giao thức.

### **3. Thời gian bỏ phiếu (Không thay đổi)**

* Tất cả người nắm giữ CAKE có thể bỏ phiếu **trong khoảng thời gian bỏ phiếu** cho mỗi đề xuất.
  * Đề xuất Cộng đồng: Cố định 3 ngày
  * Đề xuất Core: Linh hoạt, do PancakeSwap quyết định
* Quyền bỏ phiếu của bạn được xác định bởi **snapshot số dư CAKE tại block khi đề xuất được đăng**.
* **Thêm CAKE sau khi đề xuất được đăng sẽ không tăng quyền bỏ phiếu của bạn** cho cuộc bỏ phiếu cụ thể đó.

Để biết chi tiết đầy đủ, xem [Hướng dẫn bỏ phiếu](https://docs.pancakeswap.finance/protocol/voting/voting-guide).

### **4. Kết quả bỏ phiếu (Không thay đổi)**

* Kết quả dựa trên **tổng số phiếu bầu** (tổng CAKE được dùng để bỏ phiếu)
* **Hiện tại không có quorum tối thiểu** để một đề xuất được thông qua.

## Lưu ý: Quyền phủ quyết

Để bảo vệ giao thức, **Đội ngũ Core PancakeSwap có quyền can thiệp trong các tình huống quan trọng** — chẳng hạn như các mối đe dọa bảo mật hoặc các vấn đề ảnh hưởng đến hoạt động ổn định của nền tảng — **mà không cần bỏ phiếu của cộng đồng hoặc thăm dò Snapshot**.

Trong bất kỳ trường hợp nào thực hiện hành động phủ quyết, Đội ngũ Core sẽ **công khai giải thích rõ ràng** về quyết định đó.

**Các hành động phủ quyết có thể bao gồm:**

1. **Tạm thời dừng smart contract** để sửa các lỗi hoặc lỗ hổng khẩn cấp.
