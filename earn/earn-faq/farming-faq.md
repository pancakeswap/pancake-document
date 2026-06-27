---
hidden: true
---

# FAQ về Farming

### Tại sao có nhiều APR?

Trong V3, bạn có thể tập trung tài sản của mình khi cung cấp thanh khoản để tăng cổ phần của mình so với tổng thanh khoản có sẵn, kiếm được % phần thưởng cao hơn.&#x20;

Do đó, tùy thuộc vào cài đặt khoảng giá của vị thế, mỗi vị thế thanh khoản sẽ có APR phí LP riêng và APR farming riêng.

APR toàn cầu được tính bằng tổng số phần thưởng CAKE tính bằng USD, chia cho tổng số tài sản, trong các vị thế đang hoạt động, hiện đang được stake trong farm. Vì vậy, APR farming toàn cầu chỉ là tham chiếu chung và sẽ không đại diện cho APR riêng lẻ của từng vị thế.

Để xem APR farming của bạn, hãy kiểm tra các vị thế được liệt kê trong mỗi farm.

###

### Điều gì xảy ra nếu vị thế thanh khoản của tôi ra khỏi phạm vi khi đang stake trong Farm?

Trong V3, chỉ các vị thế thanh khoản đang hoạt động (trong phạm vi) mới kiếm được CAKE từ farms.

Vị thế sẽ ngừng nhận phần thưởng CAKE khi giá vượt ra ngoài phạm vi.

Nếu giá quay lại trong phạm vi, vị thế sẽ bắt đầu nhận phần thưởng CAKE trở lại. Không cần thêm hành động nào từ người stake.



### Có cách nào để tự động điều chỉnh vị thế của tôi để nó luôn trong phạm vi và kiếm phí không?

PancakeSwap v3 hỗ trợ nạp thanh khoản một cú nhấp chuột qua Zap, có sẵn trên BNB Chain và Ethereum.



### Có phải luôn luôn farm tốt hơn với vị thế thanh khoản có phạm vi nhỏ hơn không?

Cung cấp thanh khoản cho phạm vi giá nhỏ hơn sẽ giúp tập trung thanh khoản, tăng cổ phần tương đối của bạn so với tổng thanh khoản trong phạm vi giá, có khả năng kiếm được nhiều phần thưởng CAKE hơn.

Tuy nhiên, hãy nhớ rằng chỉ các vị thế thanh khoản đang hoạt động mới kiếm được phần thưởng CAKE. Điều này có nghĩa là bạn chỉ kiếm phần thưởng khi giá giao dịch hiện tại nằm trong phạm vi giá được xác định trong vị thế thanh khoản.

Nếu bạn cần điều chỉnh phạm vi giá của vị thế, bạn sẽ cần unstake, xóa thanh khoản và tạo vị thế mới với phạm vi giá đã cập nhật. Hãy nhớ rằng các điều chỉnh thường xuyên không phải lúc nào cũng là chiến lược tối ưu nhất vì nó thực hiện tổn thất tạm thời và tốn một lượng gas nhất định để hoàn thành nhiều giao dịch.



### Tôi có thể stake bao nhiêu vị thế trong một farm đơn lẻ?

Không có giới hạn tối đa về số lượng vị thế bạn có thể stake trong một farm.

Nhưng hãy nhớ rằng bạn sẽ cần chi gas để thu hoạch thủ công từ mỗi vị thế. Hãy luôn tính toán chi phí gas trong các hoạt động yield.



### Tôi nên thu hoạch phần thưởng bao lâu một lần?

Tần suất thu hoạch phần thưởng là tùy bạn, nhưng hãy nhớ rằng có một khoản phí nhỏ khi thu hoạch. Bạn có thể thấy khoản phí này trong ví của mình khi xác nhận sau khi nhấp "Harvest"**.**

Điều này cho thấy phí thu hoạch khi xuất hiện trong ví MetaMask. Các ví khác nhau sẽ hiển thị thông tin hơi khác nhau. Hãy cân nhắc để phần thưởng của bạn tăng lên một thời gian để bạn trả phí ít thường xuyên hơn.



### Tôi muốn điều chỉnh vị thế của mình trong khi đang stake trong farm thì sao?

