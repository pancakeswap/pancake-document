# FAQ Hoán Đổi

## Hoán Đổi

### Có gì mới trong Exchange V3?

* Thanh khoản tập trung - thanh khoản sẽ được tập trung vào khoảng giá được giao dịch tích cực nhất, điều đó có nghĩa là:
  * Trượt giá giao dịch thấp hơn cho các nhà giao dịch
  * Phần thưởng phí LP tiềm năng cao hơn cho các nhà cung cấp thanh khoản
* Cơ cấu phí giao dịch linh hoạt - Các nhà cung cấp thanh khoản có thể chọn giữa nhiều bậc phí giao dịch khi tạo cặp thanh khoản hoặc cung cấp thanh khoản
* Khoảng giá tùy chỉnh - Các nhà cung cấp thanh khoản cũng có thể chọn khoảng giá nào họ muốn cung cấp thanh khoản
* Các vị thế thanh khoản không thể thay thế - Mỗi vị thế thanh khoản sẽ có ID duy nhất tương ứng với cấu hình của nó (chẳng hạn như khoảng giá). Do đó, bạn sẽ có thể tạo và duy trì nhiều vị thế với cùng cặp giao dịch nhưng với cấu hình và số lượng thanh khoản khác nhau
* Tương thích ngược - Exchange v3 cũng sẽ sử dụng các cặp thanh khoản v2 và stable swap cũ để luôn cung cấp tuyến giao dịch tốt nhất
* Lệnh giới hạn tích hợp - Người dùng Pro có thể sử dụng khoảng giá tùy chỉnh mới trong việc cung cấp thanh khoản để tạo lệnh giới hạn hiệu quả, sẽ chuyển đổi tất cả token sang token mong muốn khi giá đạt mục tiêu



### Tôi có thể thêm token của riêng mình vào Exchange V3 không?

Mọi người đều có thể tạo pool thanh khoản bằng cách ký gửi thanh khoản trên V3.

Tuy nhiên, các token sau hiện **KHÔNG** được hỗ trợ:

* Token có phí khi chuyển nhượng
* Token rebase

Đối với các token này, vui lòng **KHÔNG** thêm thanh khoản trên Exchange V3. Tài sản của bạn có thể bị kẹt trong vị thế thanh khoản.



### **Tại sao giao dịch của tôi không thực hiện được?**

PancakeSwap là ứng dụng DeFi tương tác với ví để hoàn tất các giao dịch on-chain cho việc hoán đổi, tạo LP, staking trong farm và pool, v.v.

**Phí Gas**

