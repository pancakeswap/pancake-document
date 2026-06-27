# 🌊 Nhóm thanh khoản

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#id-03e94594-5a75-4687-b260-0dc69574b953" id="id-03e94594-5a75-4687-b260-0dc69574b953"></a>

Trong Exchange V3 mới, thanh khoản sẽ được quản lý dưới dạng các vị thế không thể thay thế (non-fungible). Bạn vẫn sẽ kiếm được một phần phí khi cung cấp thanh khoản.

Khi bạn thêm token vào Nhóm thanh khoản, bạn sẽ nhận được token NFT Liquidity Provider và chia sẻ phí.

### **Các vị thế thanh khoản không thể thay thế (non-fungible)**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28238%29.png" alt=""><figcaption></figcaption></figure>

Trong V3, các nhà cung cấp thanh khoản giờ đây có nhiều quyền kiểm soát hơn về phạm vi giá mà họ muốn triển khai thanh khoản. Vì vậy, khi bạn thêm token vào Nhóm thanh khoản trong V3, bạn sẽ tạo ra một vị thế thanh khoản non-fungible mới với các cài đặt riêng biệt.

Do đó, trong V3, các vị thế thanh khoản là NFT. Lưu ý rằng các NFT này có thể chuyển nhượng và chúng đại diện cho quyền sở hữu các tài sản cơ bản và phí giao dịch mà chúng kiếm được.

Trong V3, phí giao dịch sẽ không còn được tự động gộp lãi trong vị thế. Bạn có thể tự nhận chúng trên từng trang chi tiết vị thế.

Bạn có thể rút tiền bất kỳ lúc nào bằng cách xóa thanh khoản.

### **Thanh khoản đang hoạt động và phạm vi giá**

Trong V3, các nhà cung cấp thanh khoản có thể cấu hình vị thế của họ để chỉ cung cấp thanh khoản khi giá nằm trong một phạm vi nhất định. Nếu giá giao dịch vượt ra ngoài phạm vi, vị thế sẽ chỉ bao gồm một loại token trong cặp và trở nên không hoạt động.

Các vị thế thanh khoản không hoạt động sẽ không tham gia giao dịch hoặc kiếm bất kỳ phí giao dịch nào.

### **Thanh khoản tập trung**

Trong V3, vì các nhà cung cấp thanh khoản có thể tập trung tiền gửi token để chỉ cung cấp thanh khoản trong một phạm vi giá cụ thể. Với cùng lượng tài sản cơ bản, V3 có thể hỗ trợ giao dịch lớn hơn nhiều.

Điều này dẫn đến mức thanh khoản tương đối cao hơn nhiều khi so sánh với V2. Và các nhà cung cấp thanh khoản có thể kiếm được nhiều phí giao dịch hơn với cùng lượng vốn.

Đây là một ví dụ:

> Baller và Claire đều cung cấp thanh khoản trong pool CAKE/USDT với tài sản token trị giá 1.000 USD. Giá hiện tại của CAKE là 5 USDT.
>
> Tương tự như PancakeSwap v2, Baller cung cấp thanh khoản trên toàn bộ phạm vi giá. Do đó anh ấy đã nạp toàn bộ vốn, 500 USDT và 100 CAKE.
>
> Claire sử dụng tính năng thanh khoản tập trung mới trong PancakeSwap v3 và tạo vị thế với phạm vi giá từ 2 đến 12,5 USDT mỗi CAKE. Cô ấy nạp 185 USDT và 37 CAKE, tổng trị giá 370 đô. Cô ấy có thể chi 630 đô còn lại ở chỗ khác, chẳng hạn như khóa CAKE trong Syrup pool để hưởng lợi suất CAKE cao trong khi nhận một loạt lợi ích hệ sinh thái PancakeSwap.
>
> Miễn là CAKE nằm trong phạm vi giá từ 2 đến 12,5, cả Baller và Claire sẽ nhận được cùng lượng phần thưởng phí giao dịch trong khi Claire nạp ít vốn hơn nhiều vào pool thanh khoản.

### **Phí giao dịch**&#x20;

Cung cấp thanh khoản cho bạn phần thưởng dưới dạng phí giao dịch khi mọi người sử dụng pool thanh khoản để hoàn thành hoán đổi.

Bất cứ khi nào ai đó giao dịch trên PancakeSwap, đối với mỗi lần nhảy (hoán đổi) trong mỗi pool thanh khoản Exchange V3, tùy thuộc vào mức phí pool thanh khoản, người giao dịch trả một khoản phí dao động từ 0,01% đến 1%. Tỷ lệ phí và phân tích chi tiết phí được hiển thị như sau:

<details>

<summary>Phí giao dịch (EVM)</summary>

