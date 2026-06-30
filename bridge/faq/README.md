# ❓ FAQ Kết Nối Chuỗi

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Trước Khi Kết Nối Chuỗi

1.  **Tôi có thể sử dụng ví di động hoặc ví khác ngoài MetaMask để kết nối chuỗi CAKE không?**

    Hiện tại, PancakeSwap CAKE Bridging hỗ trợ Coinbase Wallet, MetaMask và các ví tương thích với MetaMask. Hỗ trợ thêm nhiều ví hơn sẽ sớm ra mắt.

    _Mẹo:_ Để tránh việc sao chép khóa riêng tư hoặc cụm từ khôi phục có rủi ro, chúng tôi khuyến nghị tạo ví mới qua các tiện ích mở rộng ví trên máy tính để bàn để kết nối chuỗi.
2.  **Tại sao một tuyến đường hoặc token không khả dụng?**

    Một số tuyến đường phụ thuộc vào dung lượng cầu nối, hỗ trợ token hoặc thanh khoản. Hãy kiểm tra lại sau hoặc thử nhà cung cấp khác. Các token có sẵn theo từng chuỗi được hiển thị trực tiếp trong giao diện Cầu nối.
3.  **Tôi gặp lỗi khi gửi giao dịch kết nối chuỗi.**

    Hãy thử nhập số lượng thủ công thay vì sử dụng nút "MAX", và loại bỏ các chữ số thập phân khỏi số lượng nếu cần thiết.
4.  **Tại sao báo giá kết nối chuỗi của tôi hiển thị "Insufficient X to cover native fee"**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    Kết nối chuỗi yêu cầu phí gas được thanh toán bằng token gốc của chuỗi nguồn, ví dụ:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    Đảm bảo bạn có đủ token gốc trong ví nguồn để trang trải phí hoàn thành giao dịch.
5.  **Tại sao nút hiển thị "X CAKE Exceeded"?**

    Có giới hạn dung lượng hàng ngày để kết nối chuỗi CAKE giữa BSC và Aptos nhằm đảm bảo an toàn. Hãy thử số lượng nhỏ hơn hoặc chờ và thử lại sau. Giới hạn được điều chỉnh động bởi các Chefs dựa trên nhu cầu.
6.  **Tại sao tôi không thể tìm thấy một token cụ thể?**

    Token đó có thể không được hỗ trợ trên tuyến đường bạn đã chọn hoặc thiếu thanh khoản. Hãy thử chuỗi khác hoặc số lượng khác.
7.  **Tôi có thể kết nối chuỗi từ BNB Chain sang Ethereum nhưng sang một địa chỉ khác không?**

    Không, vì lý do an toàn, kết nối chuỗi chỉ hoạt động giữa cùng một địa chỉ trên các chuỗi EVM.
8.  **Tại sao tôi không thể kết nối chuỗi ít hơn 0.00000001 CAKE?**

    Các token Aptos, bao gồm CAKE trên Aptos, có tối đa 8 chữ số thập phân. Các giao dịch dưới 0.00000001 sẽ bị từ chối hoặc làm tròn xuống. Điều này cũng áp dụng cho việc kết nối chuỗi Ethereum. Bất kỳ số dư còn lại nào sẽ ở trong ví nguồn của bạn.

***

## Sau Khi Kết Nối Chuỗi

1.  **Tôi có thể hủy giao dịch kết nối chuỗi sau khi xác nhận không?**

    Không, một khi đã bắt đầu, giao dịch cầu nối được xử lý bởi nhà cung cấp và không thể hủy. Để đảo ngược, hãy kết nối chuỗi tài sản trở lại qua một giao dịch mới.
2.  **Nếu giao dịch của tôi bị kẹt ở trạng thái "pending" thì sao?**

    Kết nối chuỗi có thể mất đến 30 phút. Kiểm tra trạng thái giao dịch của bạn bằng cách tìm kiếm hash giao dịch trên trình duyệt khối của nhà cung cấp cầu nối tương ứng:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    Nếu vẫn pending sau 60 phút, vui lòng liên hệ với các quản trị viên của chúng tôi qua [các kênh mạng xã hội](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
3. **Tôi chưa nhận được CAKE của mình. Tôi nên làm gì?**
   * Khi kết nối chuỗi CAKE sang Aptos lần đầu tiên, bạn có thể cần **nhận thủ công** CAKE của mình. Đảm bảo ví Aptos của bạn có đủ APT để trả gas. Xem [hướng dẫn kết nối chuỗi Aptos](https://docs.pancakeswap.finance/bridge/bridging/aptos) và [giải thích của Aptos](https://theaptosbridge.com/faq#registering-claiming-assets).
   * Khi kết nối chuỗi sang BNB Chain hoặc Ethereum, một số ví yêu cầu bạn thêm thủ công địa chỉ token CAKE để xem số dư của mình. Ví dụ, làm theo [hướng dẫn MetaMask](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) này - các ví khác nên có quy trình tương tự.
   * Nếu bạn vẫn không thấy CAKE sau 60 phút, hãy liên hệ với các quản trị viên của chúng tôi qua [các kênh mạng xã hội](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
