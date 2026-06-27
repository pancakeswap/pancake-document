---
description: Thêm thanh khoản chỉ với một cú nhấp chuột
---

# Zap

### Zap là gì <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap là tính năng cho phép bạn thêm thanh khoản một cách dễ dàng. Với Zap, bạn có thể cung cấp thanh khoản bằng bất kỳ token nào bạn có số dư bất kể token nào được yêu cầu trong pool. Chỉ cần đặt phạm vi giá, chọn số lượng cung cấp và thực hiện. Token của bạn sẽ tự động được cân bằng để tạo thành vị thế thanh khoản trong khi được giao dịch theo cách hiệu quả nhất, với mức tác động giá và trượt giá thấp nhất.

### Các Chuỗi Được Hỗ trợ

* v3 - Tất cả pool trên BNB Chain, các pool được chọn trên mạng Ethereum & Arbitrum
* Infinity - Tất cả pool CLAMM (không có hook) trên BNB Chain

### Cách Sử dụng <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

Hiện tại, Zap hỗ trợ:

* 🆕 Bất kỳ token nào!
* Sử dụng một token đơn lẻ
* 🆕 Sử dụng hai token
* 🆕 Hoặc... sử dụng nhiều token (có, nó có thể được dùng như bộ thu token bụi)

#### Bắt đầu <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Để sử dụng Zap, chỉ cần đến trang Add Liquidity, chọn cặp giao dịch bạn muốn cung cấp thanh khoản, mức phí và phạm vi giá.

Sau đó chọn số lượng token bạn muốn cung cấp thanh khoản.

Tùy chọn Zap sẽ tự động xuất hiện khi một hoặc nhiều token thiếu số dư.

Nhấp vào đường dẫn để mở modal Zap.

#### Bắt đầu Zap <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

Trong modal "Zap in" mới. Bạn có thể tìm thấy các trường sau:

1. Cặp giao dịch bạn đang Zap (cung cấp thanh khoản) vào.
2. Token nạp và số lượng cần nạp. Bạn có thể tự do thêm hoặc xóa bất kỳ token nào cho Zap.
3. Phạm vi giá của vị thế mới. Bạn cũng có thể nhấp các mũi tên để chuyển đổi giữa các hiển thị giá khác nhau.
4. Bảng phân tích chi tiết về cách tính năng Zap xử lý token nạp của bạn.
5. Tóm tắt số liệu thống kê bao gồm:
   1. Giá trị ước tính bằng USD cho vị thế thanh khoản mới.
   2. Ước tính số lượng token trong vị thế thanh khoản mới.
   3. Ước tính số tiền còn lại bằng USD sau khi Zap. Trong hầu hết các trường hợp phải bằng 0. Nếu pool thanh khoản hoặc token có thanh khoản rất ít, giá trị này có thể tăng.
   4. Tác động giá cho các hoán đổi token và cân bằng lại khi Zap.
   5. Tác động giá cho việc thêm thanh khoản và xây dựng vị thế.
   6. Phí Zap. Tùy thuộc vào cặp thanh khoản, mức phí có thể khác nhau.

{% hint style="warning" %}
Lưu ý rằng bạn có thể cần cấu hình lại số lượng cần Zap dựa trên số dư có sẵn. Nếu bạn không có số dư cho một trong các token, vui lòng xóa chúng.
{% endhint %}

{% hint style="info" %}
Bạn có thể nhận thấy rằng các cài đặt từ "Add V3 Liquidity" được tự động chuyển sang modal Zap. Bao gồm số lượng nạp và cài đặt phạm vi giá.
{% endhint %}

#### Bắt đầu Zapping <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

Cuối cùng nhấp "Approve" và xác nhận trong cửa sổ pop-up ví cho phép token.

Sau đó, nhấp "Preview" để mở modal xác nhận cuối cùng. Trước khi tiến hành, vui lòng xem lại tất cả số liệu thống kê và ước tính được hiển thị trong modal xác nhận cuối cùng. Đặc biệt là số liệu tác động và trượt giá tối đa.

Cuối cùng, nhấp "Add Liquidity" và xác nhận trong cửa sổ pop-up ví của bạn.

Sau khi tx được xác nhận, bạn sẽ thấy vị thế mới bóng loáng trong trang "My Position"

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### Cài đặt Thêm <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Nếu bạn muốn tùy chỉnh thêm trải nghiệm Zap. Chỉ cần nhấp biểu tượng bánh răng ở góc trên bên phải. Trong cài đặt, bạn có thể cấu hình:

* Trượt giá tối đa khi zapping.
* Thời gian trên thời hạn giao dịch.
* Có sử dụng thanh khoản tổng hợp của KyberSwap để thực hiện cân bằng lại token không. Tắt nếu bạn chỉ muốn giao dịch trong PancakeSwap Pools.
* Chế độ Degen có thể được sử dụng để thực hiện các Zap trượt giá cực cao. Không được khuyến nghị cho các trường hợp sử dụng thông thường, sử dụng theo rủi ro của bạn.

{% hint style="warning" %}
Lưu ý rằng các cài đặt Slippage và Deadline là độc lập với trang Swap và Liquidity.
{% endhint %}

#### Zap vào bằng hai token

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Bây giờ bạn có thể Zap thanh khoản bằng hai token. Điều này hữu ích khi số dư có sẵn của bạn không khớp với cài đặt giá và số lượng token cùng tỷ lệ cần thiết. Chỉ cần Zap và tỷ lệ sẽ được tự động cân bằng lại.

#### Zap vào bằng nhiều token

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Có, nó hoạt động giống như bộ thu token bụi. Thích hợp để dọn dẹp các số dư nhỏ trong ví của bạn và đưa chúng vào vị thế để bắt đầu kiếm từ phí giao dịch.&#x20;
