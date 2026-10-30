---
description: '2026-09-04'
---

# Sự kém hiệu quả vốn của RWA — và cách Shared Inventory giải quyết

Một thử nghiệm nghiên cứu điển hình của PancakeSwap (Phần 1: Thiết lập)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

Đây là phần đầu tiên trong nghiên cứu điển hình gồm hai phần. Trong phần này, chúng tôi trình bày vấn đề hiệu quả vốn thực sự mà các tổ chức phát hành tài sản RWA gặp phải, giới thiệu cách Shared Inventory Hook (SIH) của PancakeSwap được thiết kế để giải quyết vấn đề đó, và giới thiệu một thử nghiệm nghiên cứu điển hình trực tiếp để kiểm chứng bằng dữ liệu onchain.

Trong vài tuần tới, chúng tôi sẽ đăng Phần 2: Kết quả.

***

### 🧩 Vấn đề hiệu quả vốn là gì?

Ngành RWA yêu thích một con số: **đã token hóa được bao nhiêu.** Đó là tiêu đề của hầu hết mọi báo cáo - một loại tài sản mới xuất hiện, hàng tỷ đô la được phát hành, mức tăng trưởng hàng trăm phần trăm.

Tuy nhiên có một con số thứ hai bị chìm đi, và có thể là tín hiệu nổi bật hơn: **bao nhiêu trong số đó thực sự có thể giao dịch được?**

