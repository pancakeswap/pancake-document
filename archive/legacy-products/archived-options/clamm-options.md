# CLAMM Options

{% hint style="danger" %}
\[ARCHIVED] Options – Kể từ ngày 11 tháng 3, 2025\
Nếu bạn vẫn còn thanh khoản cần rút, hãy rút ngay bằng cách truy cập https://www.stryke.xyz/en/trade.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options mang đến một cách tiếp cận mới cho giao dịch quyền chọn trên chuỗi, cho phép nhà cung cấp thanh khoản tận dụng thanh khoản v3 trên PancakeSwap. Nhờ đó, họ có thể dùng thanh khoản cho cả các nhóm thanh khoản v3 lẫn việc bán quyền chọn, kiếm phí giao dịch AMM tiêu chuẩn, phí quyền chọn (premium) và phần thưởng bổ sung, trong khi nhà giao dịch có thể dùng thanh khoản này để mua quyền chọn kiểu Mỹ trên nhiều token khác nhau.

Được xây dựng bởi đội ngũ Stryke (trước đây là Dopex), giao thức quyền chọn CLAMM giới thiệu một hệ thống cung cấp thanh khoản kép hiệu quả cho nhà giao dịch quyền chọn (người mua) và các pool PancakeSwap v3.

Sau đây là phần phân tích có cấu trúc về cách CLAMM Options vận hành:

1. LP thêm thanh khoản vào CLAMM options đồng thời đóng góp vào pool PancakeSwap v3 được chỉ định trong khoảng giá họ chọn.
2. Khi một nhà giao dịch quyền chọn (người mua) mở vị thế, thanh khoản được rút ra từ pool v3 để phục vụ việc bán quyền chọn. LP tương ứng khi đó trở thành người bán quyền chọn và nhận phí premium.
3. Thanh khoản không được người mua quyền chọn sử dụng vẫn nằm trong pool PancakeSwap v3, và có thể kiếm phí giao dịch.
4. Lợi nhuận từ việc bán quyền chọn và cung cấp thanh khoản trong pool v3 phản ánh cùng mức impermanent loss, đảm bảo người dùng không chịu rủi ro cao hơn so với cách thêm thanh khoản truyền thống vào các pool v3.
5. LP phải đối mặt với một số rủi ro, vì thanh khoản có thể không được sử dụng do nhu cầu mua quyền chọn thấp hơn. Ngoài ra, do thanh khoản được thêm vào pool ở khoảng không hoạt động, nó có thể không kiếm được phí nào.

Quyền chọn CLAMM kiểu Mỹ của PancakeSwap sẽ ra mắt đầu tiên trên chuỗi Arbitrum, mang lại sự linh hoạt với nhiều thời hạn đáo hạn khác nhau, từ 1 giờ đến 24 giờ.

| **Thị trường**          | ARB/USDC, ETH/USDC và wBTC/USDC |
| -------------------- | --------------------------------- |
| **Loại quyền chọn**    | Call & Put                        |
| **Giá thực thi**    | Dựa trên tick của pool v3            |
| **Thời hạn đáo hạn** | 1H, 2H, 6H, 12H và 24H          |

**Điều kiện thực thi:** Người dùng có thể thực thi vị thế trước khi đóng để tránh việc quyền chọn có lãi (in-the-money) hết hạn mà không có giá trị. Bạn có thể bật tự động thực thi để nhận lợi nhuận tự động khi đáo hạn, không cần thêm thao tác nào.

### Hướng dẫn từng bước

Sau đây là hướng dẫn từng bước cách dùng PancakeSwap CLAMM Options.

**Dành cho nhà giao dịch:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**Dành cho LP:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
