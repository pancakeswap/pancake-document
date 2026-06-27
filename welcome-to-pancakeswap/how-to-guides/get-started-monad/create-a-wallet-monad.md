# Tạo Ví (Monad)

### 1. **Tại Sao Bạn Cần Ví**

Để sử dụng **PancakeSwap trên Monad**, bạn cần một **ví crypto** — đó là kho lưu trữ cá nhân cho tài sản kỹ thuật số và hộ chiếu của bạn vào DeFi. Không có ví, bạn sẽ không thể:

* **Hoán đổi token** trên Monad
* **Cung cấp thanh khoản** cho **V2 & V3 Pools** của PancakeSwap
* Tương tác với bất kỳ dApp nào hoặc lưu trữ token trên Monad

***

### 2. **Điều Cần Thiết Khi Thiết Lập Ví (Bảo Mật Trước!)**

Ví crypto cấp cho bạn toàn quyền kiểm soát tài sản — nhưng quyền lực lớn đi kèm trách nhiệm lớn. Hãy giữ ví của bạn an toàn bằng cách làm theo các thực hành tốt nhất sau:

| ✅ Nên làm                                                               | ❌ Không nên làm                                               |
| ----------------------------------------------------------------------- | ------------------------------------------------------------- |
| ✅ **Tải xuống từ nguồn chính thức** (cửa hàng ứng dụng, trang web xác minh) | ❌ Không cài đặt từ các liên kết ngẫu nhiên hoặc DM           |
| ✅ **Làm theo hướng dẫn thiết lập** một cách cẩn thận                  | ❌ Không vội vàng hoặc bỏ qua quá trình sao lưu               |
| ✅ **Sao lưu cụm từ khôi phục** và lưu trữ ngoại tuyến                 | ❌ Không chụp ảnh màn hình hoặc lưu trên điện thoại hoặc máy tính |
| ✅ **Giữ cụm từ riêng tư** — đó là cách duy nhất để khôi phục quyền truy cập | ❌ Không bao giờ chia sẻ, ngay cả khi ai đó tự xưng là "hỗ trợ" |
| ✅ Chỉ nhập cụm từ khôi phục **bên trong ứng dụng ví**                 | ❌ Không bao giờ nhập vào trang web, cửa sổ bật lên, hoặc ứng dụng khác |

> 🧠 Cụm từ khôi phục của bạn = quyền truy cập vào ví của bạn

***

### 3. **Chọn Ví: Di Động hay Máy Tính Để Bàn**

Không chắc nên dùng loại ví nào? Đây là phân tích nhanh về ví di động so với ví máy tính/web để bạn chọn loại phù hợp với phong cách của mình:

| Tính năng        | **Ví Di Động**                     | **Ví Trình Duyệt/Máy Tính**             |
| ---------------- | ---------------------------------- | --------------------------------------- |
| **Trường hợp dùng** | Hoán đổi & theo dõi khi di chuyển | Tốt nhất cho đa nhiệm hoặc sử dụng dApp sâu |
| **Dễ sử dụng**  | Trực quan, thân thiện với người mới | Tiện ích mở rộng nhẹ, truy cập nhanh   |
| **Bảo mật**     | Phụ thuộc vào bảo mật điện thoại  | Tích hợp ví phần cứng dễ hơn           |
| **Tiện lợi**    | Ứng dụng tất cả trong một         | Thủ công hơn, nhưng mạnh mẽ            |
| **Tốt nhất cho...** | Người dùng thông thường, trader ưu tiên di động | Người dùng máy tính, luồng nâng cao hơn |

> 📱 Ví di động có thể cung cấp trải nghiệm mượt mà hơn cho việc giao dịch, quản lý danh mục đầu tư, và duyệt NFT — tất cả từ điện thoại của bạn.

***

{% hint style="success" %}
**Một số** [**ví**](https://docs.monad.xyz/tooling-and-infra/wallets/software-wallets) **phổ biến mà bạn có thể sử dụng cho hệ sinh thái Monad!**
{% endhint %}

***

#### 🔌 **Tùy Chọn Tương Thích WalletConnect**

Sử dụng **WalletConnect**, bạn có thể kết nối ví với PancakeSwap trên Monad — trực tiếp từ máy tính để bàn hoặc di động:

* **Leap wallet**
* **Bitget wallet**
* **HaHa wallet**
* **Backpack,** và nhiều hơn nữa

> Bạn sẽ thấy danh sách đầy đủ các ví được hỗ trợ khi kết nối trên giao diện PancakeSwap qua WalletConnect.

***

### 4. **Các Bước Thiết Lập Ví Chung (Hướng Dẫn Nhanh)**

Dù bạn chọn ví nào, quy trình thường tương tự:

1. **Tải xuống** ứng dụng ví hoặc tiện ích mở rộng trình duyệt từ **nguồn chính thức**
2. Khởi động ứng dụng và nhấn **"Create a new wallet"**
   * (Hoặc chọn **"Import"** nếu bạn đã có một cái)
3. Đặt **mật khẩu hoặc PIN** mạnh (nếu cần)
4. Bạn sẽ được hiển thị một **cụm từ khôi phục** (12 hoặc 24 từ) —

   → **Viết ra và lưu ở nơi an toàn, ngoại tuyến**
5. **Xác nhận cụm từ khôi phục** để hoàn tất thiết lập
6. **Nạp tiền vào ví bằng MON**

   → Bạn sẽ cần **MON** để trả phí gas khi hoán đổi hoặc thêm thanh khoản trên PancakeSwap
7. Bạn có thể kết nối chuỗi tài sản sang Monad bằng [cầu nối xuyên chuỗi](https://monadbridge.com/) này