| Thành phần phí / Mức phí | 0.01% | 0.05% | 0.25% | 1%  |
| ------------------------ | ----- | ----- | ----- | --- |
| Liquidity Provider       | 67%   | 66%   | 68%   | 68% |
| CAKE Burn                | 15%   | 15%   | 23%   | 23% |
| Treasury                 | 18%   | 19%   | 9%    | 9%  |

Ví dụ, trong pool mức phí 0,25%:

* Trong số tất cả các vị thế thanh khoản đang hoạt động (trong phạm vi), tổng cộng có 10 CAKE và 10 BNB.
* Ai đó đổi 1 CAKE lấy 1 BNB.
* Ai đó khác đổi 1 BNB lấy 1 CAKE.
* Các nhà cung cấp thanh khoản trong phạm vi cung cấp thanh khoản đang hoạt động kiếm được tổng cộng 0,0017 CAKE và 0,0017 BNB từ các giao dịch.
* Các vị thế có phạm vi giá không bao phủ giá hiện tại, do đó không hoạt động, sẽ không đóng góp vào giao dịch hoặc kiếm bất kỳ phí nào.

</details>

<details>

<summary><strong>Phí giao dịch (Solana)</strong></summary>

**Các mức phí Pool CLMM V3 có sẵn:**\
0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%

**Lưu ý:** **Phân phối phí vẫn như nhau** trên tất cả các mức phí.

| Thành phần phí                      | % Tổng phí hoán đổi | Mô tả                                                              |
| ----------------------------------- | ------------------- | ------------------------------------------------------------------ |
| **LPs (Nhà cung cấp thanh khoản)**  | 84%                 | Kiếm bởi LP cung cấp thanh khoản trong phạm vi giá đang hoạt động |
| **Burn**                            | 8%                  | Loại bỏ vĩnh viễn để giảm nguồn cung CAKE                         |
| **Treasury**                        | 8%                  | Phân bổ cho kho bạc giao thức PancakeSwap                         |

**Ví dụ: Phân phối phí trong pool CAKE/SOL 0,25%**

1. **Thiết lập pool:** Tổng thanh khoản đang hoạt động: 10 CAKE và 10 SOL (các vị thế trong phạm vi).
2. **Các hoán đổi xảy ra:**
   * Người dùng A hoán đổi 1 CAKE → 1 SOL.
   * Người dùng B hoán đổi 1 SOL → 1 CAKE.
3. **Tổng phí thu:**
   * 0,25% mỗi giao dịch × 2 giao dịch = **0,005 CAKE + 0,005 SOL**.
4. **Phân phối phí:**
   * **84% cho LPs:** 0,0042 CAKE + 0,0042 SOL
   * **8% để Burn:** 0,0004 CAKE + 0,0004 SOL
   * **8% cho Treasury:** 0,0004 CAKE + 0,0004 SOL
5. **Thu nhập LP:**
   * Chỉ các **LP trong phạm vi** mới kiếm phí. Phí được phân phối theo tỷ lệ dựa trên cổ phần của mỗi LP.
   * **LP ngoài phạm vi** **không kiếm phí**.

</details>

### **Kiếm CAKE**

Để làm cho việc trở thành nhà cung cấp thanh khoản xứng đáng hơn, bạn cũng có thể đưa các vị thế thanh khoản vào làm việc để tạo ra lợi suất tươi trên [CAKE Farms](https://pancakeswap.finance/liquidity/pools), trong khi vẫn kiếm phần thưởng phí giao dịch.

***

## Exchange V2

### LP Tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28142%29.png" alt=""><figcaption></figcaption></figure>

Ví dụ, nếu bạn nạp **CAKE** và **BNB** vào Nhóm thanh khoản, bạn sẽ nhận được token **CAKE-BNB LP**.

Số lượng LP token bạn nhận đại diện cho phần của bạn trong Nhóm thanh khoản CAKE-BNB.

Bạn cũng có thể rút tiền bất kỳ lúc nào bằng cách xóa thanh khoản.

### **Kiếm phí giao dịch**

Bất cứ khi nào ai đó giao dịch trên PancakeSwap, đối với mỗi lần nhảy (hoán đổi) trong mỗi pool thanh khoản Exchange V2, người giao dịch trả phí cố định 0,25%, **trong đó 0,17%** được thêm trở lại vào Nhóm thanh khoản dưới dạng phí giao dịch.

### **Kiếm CAKE**

Exchange V2 cũ sẽ chạy song song với Exchange V3 mới. Vì vậy, một số cặp giao dịch sẽ vẫn ở trên PancakeSwap Exchange V2 và có Farm V2 tương ứng. Vui lòng kiểm tra các thẻ để xác định phiên bản exchange.



## Tổn thất tạm thời

Cung cấp thanh khoản không phải là không có rủi ro, vì bạn có thể bị tổn thất tạm thời.

["Nói một cách đơn giản, tổn thất tạm thời là sự chênh lệch giữa việc giữ token trong AMM và giữ chúng trong ví của bạn." - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
