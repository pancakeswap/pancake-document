---
description: Các thông báo lỗi phổ biến. Dùng thanh bên ➡️để nhảy đến lỗi bạn đang gặp.
---

# Khắc Phục Lỗi

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

Đôi khi bạn có thể gặp phải vấn đề không có giải pháp rõ ràng. Các mẹo khắc phục sự cố này có thể giúp bạn giải quyết các vấn đề gặp phải.

## **Sự Cố Trên Sàn Giao Dịch**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

Bạn đang cố gắng hoán đổi token, nhưng mức trượt giá của bạn quá thấp hoặc thanh khoản quá thấp.

{% tabs %}
{% tab title="Giải pháp" %}
1. Làm mới trang và thử lại sau.
2. Thử giao dịch một lượng nhỏ hơn tại một thời điểm.
3. Tăng mức độ chịu đựng trượt giá của bạn:
   1. Nhấn vào biểu tượng cài đặt trên trang thanh khoản.
   2. Tăng mức độ chịu đựng trượt giá một chút và thử lại. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. Cuối cùng, thử nhập số lượng với ít chữ số thập phân hơn.
{% endtab %}

{% tab title="Lý do" %}
**Điều này thường xảy ra khi giao dịch các token có thanh khoản thấp.**

Điều đó có nghĩa là không có đủ một trong các token bạn đang cố gắng hoán đổi trong Nhóm Thanh Khoản: đó có thể là token vốn hóa nhỏ mà ít người giao dịch.

Tuy nhiên, cũng có khả năng bạn đang cố gắng giao dịch token lừa đảo không thể bán được. Trong trường hợp này, PancakeSwap không thể chặn token hoặc hoàn lại tiền.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Bạn đang cố gắng thêm/xóa thanh khoản khỏi nhóm thanh khoản (LP), nhưng không có đủ một trong hai token trong cặp.

{% tabs %}
{% tab title="Giải pháp" %}
**Làm mới trang và thử lại, hoặc thử lại sau.**

Vẫn không hoạt động?

1. Nhấn vào biểu tượng cài đặt trên trang thanh khoản.
2. Tăng mức độ chịu đựng trượt giá một chút và thử lại.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="Lý do" %}
Lỗi này xảy ra do cố gắng thêm hoặc xóa thanh khoản cho nhóm thanh khoản (LP) với số lượng không đủ của token A hoặc token B (một trong các token trong cặp).

Có thể là giá đang cập nhật quá nhanh và mức độ chịu đựng trượt giá của bạn quá thấp.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Giải pháp cho người dùng kỹ thuật" %}
OK, bạn thực sự quyết tâm sửa điều này. Chúng tôi thực sự không khuyến nghị làm điều này trừ khi bạn biết mình đang làm gì.

Hiện tại không có cách đơn giản để giải quyết vấn đề này từ trang web PancakeSwap: bạn sẽ cần tương tác trực tiếp với hợp đồng. Bạn có thể thêm thanh khoản trực tiếp qua hợp đồng Router, trong khi đặt amountAMin thành một lượng nhỏ, sau đó rút tất cả thanh khoản.

**Phê duyệt hợp đồng LP**

Truy cập vào hợp đồng của token LP bạn đang cố gắng phê duyệt.\
Ví dụ, đây là cặp ETH/WBNB: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Chọn **Write Contract**, sau đó **Connect to Web3** và kết nối ví của bạn. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. Trong **mục "1. approve",** phê duyệt token LP cho router bằng cách nhập
   1. spender (address): nhập địa chỉ hợp đồng của token LP bạn đang cố gắng tương tác
   2. value (uint256): -1

**Truy vấn "balanceOf"**

1. Chuyển sang **Read Contract.**
2. Trong **5. balanceOf**, nhập địa chỉ ví của bạn và nhấn **Query**.
3. Ghi chú con số được xuất ra. Nó hiển thị số dư của bạn trong LP theo định dạng uint256, mà bạn sẽ cần ở bước tiếp theo.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**Thêm hoặc Xóa Thanh Khoản**