Khoảng cách giữa hai con số này chính là điểm mấu chốt. Trên công cụ theo dõi chuẩn [rwa.xyz](http://rwa.xyz), lượng giá trị được _đại diện_ onchain vượt xa lượng giá trị có thể được _giao dịch_ tại bất kỳ thời điểm nào — dữ liệu cho thấy giá trị bị khóa, tham chiếu và đã phân phối lớn hơn **hơn một bậc độ lớn so với lượng nằm trong các sổ lệnh có thể giao dịch.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_Nguồn: app.rwa.xyz/stocks_

Đối với một tổ chức phát hành RWA, đây chính là cái bẫy. Token hóa một cổ phiếu, một ETF hay một trái phiếu kho bạc là phần dễ - làm cho nó giao dịch sát giá và ổn định mới là thách thức, và đó là nơi hiệu quả vốn thành hay bại. Mục tiêu cuối cùng là để các trader _thực sự giao dịch_ tài sản token hóa một cách dễ dàng và rẻ - đó mới là nơi khối lượng giao dịch và phí phát sinh.

Và đây là lý do nó cụ thể là vấn đề về _hiệu quả vốn_, chứ không chỉ là vấn đề thanh khoản.

#### Mỗi pool được báo giá đòi hỏi một lượng USDT độc quyền riêng

Để một cặp RWA có thể giao dịch trong pool thanh khoản tập trung (CLAMM) truyền thống, tổ chức phát hành cần có tài sản định giá — USDT — được dành riêng để người mua bán vào. Niêm yết mười cặp, mô hình CLAMM đòi hỏi phải cấp vốn cho **mười lượng USDT riêng biệt**, mỗi cặp một lượng, không lượng nào có thể hỗ trợ lượng khác. Vì vậy vốn định giá bị chia nhỏ thành các silo độc quyền.

Chúng tôi đã đo lường điều này trên chính sổ lệnh của mình. Chúng tôi lấy **7 pool cổ phiếu token hóa đang hoạt động trên PancakeSwap** (mỗi pool chạy một pool V3 CLAMM truyền thống) và thống kê lượng USDT độc quyền.

Ảnh chụp nhanh: **2 tháng 9 năm 2026.**

<table data-search="false"><thead><tr><th>Cặp</th><th>USDT độc quyền trong pool</th><th>TVL của pool</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Tổng</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

Đó là **\~$745k USDT được phân bổ độc quyền.**

Và đây mới chỉ là những mã có sổ lệnh.

SNXXB, KORUB, SOXSB và DJTB hoàn toàn không có sổ USDT CLAMM - đã token hóa nhưng khó giao dịch.

***

### 🎯 Tổ chức phát hành nên tối ưu điều gì?

Gạt bỏ cơ chế sang một bên, một tổ chức phát hành RWA phải giải quyết ba điều cốt lõi:

1. **Tài sản của họ thực sự giao dịch được một cách hiệu quả** — báo giá sát cho mọi tài sản, không chỉ các token chủ lực.
2. **Dùng ít vốn nhất có thể** để làm điều đó — Tài sản định giá rất đắt; cấp vốn độc quyền cho mười lượng USDT là không hiệu quả lắm.
3. **Không phải vận hành một bàn giao dịch —** Phát hành tài sản mà không cần vận hành hạ tầng thanh khoản mỗi ngày.

Vì vậy câu hỏi là liệu thanh khoản có thể được cấu trúc khác đi hay không — và đó là điều Shared Inventory Hook của PancakeSwap được thiết kế để giải quyết.

***

### 🥞 Shared Inventory Hook (SIH)

**SIH là một hook của PancakeSwap Infinity cho phép tổ chức phát hành RWA hỗ trợ nhiều cặp từ một kho USDT dùng chung thay vì một lượng độc quyền cho mỗi cặp.**

SIH làm được điều này bằng cách cung cấp thanh khoản đúng lúc (just-in-time), mang lại:

* Báo giá sâu hơn cho các cặp
* Tác động giá thấp hơn, đặc biệt với các giao dịch lớn
* Giải phóng vốn cho tổ chức phát hành RWA vì dùng ít vốn hơn mà báo giá được nhiều cặp hơn

Hãy xem các tuyên bố này trong thực tế.

Tính đến cùng ảnh chụp nhanh **2 tháng 9 năm 2026**, SIH nắm giữ **$635,028** hàng tồn kho trong một hook duy nhất, báo giá **11 cặp** từ **$180,467** USDT dùng chung, với mức sử dụng **87.7%**. Nhờ đó, SIH đã xử lý **$3.56M qua 17,299 giao dịch.**

Tức là **một số dư USDT dùng chung khoảng \~$700k báo giá cho khoảng \~11 cặp so với \~$745k chỉ báo giá được 7 cặp**.

Cùng một công việc, chỉ được thiết kế để ngừng nhân đôi vốn.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

Đối chiếu lại với điều các tổ chức phát hành quan tâm:

* N số dư USDT độc quyền theo cách truyền thống → ✅ một kho dùng chung với SIH
* Đã phát hành nhưng không giao dịch được → ✅ giao dịch được\
  Hàng tồn kho dùng chung được bơm đúng lúc quanh giá trực tiếp nghĩa là các token không có sổ USDT V3 vẫn có thể được báo giá, chứ không chỉ được mint.
* Vận hành một bàn giao dịch → ✅ một operator được cấp quyền\
  Tổ chức phát hành cung cấp hàng tồn kho; hook và operator của nó xử lý việc báo giá.

***

### 🔬 Dùng thử Shared Inventory Simulator

Hãy xây dựng trực giác về cách SIH vận hành với công cụ so sánh tương tác của chúng tôi **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

Đây là một phép so sánh **tổng quan, đã chuẩn hóa** giữa SIH và sổ lệnh CLAMM truyền thống — một số yếu tố thực tế được giữ cố định ở cả hai phía để có thể tách biệt rõ cơ chế hiệu quả vốn. Đây là mô hình để hiểu, không phải báo cáo lãi lỗ.

Ba tab:

* **Tab Simulator** - thử điều chỉnh hàng tồn kho, độ rộng dải và dòng giao dịch để xem SIH _sẽ_ hoạt động ra sao so với một pool CLAMM tương đương trong các điều kiện khác nhau.
* **Tab Comparison** - đặt SIH trực tiếp cạnh sổ lệnh **PancakeSwap V3 CLAMM** trên cùng các pool, để bạn thấy song song sự khác biệt giữa kho USDT dùng chung và USDT độc quyền về vốn cam kết và phạm vi bao phủ.
* **Tab Live data** — đo lường SIH _thực sự_ đang hoạt động ra sao ngay lúc này, lấy từ các truy vấn onchain vận hành nghiên cứu này.

Simulator nhằm giúp minh họa cách Shared Inventory Hook vận hành. Hãy thử, rồi đối chiếu với kết quả thực tế mà chúng tôi sẽ công bố trong vài tuần tới.

***

### 🧪 Thử nghiệm

Trong **vài tuần tới**, chúng tôi vận hành SIH trực tiếp và đo lường nó so với các tuyên bố về hiệu quả vốn ở trên, sử dụng các nguồn onchain. Mỗi tuần chúng tôi sẽ đưa ra những thông tin ngắn mới về hiệu suất và kiến trúc của SIH.

**Các cặp RWA đang chạy trong nghiên cứu:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Lưu ý: SNXXB, KORUB, SOXSB và DJTB hoàn toàn không có sổ lệnh CLAMM truyền thống._

**Chúng tôi sẽ công bố kết quả trong vài tuần tới trên** [**Twitter**](https://x.com/PancakeSwap) **của PancakeSwap.**

Kết quả được công bố sẽ bao gồm:

* **Toàn bộ tập dữ liệu hiệu suất -** Tất cả dữ liệu SIH trong vài tuần tới, gộp thành một bức tranh.
* **Câu hỏi phân bổ vốn -** SIH thực sự đã tiết kiệm được bao nhiêu vốn cho một tổ chức phát hành RWA.
* **Vượt / hụt kỳ vọng -** Nơi SIH vượt kỳ vọng, và nơi cần cải thiện.
* **Kết luận -** Một kết luận có căn cứ về mức độ hiệu quả thực sự của SIH đối với hiệu quả vốn RWA.

_Lưu ý về dữ liệu: Các số liệu ở đây được lấy từ các truy vấn onchain trực tiếp và dữ liệu cặp công khai, được trích dẫn ngay trong bài. Một số so sánh dùng các khoảng thời gian khác nhau và chúng tôi đã đánh dấu rõ — nghiên cứu được thiết kế để đo lường so sánh tương đương, trong khi phần giới thiệu này chỉ có thể đặt ra câu hỏi._

***

### Muốn kích hoạt SIH cho tài sản của bạn?

Nếu bạn là tổ chức phát hành RWA và đã mệt mỏi với việc cấp vốn một lượng USDT riêng cho mỗi pool bạn báo giá, thì đây là dành cho bạn.

Chúng tôi đang onboard các tổ chức phát hành RWA. Hãy điền google form này và chúng tôi sẽ hướng dẫn bạn đưa tài sản của mình được báo giá trên SIH - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Cảm ơn bạn đã đọc! Hãy theo dõi chúng tôi trên [X](https://x.com/PancakeSwap) để nhận cập nhật mới nhất, và tham gia thảo luận trên [Telegram](https://t.me/PancakeSwap) và [Discord](https://discord.gg/pancakeswap).

Cùng xây dựng nhé,\
The Chefs 🥞

***

_Tuyên bố miễn trừ trách nhiệm: Nội dung này chỉ nhằm mục đích cung cấp thông tin chung và giáo dục. Không nên coi đây là lời khuyên về tài chính, pháp lý hay chuyên môn khác. Giá tài sản kỹ thuật số có thể biến động mạnh. Giá trị khoản đầu tư của bạn có thể giảm hoặc tăng._
