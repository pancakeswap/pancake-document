# ♾️ PancakeSwap Infinity

> Nếu bạn là nhà phát triển hoặc đang tìm kiếm tài liệu kỹ thuật chi tiết, vui lòng tham khảo tài liệu này [https://developer.pancakeswap.finance/](https://developer.pancakeswap.finance/)

**PancakeSwap Infinity** là phiên bản mới nhất của PancakeSwap AMM, được thiết kế để giao dịch phi tập trung nhanh hơn, rẻ hơn và linh hoạt hơn. Nó sử dụng kiến trúc mô-đun cho phép tùy chỉnh nhiều hơn và hỗ trợ các loại pool giao dịch và mô hình định giá khác nhau.

Với Infinity, nhà phát triển có thể xây dựng các tính năng mới dễ dàng hơn bằng cách sử dụng "hooks" — các đoạn code nhỏ chạy tại các hành động quan trọng trong vòng đời của pool. Những hooks này cho phép các trường hợp sử dụng như oracle tùy chỉnh, pool phí động, tính năng giao dịch và quản lý thanh khoản nâng cao, và nhiều hơn nữa.&#x20;

So với PancakeSwap v3, Infinity hiệu quả hơn về gas và hướng tới tương lai hơn. Bằng cách tách rời các chức năng cốt lõi như kế toán và logic giao dịch, nó cho phép tích hợp liền mạch các đường cong định giá mới với khả năng hooks — giúp giao thức phát triển mà không cần triển khai lại.

### ⭐️ Tính Năng Chính

1. Singleton
2. Flash Accounting
3. Hooks
4. Hỗ Trợ Token Bản Địa
5. Đường Cong Định Giá Tùy Chỉnh
6. ERC-6909
7. `donate()`

{% hint style="success" %}
**Mã nguồn mở:** [PancakeSwap Infinity](https://github.com/pancakeswap/infinity-core) được phát hành theo giấy phép mã nguồn mở, khuyến khích nhà phát triển đổi mới, tùy chỉnh và cộng tác tự do.
{% endhint %}
