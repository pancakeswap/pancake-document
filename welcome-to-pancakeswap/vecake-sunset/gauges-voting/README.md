---
description: Sử dụng veCAKE của bạn để bỏ phiếu và quyết định cách phân phối CAKE emission
hidden: true
---

# Bỏ phiếu Gauges

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### Gauge là gì?

Để hiểu về bỏ phiếu gauges, bạn có thể nghĩ về bất kỳ sản phẩm nào yêu cầu CAKE emission như một loạt các gauge. Điều này bao gồm các farm, pool phần thưởng CAKE hàng tuần, vault của position manager, v.v.

Những người nắm giữ veCAKE hiện có thể sử dụng veCAKE như phiếu bầu để quyết định bao nhiêu % CAKE đi vào sản phẩm nào. Pool nào tích lũy được nhiều veCAKE hơn thông qua Bỏ phiếu Gauges, thì sẽ được phân bổ nhiều CAKE emission hơn cho pool thanh khoản / vault của position manager bên dưới.

{% hint style="info" %}
Phiếu bầu trong mỗi epoch (E-0) xác định CAKE emission cho epoch tiếp theo (E+1), và những thay đổi này chỉ có hiệu lực sau khi epoch hiện tại kết thúc.
{% endhint %}

#### Loại Gauge

Có hai loại gauge - 'core' và 'non-core'. CAKE emission cho loại trước được kiểm soát bởi Kitchen, trong khi cộng đồng ảnh hưởng đến emission cho các pool 'non-core' bằng cách bỏ phiếu với veCAKE.

1. Gauge 'core' bao gồm các cặp có token chính và stablecoin (WBTC, ETH, BNB, USDC, USDT, v.v.) - Kitchen sẽ đảm bảo các cặp này nhận đủ phần thưởng CAKE vì chúng đóng góp đáng kể vào doanh thu giao thức
2. Gauge 'non-core' đại diện cho tất cả các gauge khác không được phân loại là gauge 'core'

## Cách Bỏ phiếu?

### 1 - Hiểu lịch bỏ phiếu

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Bỏ phiếu trọng số gauge được thực hiện mỗi hai tuần. Đầu epoch, giống như chia sẻ doanh thu, là lúc 00:00 UTC mỗi thứ Năm chẵn.

Trong ví dụ trên:

* Epoch 1 bắt đầu lúc 00:00 UTC, ngày 1, thứ Năm Tuần 1.
* Epoch 1 kết thúc 2 tuần sau, lúc 00:00 UTC, ngày 15, thứ Năm Tuần 3.
* Người dùng có thể bỏ phiếu trong khoảng 00:00 UTC từ ngày 1 đến ngày 14.
* **KHÔNG** có phiếu bầu nào được bỏ trong khoảng 00:00 UTC từ ngày 14 đến ngày 15 vì các phiếu đang được điều chỉnh và kiểm đếm.
* Kết quả bỏ phiếu sẽ được chụp snapshot lúc 00:00 UTC vào ngày 15. Kết thúc Epoch 1.
* Kết quả bỏ phiếu sẽ được áp dụng trong vòng 72 giờ sau khi epoch đóng.

### 2 - Đủ điều kiện

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Vì veCAKE đang giảm dần theo thời gian khóa còn lại, kết quả bỏ phiếu sẽ được chụp snapshot vào cuối mỗi epoch. Điều này bao gồm tổng số veCAKE và veCAKE của mỗi người dùng.

Trong ví dụ trên:

* Kết quả cho Epoch 1 sẽ dựa trên số dư veCAKE lúc 00:00 UTC, ngày 15.
* Người dùng có vị trí veCAKE mở khóa trước hoặc bằng ngày 15 sẽ có số dư veCAKE bằng 0 tại thời điểm snapshot. Do đó họ không có quyền bỏ phiếu cho Epoch 1.

Do đó, để đủ điều kiện, bạn phải có vị trí veCAKE đang hoạt động, mở khóa **SAU** thời gian kết thúc/snapshot của epoch hiện tại.

Trong ví dụ trên:

* Nếu bạn muốn bỏ phiếu trong epoch 1, bạn phải có vị trí veCAKE mở khóa vào ngày 21 trở lên, hoặc thứ Năm tuần 3.

### 3 - Kiểm tra kết quả bỏ phiếu hiện tại

Truy cập "CAKE staking", cuộn xuống và tìm phần "Gauges Voting", sau đó nhấp "Check Gauges".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

Ở phần trên bên trái, bạn có thể tìm thấy:

* veCAKE của bạn.
* Thời gian snapshot và thời gian kết thúc bỏ phiếu cho epoch hiện tại.
* Tổng số phần thưởng CAKE được phân phối trong epoch tiếp theo dựa trên kết quả bỏ phiếu từ epoch hiện tại.
* Tổng số phiếu bầu veCAKE đã được bỏ.

Ở phần trên bên phải, bạn có thể tìm thấy biểu đồ tròn biểu diễn % mỗi gauge nhận được.

Ở phần dưới, có danh sách đầy đủ mọi gauge bỏ phiếu. Với số phiếu bầu họ nhận được và % trọng số dự kiến họ đang nhận trong epoch hiện tại. Cũng có trường "boost" và "caps", chi tiết về hai đặc điểm gauge quan trọng. Tiếp tục đọc để biết thêm chi tiết.

#### Gauge Boost và Emission Cap