Vì vậy, điều đầu tiên cần làm là **đảm bảo bạn có đủ BNB để trả phí gas** cho các giao dịch on-chain. Thông thường, phí gas dao động tùy thuộc vào số lượng giao dịch trong hàng đợi, nếu có nhiều giao dịch hơn, có thể cần phí gas cao hơn để thực hiện giao dịch. Trên BNB Smart Chain, phí gas thường dao động từ vài cent đến một đô la USD bằng BNB. Tìm hiểu thêm về [phí gas tại đây](https://academy.binance.com/en/glossary/gas).

**Phí Giao Dịch**

Nếu hành động hoán đổi của bạn vẫn không thực hiện được và hiển thị lỗi yêu cầu điều chỉnh trượt giá — bạn có thể muốn kiểm tra xem các token bạn đang cố gắng hoán đổi có **bất kỳ phí và hạn chế nào trong giao dịch** không.

Không hiếm khi các token trên BNB Smart Chain bao gồm **phí giao dịch** trong hợp đồng của họ, thường những phí này có thể được sử dụng để đốt, tài trợ cho kho bạc của một dự án ra mắt công bằng — ví dụ, [token APX này có thuế 1% trên mỗi giao dịch](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) để gửi đến địa chỉ đốt, sao cho nhiều giao dịch hơn có nghĩa là đốt nhiều hơn, tích lũy giá trị cho người nắm giữ token APX.

Với phí giao dịch, dù nó là bao gồm (một phần của số lượng hoán đổi được gửi đến nơi khác chứ không phải địa chỉ của bạn nên đầu ra ít hơn dự kiến cho đầu vào ước tính) hay không bao gồm (yêu cầu chuyển khoản thêm từ địa chỉ của bạn để gửi thêm token nên đầu vào nhiều hơn dự kiến cho đầu ra ước tính), nó ảnh hưởng đến số lượng đầu vào và đầu ra mà bạn đồng ý để ký giao dịch. Trong nhiều trường hợp, giao dịch không thể đáp ứng các yêu cầu đầu vào và đầu ra vì khoản thuế.

**Hoán Đổi với Phí Giao Dịch**

Trước khi hoán đổi bất kỳ token nào, hãy đảm bảo bạn đã truy cập trang web của họ để hiểu xem họ có cơ chế phí giao dịch hay không (hay _thuế_ như nhiều dự án gọi). Nếu có, hãy đảm bảo bạn đặt trượt giá đủ để phù hợp với phí giao dịch — ví dụ: nếu có phí giao dịch 5%, trượt giá của bạn phải được đặt ít nhất 5% cộng với trượt giá giao dịch bình thường tùy thuộc vào số lượng giao dịch và thanh khoản của token, chẳng hạn 5.5%-6%.

Trong một số trường hợp cực đoan bao gồm một số lừa đảo, một số token thậm chí có lệnh chặn hầu hết hoặc tất cả các chuyển khoản trên chuỗi, hoặc chỉ cho phép các địa chỉ nhất định bán, trong trường hợp đó việc hoán đổi token thành công là không thể. Hãy tìm hiểu về token bạn đang cố gắng hoán đổi và nhận thức được bất kỳ phí và hạn chế nào!



### Giao diện Swap mới có sử dụng thanh khoản v2 hay stable swap không?

Có. Swap v3 mới sử dụng thanh khoản từ PancakeSwap v3, v2 và stable swap để có tuyến giao dịch tốt nhất.



### Định tuyến phân tách là gì?

Trong Swap v3, giao dịch của bạn có thể được chia thành nhiều tuyến để thực hiện giao dịch với tỷ giá tốt nhất.

Để xem thêm chi tiết về cách giao dịch của bạn được định tuyến, nhấp vào nút "v" trong phần "Route" để mở rộng và xem chi tiết.

Tìm hiểu thêm [tại đây](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences).



### Làm thế nào để tùy chỉnh hoặc vô hiệu hóa một số nguồn thanh khoản nhất định?

Swap v3 mới sử dụng thanh khoản từ PancakeSwap v3, v2 và stable swap để có tuyến giao dịch tốt nhất. Tuy nhiên, bạn có thể tùy chỉnh hoặc vô hiệu hóa một số nguồn thanh khoản nhất định nếu bạn không muốn giao dịch của mình đi qua chúng.

Khi xem tuyến giao dịch, nhấp vào nút "Customize Routing". Hoặc nhấp vào nút cog ⚙️ ở góc trên bên phải giao diện Hoán Đổi và chọn "Customize Routing".

Trong cửa sổ bật lên "Customize Routing", bạn có thể chọn nguồn thanh khoản nào bạn muốn sử dụng. Hoặc vô hiệu hóa multihops hoàn toàn.

Lưu ý: việc vô hiệu hóa multihops có thể dẫn đến trượt giá tăng hoặc tỷ giá giao dịch kém hơn trên các cặp giao dịch cụ thể. Hãy tiến hành cẩn thận.

Tìm hiểu thêm [tại đây](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources).



## Thanh Khoản

### Các bậc phí là gì và làm thế nào để chọn đúng?

Trong Exchange v3, khi bạn cung cấp thanh khoản, bạn có thể chọn giữa một số phí giao dịch khác nhau (0.01%, 0.05%, 0.25% và 1%) cho cùng một cặp token.

Ví dụ, đối với CAKE-BNB, có thể có một cặp 0.25%, nghĩa là phí giao dịch 0.25% được áp dụng cho mỗi giao dịch. Tuy nhiên, một số nhà cung cấp thanh khoản có thể chọn cung cấp thanh khoản cho cặp giao dịch CAKE-BNB với tỷ lệ phí 0.05%, cung cấp báo giá tốt hơn và thu hút nhiều khối lượng giao dịch hơn.

Không có câu trả lời "đúng" cho cấu hình phí giao dịch nào cần chọn. Nó phụ thuộc vào các token trong cặp giao dịch. Thông thường, các token biến động mạnh nên có phí giao dịch cao hơn để bù đắp tốt hơn cho tổn thất tạm thời do biến động. Mặt khác, các token như stablecoin có biến động giá nhỏ hơn và tổn thất tạm thời thấp hơn, do đó phí giao dịch của chúng nên thấp hơn.

Khi chọn một cặp token, giao diện "Add Liquidity" sẽ tự động chọn bậc phí phổ biến nhất cho bạn.



### Tại sao hai token ký gửi của tôi không bằng nhau về giá trị USD?

Trong Exchange V3, các tài sản cơ sở trong một vị thế thanh khoản sẽ không luôn có giá trị bằng nhau bằng USD. Nó sẽ phụ thuộc vào cài đặt khoảng giá của vị thế và giá hiện tại của cặp.

Trên thực tế. Nếu vị thế của bạn đi ra ngoài phạm vi, tất cả token sẽ được chuyển đổi thành một tài sản duy nhất. Ngoài ra, bạn có thể cung cấp thanh khoản cho khoảng giá không bao gồm giá hiện tại và chỉ ký gửi một tài sản duy nhất. Tiếp tục đọc để tìm hiểu thêm ⬇️



### Điều gì xảy ra nếu vị thế thanh khoản của tôi đi ra ngoài phạm vi?

Bạn sẽ không kiếm được bất kỳ phần thưởng phí giao dịch nào nếu giá hiện tại đi ra ngoài phạm vi giá được xác định trong vị thế của bạn.

Ngoài ra, tất cả token sẽ được chuyển đổi thành một tài sản duy nhất tùy thuộc vào hướng của điều kiện giá.

Ví dụ, nếu vị thế của CAKE/BUSD được cấu hình với khoảng giá từ 3 BUSD mỗi CAKE đến 5 BUSD mỗi CAKE. Và tất cả tài sản trong vị thế sẽ được chuyển đổi thành BUSD nếu giá CAKE bằng hoặc cao hơn 5 BUSD mỗi CAKE, và ngược lại.

Lưu ý rằng nếu giá quay trở lại phạm vi, bạn sẽ bắt đầu nhận phần thưởng phí giao dịch trở lại. Không cần thực hiện thêm hành động nào.



### Liệu cung cấp thanh khoản trong phạm vi nhỏ hơn có luôn tốt hơn không?

Cung cấp thanh khoản trong khoảng giá nhỏ hơn sẽ giúp tập trung thanh khoản của bạn vào một khoảng giá cụ thể, tăng cường cổ phần tương đối của bạn so với tổng thanh khoản trong khoảng giá, có khả năng kiếm được nhiều phần thưởng phí giao dịch hơn.

Tuy nhiên, hãy lưu ý rằng chỉ các vị thế thanh khoản đang hoạt động mới kiếm được phần thưởng phí giao dịch từ các giao dịch. Điều này có nghĩa là bạn chỉ kiếm được phần thưởng khi giá giao dịch hiện tại nằm trong khoảng giá được xác định trong vị thế thanh khoản.



### Có cách nào để tự động điều chỉnh vị thế của tôi sao cho luôn trong phạm vi và kiếm phần thưởng phí không?

PancakeSwap v3 hỗ trợ ký gửi thanh khoản một cú nhấp qua Zap, có sẵn trên BNB Chain và Ethereum.



### Cơ cấu phí giao dịch cho Exchange v3 sẽ như thế nào?

|                          | 0.01% | 0.05% | 0.25% | 1%  |
| ------------------------ | ----- | ----- | ----- | --- |
| Nhà Cung Cấp Thanh Khoản | 67%   | 66%   | 68%   | 68% |
| Đốt CAKE                 | 15%   | 15%   | 23%   | 23% |
| Kho Bạc                  | 18%   | 19%   | 9%    | 9%  |

### Phần thưởng phí LP có được tự động cộng gộp như Exchange v2 không?

Không.

Trong Exchange v3, bạn sẽ cần nhận phần thưởng phí giao dịch thủ công. Bạn có thể làm điều đó trên trang chi tiết vị thế. Bạn có thể tìm thấy tất cả các vị thế thanh khoản v3 của mình trên trang thanh khoản.



### Điều gì ảnh hưởng đến APR phí LP?

Trong Exchange v3, APR phần thưởng phí LP có thể thay đổi giữa các vị thế thanh khoản. Nó dựa trên các yếu tố sau:

* Khối lượng giao dịch\
  \- khối lượng nhiều hơn tạo ra nhiều phần thưởng phí hơn
* Bậc phí cặp thanh khoản\
  \- bậc phí cao hơn tạo ra nhiều phần thưởng phí hơn từ các giao dịch riêng lẻ
* Số lượng token đã ký gửi\
  \- nhiều token trong vị thế tạo ra cổ phần tương đối lớn hơn so với tổng thanh khoản đang hoạt động, nhận nhiều phần thưởng phí giao dịch hơn từ các giao dịch
* Khoảng giá đã chọn\
  \- khoảng giá nhỏ hơn cho phép tập trung cao hơn cho cùng lượng token đã ký gửi, tạo ra cổ phần tương đối lớn hơn so với tổng thanh khoản đang hoạt động, và nhận nhiều phần thưởng phí giao dịch hơn từ các giao dịch
* Lượng thanh khoản hiện đang hoạt động\
  \- nếu có nhiều người dùng ký gửi và tập trung thanh khoản của họ với cùng phạm vi như bạn, bạn sẽ kiếm ít phí giao dịch hơn do cổ phần tương đối nhỏ hơn so với tổng
* Liệu vị thế thanh khoản có đang hoạt động hay không\
  \- chỉ các vị thế thanh khoản đang hoạt động mới kiếm được phần thưởng phí giao dịch



### Tôi có thể cung cấp thanh khoản v2 không?

Việc cung cấp thanh khoản v2 không còn được khuyến nghị nữa. Chúng tôi đề xuất sử dụng thanh khoản v3 để tận dụng các tính năng mới để cải thiện hiệu quả.

Nếu bạn muốn tiến hành thêm thanh khoản v2:

* Nếu cặp token không có pool v3, hoặc nó có nhiều thanh khoản hơn trong v2 so với pool lớn nhất trong v3. Nút "Add V2 Liquidity" sẽ xuất hiện. Chỉ cần nhấp để chuyển sang thêm thanh khoản v2
* Ngoài ra, sử dụng `/v2` trong URL để luôn sử dụng cung cấp thanh khoản v2



### Tại sao tôi không thể thêm thanh khoản vào cặp tôi vừa tạo?

Do lỗi từ Exchange V2 cũ (có trong mọi fork UniSwap V2), bạn sẽ không thể thêm thanh khoản vào cặp sử dụng giao diện thanh khoản PancakeSwap thông thường và các lời gọi hợp đồng nếu một cặp:

* Được tạo bằng cách gọi `createPair` trên FactoryV2 mà không ký gửi thanh khoản ban đầu và đúc các token LP ban đầu
* Sau đó, một trong các token trong cặp đã được chuyển thủ công vào hợp đồng pool trong khi gọi `sync`

{% hint style="info" %}
Gần đây, các cuộc tấn công như vậy đã tăng lên trên PancakeSwap Exchange V2 trên BNB Chain.&#x20;

Chúng tôi đặc biệt khuyến nghị sử dụng giao diện UI của chúng tôi để tạo cặp giao dịch cho token của bạn bằng cách thêm thanh khoản ban đầu với việc tạo cặp.
{% endhint %}

Trong khi các Chefs đang nỗ lực giải quyết vấn đề này, đây là hướng dẫn từng bước để giải quyết bằng BscScan:

#### Tìm địa chỉ pool và trang BscScan của nó

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

Nếu cặp của bạn bị ảnh hưởng, bạn sẽ thấy liên kết đến trang BscScan cho cặp/pool giao dịch trong thông báo lỗi.

Ngoài ra, bạn có thể đến Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)), đi đến "Read Contract", "6. getPair", nhập địa chỉ của hai token trong cặp giao dịch của bạn và nhấp "Query". Bạn sẽ thấy địa chỉ cặp trong trường trả về.

