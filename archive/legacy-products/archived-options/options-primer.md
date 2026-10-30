# Cẩm nang cơ bản về Options



{% hint style="danger" %}
\[ĐÃ LƯU TRỮ] Options – Tính đến ngày 11 tháng 3 năm 2025\
Nếu bạn vẫn còn thanh khoản cần rút, vui lòng rút ngay bằng cách truy cập https://www.stryke.xyz/en/trade.
{% endhint %}



## Options là gì?

Options là các hợp đồng phái sinh cho người mua quyền, nhưng không phải nghĩa vụ, mua (quyền chọn mua - call option) hoặc bán (quyền chọn bán - put option) một tài sản cơ sở ở mức giá định trước (giá thực hiện - strike price) trong một khoảng thời gian xác định (ngày đáo hạn).

## Các loại Options

### Call Options

Call option cho người nắm giữ quyền mua tài sản cơ sở ở mức giá thực hiện đã thỏa thuận vào hoặc trước ngày đáo hạn. Các trader mua call option khi họ kỳ vọng giá của tài sản cơ sở sẽ tăng. Điều này cho phép họ hưởng lợi từ khả năng giá tăng mà không cần sở hữu hoàn toàn tài sản cơ sở.

> Một trader mua call option trên Bitcoin với giá thực hiện $50,000 đáo hạn sau một tháng. Nếu giá Bitcoin tăng trên $50,000 trong tháng đó, nhà đầu tư có thể thực hiện quyền chọn để mua Bitcoin ở mức $50,000, có khả năng thu lợi nhuận từ chênh lệch giá.

### Put Options

Put option cho người nắm giữ quyền bán tài sản cơ sở ở mức giá thực hiện đã thỏa thuận vào hoặc trước ngày đáo hạn. Các trader mua put option khi họ kỳ vọng giá của tài sản cơ sở sẽ giảm. Điều này cho phép họ kiếm lợi nhuận từ khả năng giá giảm mà không cần bán khống tài sản cơ sở. Thông thường, put option cũng được dùng để phòng ngừa rủi ro giảm giá đối với danh mục đầu tư.

> Một trader mua put option trên Ethereum với giá thực hiện $3,000 đáo hạn sau hai tuần. Nếu giá Ethereum giảm xuống dưới $3,000 trong khoảng thời gian đó, trader có thể thực hiện quyền chọn để bán Ethereum ở mức $3,000, qua đó giảm thiểu khoản lỗ tiềm tàng.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Các vị thế Options

Với mỗi loại option, có hai vị thế khả dĩ:

### **Long Option (Người mua Option)**&#x20;

Vị thế này yêu cầu trả trước một khoản phí (premium) để có được option. Nếu option có lãi, người nắm giữ sẽ nhận được khoản thanh toán.

### **Short Option (Người viết/bán Option)**

Ở vị thế này, người bán nhận trước một khoản premium khi phát hành option. Tuy nhiên, nếu option có lãi (đối với người mua; dựa trên giá cơ sở, giá thực hiện và loại option), người bán có nghĩa vụ trả một khoản thanh toán.

## Option kiểu Mỹ và kiểu Châu Âu

* **Option kiểu Mỹ:** Có thể thực hiện bất cứ lúc nào trước ngày đáo hạn. Sự linh hoạt này khiến chúng có giá trị hơn option kiểu Châu Âu.
* **Option kiểu Châu Âu:** Chỉ có thể thực hiện vào ngày đáo hạn. Chúng thường rẻ hơn option kiểu Mỹ do thiếu tính linh hoạt.

## Khi nào nên dùng Options?

Dưới đây là một số trường hợp sử dụng ví dụ:

1. **Đầu cơ:** Một nhà đầu tư tin rằng giá Bitcoin sẽ tăng trong tháng tới. Họ mua call option trên Bitcoin để kiếm lợi nhuận từ đợt tăng giá dự kiến.
2. **Phòng ngừa rủi ro:** Một validator tiền mã hóa muốn phòng ngừa khả năng giá Ethereum giảm. Họ mua put option trên Ethereum để bảo vệ khỏi khoản lỗ nếu giá giảm xuống dưới một mức nhất định.
3. **Tạo thu nhập:** Một nhà đầu tư tiền mã hóa nắm giữ lượng lớn Ether quyết định viết call option trên số tài sản đang nắm giữ, kiếm premium trong khi vẫn tham gia vào các biến động giá tăng tiềm năng.

## Định giá Options

Định giá options rất phức tạp và liên quan đến nhiều yếu tố, trong đó mô hình Black-Scholes được sử dụng phổ biến nhất.&#x20;

Các yếu tố chính ảnh hưởng đến định giá options bao gồm:

