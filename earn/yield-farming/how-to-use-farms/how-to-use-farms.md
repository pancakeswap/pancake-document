---
description: Yield Farming trên PancakeSwap rất dễ dàng!
---

# Cách Sử dụng Farms (Kế thừa)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-header.png)

Yield Farming trong Farms là cách tuyệt vời để kiếm phần thưởng CAKE trên PancakeSwap.

Không giống như Syrup Pools, Farms yêu cầu bạn stake **hai token** để cung cấp thanh khoản và nhận NFT vị thế thanh khoản hoặc LP Tokens, sau đó bạn stake trong Farm để kiếm phần thưởng. Điều này cho phép bạn kiếm CAKE trong khi vẫn giữ vị thế trong các token khác!

{% hint style="warning" %}
Yield farming có thể mang lại phần thưởng tốt hơn Syrup Pools, nhưng nó đi kèm với rủi ro về **Tổn thất tạm thời**. Nghe có vẻ đáng sợ, nhưng đáng để tìm hiểu về khái niệm này trước khi bắt đầu.

Xem [bài viết tuyệt vời về Tổn thất tạm thời ](https://academy.binance.com/en/articles/impermanent-loss-explained)từ Binance Academy để tìm hiểu thêm.
{% endhint %}

## Farm V3

### **Chuẩn bị**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2832%29.png)

Bạn cần có vị thế thanh khoản để tham gia vào Farm. Farms chỉ có thể chấp nhận các vị thế thanh khoản từ cặp giao dịch chính xác với mức phí đã chọn; ví dụ, Farm CAKE-BNB 0,25% chỉ chấp nhận các vị thế thanh khoản CAKE-BNB với mức phí 0,25% được chọn. Nó sẽ không chấp nhận:

* Các cặp khác, như CAKE-BUSD
* Cùng cặp nhưng với các mức phí khác: như CAKE-BNB với mức phí 0,05%

Để tạo vị thế LP chính xác, bạn cần cung cấp thanh khoản cho cặp giao dịch đó với mức phí chính xác được chọn. Vì vậy để có được vị thế LP CAKE-BNB 0,25%, trước tiên bạn phải cung cấp thanh khoản cho cặp CAKE-BNB với mức phí 0,25%.

Nghe có vẻ đáng sợ, nhưng không quá phức tạp. Hãy đi qua từng bước.

### **Tìm Farm của bạn**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28239%29.png)

Trước khi tiến hành, bạn sẽ muốn chọn Farm phù hợp với mình. [Truy cập trang Farms](https://pancakeswap.finance/farms) để xem danh sách các Farms có sẵn.

Bạn có thể chọn tùy chọn sắp xếp khác, chẳng hạn theo APR, cho Farms với tỷ lệ phần thưởng cao nhất hiện tại. Lưu ý rằng APR được tính toàn cầu cho các vị thế riêng lẻ; có thể thay đổi tùy thuộc vào cài đặt phạm vi giá của họ.

Khi bạn tìm thấy Farm muốn sử dụng, ghi lại cặp giao dịch và mức phí của nó, ví dụ: BNB-CAKE và 0,25%, trong trường hợp bạn cần sau này.

### **Cung cấp thanh khoản để tạo vị thế**

Khi bạn đã tìm thấy Farm để stake, bạn cần cung cấp thanh khoản:

1 - Nếu bạn không có bất kỳ vị thế nào, bạn sẽ thấy nút "Add Liquidity", chỉ cần nhấp vào để mở cửa sổ "Add Liquidity" mà không rời khỏi trang Farm.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2840%29.png)

2 - Ngoài ra, bạn có thể nhấp vào hàng Farm bạn đã chọn từ danh sách. Nó sẽ mở để hiển thị thêm chi tiết. Hoặc với chế độ xem thẻ, nhấp "Details" để mở rộng chi tiết. Nhấp đường dẫn "Add XXX-YYY LP" trong phần chi tiết để thêm thanh khoản.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28242%29.png)

### **Stake vị thế vào farm**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28124%29.png)

