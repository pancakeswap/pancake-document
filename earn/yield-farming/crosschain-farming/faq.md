# FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### Tôi nên làm gì trên PancakeSwap ở các blockchain khác?

Cung cấp thanh khoản, giao dịch và farm như bạn vẫn làm. Nếu bạn đã là người dùng multichain, hãy nhớ cung cấp thanh khoản trên PancakeSwap ở các blockchain khác mà chúng tôi đã triển khai (như Ethereum), vì chúng tôi có phần thưởng CAKE trên BNB Smart Chain cho bạn, cho phép bạn kiếm thêm CAKE mà không cần bridge các tài sản đó!

### **Có thêm cặp nào không?**

Có, nhưng chúng tôi sẽ triển khai theo từng bước để đảm bảo ưu tiên an toàn cho tiền của người dùng và lạm phát CAKE. Hãy cho chúng tôi biết trong các chat cộng đồng những gì bạn nghĩ nên được thêm vào PancakeSwap ở các blockchain khác, cũng như các blockchain khác chúng tôi nên triển khai PancakeSwap.

### **Tại sao chi phí gas khi stake LP token cao?**

Một lượng nhỏ token gốc (ví dụ: ETH trên Ethereum) là cần thiết cho lần thiết lập đầu tiên. Vì vậy giao dịch đầu tiên sẽ tốn kém hơn một chút.

