---
hidden: true
---

# Wormhole Bridge FAQ

### H: Làm thế nào tôi có thể kiểm tra giao dịch của mình? <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormhole explorer

Trên trang trạng thái cầu nối. Bạn có thể thấy một liên kết sẽ đưa bạn đến giao dịch của mình trên Wormhole Explorer. Khi giao dịch chuỗi nguồn của bạn đã hoàn tất nhưng chưa được Wormhole xác minh, trạng thái giao dịch của bạn sẽ trông như sau:

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KyaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

Tùy chọn tìm kiếm để đổi là một phương pháp thay thế mà bạn có thể làm theo để hoàn tất giao dịch chuỗi đích của mình. Bạn có thể sử dụng phương pháp này trong trường hợp wormhole bridge bị dừng lại hoặc không cập nhật được trạng thái giao dịch cầu nối của bạn. Để đổi giao dịch, trước tiên hãy nhấp vào nút đổi

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

Sau đó nó sẽ hiển thị tùy chọn này để tiếp tục giao dịch của bạn. Nhấp vào đây để được điều hướng đến diễn đàn (liên kết trong câu hỏi tiếp theo) nơi bạn có thể hoàn tất giao dịch đổi của mình. <br>

### H: Tôi đã gửi token đến \<chain> - token của tôi không đến ví đích nhưng đã rời ví nguồn. Tôi phải làm gì?[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

Bạn cần a) đổi chúng, hoặc nếu việc đổi đã thành công, b) thêm chúng vào ví của bạn:

**a) Đổi:**

* Truy cập [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem)
* Bạn cần nhập chuỗi nguồn và ID giao dịch tương ứng (mà bạn có thể tìm thấy trong ví của mình, hoặc với địa chỉ của bạn trong trình duyệt khối của blockchain)

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* Nhấp vào Recover
* Nhấp vào Redeem và chấp nhận phê duyệt ví

**b) Thêm vào ví của bạn:**

**Metamask:**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* Trong tab tài sản Metamask, nhấp vào import tokens
* Địa chỉ hợp đồng có thể được tìm thấy trong giao dịch trình duyệt khối liên quan và nhấp vào tên token. Khi bạn nhấp vào tên token, nó sẽ mở một cửa sổ mới và địa chỉ hợp đồng nằm ở phía bên phải trong phần tóm tắt hồ sơ.
* Bạn cũng cần một ký hiệu - đây có thể là bất cứ điều gì bạn muốn để nhận ra token.
* Nhấp vào add custom token

Xem hướng dẫn video - Cách thêm token vào ví Metamask của bạn [tại đây.](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)

### Tôi đã kết nối chuỗi token X nhưng bây giờ không thể hoán đổi nó. Không có DEX nào có thị trường thanh khoản,[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

Bạn đã kết nối chuỗi một token không có thanh khoản trên chuỗi đích. Bạn sẽ cần sử dụng Portal bridge để kết nối chuỗi token này trở lại. Bạn có thể làm điều này bằng cách dán địa chỉ hợp đồng token (mà bạn có thể tìm thấy trong ví của mình hoặc với địa chỉ của bạn trong trình duyệt khối của blockchain) vào trường tìm kiếm "select a token" của Portal.

Bạn có thể tìm thấy tổng quan toàn diện về các thị trường thanh khoản [tại đây](https://portalbridge.com/docs/faqs/liquid-markets).

#### Làm thế nào tôi có thể đổi token của mình trên chuỗi đích?[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

Nếu bạn vô tình làm mới trang trong quá trình chuyển hoặc không đổi token của mình, bạn có thể làm theo hướng dẫn [tại đây](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow).
