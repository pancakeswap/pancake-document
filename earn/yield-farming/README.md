# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

Yield Farms cho phép người dùng kiếm CAKE trong khi hỗ trợ PancakeSwap bằng cách stake LP Tokens.

Xem hướng dẫn [Cách Sử dụng Farms](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) để bắt đầu farming.

Tìm hiểu [cách tìm hợp đồng thông minh Farm](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
Yield farming có thể mang lại phần thưởng tốt hơn Syrup Pools, nhưng nó đi kèm với rủi ro về **Tổn thất tạm thời**. Nghe có vẻ đáng sợ, nhưng đáng để tìm hiểu về khái niệm này trước khi bắt đầu.

Xem [bài viết tuyệt vời về Tổn thất tạm thời ](https://academy.binance.com/en/articles/impermanent-loss-explained)từ Binance Academy để tìm hiểu thêm.
{% endhint %}

## Tính toán phần thưởng

Tính toán APR Yield Farm bao gồm cả:

* **APR phần thưởng LP** kiếm được thông qua việc cung cấp thanh khoản và;
* **APR phần thưởng cơ bản Farm** kiếm được khi stake LP Tokens trong Farm.

Tại sao? Vì khi bạn stake LP token trong farm để kiếm CAKE, bạn vẫn đang cung cấp thanh khoản cho pool thanh khoản, vì vậy bạn cũng kiếm được phần thưởng LP!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

Vậy chúng tôi tính các con số đó như thế nào?

### Tính toán APR Phần thưởng Cơ bản Farm

**APR Cơ bản Farm** được tính theo số nhân farm và tổng lượng thanh khoản trong farm -- đây là lượng CAKE được phân phối cho farm.

### Tính toán APR Phần thưởng LP

Ngoài ra, các farmer nhận **phần thưởng LP** để cung cấp thanh khoản. Đây là ví dụ tính toán **phần thưởng LP**:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

Trong cặp WBNB/BUSD ở trên, chúng ta thấy các giá trị này:

**Thanh khoản:** $387,42M\
**Khối lượng 24H:** $96,97M\
**Khối lượng 7D:** 709,73M

* Tính phí hàng năm
  * Sử dụng khối lượng 24H để tính **cổ phần phí** của các nhà cung cấp thanh khoản trong pool (dựa trên cơ cấu phí giao dịch 0,17%):\
    $96.970.000 × 0,17/100 = **$164.849**
  * Tiếp theo, sử dụng **cổ phần phí** đó để ước tính **phí hàng năm dự kiến** kiếm được bởi pool (dựa trên khối lượng 24h hiện tại):\
    $164.849 × 365 = **$60.169.885**
* Bây giờ chúng ta có thể sử dụng phí hàng năm để tính **APR phần thưởng LP:** Đó là **phí hàng năm** chia cho **thanh khoản:**\
  ($60.169.885/$387.420.000) × 100 = **15,53% APR phần thưởng LP**
