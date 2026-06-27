---
description: Kết nối chuỗi CAKE giữa các chuỗi EVM và Aptos
---

# Cách Kết Nối Chuỗi - EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Hướng dẫn sau đây sử dụng BNB Chain làm ví dụ về chuỗi EVM. Quy trình tương tự có thể áp dụng cho Ethereum.
{% endhint %}

## Kết Nối Chuỗi CAKE từ BNB Smart Chain sang Aptos

1 - Đảm bảo ví của bạn hỗ trợ cả BNB Smart Chain và Aptos Mainnet. Hoặc bạn đã cài đặt cả hai ví trong trình duyệt của mình.

Sau đó mở [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Đầu tiên, chúng ta cần kết nối ví BNB Smart Chain của mình.

Nhấp vào "Connect" và chọn ví bạn muốn trong phần "EVM". Sau đó xác nhận và phê duyệt trong cửa sổ bật lên của ví.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Sau đó, chúng ta cần kết nối ví Aptos của mình.

Trong modal kết nối ví, chọn ví bạn muốn trong phần "Aptos". Sau đó xác nhận và phê duyệt trong cửa sổ bật lên của ví.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Nhấp vào "v" trong trường chọn token phía trên và chọn "CAKE".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - Nhập số lượng CAKE bạn muốn kết nối chuỗi sang Aptos.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Nếu ví Aptos của bạn mới tạo và không có số dư APT (Aptos Coin). Chúng tôi khuyến nghị giữ tùy chọn "gas on destination" ở mức mặc định. Cầu nối sẽ nạp một lượng nhỏ APT vào ví của bạn, không chỉ để giúp bạn khởi đầu hành trình trên Aptos, mà bạn cũng sẽ cần APT để trả gas cho việc đăng ký và nhận CAKE đã được kết nối chuỗi.

Thay đổi tùy chọn này có thể khiến việc kết nối chuỗi thất bại.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - Nhấp vào "Transfer" để khởi tạo giao dịch kết nối chuỗi và xác nhận qua cửa sổ xác nhận ví.

Xin lưu ý rằng tùy thuộc vào tình trạng ví BNB Smart Chain và ví Aptos của bạn. Bạn có thể cần phê duyệt **nhiều** xác nhận ví. Ví dụ nếu bạn đang kết nối chuỗi CAKE sang Aptos lần đầu tiên, bạn sẽ cần:

* Phê duyệt chi tiêu CAKE trên hợp đồng kết nối chuỗi (từ ví BNB Smart Chain của bạn)
* Đăng ký CAKE (từ ví Aptos của bạn)

Để biết thêm chi tiết, hãy xem [phân tích này](aptos.md#bridging-cake-to-aptos-for-the-first-time).

8 - Hãy ngồi lại và thư giãn. Chỉ cần vài phút. Sau khi kết nối chuỗi hoàn tất, CAKE sẽ được nạp vào ví Aptos của bạn. Bạn có thể theo dõi tiến trình qua thanh tiến trình.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## Kết Nối Chuỗi CAKE sang Aptos Lần Đầu Tiên

Việc kết nối chuỗi CAKE sang ví Aptos yêu cầu các giao dịch đăng ký và nhận. Điều này được thực hiện để tăng cường bảo mật người dùng và là đặc thù của Aptos.

### **Nếu bạn đã có APT (Aptos Coin) trong ví:**

Bạn sẽ được nhắc đăng ký CAKE trên ví Aptos của mình nếu chưa đăng ký. Trong trường hợp này không cần giao dịch nhận thêm.

### **Nếu bạn chưa có APT (Aptos Coin) trong ví:**

Sau khi giao dịch cầu nối hoàn tất, bạn cần nhận CAKE thủ công. Để trang trải phí gas cho việc nhận, token APT sẽ được gửi đến ví Aptos của bạn từ ví nguồn.

Các bước đăng ký và nhận này chỉ áp dụng lần đầu tiên bạn tương tác với một token trên Aptos. Các giao dịch chuyển tiếp theo của cùng token sẽ không yêu cầu các hành động này.

Trước khi kết nối chuỗi CAKE sang Aptos lần đầu tiên, hãy đảm bảo địa chỉ Aptos của bạn có đủ APT để trả phí gas. Để biết thêm chi tiết, hãy xem giải thích của Aptos tại đây: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Kết Nối Chuỗi CAKE từ Aptos sang BNB Smart Chain

1 - Đảm bảo ví của bạn hỗ trợ cả BNB Smart Chain và Aptos Mainnet. Hoặc bạn đã cài đặt cả hai ví trong trình duyệt của mình.

Sau đó mở [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Đầu tiên, chúng ta cần kết nối ví BNB Smart Chain của mình.

Nhấp vào "Connect" và chọn ví bạn muốn trong phần "EVM". Sau đó xác nhận và phê duyệt trong cửa sổ bật lên của ví.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Sau đó, chúng ta cần kết nối ví Aptos của mình.

Trong modal kết nối ví, chọn ví bạn muốn trong phần "Aptos". Sau đó xác nhận và phê duyệt trong cửa sổ bật lên của ví.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Nhấp vào "v" trong trường chọn token phía trên và chọn "CAKE". Sau đó nhấp vào nút mũi tên đôi ở giữa trang để đổi chiều hướng kết nối chuỗi.

Hãy đảm bảo mạng "Aptos" nằm ở trường phía trên.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - Nhập số lượng CAKE bạn muốn kết nối chuỗi sang BNB Smart Chain.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - Nếu ví BNB Smart Chain của bạn mới tạo và không có số dư BNB (token gas). Chúng tôi khuyến nghị giữ tùy chọn "gas on destination" ở mức mặc định. Cầu nối sẽ nạp một lượng nhỏ BNB vào ví của bạn. Điều này sẽ giúp bạn khởi đầu hành trình trên BNB Smart Chain và khám phá hệ sinh thái PancakeSwap sôi động.

7 - Nhấp vào "Transfer" và phê duyệt các giao dịch từ cửa sổ bật lên của ví.

8 - Hãy ngồi lại và thư giãn. Chỉ cần vài phút. Sau khi kết nối chuỗi hoàn tất, CAKE sẽ được nạp vào ví BNB Smart Chain của bạn. Bạn có thể theo dõi tiến trình qua thanh tiến trình.