#### Kiểm tra token nào đã được ký gửi và chuyển token còn lại vào cặp theo cách thủ công

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png)

Từ trường số dư token trên BscScan, bạn có thể kiểm tra token nào đã được ký gửi vào pool. Thông thường, đó phải là token được ghép cặp. (Như WBNB, USDT, v.v...)

Sau khi xác nhận, bạn phải chuyển thủ công tài sản còn lại vào hợp đồng pool. Bạn có thể làm điều đó trong ứng dụng ví bạn ưa thích bằng cách nhập địa chỉ pool là người nhận.

Bạn có thể chuyển bất kỳ số lượng nào nhưng vì đây thực chất là "quyên góp" tài sản cho một pool. Bạn sẽ chuyển tài sản của mình vào một pool thanh khoản mà không đúc token thanh khoản. Vì vậy, chúng tôi đề xuất giữ số lượng này ở mức tối thiểu.

{% hint style="warning" %}
QUAN TRỌNG: Sau khi bạn đã chuyển token, bạn phải gọi `sync()` ngay lập tức trên pool.
{% endhint %}

Bạn có thể làm điều đó bằng cách đến trang BscScan cho cặp giao dịch, đi đến "Write Contract", "8. Sync" và nhấp nút "Write". Bạn sẽ cần kết nối ví trước khi thực hiện giao dịch.