Truy cập hợp đồng router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Chọn **Write Contract** và **Connect to Web3** như trên.
2. Tìm **addLiquidity** hoặc **removeLiquidity** (tùy thuộc vào những gì bạn đang cố gắng làm)
3. Nhập địa chỉ token của cả hai token trong LP.
4. Trong **liquidity (uint256),** nhập số uint256 bạn có được từ "balanceOf" ở trên.
5. Đặt **amountAMin** hoặc **amountBMin** thấp: thử 1 cho cả hai.
6. Thêm địa chỉ ví của bạn vào **to (address)**.
7. Deadline phải là thời gian epoch lớn hơn thời gian thực thi giao dịch.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
Điều này có thể gây ra trượt giá rất cao và có thể khiến người dùng mất một số tiền nếu bị chạy trước giao dịch
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Thử lại, nhưng xác nhận (ký và phát sóng) giao dịch ngay khi bạn tạo ra nó.

Điều này xảy ra vì bạn bắt đầu thực hiện giao dịch, nhưng bạn không ký và phát sóng nó cho đến khi quá thời hạn. Điều đó có nghĩa là bạn không nhấn "Confirm" đủ nhanh.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Thử chỉnh sửa số lượng trên trường "To". Do đó đặt ký hiệu "(estimated)" vào "From". Sau đó bắt đầu hoán đổi ngay lập tức.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

Điều này thường xảy ra khi bạn đang cố gắng hoán đổi token có phí riêng.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

