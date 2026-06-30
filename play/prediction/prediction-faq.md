# FAQ Dự đoán

{% hint style="info" %}
Dùng thanh điều hướng bên để nhanh chóng tìm câu trả lời cho câu hỏi của bạn!
{% endhint %}

## A) Câu hỏi chung

### **1. Phí là bao nhiêu?**

3% tổng quỹ của mỗi vòng sẽ đi vào kho bạc, trong đó 100% sẽ được dùng để mua lại và đốt CAKE.

### 2. Tỷ lệ thanh toán được tính như thế nào?

* Tỷ lệ thanh toán cho Bể LÊN = Tổng giá trị cả hai bể ÷ Giá trị Bể LÊN
* Tỷ lệ thanh toán cho Bể XUỐNG = Tổng giá trị cả hai bể ÷ Giá trị Bể XUỐNG

**Ví dụ - Đặt cược 2 BNB "XUỐNG", kết quả = "XUỐNG":**

* Phía XUỐNG = 15 BNB, tổng quỹ thưởng = 150 BNB&#x20;
* Tỷ lệ thanh toán XUỐNG = 150 BNB / 15 BNB = 10x
* Số tiền thanh toán = Tỷ lệ thanh toán × Vị thế × (1 - Phí kho bạc)
  * Nếu bạn đặt 2 BNB vào XUỐNG, thanh toán = (2 × 10) × (1 − 0,03) = 19,4 BNB
* Lợi nhuận = 19,4 − 2 = 17,4 BNB

### 3. Có giới hạn thời gian trước khi tôi có thể thu thập tiền thắng không?

Không, bạn sẽ có thể thu thập tiền thắng vào bất kỳ lúc nào trong tương lai.

### 4. Địa chỉ hợp đồng PancakeSwap Prediction là gì?

**BNB Chain**

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Vị thế & Kết quả

### 1. **Tôi có thể thay đổi hay hủy vị thế của mình không?**

Không. Sau khi bạn đã nhập vị thế, bạn KHÔNG THỂ thay đổi hướng, thêm vào hay rút vị thế của mình. Nó đã bị khóa, vì vậy hãy đảm bảo bạn hoàn toàn hài lòng với hướng vị thế của mình trước khi xác nhận. &#x20;

### 2. Khi nào thị trường bị hủy? Điều gì xảy ra lúc đó?

* **Khi nào:** Oracle hoặc dịch vụ backend bị lỗi, hoặc các tình huống bất thường khác.
* **Kết quả:** Người dùng có thể nhận lại 100% số tiền cược ban đầu (không phí).

### 3. Kết quả vòng thay đổi sau khi vòng kết thúc! Tại sao?

Đôi khi, sau khi một vòng đóng, kết quả cuối cùng có thể khác với kết quả cuối cùng được hiển thị trong khi vòng đang diễn ra. Nếu bạn xem một vòng kết thúc với "XUỐNG", nó có thể dường như lật sang "LÊN" vài giây sau.

Điều này xảy ra vì chúng tôi sử dụng nguồn cấp giá Oracle để xác định kết quả cuối cùng của một vòng. Khoảng thời gian giữa khi một vòng kết thúc và vòng tiếp theo bắt đầu là 30 giây, nhưng Oracle làm mới mỗi 20 giây. Có thể trong khoảng thời gian ngắn này, Oracle có thể gửi cập nhật trong khi giao dịch để kích hoạt vòng tiếp theo đang được đào. Điều này có thể khiến kết quả của vòng trước bị "lật".

### 4. Giá Khóa & Giá Đóng là gì?

* **Giá Khóa:** Giá vào đầu giai đoạn LIVE.
* **Giá Đóng:** Giá vào cuối vòng, được dùng để xác định người thắng.

**Ví dụ – Vòng 400 (Dự đoán BNB):**

1. **12:00–12:05:** Đặt cược → Người dùng đặt 0,1 BNB vào "LÊN"
2. **12:05–12:10:** Giai đoạn Khóa → Giá Khóa = $850
3. **12:10:** Giai đoạn Đóng → Giá Đóng = $860
4. **Kết quả: Cược "LÊN"** thắng

**Lưu ý:**

* Giá Oracle có thể mất tối đa 20 giây để cập nhật.
* Nhà cái thắng: Tất cả cược đi về nhà cái

### 5. Những tình huống nào được coi là NHÀ CÁI THẮNG?

**Các tình huống:**

1. Không có cược đối lập và người dùng thua (ví dụ: chỉ có một người dùng đặt LÊN và kết quả = XUỐNG)
2. Giá Khóa = Giá Đóng

**Điều gì xảy ra:**

* PancakeSwap nhận 100% bể; tất cả quỹ đi vào đốt CAKE.
* Người dùng ở cả hai phía đều mất số tiền cược ban đầu.

**Ví dụ - Không có cược đối lập:**

* Người dùng A đặt LÊN, không có cược XUỐNG, kết quả = XUỐNG → Người dùng A thua; 100% quỹ đi vào kho bạc.
* Người dùng B đặt LÊN, không có cược XUỐNG, kết quả = LÊN → Người dùng B lấy lại 97% tiền gửi.



## C) Tạm dừng thị trường

### 1. Thị trường bị tạm dừng có nghĩa là gì?

Thị trường bị tạm dừng khi có các điều kiện ảnh hưởng đến độ tin cậy của hợp đồng. Thị trường bị tạm dừng có nghĩa là sẽ không có cược nào diễn ra cho bất kỳ vòng nào.

