# FAQ

1. **Infinity khác PancakeSwap V3 như thế nào?**\
   Infinity bổ sung các tính năng mới như hooks có thể lập trình, nhiều [loại pool](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) hơn (như LBAMM và CLAMM), và tiết kiệm gas. Tuy nhiên, cơ chế hoán đổi và cung cấp thanh khoản cốt lõi về cơ bản tương tự v3 ngoại trừ một số khác biệt nhỏ trong pool LBAMM cho việc cung cấp thanh khoản.\
   <br>
2.  **Sự khác biệt giữa LBAMM và CLAMM là gì?**

    1. **LBAMM (Liquidity Book AMM):** Sử dụng các bin thanh khoản, mỗi bin giữ thanh khoản ở các mức giá khác nhau. LP có thể cung cấp thanh khoản trên các bin, hoán đổi được thực hiện ở một mức giá duy nhất trong một bin.
    2. **CLAMM (Concentrated Liquidity AMM):** Cho phép người dùng cung cấp thanh khoản trong các phạm vi giá tùy chỉnh như trong PancakeSwap V3.

    \
    Để biết thêm chi tiết, hãy truy cập [tại đây](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types). \
    <br>
3. **Làm thế nào để nhận phần thưởng farm, và tại sao bị giới hạn mỗi 8 giờ?**\
   Bạn có thể nhận phần thưởng farm từ các vị thế thanh khoản bằng cách nhấp vào nút "Thu Hoạch". Infinity cho phép nhận phần thưởng hàng loạt trên tất cả vị thế farm đang hoạt động, tiết kiệm chi phí gas. Phần thưởng được tính toán và xử lý mỗi 8 giờ để tối ưu hóa chi phí gas và tính toán. \
   \
   Để biết thêm chi tiết về cơ chế farming, hãy truy cập [tại đây](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms). \
   <br>
4.  **Các hooks của Infinity hoạt động như thế nào?**\
    Hooks là các tiện ích mở rộng hợp đồng thông minh có thể tùy chỉnh, bổ sung thêm chức năng cho pool. Chúng có thể kích hoạt các hành động bổ sung trong quá trình hoán đổi hoặc sự kiện thanh khoản — ví dụ: điều chỉnh phí, cung cấp chiết khấu hoặc áp dụng logic khác.<br>

    Hooks được gắn vào pool khi tạo. Trong hầu hết các trường hợp, **người dùng không cần thực hiện thêm bước nào**. Miễn là bạn đang hoán đổi hoặc cung cấp thanh khoản như thường lệ, bạn sẽ tự động hưởng lợi từ logic của hook nếu nó áp dụng cho pool đó.<br>

    👉 **Bạn có thể xem các hooks đang hoạt động và chi tiết của chúng trên trang của từng pool trong phần "Tính Năng Pool".**\
    <br>
5.  **Tại sao tôi không nhận được phí khi rút vị thế từ pool LBAMM?**\
    Trong các pool LBAMM (Liquidity Book AMM), phí được tự động thêm vào các bin thanh khoản đang hoạt động của bạn. Điều này có nghĩa là:

    1. Khi bạn rút vị thế, phí kiếm được được bao gồm trong tổng số lượng token bạn đang rút.
    2. Không giống các AMM truyền thống, không có số dư "phí cần thu" riêng biệt — tất cả được gộp vào giá trị vị thế của bạn.

    \
    Nếu bạn không nhận thấy token bổ sung khi rút, có thể là vì:

    1. Vị thế của bạn có thể đã gánh chịu tổn thất tạm thời nhiều hơn phí đã thu do biến động giá trong thời gian nắm giữ vị thế.
    2. Thanh khoản của bạn không nằm trong các bin đang hoạt động nơi có giao dịch xảy ra.