* **Giá tài sản cơ sở:** Giá thị trường hiện tại của tài sản cơ sở.
* **Giá thực hiện:** Mức giá mà người nắm giữ option có thể mua hoặc bán tài sản cơ sở.
* **Biến động:** Mức độ dao động giá của tài sản cơ sở.&#x20;
* **Thời gian đến ngày đáo hạn:** Thời gian còn lại cho đến khi option hết hạn.
* **Lãi suất:** Tỷ suất lợi nhuận phi rủi ro.

Định giá options xác định khoản premium/phí mà người viết nhận được khi một trader option mua option của họ. Người viết option phải đối mặt với rủi ro phải trả thanh toán nếu option của họ đáo hạn ở trạng thái In-The-Money hay ITM (có lợi cho người mua). Do đó, premium mà họ kiếm được từ người mua phải phản ánh hợp lý xác suất xảy ra sự kiện ITM.

Premium của options CLAMM PancakeSwap được tính từ mô hình Black-Scholes với các giả định sau:

* Lãi suất phi rủi ro được giả định bằng không.
* Biến động dựa trên biến động lịch sử 30 ngày của tài sản cơ sở \[dùng làm đại diện cho biến động ngầm định (IV)].

Một vài ngoại lệ bao gồm:

* IV của $ETH và $BTC được lấy trực tiếp từ Deribit nếu giá thực hiện khớp nhau. Nếu giá thực hiện không khớp, các mức giá thực hiện gần nhất phía trên và phía dưới từ Deribit được tính trọng số theo mức độ chênh lệch để xác định IV.
* $ARB sử dụng biến động lịch sử dựa trên beta 30 ngày bằng cách tính giá thực hiện hiệu dụng của tài sản cơ sở so với $ETH để ngoại suy IV, sau đó nhân với beta của tài sản cơ sở so với $ETH

Các tài sản có biến động cao sẽ có premium đắt hơn các tài sản ít biến động hơn vì người viết option phải chịu rủi ro lớn hơn khi option đáo hạn ITM.

## Thanh toán Options

### Điều kiện thanh toán

* Việc thanh toán được xác định dựa trên trạng thái moneyness của option tại thời điểm đáo hạn.
* Khoản thanh toán chỉ được tính nếu option ở trạng thái In-The-Money (ITM) khi thực hiện.

### Điều kiện ITM

* **Call Option:** Nếu Giá giao ngay tại thời điểm thanh toán > Giá thực hiện
* **Put Option:** Nếu Giá giao ngay tại thời điểm thanh toán < Giá thực hiện

### Cách tính thanh toán

* **Call Option:** #Options \* (Giá giao ngay tại thời điểm thanh toán - Giá thực hiện)
* **Put Option:** #Options \* (Giá thực hiện - Giá giao ngay tại thời điểm thanh toán)

### Moneyness

Moneyness là giá trị nội tại của một option, được xác định bằng cách so sánh giá thực hiện với giá giao ngay tại thời điểm thực hiện.

### Phân loại

1. Out-of-The-Money (OTM):
   1. Một option là OTM nếu giá giao ngay tại thời điểm thanh toán khác với giá thực hiện và không có giá trị nào được trao đổi nếu thanh toán diễn ra ngay lập tức.
   2. Điều kiện:
      1. Call Option: Giá giao ngay < Giá thực hiện
      2. Put Option: Giá giao ngay > Giá thực hiện

{% hint style="info" %}
Một call option $ETH với giá thực hiện $2,000 sẽ là OTM nếu giá giao ngay là $1,800 ($1,800 < $2,000 tức là OTM).
{% endhint %}

2. At-The-Money (ATM):
   1. Một option là ATM nếu giá giao ngay tại thời điểm thanh toán bằng giá thực hiện và không có giá trị nào được trao đổi nếu thanh toán diễn ra ngay lập tức.
   2. Điều kiện: Cả Call và Put Option: Giá giao ngay = Giá thực hiện

{% hint style="info" %}
Cả call option và put option $ETH với giá thực hiện $1,800 đều sẽ là ATM nếu giá giao ngay cũng là $1,800 ($1,800 = $1,800 tức là ATM).
{% endhint %}

3. In-The-Money (ITM):
   1. Một option là ITM nếu giá giao ngay tại thời điểm thanh toán khác với giá thực hiện và có giá trị được trao đổi nếu thanh toán diễn ra ngay lập tức.
   2. Điều kiện:
      1. Call Option: Giá giao ngay > Giá thực hiện
      2. Put Option: Giá giao ngay < Giá thực hiện

{% hint style="info" %}
Một call option $ETH với giá thực hiện $1,600 sẽ là ITM nếu giá giao ngay là $1,800 ($1,800 > $1,600 tức là ITM).
{% endhint %}

Khoản thanh toán mà người mua option kiếm được bằng với tài sản thế chấp mà người viết option bị mất. Khoản thanh toán không bao gồm premium đã trả, khoản này được tính đến khi tính lãi hoặc lỗ cho người mua và người viết option.