### 2. Điều gì khiến thị trường PancakeSwap Prediction tạm dừng?

Thị trường dự đoán sẽ tạm dừng trong các điều kiện sau:

1. Hợp đồng dự đoán không thể lấy giá từ oracle ChainLink do oracle chưa đăng giá vào thời điểm vòng kết thúc.
2. Hợp đồng dự đoán không thể thực hiện một hành động (kết thúc vòng hoặc lấy giá từ oracle) do giao dịch bị kẹt trong mempool quá 15 block.
3. PancakeSwap đã quyết định ngừng dự đoán cho thị trường/tài sản đó.

### 3. Điều gì xảy ra với vị thế của tôi nếu thị trường tạm dừng?

Nếu thị trường tạm dừng khi bạn đang có vị thế đang diễn ra, quỹ của bạn sẽ có thể được lấy lại, theo cách tương tự như bạn thường nhận tiền thắng.

Để lấy lại quỹ, bạn sẽ cần trả một số phí gas. Chúng tôi không thể bồi thường cho bạn phí gas, vì vậy hãy lưu ý rủi ro nhỏ này trước khi tham gia.

### 4. Khi nào thị trường sẽ tiếp tục sau khi tạm dừng?

Thị trường sẽ tiếp tục khi một admin (một trong các đầu bếp) khởi động lại thị trường theo cách thủ công.



## D) Xử lý sự cố & Yêu cầu

### 1. Làm thế nào để nhận tiền thắng cũ từ thị trường CAKEUSD trên BNB Chain?&#x20;

* Truy cập [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc)
* Kiểm tra tab lịch sử để xem tiền thắng từ các vòng lịch sử

### 2. Tại sao tôi không thể thấy tiền thắng trong ví của mình?

Khi bạn thu thập tiền thắng, chúng có thể không xuất hiện trong nhật ký giao dịch của ví bạn như thường lệ.\
Điều này là vì chúng sử dụng loại giao dịch khác: Giao dịch nội bộ.\
Nhập địa chỉ ví của bạn trên BscScan, sau đó kiểm tra tab "Internal Txns" để xác nhận chúng đã đến.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. Tại sao kết quả vòng của tôi không hiển thị?

Có bộ đệm 15 block trên mỗi vòng, có thể gây ra độ trễ lên đến 45 giây sau khi vòng kết thúc.\
Bộ đệm này là để phù hợp với thực tế rằng chúng tôi có thể không lấy được giá một cách đáng tin cậy và kết thúc vòng ngay lập tức: các yếu tố blockchain khác nhau ảnh hưởng đến tốc độ xác nhận giao dịch trên mạng.

### 4. Tôi không thể thu thập tiền thắng, tôi phải làm gì?

Hãy đảm bảo bạn có đủ BNB trong ví để trả phí gas. Bạn cần một ít BNB để kích hoạt hợp đồng thông minh.

### **5. Nếu tôi không thể nhận tiền thắng từ trang web thì sao?**

Bạn có thể nhận tiền thắng trực tiếp từ hợp đồng. Hãy làm theo các bước trong 3 tab bên dưới.

{% tabs %}
{% tab title="Kiểm tra các vòng bạn đã chơi" %}
Cách kiểm tra lịch sử các vòng bạn đã chơi

1. Truy cập trang BscScan của [hợp đồng Dự đoán](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ví dụ: BNBUSD).
2. Kéo xuống "8. getUserRounds".
3. Nhập địa chỉ ví của bạn vào "user(address)".
4. Đặt "cursor(uint256)" là 0 và "size(uint256)" là 1000.
5. Nhấn "Query"
6. Các vòng bạn đã tham gia sẽ hiển thị bên dưới ở hàng đầu tiên. (sau "uint256\[]:")
{% endtab %}

{% tab title="Kiểm tra xem bạn có thể nhận không" %}
Đầu tiên, kiểm tra xem bạn có thực sự có thể nhận từ vòng bạn đã chơi không.

1. Truy cập trang BscScan của [hợp đồng Dự đoán](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ví dụ: BNBUSD) và vào tab Read
2. Kéo xuống "4. claimable".
3. Nhập id vòng bạn muốn kiểm tra vào "epoch(uint256)".
4. Nhập địa chỉ ví của bạn vào "user(address)".
5. Nhấn "Query"
6. Nếu vòng có thể nhận, nó sẽ hiển thị "true".
7. Nếu kết quả là "false". Hãy lặp lại các bước trên và thử với "19. refundable".&#x20;
8. Lưu ý: ⬆️ Nếu bạn thấy một vòng trả về "false" trên cả "4. claimable" và "19. refundable", nhưng nó hiển thị trên trang web, có thể nó đã được nhận rồi và trang web đang bị chậm trễ.
{% endtab %}

{% tab title="Nhận từ một vòng" %}
Cách nhận

1. Truy cập trang BscScan của [hợp đồng Dự đoán](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (ví dụ: BNBUSD) và vào tab Write
2. Nhấn "🔴 Connect to Web3"
3. Dùng MetaMask hoặc WalletConnect để kết nối.
4. Kéo xuống "3. claim"
5.  Nhập số vòng bạn muốn nhận theo định dạng này, bao gồm cả dấu ngoặc \[]: `[12345]`&#x20;

    Nếu bạn muốn nhận từ nhiều vòng cùng một lúc, hãy phân tách các vòng bằng dấu phẩy như thế này: `[12345,12346,12347]`
6. Nhấn "Write"
7. Xác nhận trên ví&#x20;
{% endtab %}
{% endtabs %}