Sau khi giao dịch được xác nhận, bạn có thể thêm thanh khoản tiếp theo trên giao diện PancakeSwap.

#### Nếu tôi muốn xác định giá ra mắt thì sao?

Bạn phải điều chỉnh pool về giá ra mắt trong khi chuyển token và sửa pool.

Số lượng cần chuyển có thể được tính bằng:

* `tokenInside`: token đã được chuyển vào pool. Thông thường đó phải là token được ghép cặp. (Như WBNB, USDT, v.v...)
* `tokenToSend`: token sắp được gửi vào pool. Thông thường đó phải là token dự án của bạn
* `tokenInside.price`: giá USD của tokenInside
* `tokenToSend.price`: giá USD của tokenToSend (giá ra mắt)
* `pool`: pool V2

Với công thức sau:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

Nếu kết quả nhỏ hơn 0 (thường xảy ra khi giá ra mắt rất lớn. Bạn có thể cần ký gửi thêm `tokenInside` vào pool trước)



### Làm thế nào để quản lý stable LP và v2 LP cũ?

Bạn có thể quản lý chúng như bình thường bằng cách đến trang [Liquidity](https://pancakeswap.finance/liquidity).



### Tại sao tôi cần đặt lại approval trên USDT trước khi enable/approve?

Khi hoạt động trên Ethereum mainnet, token USDT tuân theo logic khác để quản lý approvals và token allowance.&#x20;

Do đó, khi spending allowances quá thấp. Nó yêu cầu bạn đặt lại approval trước khi đặt allowance mới.
