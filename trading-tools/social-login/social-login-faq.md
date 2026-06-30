# Social Login FAQ

{% hint style="info" %}
Để biết thêm thông tin, xem: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 Tổng quan Chung

**1. Social login của PancakeSwap là gì và tại sao tôi nên sử dụng nó?**

Social login cho phép bạn truy cập PancakeSwap bằng tài khoản **Google**, **X (Twitter)**, **Discord** hoặc **Telegram** — không cần tiện ích mở rộng ví hoặc cụm từ khôi phục. Một ví tự quản lý được tạo ở phía sau, để bạn có thể thử DeFi ngay lập tức, ngay cả với số tiền nhỏ. Điều này giảm rào cản gia nhập, đặc biệt trong những thời điểm nhạy cảm về thời gian.

**2. Social login hỗ trợ những chuỗi nào?**

Ví social login của bạn hoạt động trên tất cả các chuỗi hiện được PancakeSwap hỗ trợ:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

Tất cả các ví đều **tương thích EVM** và có thể được sử dụng trên các mạng này natively thông qua PancakeSwap. Nếu bạn muốn hỗ trợ thêm các chuỗi khác (bao gồm cả non-EVM), hãy cho chúng tôi biết!

**3. Tôi có thể sử dụng ví social login ở đâu?**

Bạn có thể sử dụng trực tiếp trong bất kỳ **trình duyệt** máy tính để bàn hoặc di động nào thông qua ứng dụng web PancakeSwap. Nó **không tương thích** với các ứng dụng ví bên ngoài hoặc trình duyệt dApp.



### 🛠️ Thiết lập & Sử dụng Ví

**4. Ví được tạo và bảo mật như thế nào?**

Ví của bạn được tạo tự động khi đăng nhập và được bảo mật bằng **hệ thống chia sẻ khóa 2-trong-2**. Cả hai phần đều cần thiết để tái tạo khóa và tạo chữ ký.

Để biết thêm thông tin về mã hóa phần chia sẻ, xem:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. Tôi có thể tạo bao nhiêu ví?**

Bạn nhận được **một ví cho mỗi tài khoản mạng xã hội cho mỗi dApp**. Ví dụ, nếu bạn sử dụng đăng nhập Google trên một ứng dụng khác cũng sử dụng Privy, nó sẽ tạo một ví riêng biệt.



### 🔐 Bảo mật & Quyền riêng tư

**6. Ai đó có thể truy cập ví của tôi nếu họ lấy cắp thiết bị của tôi không?**

Không. Ngay cả khi ai đó có quyền truy cập vào thiết bị của bạn, họ vẫn cần cả **social login** của bạn và (nếu đã đặt) **mật khẩu khôi phục** của bạn.

**7. PancakeSwap hoặc Privy lưu trữ dữ liệu gì?**

* PancakeSwap **không lưu trữ** bất kỳ phần chia sẻ khóa nào liên quan đến ví.
* Privy lưu trữ **Auth Share được mã hóa và Recovery Share (nếu luồng khôi phục chưa được thiết lập)**.

> Nếu bạn chưa hoàn thành thiết lập khôi phục, Recovery Share của bạn vẫn được lưu trữ với Privy theo mặc định. Để biết thêm thông tin, hãy truy cập: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 Khôi phục & Quản lý Phiên

**8. Tôi có thể sử dụng cùng một ví trên thiết bị hoặc trình duyệt khác không?**

Có! Chỉ cần đăng nhập bằng cùng tài khoản mạng xã hội. Nếu là thiết bị mới, bạn sẽ trải qua quy trình khôi phục bằng mật khẩu khôi phục (nếu đã thiết lập).

**9. Điều gì xảy ra nếu tôi chuyển đổi thiết bị?**

Bạn sẽ được yêu cầu đăng nhập lại bằng tài khoản mạng xã hội và trải qua luồng khôi phục (thiết lập mật khẩu). Nếu bạn chưa thiết lập mật khẩu khôi phục, đăng nhập bằng tài khoản mạng xã hội là đủ.

**10. Điều gì nếu tôi mất quyền truy cập vào cả social login và phương thức khôi phục?**

Nếu bạn mất quyền truy cập vào cả tài khoản mạng xã hội và phương thức khôi phục của mình, **ví của bạn không thể khôi phục**. Không có cụm từ khôi phục dự phòng, và việc xuất khóa riêng tư hiện không được hỗ trợ.

> ⚠️ Hãy nhớ: Việc xuất khóa riêng tư, nếu được kích hoạt trong tương lai, sẽ trao toàn quyền kiểm soát ví của bạn cho bất kỳ ai có nó — hãy xử lý nó với sự thận trọng tuyệt đối.

**11. Các phiên hoạt động kéo dài bao lâu?**

Các phiên kéo dài 30 **ngày**. Sau đó, bạn sẽ được nhắc **đăng nhập lại** và (nếu cần) nhập lại thông tin xác thực khôi phục của bạn. Trong phiên hoạt động, bạn có thể giao dịch mà không cần phê duyệt thủ công từng hành động.



### ⚙️ Khả năng tương thích & Hạn chế

**12. Tôi có thể xuất hoặc nhập ví không?**

* **Xuất**: Không được hỗ trợ theo mặc định, vì lý do bảo mật. Điều này có thể thay đổi trong các bản cập nhật tương lai.
* **Nhập**: Không được hỗ trợ. Bạn không thể nhập ví bên ngoài như MetaMask hay Phantom.

**13. Tôi có thể kết nối ví này với các dApp khác bằng WalletConnect không?**

Hiện tại chưa. Ví nhúng **chỉ giới hạn sử dụng trên PancakeSwap**. Nếu bạn quan tâm đến việc sử dụng rộng rãi hơn, hãy cho chúng tôi biết — các mở rộng trong tương lai là có thể.



### 🚀 Tính năng Nâng cao

**14. Ví social login có hỗ trợ Account Abstraction không?**

Có. Nó hỗ trợ **các tính năng Account Abstraction** như gộp giao dịch và **tài trợ gas** thông qua các tích hợp như Biconomy v.v.

**15. Các giao dịch không cần ký được kích hoạt như thế nào?**

* Sau khi đăng nhập, phiên của bạn hoạt động trong tối đa 30 **ngày**. Trong thời gian này, PancakeSwap có thể yêu cầu Privy ký giao dịch thay mặt bạn bằng thông tin xác thực phiên của bạn.&#x20;
* Bạn sẽ không thấy popup ví cho mỗi hành động — mọi thứ được xử lý ở nền. Sau 30 ngày, bạn cần đăng nhập lại để tiếp tục sử dụng trải nghiệm không cần ký này.
