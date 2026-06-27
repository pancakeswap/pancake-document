# Bảng Thuật Ngữ Perpetuals V1

**Tại đây bạn sẽ tìm thấy định nghĩa của tất cả các thuật ngữ liên quan đến giao dịch hợp đồng tương lai**

### **Giao Dịch Hợp Đồng Vĩnh Viễn**

&#x20;Hợp đồng vĩnh viễn (perpetuals), hoán đổi vĩnh viễn (perpetual swaps), hay perps là một loại hợp đồng tương lai đặc biệt không có ngày hết hạn.



### **Đòn Bẩy**

Đòn bẩy là một cơ chế giao dịch. Các nhà giao dịch có thể sử dụng nó để tăng mức độ tiếp xúc với thị trường bằng cách cho phép họ thanh toán ít hơn toàn bộ số tiền đầu tư. Nói đơn giản, bạn vay tiền để tận dụng đòn bẩy cho khoản đầu tư của mình.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **Ký Quỹ**

là khoản đảm bảo bạn đặt cho các vị thế sử dụng đòn bẩy. Có hai chế độ để sử dụng:

* Chế Độ Cross Margin (Ký quỹ Chéo): Tất cả các vị thế cross dưới cùng một tài sản ký quỹ chia sẻ cùng số dư ký quỹ cross của tài sản đó. Trong trường hợp thanh lý, toàn bộ số dư ký quỹ của tài sản cùng với các vị thế đang mở còn lại dưới tài sản đó có thể bị tịch thu.
* Chế Độ Isolated Margin (Ký quỹ Cô lập): Quản lý rủi ro trên các vị thế riêng lẻ bằng cách giới hạn lượng ký quỹ được phân bổ cho mỗi vị thế. Nếu tỷ lệ ký quỹ của một vị thế đạt 100%, vị thế đó sẽ bị thanh lý. Ký quỹ có thể được thêm hoặc xóa khỏi các vị thế sử dụng chế độ này.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOg5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Tỷ Lệ Ký Quỹ**: Tỷ Lệ Ký Quỹ = Ký Quỹ Duy Trì / Số Dư Ký Quỹ. Vị thế của bạn sẽ bị thanh lý khi Tỷ Lệ Ký Quỹ đạt 100%.

**Tỷ Lệ Duy Trì**: Số dư ký quỹ tối thiểu cần thiết để duy trì các vị thế đang mở của bạn.

**Số Dư Ký Quỹ** = Số Dư Ví + Lãi/Lỗ Chưa Thực Hiện. Vị thế của bạn sẽ bị thanh lý khi Số Dư Ký Quỹ <= Ký Quỹ Duy Trì.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Tài sản:

**Nạp tiền**: Nạp tiền vào tài khoản hợp đồng tương lai của bạn

**Rút tiền**: Rút tiền từ tài khoản hợp đồng tương lai về ví của bạn

**Số Dư**: Số Dư Ví = Tổng Chuyển Khoản Ròng + Tổng Lợi Nhuận Đã Thực Hiện + Tổng Phí Funding Ròng - Tổng Hoa Hồng.

**Lãi/Lỗ Chưa Thực Hiện**: Lãi và lỗ chưa thực hiện trên vị thế này được tính dựa trên Giá Mark, và tỷ lệ hoàn vốn trên vốn chủ sở hữu.

**Các Chế Độ:**&#x20;

* Chế Độ Tài Sản Đơn: Hỗ trợ giao dịch USDⓈ-M Futures chỉ sử dụng tài sản ký quỹ đơn lẻ của symbol. Lãi/lỗ của các vị thế cùng tài sản ký quỹ có thể được bù trừ. Hỗ trợ Chế Độ Cross Margin và Chế Độ Isolated Margin.
* Chế Độ Đa Tài Sản: Giao dịch USDⓈ-M Futures trên nhiều tài sản ký quỹ. Lãi/lỗ có thể được bù trừ giữa các vị thế tài sản ký quỹ khác nhau. Chỉ hỗ trợ Chế Độ Cross Margin.