Trong khi stake trong farm, bạn có thể thêm hoặc xóa thanh khoản mà không cần unstake. Chỉ cần tìm vị thế thanh khoản bạn muốn điều chỉnh và nhấp vào tiêu đề/id của nó, bạn sẽ thấy trang chi tiết vị thế nơi bạn có thể sử dụng các nút "Add" và "Remove".

Nếu bạn muốn điều chỉnh cấu hình phạm vi giá của vị thế thanh khoản, bạn sẽ cần unstake khỏi farm, xóa tất cả thanh khoản và tạo lại vị thế mới bằng cách thêm thanh khoản.



### Điều gì ảnh hưởng đến APR Farming?

Trong Farm v3, APR phần thưởng CAKE có thể thay đổi giữa các vị thế thanh khoản. Nó dựa trên các yếu tố sau:

* Tỷ lệ emission CAKE đến Farms\
  \- nhiều CAKE sẽ tạo ra lợi suất cao hơn cho tất cả farms. Đọc thêm trên [trang tokenomics của chúng tôi](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics)
* Số nhân Farm\
  \- farms với số nhân cao hơn sẽ nhận được nhiều CAKE tỷ lệ hơn so với tất cả farms. Lưu ý rằng v3 và v2 + stable swap farms đang sử dụng hai bộ số nhân riêng biệt. Và farms trên Ethereum và BNB Chain cũng đang sử dụng hai bộ số nhân riêng biệt.
* Số lượng token được nạp vào vị thế\
  \- nhiều token trong vị thế tương ứng với cổ phần tương đối lớn hơn so với tổng thanh khoản đang hoạt động trong pool farm và nhận được nhiều phần thưởng CAKE hơn
* Phạm vi giá đã chọn\
  \- phạm vi giá nhỏ hơn cho phép tập trung cao hơn với cùng lượng token được nạp, tương ứng với cổ phần tương đối lớn hơn so với tổng thanh khoản đang hoạt động trong pool farm và nhận được nhiều phần thưởng CAKE hơn
* Lượng thanh khoản đang hoạt động hiện tại\
  \- nếu có nhiều người dùng hơn nạp và tập trung thanh khoản với cùng phạm vi như bạn, bạn sẽ kiếm được phần thưởng CAKE do cổ phần tương đối nhỏ hơn so với tổng số
* Liệu vị thế thanh khoản có đang hoạt động hay không\
  \- chỉ các vị thế thanh khoản đang hoạt động mới kiếm được phần thưởng CAKE từ farm



### Tại sao tôi thấy cửa sổ pop-up "Update Positions"?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28321%29.png)

Ngay sau khi ra mắt V3, các Chefs đã triển khai cập nhật cho Farms để làm cho các tính toán phần thưởng chính xác và đáng tin cậy hơn. Nếu bạn thấy cửa sổ pop-up này, điều đó có nghĩa là một số vị thế của bạn sẽ cần cập nhật.

Chỉ cần nhấp "Update All" và xác nhận trong cửa sổ pop-up ví của bạn.

Lưu ý rằng các Chefs cũng đang áp dụng cập nhật này cho dữ liệu staking lịch sử giữa khi ra mắt Farm V3 và khi cập nhật này được triển khai. Nếu có bất kỳ phần thưởng CAKE bổ sung nào, chúng sẽ được airdrop vào ví của bạn trước ngày 1 tháng 5 năm 2023.



### Tại sao farm 2x trong V3 có APR thấp hơn farm 1x trong V2?

Đầu tiên, khi so sánh APR, bạn cần đảm bảo tổng thanh khoản đã stake giữa hai farms là bằng nhau.

Ngoài ra, bây giờ chúng ta có nhiều nhóm farms có luồng CAKE emission riêng. Và mỗi nhóm farms chia sẻ các bộ số nhân riêng biệt.

Một farm riêng lẻ sẽ nhận emission CAKE dựa trên:

* A = Tổng CAKE mỗi giây/block cho nhóm farm mà nó thuộc về
* B = Tổng số nhân trong nhóm mà nó thuộc về
* C = Số nhân mà nó có

`CAKE per block/second = C / B * A`

Các con số trên có thể được tìm thấy trong mỗi hợp đồng [MasterChef](/broken/pages/-MeTWzQOSmb1ej51HT0I).



### Tôi có thể sử dụng bCAKE trong v3 Farms không?

Có

bCAKE cho V3 Farms sẽ đến ngay sau khi triển khai PancakeSwap Farm V3. Hãy chờ đón.
