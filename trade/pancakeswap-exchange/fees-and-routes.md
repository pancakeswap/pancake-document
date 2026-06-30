# Phí và Lộ Trình

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

Trong Exchange V3, theo mặc định, PancakeSwap Smart Router sẽ sử dụng thanh khoản từ V3, V2, StableSwap (BNB Chain), và AMM cùng các nhà tạo lập thị trường (BNB Chain & Ethereum) để thực hiện giao dịch và tìm giá tốt nhất cho trader.

Tuy nhiên, người dùng luôn có thể tùy chỉnh giao dịch của mình bằng cách chọn nguồn thanh khoản mà router sẽ sử dụng, và bật hoặc tắt multihops và split routing.

### **Kiểm tra mức phí và số tiền phí đang áp dụng**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

Để kiểm tra phí giao dịch sẽ bị tính cho hoán đổi hiện tại của bạn, hãy xem phần "Phí" trong phần chi tiết hoán đổi.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

Để kiểm tra loại pool và bậc phí mà giao dịch của bạn đang được định tuyến qua, hãy xem phần "Lộ Trình".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

Để tìm hiểu thêm chi tiết, nhấp vào biểu tượng kính lúp để mở màn hình hiển thị toàn bộ lộ trình giao dịch.



### **Tùy chỉnh nguồn thanh khoản**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

Ở đầu giao diện "Tùy Chỉnh Định Tuyến", bạn có thể chọn nguồn thanh khoản mà router sẽ sử dụng khi định tuyến giao dịch. Để mở giao diện này, bạn có thể:

* Nhấp "Tùy Chỉnh Định Tuyến" ở cuối màn hình hiển thị lộ trình giao dịch.
* Nhấp biểu tượng bánh răng trong giao diện hoán đổi, rồi nhấp "Tùy Chỉnh Định Tuyến" ở cuối.

Theo mặc định, tất cả nguồn thanh khoản đều được bật và Smart Router sẽ tận dụng đầy đủ tất cả thanh khoản có sẵn trong PancakeSwap.

Lưu ý rằng router sẽ KHÔNG định tuyến giao dịch giữa các pool thanh khoản AMM và nhà tạo lập thị trường MM. Khi giao dịch của bạn được thực hiện bởi nhà tạo lập thị trường MM, nó sẽ không đi qua bất kỳ pool thanh khoản AMM nào.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

Bạn có thể nhấp nút "Đặt Lại" ở góc trên bên phải để khôi phục cấu hình về mặc định.



### **Tùy chỉnh tùy chọn định tuyến**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

Ở cuối giao diện "Tùy Chỉnh Định Tuyến", bạn có thể tùy chỉnh tùy chọn định tuyến bằng cách bật hoặc tắt multihops và split routing.

Multihops cho phép token hoán đổi qua nhiều bước giữa nhiều pool thanh khoản để đạt được giao dịch tốt nhất. Tắt tính năng này sẽ giới hạn giao dịch chỉ hoán đổi trực tiếp, có thể gây ra trượt giá cao hơn hoặc thậm chí mất tiền.

Split routing cho phép hoán đổi token được chia thành nhiều lộ trình để đạt được giao dịch tốt nhất. Tắt tính năng này sẽ hạn chế giao dịch chỉ được thực hiện qua một lộ trình duy nhất, có thể dẫn đến hiệu quả thấp hơn hoặc trượt giá cao hơn.

{% hint style="warning" %}
Khi giao dịch của bạn không thể thực hiện do cấu hình giao dịch tùy chỉnh, một cảnh báo sẽ xuất hiện, bạn có thể nhấp "Kiểm tra cài đặt" để nhanh chóng mở giao diện "Tùy Chỉnh Định Tuyến". Hoặc chọn "Đặt lại về mặc định" để nhanh chóng khôi phục cấu hình về mặc định.
{% endhint %}
