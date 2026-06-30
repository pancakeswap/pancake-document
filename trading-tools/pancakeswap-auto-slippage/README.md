# 🎯 PancakeSwap Auto Slippage

PancakeSwap đã giới thiệu Auto Slippage để giúp việc giao dịch dễ dàng và hiệu quả hơn. Auto Slippage tự động điều chỉnh trượt giá cho bạn dựa trên điều kiện thị trường hiện tại, giúp ngăn chặn các giao dịch thất bại và giảm rủi ro mất tiền do lỗi trượt giá.

## Trượt giá là gì?

**Trượt giá** xảy ra khi giá bạn kỳ vọng cho một giao dịch khác với giá mà giao dịch thực sự được hoàn thành. Điều này có thể xảy ra vì một số lý do:

* Biến động thị trường – Giá có thể thay đổi nhanh chóng giữa thời điểm bạn đặt lệnh và xác nhận
* Thanh khoản thấp – Không có đủ token ở mức giá bạn kỳ vọng
* Độ trễ blockchain – Thời gian xác nhận có thể khiến giá thay đổi trước khi giao dịch được hoàn tất

{% hint style="info" %}
Ví dụ:

Bạn cố gắng hoán đổi 100 CAKE lấy BNB, kỳ vọng 1 CAKE = 0.01 BNB. Nhưng đến khi giao dịch của bạn được thực hiện, giá đã thay đổi và bạn chỉ nhận được 0.0098 BNB cho mỗi CAKE. Sự chênh lệch nhỏ này chính là trượt giá.
{% endhint %}

## Dung sai Trượt giá là gì?

**Dung sai trượt giá** là mức chênh lệch giá tối đa bạn sẵn sàng chấp nhận trước khi giao dịch của bạn bị hủy. Nếu giá biến động vượt quá mức dung sai đã đặt, giao dịch của bạn sẽ thất bại để ngăn chặn các tổn thất không mong muốn.

{% hint style="info" %}
Ví dụ:

Nếu bạn đặt dung sai trượt giá là 1% và giá thay đổi hơn 1% trước khi giao dịch hoàn tất, giao dịch sẽ không được thực hiện.
{% endhint %}

## Điều gì xảy ra nếu Dung sai Trượt giá của tôi quá thấp?

Nếu dung sai trượt giá **đặt quá thấp**, có nhiều khả năng giao dịch của bạn sẽ thất bại — đặc biệt khi:

* Thị trường biến động mạnh
* Bạn đang hoán đổi token có thanh khoản thấp
* Sử dụng token có thuế hoặc cơ chế phức tạp

{% hint style="warning" %}
Quan trọng: Ngay cả khi giao dịch thất bại, bạn vẫn sẽ tiêu tốn phí gas cho lần thử đó.
{% endhint %}

## Giới thiệu Auto Slippage - Tại sao Auto Slippage hữu ích?

Auto Slippage tự động điều chỉnh trượt giá của bạn dựa trên điều kiện thị trường hiện tại, giúp bạn tiết kiệm thời gian và giảm nguy cơ giao dịch thất bại.&#x20;

Với **Auto Slippage**, không cần phải điều chỉnh dung sai trượt giá thủ công. Điều này giúp ngăn chặn các vấn đề phổ biến như:

* **Đặt trượt giá quá thấp**, có thể khiến giao dịch thất bại do thay đổi giá nhỏ trong quá trình thực thi.
* **Đặt trượt giá quá cao**, có thể dẫn đến việc nhận được ít token hơn dự kiến do chấp nhận phạm vi giá rộng hơn.

{% hint style="info" %}
Để đảm bảo trải nghiệm giao dịch tốt nhất, auto slippage đã được **bật tự động**. Nếu đã đặt dung sai trượt giá thủ công, cài đặt trượt giá mới sẽ được áp dụng.
{% endhint %}



## Auto Slippage hoạt động như thế nào?

<pre class="language-html"><code class="lang-html"><strong>Auto Slippage (%) = (Chi phí Gas tính bằng USD / Giá trị Token Đầu ra tính bằng USD) * 100%
</strong></code></pre>

* Nếu chi phí gas cao so với giá trị token đầu ra, Auto Slippage sẽ đặt mức trượt giá cao hơn để đảm bảo giao dịch được thực hiện.
* Nếu gas rẻ và giá trị token đầu ra lớn, mức trượt giá nhỏ hơn sẽ được sử dụng.

Auto Slippage sẽ chọn giá trị trong khoảng từ **0.5%** đến **5.0%**, tùy thuộc vào điều kiện token và mạng lưới.



## Auto Slippage có khả dụng trên tất cả các mạng không?

Không — Auto Slippage chỉ được hỗ trợ trên các chuỗi Layer 1 (L1) như BNB Chain, Ethereum, v.v.

Nó không được hỗ trợ trên các chuỗi Layer 2 (L2), vì:

* Công thức auto slippage dựa trên các giá trị chi phí gas có ý nghĩa để tính toán cài đặt trượt giá hữu ích
* Vì phí gas L2 rất thấp, việc áp dụng auto slippage trên L2 sẽ không cải thiện tỷ lệ thành công của giao dịch

{% hint style="success" %}
 Nếu Auto Slippage **không được hỗ trợ** trên một mạng:

* Cài đặt trượt giá đã sử dụng trước đó của bạn sẽ được áp dụng
* Nếu bạn chưa đặt trước đó, giá trị mặc định sẽ là 0.5%
{% endhint %}