Sau khi hoàn thành việc thêm thanh khoản. Bạn sẽ thấy vị thế của mình được liệt kê dưới farm bạn muốn sử dụng.

Nếu bạn có nhiều vị thế, bạn có thể nhấp "View All" để xem chúng trong cửa sổ pop-up mới.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28198%29.png) ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28151%29.png)

Nhấp "Stake" trên vị thế được liệt kê và ví của bạn sẽ yêu cầu xác nhận.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28229%29.png)

Sau một khoảng chờ ngắn, cửa sổ sẽ đóng lại và bạn sẽ thấy vị thế đã stake trong chi tiết.

Bạn có thể lặp lại các bước trên để nhanh chóng stake nhiều vị thế với các cấu hình phạm vi giá khác nhau. Mỗi vị thế sẽ kiếm CAKE và cần được thu hoạch riêng lẻ.

### **Thu hoạch phần thưởng farming**

Trong Farm V3, bạn có thể stake nhiều vị thế trong cùng một farm. Mỗi vị thế đã stake sẽ kiếm CAKE và cần được thu hoạch riêng lẻ.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28230%29.png)

Để thu hoạch phần thưởng CAKE từ vị thế đã stake, chỉ cần quay lại trang Farm và xác định farm và vị thế bạn muốn thu hoạch. Bạn có thể sử dụng nút chuyển "Staked Only" để lọc nhanh các farms bạn đang staking.

Nếu bạn có nhiều vị thế đã stake, bạn có thể nhấp "View All" để xem chúng trong cửa sổ pop-up mới.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28241%29.png)

Nhấp "Harvest" trên vị thế và ví của bạn sẽ yêu cầu xác nhận. Sau một khoảng chờ ngắn, phần thưởng CAKE sẽ được gửi đến ví của bạn.

### **Thêm hoặc xóa thanh khoản trong khi đang stake trong farm**

Khi đang stake trong farm, bạn vẫn có thể thêm hoặc xóa thanh khoản mà không cần unstake khỏi farm.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28230%29.png)

Để làm vậy, chỉ cần quay lại trang Farm và xác định farm và vị thế bạn muốn điều chỉnh. Bạn có thể sử dụng nút chuyển "Staked Only" để lọc nhanh các farms bạn đang staking.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28267%29.png)

Nhấp vào tiêu đề vị thế với cặp token, mức phí, ID vị thế và mũi tên ">". Bạn sẽ được đưa đến trang chi tiết vị thế.

Chỉ cần sử dụng nút "Add" hoặc "Remove" để điều chỉnh thanh khoản trong vị thế đã stake.

Lưu ý rằng tất cả phần thưởng CAKE chưa nhận sẽ được thu hoạch và gửi đến ví của bạn khi điều chỉnh vị thế.

### **Unstake vị thế khỏi farm**

Bạn có thể unstake vị thế bất kỳ lúc nào.

Để unstake, chỉ cần quay lại trang Farm và xác định farm và vị thế bạn muốn unstake. Bạn có thể sử dụng nút chuyển "Staked Only" để lọc nhanh các farms bạn đang staking.

Nếu bạn có nhiều vị thế đã stake, bạn có thể nhấp "View All" để xem chúng trong cửa sổ pop-up mới.

Nhấp "Unstake" trên vị thế và ví của bạn sẽ yêu cầu xác nhận. Sau một khoảng chờ ngắn, NFT vị thế của bạn sẽ được trả lại vào ví, cùng với tất cả phần thưởng CAKE đang chờ xử lý.

## Farm V2

### Chuẩn bị

Yield farming cần một chút công việc để thiết lập.

Bạn cần có một số "LP Tokens" để tham gia vào Farm. Farms chỉ có thể chấp nhận LP Token chính xác của riêng chúng; ví dụ, Farm CAKE-BNB chỉ chấp nhận CAKE-BNB LP Tokens.

Để có được LP Token chính xác, bạn cần cung cấp thanh khoản cho cặp giao dịch đó. Vì vậy để có được CAKE-BNB LP Tokens, trước tiên bạn phải cung cấp thanh khoản cho cặp CAKE-BNB.