{% hint style="info" %}
Lưu ý: Nếu có vị thế đang mở hoặc lệnh đang mở trong USDⓈ-M Futures, Chế Độ Đa Tài Sản không thể được kích hoạt. Chế Độ Đa Tài Sản chỉ áp dụng cho USDⓈ-M Futures. Trước khi kích hoạt Chế Độ Đa Tài Sản, hãy đọc kỹ hướng dẫn để quản lý tốt hơn rủi ro tài khoản USDⓈ-M Futures khi sử dụng Chế Độ Đa Tài Sản.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Lệnh

**Mua/Long (Vị thế dài):** Mở lệnh Long. Trong lệnh này, bạn mua một tài sản và chờ bán khi giá tăng. "Mua" và "long" được sử dụng thay thế cho nhau.

**Bán/Short (Vị thế ngắn):** Mở lệnh Short. Trong lệnh này, bạn vay một tài sản, bán nó và hy vọng mua lại khi giá giảm. "Bán" và "short" được sử dụng thay thế cho nhau.

**Lệnh Giới Hạn (Limit Order):** Lệnh giới hạn là lệnh mua hoặc bán ở một mức giá cụ thể hoặc tốt hơn. Lệnh giới hạn không được đảm bảo thực thi.

**Lệnh Thị Trường (Market Order):** Lệnh thị trường là lệnh mua hoặc bán ở mức giá hiện tại tốt nhất. Nó được thực thi dựa trên các lệnh giới hạn đã được đặt trước đó trong sổ lệnh. Khi đặt lệnh thị trường, bạn sẽ trả phí với tư cách là taker thị trường.

**Lệnh Stop Limit:** Cách dễ nhất để hiểu lệnh stop-limit là chia nó thành giá stop và giá limit. Giá stop đơn giản là mức giá kích hoạt lệnh giới hạn, và giá limit là giá của lệnh giới hạn được kích hoạt. Điều này có nghĩa là khi giá stop của bạn được đạt, lệnh giới hạn của bạn sẽ ngay lập tức được đặt vào sổ lệnh.

**Lệnh Stop Market:** Tương tự như lệnh stop-limit, lệnh stop market sử dụng giá stop làm kích hoạt. Tuy nhiên, khi giá stop được đạt, nó kích hoạt một lệnh thị trường thay thế.

**Trailing Stop:** Trailing stop là loại lệnh được thiết kế để khóa lợi nhuận hoặc giới hạn tổn thất khi giao dịch di chuyển có lợi. Trailing stop chỉ di chuyển khi giá di chuyển có lợi. Một khi nó di chuyển để khóa lợi nhuận hoặc giảm tổn thất, nó không di chuyển ngược lại.

**Post Only:** Chế Độ Post-only có nghĩa là Nhà Giao Dịch chỉ có thể đặt Lệnh nếu nó được đăng vào Sổ Lệnh như một Lệnh Maker. Lệnh nào được đăng như Lệnh Taker sẽ bị từ chối. Không có Lệnh Thị Trường nào có thể được đặt và không có Lệnh nào sẽ được khớp. Các lệnh đang nghỉ có thể được hủy trong chế độ post-only.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6Qj V03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**Reduce Only (Chỉ Giảm):** Lệnh Reduce-Only chỉ giảm vị thế của bạn, không tăng nó.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjvjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**Hướng dẫn TIF** cho phép bạn chỉ định khoảng thời gian lệnh của bạn sẽ duy trì hoạt động trước khi được thực thi hoặc hết hạn. Bạn có thể chọn một trong các tùy chọn sau cho hướng dẫn TIF:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Good Till Cancel - Có hiệu lực cho đến khi hủy): Lệnh sẽ duy trì hoạt động cho đến khi được khớp hoặc hủy.&#x20;
* **IOC** (Immediate Or Cancel - Thực hiện ngay hoặc hủy): Lệnh sẽ thực thi ngay lập tức (toàn bộ hoặc một phần). Nếu chỉ được thực thi một phần, phần chưa được khớp của lệnh sẽ bị hủy.&#x20;
* **FOK** (Fill Or Kill - Khớp hoàn toàn hoặc hủy): Lệnh phải được khớp hoàn toàn ngay lập tức. Nếu không, nó sẽ không được thực thi.
