---
description: Cách "gỡ kẹt" bất kỳ giao dịch đang chờ xử lý nào bị kẹt trong MetaMask của bạn
---

# Sửa Giao Dịch Đang Chờ Xử Lý Bị Kẹt Trên MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Nếu giao dịch của bạn bị kẹt ở trạng thái chờ xử lý trong Metamask và nút "Cancel" không giúp ích được, bạn có thể cần sử dụng phương pháp này để xóa hàng đợi.

Phương pháp này về cơ bản hoạt động bằng cách ghi đè giao dịch bị kẹt bằng một giao dịch khác có mức độ ưu tiên cao hơn.

### **1. Bật Tùy Chỉnh Nonce Giao Dịch**

1\. Mở plugin MetaMask của bạn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Nhấp vào biểu tượng vòng tròn màu sắc ở góc trên bên phải và nhấp vào **Settings** từ menu thả xuống.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Trong menu Settings, chọn **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Cuộn xuống cho đến khi bạn thấy **Advanced gas controls**. Bật nó lên ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Vẫn trong cài đặt Advanced, tiếp tục cuộn cho đến khi bạn thấy **Customize transaction nonce**. Bật nó lên ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Tìm Giao Dịch Bị Kẹt Của Bạn**

Bây giờ chúng ta sẽ tìm giao dịch bị kẹt và ghi chú "nonce". Đó là một loại định danh, mà chúng ta sẽ sử dụng lại sau.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Trở lại trang đầu của MetaMask. Trong tab "Assets", tìm loại token của giao dịch bị kẹt (trong trường hợp này là CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. Trong menu của token, tìm giao dịch **Pending** trong khu vực Queue. Nhấp vào giao dịch của bạn để biết thêm chi tiết.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. Tìm mục **Nonce** và ghi chú con số này.

### **3. Ghi Đè Giao Dịch Bị Kẹt**

Bây giờ chúng ta sẽ tạo một giao dịch mới để thay thế giao dịch bị kẹt. Chúng ta sẽ tùy chỉnh số Nonce, để nó giống với số bạn vừa ghi lại.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. Tạo một giao dịch mới để thay thế giao dịch bị kẹt của bạn. Lần này, tăng **Phí Giao Dịch**. Ở đây chúng tôi đã tăng từ 9 lên 20. Điều này sẽ làm cho giao dịch của bạn có nhiều khả năng được thêm vào một block hơn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. Trên trang xác nhận, đảm bảo Giá Gas của bạn bây giờ ở mức cao hơn mới.

10\. Tìm mục **CUSTOM NONCE** và thay đổi nonce thành số bạn đã ghi lại ở bước 7. Bây giờ nhấp vào Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Giao dịch mới của bạn bây giờ sẽ được chấp nhận vào một block. Để kiểm tra, mở MetaMask và nhấp vào tab **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. Giao dịch đã hoàn thành của bạn sẽ hiển thị ở đầu danh sách Activity. Nếu nó vẫn hiển thị "Pending" màu cam, bạn sẽ cần đợi thêm một chút, hoặc thử lại quy trình với phí giao dịch thậm chí cao hơn (giá gas).

Vì không có ví nào có thể tạo hai giao dịch có cùng nonce, nếu giao dịch thay thế bạn tạo thành công, giao dịch bị kẹt của bạn sẽ bị hủy.<br>
