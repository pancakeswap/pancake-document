---
description: Cách "gỡ kẹt" mọi giao dịch đang chờ xử lý bị kẹt trong MetaMask của bạn
---

# Khắc phục giao dịch Pending bị kẹt trên MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Nếu giao dịch của bạn bị kẹt ở trạng thái pending trong Metamask, và nút “Cancel” không giúp được, bạn có thể cần dùng phương pháp này để xóa hàng đợi tồn đọng.

Phương pháp này hoạt động bằng cách ghi đè giao dịch bị kẹt bằng một giao dịch khác có mức ưu tiên cao hơn.

### **1. Bật Nonce giao dịch tùy chỉnh**

1\. Mở tiện ích MetaMask của bạn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Nhấp vào biểu tượng hình tròn nhiều màu ở góc trên bên phải và nhấp **Settings** từ menu thả xuống.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Trong menu Settings, chọn **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Cuộn xuống cho đến khi bạn thấy **Advanced gas controls**. Bật mục này sang ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Vẫn trong phần cài đặt Advanced, tiếp tục cuộn cho đến khi bạn thấy **Customize transaction nonce**. Bật mục này sang ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Tìm giao dịch bị kẹt của bạn**

Bây giờ chúng ta sẽ tìm giao dịch bị kẹt và ghi lại “nonce”. Đó là một loại mã định danh mà chúng ta sẽ dùng lại sau.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Quay lại trang đầu của MetaMask. Trong tab “Assets”, tìm loại token của giao dịch bị kẹt (trong trường hợp này là CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. Trong menu của token, tìm giao dịch **Pending** của bạn trong khu vực Queue. Nhấp vào giao dịch để xem thêm chi tiết.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. Tìm mục **Nonce** và ghi lại con số này.

### **3. Ghi đè giao dịch bị kẹt**

Bây giờ chúng ta sẽ tạo một giao dịch mới để thay thế giao dịch bị kẹt. Chúng ta sẽ tùy chỉnh số Nonce sao cho giống với số bạn vừa ghi lại.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Tạo một giao dịch mới để thay thế giao dịch bị kẹt của bạn. Lần này, hãy tăng **Transaction Fee**. Ở đây chúng tôi đã tăng từ 9 lên 20. Điều này sẽ giúp giao dịch của bạn có nhiều khả năng được thêm vào một khối hơn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. Trên trang xác nhận, hãy đảm bảo Gas Price của bạn hiện ở mức cao hơn mới.

11\. Tìm mục **CUSTOM NONCE** và đổi nonce thành số bạn đã ghi lại ở bước 8. Bây giờ nhấp Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. Giao dịch mới của bạn bây giờ sẽ được chấp nhận vào một khối. Để kiểm tra, mở MetaMask và nhấp tab **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. Giao dịch đã hoàn tất của bạn sẽ hiển thị ở đầu danh sách Activity. Nếu vẫn hiển thị “Pending” màu cam, bạn cần chờ thêm một chút, hoặc thử lại quy trình với phí giao dịch (gas price) cao hơn nữa.

Vì không ví nào có thể tạo hai giao dịch có cùng nonce, nếu giao dịch thay thế bạn tạo thành công, giao dịch bị kẹt của bạn sẽ bị hủy.<br>