Để đảm bảo phần thưởng CAKE đến với các gauge hiệu quả nhất. Mỗi gauge có thể được áp dụng boost và/hoặc emission cap. Hai đặc điểm này đều có thể tồn tại cùng nhau.

Gauge Boost là hệ số nhân được áp dụng cho số phiếu bầu mà một gauge nhận được, từ 1x đến 2.5x (các gauge cho pool V3 bị giới hạn ở 2x). Đây là để khuyến khích phiếu bầu và thanh khoản cho các cặp giao dịch quan trọng.

Emission cap là mức trần tối đa về % trọng số mà một gauge có thể nhận được, từ 2% đến 20%. Đây là để thúc đẩy sự công bằng trong phân bổ và ngăn chặn lạm dụng hệ thống gauge.

Ví dụ:

* Một gauge có 10 phiếu, boost 2x và cap 15%. Tổng phiếu là 100.
* Sau khi áp dụng boost, gauge này sẽ có 20 phiếu, 20% trọng số so với tổng (100).
* Tuy nhiên, vì nó có cap 15%, % phần thưởng CAKE cuối cùng mà gauge này nhận được trong epoch tiếp theo sẽ được điều chỉnh xuống 15%.

#### Gauge Boost và Emission Cap được xác định như thế nào?

Trong quá trình ứng dụng gauge, chúng tôi yêu cầu người nộp đơn đề xuất giá trị hệ số nhân boost và % emission cap họ muốn gán cho gauge. Những điều này phải được bỏ phiếu bởi những người nắm giữ veCAKE, cùng với toàn bộ ứng dụng gauge.

Lựa chọn mặc định cho tất cả các gauge là hệ số nhân 1.00x và emission cap 5%. Chúng có thể được thay đổi với các đề xuất trong tương lai.

{% hint style="info" %}
Lưu ý rằng kết quả bỏ phiếu được cập nhật hàng tuần. Các con số được tính dựa trên số dư veCAKE lúc 00:00 UTC, thứ Năm sắp tới.
{% endhint %}

### 4 - Thêm gauge để bỏ phiếu

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Để bỏ phiếu cho một gauge, cuộn xuống và tìm phần "My Votes". Nhấp "Add Gauge".

Trong cửa sổ bật lên, bạn có thể thêm các gauge vào danh sách phiếu bầu của mình bằng cách nhấp biểu tượng "+" màu xanh. Bạn có thể tìm thấy kết quả bỏ phiếu hiện tại trong danh sách, cùng với boost và caps.

Để nhanh chóng tìm một gauge, bạn có thể sử dụng bộ lọc để lọc các gauge theo blockchain, mức phí và loại thanh khoản. Hoặc nhập ticker token vào trường tìm kiếm.

### 5 - Chọn % veCAKE để bỏ phiếu cho mỗi gauge

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Sau khi thêm các gauge, bạn có thể chọn bao nhiêu % veCAKE của mình sẽ đi vào mỗi gauge.

Điều này vì:

* veCAKE giảm dần theo thời gian khóa còn lại. Rất khó thực tế để ước tính và tính toán chính xác bao nhiêu veCAKE để bỏ phiếu.
* Rất phiền khi phải bỏ phiếu lại trong mỗi epoch sắp tới. Do đó, bỏ phiếu gauges được thiết kế để mang theo quyết định bỏ phiếu của bạn qua tất cả các epoch sắp tới cho đến khi bạn bỏ một phiếu mới.

Trong ví dụ trên:

* Hiện tại, tôi có 2.62 veCAKE.
* Tôi quyết định phân bổ 80% cho CAKE-BNB, tức là 2.10 veCAKE vào lúc này.
* 20% cho USDC-ETH, tức là 0.52 veCAKE, vào lúc này.
* Tổng veCAKE của tôi sẽ giảm dần theo thời gian khóa còn lại. Tại thời điểm snapshot, tôi có thể có ít veCAKE hơn, nhưng quyết định phân chia 80% - 20% của tôi vẫn sẽ được áp dụng cho kết quả cuối cùng.
* Ngoài ra, quyết định 80% - 20% này sẽ được áp dụng cho mỗi epoch sắp tới cho đến khi tôi cập nhật nó bằng cách gửi yêu cầu bỏ phiếu mới. Hoặc cho đến khi veCAKE của tôi về 0 do mở khóa.

Sau khi xác nhận quyết định của mình, hãy nhấp "Submit vote" và xác nhận trong ví của bạn.

### 6 - Cập nhật phiếu bầu của bạn

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Sau khi phiếu bầu được gửi, bạn có thể thấy phiếu bầu của mình được cập nhật thành "Current Votes". Và veCAKE còn lại sẽ được cập nhật.

Lưu ý rằng quyết định bỏ phiếu cho mỗi gauge chỉ có thể được cập nhật mỗi 10 ngày. Sau khi bạn gửi yêu cầu bỏ phiếu, tất cả các gauge đã bỏ phiếu sẽ được áp dụng thời gian chờ 10 ngày trước khi bạn có thể gửi yêu cầu cập nhật khác.

Để cập nhật quyết định bỏ phiếu của bạn, hãy thay đổi % phần trăm và gửi lại.

{% hint style="info" %}
Lưu ý rằng sau khi nhận thêm veCAKE bằng cách thêm CAKE hoặc gia hạn thời gian khóa. Bạn cần cập nhật thủ công mỗi gauge bằng cách gửi lại yêu cầu bỏ phiếu.

Thời gian chờ 10 ngày vẫn áp dụng bất kể bạn có thay đổi quyết định % của mình hay không.
{% endhint %}