Đảm bảo bạn có nhiều hơn 30% token trong ví so với số lượng bạn dự định giao dịch, hoặc thử giao dịch số lượng thấp hơn. Nếu bạn muốn bán tối đa có thể, hãy thử 70% hoặc 69% thay vì 100%.\
Được gây ra bởi thiết kế của các token Restorative Rebase như tDoge hoặc tBTC.\
[Hiểu cách hoạt động của các token rebase phục hồi](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Một nguyên nhân có thể khác của vấn đề này là nhà phát hành token độc hại vừa đình chỉ giao dịch cho token của họ. Hoặc họ đã làm cho hành động bán chỉ có thể thực hiện được cho các địa chỉ ví được chọn. Hãy luôn tự nghiên cứu để tránh bất kỳ gian lận tiềm năng nào. Nếu token bạn đang cố gắng hoán đổi nhưng thất bại với mã lỗi này đến từ airdrop, đó rất có thể là lừa đảo. Vui lòng không thực hiện bất kỳ phê duyệt token nào hoặc theo bất kỳ liên kết nào, tài sản của bạn có thể gặp rủi ro nếu bạn làm như vậy.

### Giao dịch không thể thành công

Thử giao dịch số lượng nhỏ hơn, hoặc tăng mức độ chịu đựng trượt giá qua biểu tượng cài đặt và thử lại. Điều này được gây ra bởi thanh khoản thấp.

### **Price Impact too High**

Thử giao dịch số lượng nhỏ hơn, hoặc tăng mức độ chịu đựng trượt giá qua biểu tượng cài đặt và thử lại. Điều này được gây ra bởi thanh khoản thấp.

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Giải pháp" %}
**Nếu bạn gặp lỗi này khi xóa thanh khoản khỏi cặp BNB:**

Vui lòng chọn "Receive WBNB" và thử lại.

**Nếu bạn gặp lỗi này khi cố gắng hoán đổi:**

Vui lòng liên hệ với đội dự án của token bạn đang cố gắng hoán đổi. \*\*\*\* Vấn đề này phải được giải quyết bởi đội dự án.
{% endtab %}

{% tab title="Lý do" %}
**Vấn đề này (khi hoán đổi) được gây ra bởi các token đã hardcode router PancakeSwap V1 vào hợp đồng của họ.**

Mặc dù thực hành này không được khuyến nghị nhất, lý do các dự án này đã làm điều này có vẻ là do tokenomics của họ, trong đó mỗi lần mua gửi một % của token đến LP.

Các dự án bị ảnh hưởng có thể sẽ không hoạt động với router V2: họ rất có thể cần tạo phiên bản mới của token trỏ đến địa chỉ router mới của chúng tôi và di chuyển bất kỳ người giữ token hiện tại nào sang token mới của họ.

Chúng tôi khuyến nghị rằng bất kỳ dự án nào đã tạo các token như vậy cũng nên nỗ lực ngăn người dùng thêm chúng vào V2 LP.

Địa chỉ router cập nhật là [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

Khi cố gắng hoán đổi token, giao dịch thất bại và thông báo lỗi này được hiển thị. Lỗi này đã được báo cáo trên các thiết bị di động sử dụng Trust Wallet.

{% tabs %}
{% tab title="Giải pháp" %}
1. Thử lại giao dịch với mức độ cho phép trượt giá tăng lên.
2. Nếu 1. không giải quyết được vấn đề của bạn, hãy xem xét sử dụng ví khác như SafePal cho giao dịch của bạn.
{% endtab %}

{% tab title="Lý do" %}
**Điều này thường xảy ra khi giao dịch các token với mức độ cho phép trượt giá không đủ trên Trust Wallet.**

Chi tiết chính xác của vấn đề vẫn đang được điều tra.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Khi cố gắng hoán đổi token, giao dịch thất bại và thông báo lỗi này được hiển thị. Lỗi này đã được báo cáo trên các nền tảng.

{% tabs %}
{% tab title="Giải pháp" %}
1. Kiểm tra để đảm bảo bạn có đủ tài sản.
2. Đảm bảo bạn đã cấp cho hợp đồng quyền chi tiêu số lượng tài sản bạn đang cố gắng giao dịch.
{% endtab %}

{% tab title="Lý do" %}
Lỗi này xảy ra khi giao dịch token với mức độ cho phép không đủ, hoặc khi ví có số dư không đủ.\
Nếu bạn đang giao dịch token với Restorative Rebase như tau assets tDoge hoặc tBTC, hãy đảm bảo bạn hiểu cách chúng hoạt động trước với [hướng dẫn về token Rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

## **Sự Cố Với Farm**

### Fail with error 'ds-math-sub-underflow'

Bạn đã hết mức độ cho phép của token LP cho hợp đồng MasterChef.

**Sử dụng trình quản lý phê duyệt token như unrekt hoặc BscScan để**

## **Sự Cố Với Syrup Pool**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

Bạn không có đủ SYRUP trong ví để hủy staking từ nhóm CAKE-CAKE.

**Lấy ít nhất số lượng SYRUP bằng với số lượng CAKE bạn đang cố gắng hủy staking.**

1. Mua SYRUP trên sàn giao dịch. Nếu bạn muốn hủy staking 100 CAKE, bạn cần ít nhất 100 SYRUP.
2. Thử hủy staking lại.

Nếu điều đó vẫn thất bại, bạn có thể thực hiện "emergencyWithdraw" từ hợp đồng trực tiếp để hủy staking token của bạn.

1. Truy cập: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Nhấp vào **"Connect to Web3"** và kết nối ví của bạn. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. Trong phần **"4. emergencyWithdraw"**, nhập "0" và nhấp vào "Write".

Thao tác này sẽ hủy staking token của bạn và mất bất kỳ phần thưởng CAKE chưa thu hoạch nào.

{% hint style="warning" %}
**Điều này sẽ mất bất kỳ phần thưởng nào bạn chưa thu hoạch.**
{% endhint %}

Để ngăn điều này xảy ra lại, **đừng bán SYRUP của bạn.** Bạn vẫn cần nó để hủy staking từ nhóm "Stake CAKE Earn CAKE".

Lỗi này đã xảy ra vì bạn đã bán hoặc chuyển token SYRUP. SYRUP được đúc theo tỷ lệ 1:1 với CAKE khi bạn stake trong CAKE-CAKE Syrup Pool. SYRUP phải được đốt theo tỷ lệ 1:1 với CAKE khi gọi leaveStaking (hủy staking CAKE của bạn khỏi nhóm), vì vậy nếu bạn không có đủ, bạn không thể hủy staking khỏi nhóm.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Lỗi Hết Gas

> Warning! Error encountered during contract execution \[out of gas]

Bạn đã đặt giới hạn gas thấp khi cố gắng thực hiện giao dịch.

{% tabs %}
{% tab title="Giải pháp" %}
Thử tăng **giới hạn gas** thủ công (không phải giá gas!) trong ví trước khi ký giao dịch.

Giới hạn 200000 thường là đủ.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

Ví dụ trên là từ Metamask; kiểm tra tài liệu ví của bạn nếu bạn không chắc cách điều chỉnh giới hạn gas.
{% endtab %}

{% tab title="Lý do" %}
Về cơ bản, ví của bạn (Metamask, Trust Wallet, v.v.) không thể hoàn thành những gì nó đang cố gắng làm.

Ví của bạn ước tính rằng giới hạn gas quá thấp, vì vậy lời gọi hàm hết gas trước khi lời gọi hàm hoàn thành.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Giải pháp" %}
1. Sử dụng Unrekt.net để thu hồi quyền phê duyệt cho hợp đồng thông minh bạn đang cố gắng tương tác
2. Phê duyệt lại hợp đồng, không đặt giới hạn cho mức độ chi tiêu được phép
3. Thử tương tác với hợp đồng lại.
{% endtab %}

{% tab title="Lý do" %}
Điều này xảy ra khi bạn đặt giới hạn cho mức độ chi tiêu được phép khi bạn lần đầu phê duyệt hợp đồng, sau đó cố gắng hoán đổi nhiều hơn giới hạn.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

Bạn có thể đang cố gắng hủy staking từ Syrup Pool với phần thưởng thấp. Giải pháp bên dưới.

Nếu không, bạn có thể đang cố gắng gửi token mà bạn không có trong ví (ví dụ, cố gắng gửi token đã được gán cho giao dịch đang chờ xử lý). Trong trường hợp này, chỉ cần đảm bảo bạn có token bạn đang cố gắng sử dụng.

{% tabs %}
{% tab title="Giải pháp" %}
Đầu tiên,[ thông báo cho đội ngũ](../social-accounts.md) nhóm nào bạn đang cố gắng hủy staking, để họ có thể bổ sung phần thưởng. Nếu bạn đang vội hủy staking và không muốn mất phần thưởng đang chờ, hãy thử emergencyWithdraw:

Bạn có thể thực hiện "emergencyWithdraw" từ hợp đồng trực tiếp để hủy staking token của bạn.

1. Tìm địa chỉ hợp đồng của Syrup Pool bạn đang cố gắng hủy staking. Bạn có thể tìm thấy nó trong nhật ký giao dịch của ví.
2. Truy cập [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) và trong thanh tìm kiếm, nhập địa chỉ hợp đồng.
3. Chọn **Write Contract.**
4. Nhấp vào **"Connect to Web3"** và kết nối ví của bạn.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. Trong phần **"3. emergencyWithdraw",** và nhấp vào "Write".

Thao tác này sẽ hủy staking token của bạn và mất bất kỳ phần thưởng chưa thu hoạch nào.

{% hint style="warning" %}
**Điều này sẽ mất bất kỳ phần thưởng nào bạn chưa thu hoạch.**
{% endhint %}
{% endtab %}

{% tab title="Lý do" %}
Lỗi này thường xuất hiện khi bạn đang cố gắng hủy staking từ Syrup Pool cũ, nhưng không còn đủ phần thưởng trong nhóm để bạn thu hoạch khi rút tiền. Điều này gây ra giao dịch thất bại.
{% endtab %}
{% endtabs %}

## **Sự Cố Với Dự Đoán**

Kiểm tra [Broken link](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")

## **Các Sự Cố Khác**

### Lỗi Provider

> Provider Error\
> No provider was found

Điều này xảy ra khi bạn cố gắng kết nối qua extension trình duyệt như MetaMask hoặc Binance Chain Wallet, nhưng bạn chưa cài đặt extension.

{% tabs %}
{% tab title="Giải pháp" %}
Cài đặt extension trình duyệt chính thức để kết nối, hoặc đọc hướng dẫn của chúng tôi về [cách kết nối ví với PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide).
{% endtab %}
{% endtabs %}

### Unsupported Chain ID

Chuyển chuỗi của bạn sang BNB Smart Chain. Kiểm tra tài liệu ví của bạn để có hướng dẫn nếu bạn cần trợ giúp.

### Already processing eth\_requestAccounts. Please wait.

Đảm bảo bạn đã đăng nhập vào ứng dụng ví và nó được kết nối với BNB Smart Chain.

### Sự cố khi mua SAFEMOON và các token tương tự

Để giao dịch SAFEMOON, bạn phải nhấp vào biểu tượng cài đặt và **đặt mức độ chịu đựng trượt giá lên 12% hoặc hơn.**\
Điều này là vì **SafeMoon tính phí 10% trên mỗi giao dịch**:

* Phí 5% = phân phối lại cho tất cả người nắm giữ hiện tại
* Phí 5% = dùng để thêm thanh khoản

Đây cũng là lý do tại sao bạn có thể không nhận được nhiều token như bạn mong đợi khi mua.\
Đọc thêm trên [Cách Mua Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Lỗi Internal JSON-RPC

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Xảy ra khi cố gắng xóa thanh khoản trên một số token qua Metamask. Nguyên nhân gốc rễ vẫn chưa được biết. Thử sử dụng ví thay thế.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

Bạn không có đủ BNB để trả phí giao dịch. Bạn cần thêm BNB mạng BEP-20 trong ví.

### Lỗi: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Tăng giới hạn gas cho giao dịch trong ví của bạn. Kiểm tra tài liệu ví của bạn để tìm hiểu cách tăng giới hạn gas.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Nguyên nhân không rõ ràng. Thử các bước này trước khi thử lại:

1. Tăng giới hạn gas
2. Tăng trượt giá
3. Xóa bộ nhớ đệm

## **Sự Cố Với Hồ Sơ**

### Oops! We couldn't find any Pancake Collectibles in your wallet.

Chúng tôi đang điều tra logic đằng sau vấn đề này. Trong thời gian đó, vui lòng thử cách giải quyết tạm thời.

{% tabs %}
{% tab title="Cách giải quyết 1" %}
1. Truy cập trang "Collectible", sau đó quay lại trang hồ sơ.\
   Nếu bạn không thể tìm thấy liên kết, hãy truy cập [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles) trực tiếp.
2. Thử tạo hồ sơ lại.
{% endtab %}

{% tab title="Cách giải quyết 2" %}
Thay đổi môi trường.

* Xóa bộ nhớ đệm và thử lại.
* Thử lại trên trình duyệt khác.
* Thử lại trên ứng dụng ví khác.
* Thử lại trên mạng khác (chuyển đổi giữa Wi-Fi và mạng di động)
{% endtab %}
{% endtabs %}

### Kiểm tra tên người dùng cứ quay vòng

Có hai nguyên nhân có thể.

1. Bạn có nhiều ví được cài đặt trên trình duyệt.
2. Vấn đề mạng.

{% tabs %}
{% tab title="Giải pháp 1" %}
Nguyên nhân gốc rễ: Bạn có nhiều ví được cài đặt trên trình duyệt.\
\
Nó có thể gây ra xung đột giữa các ví. Điều này nằm ngoài tầm kiểm soát của PancakeSwap và chúng tôi không thể làm gì.

1. Chỉ có một ví duy nhất được cài đặt trên trình duyệt, xóa những ví còn lại.
2. Kết nối lại ví và thử cài đặt tên người dùng lại.
{% endtab %}

{% tab title="Giải pháp 2" %}
Nguyên nhân gốc rễ: Mạng không ổn định.

Bạn phải thử lại.

1. Xóa hoàn toàn những gì đã được nhập trong trường văn bản.
2. Nhập lại tên người dùng, sau đó đợi vài giây.
3. Nếu không hoạt động, tải lại trang và thử lại.
{% endtab %}
{% endtabs %}
