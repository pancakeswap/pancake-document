# ❓ FAQ

### 1. Mức trượt giá hoạt động như thế nào trong hoán đổi xuyên chuỗi?

Đối với hoán đổi xuyên chuỗi, phần trăm mức trượt giá bạn chọn được áp dụng độc lập cho các hoán đổi trên cả chuỗi nguồn và chuỗi đích.

**Ví dụ:**

* Hoán đổi BNB trên BNB Chain sang ARB trên Arbitrum
* Mức trượt giá được đặt là 1%
* Lộ trình có thể là:
  1. Hoán đổi BNB sang USDC trên BNB Chain
  2. Kết nối cầu nối USDC từ BNB Chain sang Arbitrum qua Across
  3. Hoán đổi USDC sang ARB trên Arbitrum
* Trong trường hợp này, mức trượt giá 1% được áp dụng riêng cho:
  * Hoán đổi trên BNB Chain
  * Hoán đổi trên Arbitrum

Điều này đảm bảo bạn được bảo vệ khỏi biến động giá quá mức ở cả hai nhánh của giao dịch trong khi không ảnh hưởng đến quá trình kết nối cầu nối.

### 2. Điều gì xảy ra nếu giao dịch của tôi thất bại?

Nếu hoán đổi xuyên chuỗi của bạn gặp sự cố ở bất kỳ giai đoạn nào, đây là cách xử lý:

1.  **Thất Bại Hoán Đổi/Giao Dịch trên Chuỗi Nguồn**

    ➝ Bạn sẽ nhận lại ngay lập tức token gốc trên chuỗi nguồn.
2.  **Thất Bại Giao Dịch Cầu Nối**

    ➝ Across sẽ xử lý hoàn tiền trong vòng 90 phút đến 2 giờ, và bạn sẽ nhận lại tài sản đã kết nối trên chuỗi nguồn. Trong khi đó Relay xử lý hoàn tiền trong vòng một phút trong các kịch bản như vậy giữa SOL <> EVM.
3.  **Thất Bại Hoán Đổi trên Chuỗi Đích**

    ➝ Bạn sẽ nhận tài sản đã kết nối cầu nối trên chuỗi đích, mà không có hoán đổi cuối cùng sang token mục tiêu.

{% hint style="info" %}
**Lưu ý:** Bạn luôn có thể kiểm tra trạng thái giao dịch của mình qua tab lịch sử giao dịch trong giao diện kết nối ví.
{% endhint %}

### 3. Hoán đổi xuyên chuỗi của tôi có được bảo vệ MEV không?

MEV Guard chỉ được hỗ trợ trên BNB Chain khi hoán đổi được khởi tạo trực tiếp từ ví được kết nối với MEV Guard đã bật.

* Nếu hoán đổi xuyên chuỗi của bạn liên quan đến hoán đổi trên BNB Chain là chuỗi nguồn, và bạn đã bật MEV Guard, thì hoán đổi đó sẽ được bảo vệ MEV.
* Nếu BNB Chain là chuỗi đích, hoán đổi được thực hiện bởi relayer/hệ thống kết nối cầu nối và sẽ không được bảo vệ MEV, vì nó không được khởi tạo từ ví được kết nối của bạn.

{% hint style="info" %}
**Lưu ý:** Các chuỗi khác như Arbitrum và Base hiện không hỗ trợ bảo vệ MEV Guard trên PancakeSwap.
{% endhint %}

### 4. Tôi có thể hoán đổi stablecoin giữa các chuỗi không?

Có — bạn có thể hoán đổi và kết nối cầu nối các stablecoin như USDC, USDT và DAI trực tiếp giữa bất kỳ chuỗi nào được hỗ trợ.

Bạn có hai lựa chọn:

1.  **Kết Nối Cầu Nối Trực Tiếp:**

    Kết nối cầu nối trực tiếp các stablecoin được hỗ trợ (như USDC, USDT, v.v.) từ một chuỗi sang chuỗi khác.
2.  **Hoán Đổi Sang Token Khác:**

    Bạn cũng có thể hoán đổi stablecoin sang bất kỳ token nào được hỗ trợ trên chuỗi đích bằng cách sử dụng các nhóm thanh khoản của PancakeSwap — trước hoặc sau khi kết nối cầu nối.

{% hint style="info" %}
**Lưu ý:** Các stablecoin được hỗ trợ để kết nối cầu nối trực tiếp có thể khác nhau tùy theo chuỗi.
{% endhint %}

### 5. Hoán đổi của tôi có sử dụng PCSX không?

Không — PCSX không được hỗ trợ để phục vụ hoán đổi xuyên chuỗi.

Hoán đổi xuyên chuỗi trên PancakeSwap được định tuyến độc quyền qua:

* **Các nhóm thanh khoản của PancakeSwap** (v2, v3, Infinity, StableSwap) cho các hoán đổi trên chuỗi, và
* **Giao thức Across & Relay** để kết nối tài sản giữa các chuỗi.

PCSX không thể được sử dụng để thực hiện hoặc định tuyến bất kỳ phần nào của giao dịch hoán đổi xuyên chuỗi.

### 6. Có giới hạn tối thiểu hoặc tối đa về số lượng hoán đổi không?

Có — cả giới hạn tối thiểu và tối đa đều áp dụng cho các giao dịch xuyên chuỗi.

* **Giới Hạn Tối Đa:**\
  Phụ thuộc vào thanh khoản cầu nối khả dụng cho token và chuỗi được chọn. Giá trị này có thể biến động theo thời gian thực dựa trên điều kiện mạng lưới và thanh khoản.
* **Giới Hạn Tối Thiểu:**\
  Được đặt để đảm bảo việc relayer xử lý giao dịch cầu nối là khả thi về mặt kinh tế.

{% hint style="info" %}
**Lưu ý:** Giới hạn tối thiểu và tối đa chính xác khác nhau tùy theo token cầu nối. Nếu số lượng giao dịch của bạn nằm ngoài phạm vi cho phép, giao diện sẽ hiển thị thông báo lỗi rõ ràng và nhắc bạn điều chỉnh số lượng.
{% endhint %}
