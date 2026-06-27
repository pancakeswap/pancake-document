# FAQ Monad

#### 1. Có những mức phí nào cho nhóm thanh khoản trên PancakeSwap?

**Các Mức Phí Được Hỗ Trợ:**

* Các mức phí sau có sẵn cho các nhóm V3 (thanh khoản tập trung): `0.01%, 0.05%, 0.25%, 1%`&#x20;
* Đối với nhóm V2 chỉ hỗ trợ mức phí 0.25%

#### 2. Ai cũng có thể tạo nhóm không?

Có. Việc tạo nhóm không cần cấp phép, với một vài ngoại lệ:

* Chỉ có thể tồn tại một nhóm cho một **cặp token + mức phí** nhất định (ví dụ: chỉ có thể tồn tại một nhóm WMON <> USDC 0.05% tại một thời điểm)

#### 3. Mất bao lâu để nhóm mới tạo xuất hiện?

* Các nhóm thường xuất hiện trong danh sách nhóm khoảng **5 phút** sau khi tạo.
* Nếu không xuất hiện:
  * Sử dụng **thanh tìm kiếm** để tìm thủ công.
  * Các nhóm có thể bị lọc khỏi danh sách do **TVL thấp**.

#### 4. Tại sao APR hoặc TVL của nhóm tôi vẫn hiển thị là không?

Điều này được mong đợi ngay sau khi một nhóm mới được tạo:

* Dữ liệu APR và TVL sẽ chỉ được điền sau khi **ít nhất một giao dịch hoán đổi** xảy ra trong nhóm.
* Sau khi hoán đổi, các chỉ số này sẽ bắt đầu hiển thị trong khoảng **15 phút**.

#### **5. Tại sao các giao dịch đôi khi thất bại nếu ví của tôi có ít hơn 10 MON?**

Monad có quy tắc rằng mọi tài khoản phải giữ **bộ đệm an toàn tối thiểu là 10 MON**. Nếu số dư của bạn thấp và bạn gửi quá nhiều giao dịch quá nhanh, mạng có thể **ngừng chấp nhận các giao dịch mới**.

#### **6. Tại sao 1-2 giao dịch đầu tiên hoạt động, nhưng các giao dịch tiếp theo lại thất bại?**

Monad xử lý các khối bằng cách sử dụng quan điểm "trễ hơn một chút" về số dư của bạn. Vì vậy:

* Giao dịch **đầu tiên** của bạn thường ổn.
* Giao dịch **thứ hai** cũng có thể được xử lý.
* Nhưng nếu bạn gửi **nhiều giao dịch trong thời gian ngắn**, mạng nghĩ bạn có thể không có đủ MON để trả tất cả phí gas.

Vì vậy, nó **chặn** giao dịch tiếp theo. Đây là bình thường và là một phần của hệ thống an toàn.

#### **7. Tại sao lại nghiêm ngặt hơn với tài khoản thông minh (ví hợp đồng)?**

Tài khoản thông minh tuân theo **các quy tắc nghiêm ngặt hơn**:

* Chúng phải **luôn** giữ ít nhất **10 MON** trong khi chạy mã hợp đồng.
* Nếu tài khoản thông minh của bạn dưới 10 MON, giao dịch có thể **bị hoàn lại ngay lập tức**, ngay cả khi EOA vẫn hoạt động trong một vài giao dịch.

Đây là lý do người dùng tài khoản thông minh thấy thất bại sớm hơn.

#### **8. Điều này có nghĩa là tôi không thể sử dụng Monad với ít hơn 10 MON không?**

Bạn _vẫn_ có thể sử dụng, đặc biệt với EOA bình thường — nhưng:

* Đừng gửi nhiều giao dịch liên tiếp.
* Chờ vài khối giữa các giao dịch.
* Giữ một ít MON trong ví để tránh sự cố.

#### **9. Làm thế nào để tránh những thất bại này?**

Mẹo đơn giản:

* Giữ **10 MON hoặc nhiều hơn** trong ví nếu có thể.
* Nếu bạn thiếu MON, **giãn cách các giao dịch** (đừng gửi liên tục).
* Người dùng tài khoản thông minh nên giữ **nhiều hơn 10 MON một chút**, vì các lệnh gọi hợp đồng sử dụng gas thêm.
