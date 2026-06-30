---
hidden: true
---

# Cách Sử Dụng Lệnh Giới Hạn

## Lệnh Giới Hạn là gì

Lệnh giới hạn là công cụ cho phép người dùng mua hoặc bán tài sản ở một mức giá cụ thể hoặc tốt hơn, thay vì phụ thuộc vào giá thị trường tại thời điểm thực thi. Trong lệnh giới hạn, mặc dù giá được đảm bảo nhưng việc thực thi lệnh không được đảm bảo — lệnh giới hạn chỉ được thực thi nếu giá đáp ứng điều kiện của lệnh.

## Cách đặt lệnh giới hạn

1. Đến trang Swap và chọn tùy chọn lệnh giới hạn bằng cách nhấp vào "LIMIT", hoặc sử dụng liên kết này: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. Chọn token "Từ" và "Đến" bạn muốn giao dịch. Trong ví dụ này, chúng tôi chọn USDC và ETH tương ứng, nghĩa là chúng tôi muốn mua ETH bằng USDC.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. Nhập số lượng bạn muốn giao dịch. Lưu ý rằng giá giới hạn sẽ hiển thị giá thị trường hiện tại và từ đó ước tính số lượng token đích đầu ra (ETH)
2. Đặt giá giới hạn mong muốn. Giao dịch SẼ CHỈ được thực thi khi giá thị trường hiện có bằng hoặc tốt hơn giá giới hạn. Số lượng token đích đầu ra sẽ được cập nhật tương ứng.

Trong ví dụ dưới đây, chúng tôi muốn mua ETH khi giá là $1.900 hoặc tốt hơn. Số lượng ETH nhận được sẽ bằng hoặc lớn hơn 0.037 ETH. Chỉ các giá thầu bằng hoặc tốt hơn số lượng này mới đủ điều kiện để khớp lệnh. Số lượng này đã tính đến chi phí gas và phí.&#x20;

{% hint style="info" %}
Lưu ý quan trọng: Vì phí được thanh toán từ số lượng token đầu ra, nên giá giới hạn đã bao gồm phí gas và phí giao dịch, vì vậy người dùng nên tính đến điều này khi đặt giá. Ví dụ, phí gas của một lệnh rất nhỏ có thể chiếm tỷ lệ rất lớn trên tổng đầu ra của lệnh, phản ánh giá giới hạn thực tế không cạnh tranh với giá thị trường giao ngay.
{% endhint %}

3.  Nhấn "Place order". Kiểm tra lại chi tiết lệnh, chấp nhận tuyên bố từ chối trách nhiệm và nhấn "Confirm order".

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. Sau khi giao dịch hoàn tất, bạn sẽ thấy lệnh trong phần lịch sử lệnh, dưới "Open orders". \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. Các lệnh đang mở có thể được hủy bất cứ lúc nào bằng cách mở rộng lệnh và nhấp vào nút "Cancel Order".

Những điều cần xem xét:

* Lệnh của bạn có thể không được thực thi nếu giá thị trường hiện có kém hơn giá giới hạn bạn đã đặt.
* Các giao dịch dựa trên một giao thức phi tập trung sử dụng các taker ngoài chuỗi cạnh tranh để khớp lệnh. Các taker này có quyền yêu cầu phí, giao thức sẽ trừ phí cho taker thắng từ token đầu ra.&#x20;
* Các taker có thể tính đến phí gas cho giao dịch của bạn khi đặt phí của họ, điều này có thể dẫn đến biến động trong số tiền phí.
* Khi chỉ định giá giới hạn, người dùng sẽ thấy trong giao diện số lượng token đích tối thiểu họ sẽ nhận được nếu lệnh được khớp. Chỉ các taker đưa ra giá thầu bằng hoặc tốt hơn số lượng này mới đủ điều kiện để khớp lệnh. Số lượng này đã tính đến chi phí gas và phí giao dịch.