Nghe có vẻ đáng sợ, nhưng không quá phức tạp. Hãy đi qua từng bước.

### Tìm Farm của bạn

Trước khi tiến hành, bạn sẽ muốn chọn Farm phù hợp với mình. [Truy cập trang Farms](https://pancakeswap.finance/farms) và bạn sẽ thấy danh sách các Farms có sẵn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2862%29.png)

Bạn có thể chọn tùy chọn sắp xếp khác nếu thích, chẳng hạn theo **APR** cho Farms với tỷ lệ phần thưởng cao nhất hiện tại.

Khi bạn tìm thấy Farm muốn sử dụng, ghi lại cặp giao dịch, ví dụ: BNB-CAKE trong trường hợp bạn cần sau này.

### Cung cấp thanh khoản để nhận LP Tokens

Khi bạn đã tìm thấy Farm để stake, bạn cần thêm thanh khoản để có LP Tokens.

1. Nhấp vào hàng Farm bạn đã chọn từ danh sách. Nó sẽ mở để hiển thị thêm chi tiết.
2. Ở bên trái, bạn sẽ thấy một số đường dẫn. Nhấp đường dẫn **Get (your pair) LP**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28131%29.png)

### Đưa LP Tokens vào farm

Bây giờ bạn đã có LP Tokens, bạn đã sẵn sàng để bắt đầu stake chúng trong Farm và kiếm phần thưởng!

1 - Quay lại [trang Farms](https://pancakeswap.finance/farms) và xác định Farm của bạn. Nhấp vào bất kỳ đâu trên hàng hiển thị cặp của bạn. Nó sẽ mở rộng để hiển thị thêm chi tiết.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28244%29.png)

Khi bạn đã sẵn sàng, nhấp nút **Enable** và xác nhận hành động trong ví của bạn.

2 - Sau một khoảng chờ ngắn, nút Enable sẽ chuyển thành **Stake LP**. Nhấp vào và một cửa sổ mới sẽ xuất hiện.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28171%29.png)

3 - Nhập số lượng LP Tokens bạn muốn farm vào trường, hoặc chỉ cần nhấp **Max** để sử dụng tất cả LP Tokens của bạn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28109%29.png)

4 - Khi bạn đã nhập số lượng, nút **Confirm** sẽ sáng lên. Nhấp vào. Ví của bạn sẽ yêu cầu xác nhận hành động.

5 - Sau một khoảng chờ ngắn, cửa sổ sẽ đóng lại và bạn sẽ thấy số dư LP Token đã stake mới trong phần chi tiết.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28261%29.png)

{% hint style="info" %}
Khi bạn đang thực hiện farming xuyên chuỗi trên blockchain EVM khác ngoài BNB chain. Bạn sẽ cần đợi khoảng 30 phút để các giao dịch cross-chain được xác nhận.

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/crosschain-farm-wait.png" alt="" data-size="original">

Để theo dõi tiến trình giao dịch farming xuyên chuỗi. Nhấp biểu tượng tròn bên cạnh số dư đã stake hoặc kiểm tra phần "Recent Transaction" ở góc trên bên phải.
{% endhint %}

{% hint style="warning" %}
Khi bạn đang thực hiện farming xuyên chuỗi trên blockchain EVM khác ngoài BNB chain lần đầu tiên. Một lượng nhỏ token gốc (ví dụ: ETH cho Ethereum) là cần thiết cho lần thiết lập đầu tiên. Vì vậy giao dịch đầu tiên sẽ tốn kém hơn một chút.
{% endhint %}

### Thêm hoặc xóa LP Tokens khỏi Farm

Bạn có thể quyết định muốn thêm nhiều LP Tokens vào Farm sau đó, hoặc lấy một số ra khỏi Farm. Bạn có thể làm điều này rất dễ dàng bất cứ lúc nào.

