---
description: veCAKE Staking và Phân bổ IFO
hidden: true
---

# iCAKE

### **iCAKE mới là gì?**

Sau khi chuyển đổi sang veCAKE, iCAKE mới sẽ dựa trên số dư veCAKE

* Giống như iCAKE cũ, nó xác định giới hạn commit CAKE tối đa trong PancakeSwap IFO public sales. Ví dụ, nếu bạn có 200 iCAKE, bạn có thể commit 200 CAKE trong IFO public sales.
* Số iCAKE mới được tính sử dụng số dư veCAKE tại cuối mỗi IFO. Do đó, bạn sẽ có số iCAKE khác nhau cho mỗi IFO.
* Vì số dư veCAKE giảm dần theo thời gian khóa còn lại, iCAKE của bạn trong các IFO tương lai sẽ giảm cùng với số dư veCAKE. Để duy trì số iCAKE, hãy thêm CAKE vào staking hoặc gia hạn/kéo dài thời gian khóa của bạn.

**iCAKE KHÔNG phải là token mới, nó là một chỉ số số học được sử dụng bởi hệ thống PancakeSwap IFO.**

### iCAKE được tính như thế nào?

Số iCAKE bạn có dựa trên số dư veCAKE tại cuối mỗi IFO, nhân với một tỷ lệ được xác định trước.

veCAKE là giá trị được tính động dựa trên lượng CAKE bạn khóa và thời gian còn lại trong thời gian khóa. Để tìm hiểu thêm về cách tính veCAKE, hãy xem [tại đây](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef).

Một tỷ lệ bổ sung được áp dụng trên số dư veCAKE, được Kitchen điều chỉnh cho mỗi IFO. Ví dụ, nếu tỷ lệ là 2x, và bạn có 1 veCAKE tại cuối IFO tiếp theo, bạn có thể commit tối đa 2 CAKE.

Ví dụ:

* Bạn khóa 100 CAKE trong 2 năm.
  * Thời gian khóa còn lại của bạn là: `2 * 52 * 7 * 24 * 60 * 60 = 62899200`  (giây)
  * Thời gian khóa tối đa là: `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (giây)
  * Tại thời điểm hiện tại, bạn có: `100 * (62899200 / 126403199) ~= 49.76` veCAKE
* IFO tiếp theo được lên lịch; thời gian kết thúc của nó là chính xác 1 tuần sau, tức là `604800` giây sau thời điểm hiện tại.
  * Tại thời điểm đó, thời gian khóa còn lại của bạn là: `62899200 - 604800 = 62294400` (giây)
  * Tại thời điểm đó, bạn có: `100 * (62294400 / 126403199) ~= 49.28` veCAKE
* Đối với IFO này, tỷ lệ được đặt là `3x`
* Do đó, đối với IFO này, bạn có: `49.28 * 3 = 147.84` iCAKE, có nghĩa là bạn có thể commit tối đa 147.84 CAKE trong đợt bán công khai.

### Cách kiểm tra số iCAKE tôi có?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

Bạn có thể kiểm tra số iCAKE của mình trên trang IFO [tại đây](https://pancakeswap.finance/ifo).

Lưu ý rằng khi không có IFO sắp tới, iCAKE của bạn sẽ được tính sử dụng số dư veCAKE theo thời gian thực, giảm dần từng giây.

Khi có IFO sắp tới, iCAKE của bạn sẽ được tính sử dụng số dư veCAKE tại thời điểm snapshot, tức là cuối IFO. iCAKE của bạn sẽ không giảm hoặc thay đổi cho đến khi IFO kết thúc.

### **Làm thế nào để tăng số iCAKE tôi có?**

Bạn có thể tăng số iCAKE bất cứ lúc nào bằng cách:

* Thêm CAKE vào vị trí staking veCAKE của bạn.
* Gia hạn vị trí staking veCAKE của bạn.

trên [Trang CAKE Staking](https://pancakeswap.finance/cake-staking)

### "Tỷ lệ" trong tính toán iCAKE là gì?

Tỷ lệ là yếu tố kiểm soát bổ sung được áp dụng trên số dư veCAKE khi tính iCAKE.

Ví dụ, nếu tỷ lệ là 2x, và bạn có 1 veCAKE tại cuối IFO tiếp theo, bạn có thể commit tối đa 2 CAKE.

Giữa mỗi IFO, Kitchen sẽ tối ưu hóa "Tỷ lệ" dựa trên các chỉ số khác nhau. Việc điều chỉnh sẽ được công bố trên tất cả các kênh mạng xã hội.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

Bạn có thể kiểm tra số "Tỷ lệ" hiện tại cho việc tính iCAKE bằng cách vào [trang IFO](https://pancakeswap.finance/ifo).
