# FAQ & Xử lý sự cố Syrup Pool

## Xử lý sự cố

### **Tôi không tìm thấy Syrup Pool tôi đang stake!**

Bạn sẽ có thể tìm thấy Syrup Pool trong tab "Finished" trên trang Syrup Pools.&#x20;

Bằng cách chọn "Staked Only", sẽ dễ dàng hơn để tìm tài sản của bạn.

### **Tại sao tôi không thể unstake token của mình từ Syrup Pool?**

Nếu bạn không thể unstake từ các pool Stake Cake, Earn CAKE, vui lòng kiểm tra để đảm bảo rằng bạn chưa bán token SYRUP trong ví của mình. Token này hoạt động như bằng chứng sở hữu\` đối với CAKE của bạn trong Manual CAKE pool.&#x20;

### **Tại sao token kiếm được của tôi về 0 sau khi staking/unstaking?**

Đừng lo lắng! Chúng đã có trong ví của bạn rồi.

Mỗi khi bạn stake hoặc unstake từ Syrup Pool hoặc farm, token kiếm được của bạn sẽ được thu hoạch và gửi đến ví của bạn cùng một lúc.

## **Câu hỏi chung**

### APR cho Syrup Pools được tính như thế nào?

> APR Syrup Pool = Phần thưởng hàng năm (USD) / Tiền của người dùng stake trong Syrup Pool (USD) \* 100

Làm ví dụ cơ bản, hãy lấy pool 60 ngày với 300.000 USD phần thưởng và 3.000.000 USD CAKE được stake trong đó.

APR dao động khi nhiều CAKE được người dùng stake hơn và khi giá CAKE và token phần thưởng thay đổi.

|                                                         | **Tính toán**                     | Số lượng                                      |
| ------------------------------------------------------- | --------------------------------- | --------------------------------------------- |
| Tổng phần thưởng phân phối (giá trị USD)                |                                   | 300.000 USD                                   |
| Thời gian phân phối                                     |                                   | 60 ngày                                       |
| Phân phối hàng ngày                                     | 300.000 / 60 =                    | 5.000 USD mỗi ngày                            |
| **Phần thưởng hàng năm (giá trị USD)**                  | 5.000 \* 365 =                    | **1.825.000 USD**                             |
| **Giá trị CAKE được người dùng stake trong pool (USD)** |                                   | **3.000.000 USD**                             |
| **APR**                                                 | (1.825.000 / 3.000.000) \* 100 =  | <p></p><p><strong>60,833% APR</strong></p>    |

### **Con số "End" trên Syrup Pool của tôi đề cập đến gì?**

Đây cho thấy số lượng block còn lại cho đến khi phần thưởng cho pool đó ngừng phân phối. Khi pool đạt đến block đó, bạn nên unstake token của mình, vì bạn sẽ không nhận được bất kỳ phần thưởng nào sau đó.

### **Phần thưởng từ Syrup Pools đến từ đâu?**

Có ba loại Syrup Pools chính.

1. Stake CAKE, kiếm CAKE
2. Stake CAKE, kiếm token khác.&#x20;
3. Stake token khác, kiếm CAKE

Phần thưởng cho các Syrup Pools "Stake CAKE, earn CAKE" đến từ [CAKE emissions](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). Mỗi block, một số lượng token CAKE được phân bổ như phần thưởng cho các pool này.

Phần thưởng cho loại "Stake CAKE, earn other tokens" được cung cấp bởi các nhóm dự án tài trợ cho Syrup Pool.

Đối với loại "Stake other tokens, earn CAKE", kho bạc PancakeSwap mua lại CAKE từ thị trường để phân phối như phần thưởng. Các pool này được tài trợ bởi PancakeSwap, không phải bởi các dự án.

### SYRUP Token là gì?

SYRUP Token của PancakeSwap được gửi vào ví của bạn khi bạn tương tác với **Manual** "Stake CAKE, Earn CAKE" Syrup Pool. Nó không được stake.

Về cơ bản đây là IOU cho thấy bạn đã stake bao nhiêu CAKE trong pool.

Nó sẽ được trả lại tự động khi bạn unstake CAKE từ pool đó.

{% hint style="warning" %}
Đừng bán token SYRUP của bạn! Bạn cần trả lại SYRUP để unstake CAKE từ Manual CAKE pool. Số lượng SYRUP bạn trả lại phải bằng với số lượng CAKE bạn unstake.
{% endhint %}