1. Quay lại [trang Yield Farms](https://pancakeswap.finance/farms). Ở đầu trang bạn sẽ thấy nút chuyển **Staked only**. Nhấp vào nút chuyển.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28240%29.png)

Bây giờ bạn chỉ nên thấy các cặp bạn có LP Tokens trong danh sách, giúp dễ dàng tìm Farm của bạn hơn.

1. Tìm Farm bạn có LP Tokens và nhấp vào hàng để xem chi tiết. Bạn sẽ thấy nút **-** và **+** ở bên phải. Nhấp **-** để xóa LP Tokens hoặc **+** để thêm nhiều LP Tokens hơn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28102%29.png)

1. Một cửa sổ sẽ mở trông giống như cái bạn đã sử dụng trước đó để lần đầu stake LP Tokens. Như lần trước, nhập số lượng bạn muốn unstake/stake hoặc nhấp **Max** để xóa/thêm tất cả LP Tokens có sẵn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2879%29.png)

1. Hãy chắc chắn thông tin của bạn chính xác. Khi bạn đã sẵn sàng, nhấp nút **Confirm** và xác nhận hành động trong ví của bạn.
2. Sau một khoảng chờ ngắn, số dư mới của bạn sẽ được hiển thị trong phần chi tiết của cặp LP Token. Nếu bạn đã unstake LP Tokens, bất kỳ phần thưởng chưa thu hoạch nào cũng sẽ được tự động thu thập.

### Thu thập phần thưởng farming của bạn

Farming sẽ mang lại phần thưởng CAKE theo thời gian. Bạn có thể thu thập những phần thưởng này và sử dụng chúng để có thêm LP Tokens, stake trong Syrup Pools, sử dụng để chơi Xổ số hoặc bất cứ thứ gì bạn muốn.

### Quay lại Farm để Thu hoạch

Bạn có thể thu hoạch phần thưởng Farm và Syrup Pool của mình cùng nhau từ trang Chủ. Nếu bạn muốn chỉ thu thập phần thưởng farming, hãy làm theo hướng dẫn.

Để thu thập phần thưởng, bạn cần truy cập Farm đã chọn và thu thập CAKE đang chờ bạn.

1 - Quay lại trang Farms [tại đây](https://pancakeswap.finance/farms).

2 - Tìm Farm bạn đã stake LP Tokens và nhấp vào hàng để xem chi tiết. Bạn sẽ thấy ước tính phần thưởng trong "CAKE earned".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28181%29.png)

3 - Nhấp nút **Harvest** và xác nhận hành động trong ví của bạn. Sau một khoảng chờ ngắn, CAKE sẽ được nhận vào ví của bạn để sử dụng theo ý muốn.

{% hint style="info" %}
Khi bạn đang thực hiện farming xuyên chuỗi trên blockchain EVM khác ngoài BNB chain. Bạn sẽ luôn cần chuyển sang BNB Smart Chain để thu hoạch phần thưởng farming.

Nếu ví của bạn không hỗ trợ chuyển đổi chuỗi. Staking hoặc unstaking LP tokens sẽ luôn thu hoạch CAKE của bạn. Lưu ý rằng CAKE đã thu hoạch sẽ được phân phối trên BNB Smart Chain.

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28164%29.png" alt="" data-size="original">
{% endhint %}

## Tôi nên thu hoạch phần thưởng bao lâu một lần?

Tần suất thu hoạch phần thưởng là tùy bạn, nhưng hãy nhớ rằng có một khoản phí nhỏ khi thu hoạch.

Bạn có thể thấy khoản phí này trong ví của mình khi xác nhận sau khi nhấp **Harvest**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28281%29.png)

Điều này cho thấy phí thu hoạch khi xuất hiện trong ví MetaMask. Các ví khác nhau sẽ hiển thị thông tin hơi khác nhau. Hãy cân nhắc để phần thưởng của bạn tăng lên một thời gian để bạn trả phí ít thường xuyên hơn.

Và đó là tất cả những gì cần làm! Bạn cũng có thể muốn xem [cách sử dụng PancakeSwap Syrup Pools](https://docs.pancakeswap.finance/get-started/syrup-pool-guide) để kiếm phần thưởng.

Chúc farming vui vẻ!