Ngoài ra, có các phí khác (chủ yếu là chi phí gas) liên quan đến farming xuyên chuỗi. Xem [phần chuyên dụng này](faq.md#are-there-any-fees-when-i-do-crosschain-farming) để tìm hiểu thêm.

### **Tại sao staking và unstaking mất 30 phút để hoàn thành?**

Tất cả các giao dịch cross-chain sẽ mất khoảng 30 phút để hoàn thành. Đó là vì:

* Giao dịch phải được thực hiện trên cả blockchain farming (như Ethereum) và BNB Chain.
* Việc truyền tải thông điệp cross-chain mất thời gian.
* Để đảm bảo an toàn và tất cả dữ liệu được đồng bộ và nhất quán giữa các blockchain khác nhau.

### **Phần thưởng CAKE đã thu hoạch của tôi ở đâu?**

CAKE thu hoạch của bạn sẽ được phân phối trên BNB Smart Chain. Vui lòng chuyển mạng blockchain trong ví của bạn để kiểm tra số dư CAKE.

### **Tôi không thể thu hoạch vì ví của tôi không hỗ trợ chuyển đổi giữa các blockchain khác nhau!**

Vui lòng thử sử dụng một ứng dụng ví khác hỗ trợ multichain và chuyển đổi chuỗi.

Lưu ý rằng việc staking và unstaking LP tokens cũng sẽ thu hoạch tất cả CAKE đã kiếm được vào ví của bạn trên BNB Smart Chain. Do đó nếu bạn không muốn sử dụng ứng dụng ví khác, chỉ cần stake thêm hoặc unstake một lượng nhỏ LP tokens để thu hoạch CAKE đã kiếm được.

### Có phí nào khi tôi farming xuyên chuỗi không?

Không giống như farming gốc trên BNB Chain, farming trên các blockchain khác đòi hỏi các hoạt động cross-chain. Đây là các phí liên quan:

**1 - Phí gas để tạo hợp đồng proxy**

Một hợp đồng proxy phải được tạo trên BNB Chain cho farming xuyên chuỗi. Chi phí gas để tạo hợp đồng proxy được bao gồm trong giao dịch.

Phí này chỉ tính một lần trong giao dịch "stake" đầu tiên.

**2 - Phí gas cho các cuộc gọi trên BNB Chain**

Khi người dùng gửi hoặc rút LP tokens. Một executor sẽ thực hiện giao dịch thay mặt người dùng trên BNB Chain. Chi phí gas cho các cuộc gọi này được bao gồm trong giao dịch.

Phí này được tính trong mỗi giao dịch gửi hoặc rút.

**3 - Phí gas cho các cuộc gọi trên các blockchain khác**

Khi người dùng rút LP tokens. Một executor sẽ thực hiện các giao dịch cuối cùng để giải phóng LP tokens trên các blockchain khác (như Ethereum). Chi phí gas cho các cuộc gọi này được bao gồm trong giao dịch.

Phí này chỉ được tính trong các giao dịch rút.

**4 - Phí nhắn tin cross-chain**

Chúng tôi sử dụng message bus được hỗ trợ bởi Celer để định tuyến các tin nhắn cross-chain của chúng tôi. Do đó một khoản phí tin nhắn được bao gồm dựa trên độ dài byte của tin nhắn.

Phí này được tính trong mỗi giao dịch stake. Trong các giao dịch unstake, phí này được tính hai lần vì cần giao tiếp hai chiều giữa BNB Chain và các blockchain khác để đảm bảo an toàn.

```
messagingFee = feeBase + message.length * feePerByte;
```

Bạn có thể tìm thấy các biến trong công thức trong hợp đồng message bus:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - Quỹ khởi động**

Đây không thực sự là "phí".&#x20;

Đối với mỗi người dùng mới bắt đầu farming xuyên chuỗi PancakeSwap. Trong giao dịch "stake" đầu tiên, chúng tôi sẽ gửi 0,005 BNB vào ví BNB Chain của họ. Số lượng token gốc tương ứng trên chuỗi farming (như ETH trên Ethereum) sẽ được tính từ giao dịch gửi, sử dụng giá thị trường được cung cấp bởi oracle giá.

Điều này giúp người dùng bắt đầu hành trình BNB Chain của họ một cách dễ dàng. Chúng tôi hiểu sự khó chịu khi có tất cả CAKE đã thu hoạch nhưng không thể khám phá hệ sinh thái PancakeSwap sôi động mà không tìm cách khác để mua BNB cho gas.

Phí này chỉ tính một lần trong giao dịch "stake" đầu tiên.

### Emissions đến từ đâu?&#x20;

_cập nhật vào ngày 10 tháng 10 năm 2022_

Hiện tại, các Chefs đã chuyển hướng 0,0189 CAKE mỗi block từ CAKE pool sang tất cả crosschain farms.&#x20;

Đây là phân tích emissions:

<table><thead><tr><th width="249"></th><th>Số nhân</th><th>CAKE mỗi block</th></tr></thead><tbody><tr><td><strong>CAKE Pool</strong></td><td>-</td><td><strong>8.9811</strong></td></tr><tr><td><strong>Tất cả Crosschain Farms</strong></td><td>-</td><td><strong>0.0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0.5x</td><td>0.0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0.2x</td><td>0.0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0.2x</td><td>0.0042</td></tr></tbody></table>

### Điều gì xảy ra trong quá trình gửi, thu hoạch và rút?

Farming xuyên chuỗi PancakeSwap giống như sử dụng LP token "đại diện" để farm trên BNB Chain, với cùng PancakeSwap MasterChef. Phần thưởng CAKE được tính toán và phân phối trên BNB Chain, được kiểm soát và bảo vệ bởi cùng hợp đồng MasterChef.

#### Khi Gửi:

1. Người dùng yêu cầu gửi LP tokens trên các blockchain farming (như Ethereum).
2. LP tokens đang được chuyển đến các hợp đồng vault farming.
3. Celer message bus được sử dụng để gửi tin nhắn "deposit" đến BNB Chain.
4. Một executor trên BNB Chain đúc cùng số lượng farming token làm "đại diện" và sau đó gửi chúng vào farms.

#### Khi Thu hoạch:

Vì phần thưởng CAKE được tính toán và phân phối trên BNB Chain. Người dùng có thể nhận phần thưởng CAKE với một giao dịch BNB Chain duy nhất mà không cần các hoạt động cross-chain.

#### Khi Rút:

1. Người dùng yêu cầu rút LP tokens trên các blockchain farming (như Ethereum).
2. Celer message bus được sử dụng để gửi tin nhắn "withdraw" đến BNB Chain.
3. Một executor trên BNB Chain rút farming token từ farms, đốt những token đó, chuyển CAKE đã kiếm được cho người dùng và sử dụng Celer message bus để gửi tin nhắn xác nhận trở lại blockchain farming ban đầu.
4. Một executor trên blockchain farming xác nhận mọi thứ và sau đó giải phóng LP tokens từ các hợp đồng vault.
