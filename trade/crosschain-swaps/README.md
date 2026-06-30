# 🔀 Hoán Đổi Xuyên Chuỗi

Hoán đổi xuyên chuỗi cho phép người dùng hoán đổi token giữa các chuỗi một cách liền mạch — tất cả trong một giao dịch duy nhất, được tối ưu hóa.

Hoán đổi xuyên chuỗi được hỗ trợ giữa:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**Giao dịch cực kỳ nhanh — thường hoàn tất trong vài giây đến dưới một phút.**
{% endhint %}

***

### 🔍 Cách Hoạt Động

1. Người dùng chọn chuỗi Từ / Đến và token Từ / Đến
2. Bộ định tuyến PancakeSwap tính toán lộ trình hiệu quả nhất
3. Hoán đổi được thực hiện thông qua các nhóm thanh khoản của PancakeSwap (v2, v3, Infinity, StableSwaps) trên chuỗi nguồn và chuỗi đích
4. Việc kết nối chuỗi được xử lý qua các giao thức đối tác: [Across](https://across.to/) (cho EVM <> EVM), [Relay](https://relay.link/bridge) (cho SOL <> EVM)

{% hint style="success" %}
**Hoán đổi xuyên chuỗi khả dụng cho bất kỳ token nào có đủ thanh khoản trên cả chuỗi nguồn và chuỗi đích.**
{% endhint %}

***

### 💸 Phí

* **PancakeSwap không thu bất kỳ phí nào cho các giao dịch xuyên chuỗi.**
* Phí bao gồm:
  1. **Phí Giao Dịch:** Phát sinh từ các hoán đổi trong nhóm thanh khoản trên chuỗi nguồn và chuỗi đích
  2. **Phí Cầu Nối:** Trả cho các relayer để kết nối tài sản giữa các chuỗi

***

### 🎯 Intents Là Gì?

Intents cho phép người dùng xác định kết quả mong muốn mà không cần lo lắng về cách thực hiện.

Ví dụ về Intents:

* "Hoán đổi 1 ETH trên Base lấy ít nhất 3000 USDC trên Arbitrum"

Nếu không có intents, người dùng sẽ phải thực hiện thủ công:

* Kết nối cầu nối ETH sang Arbitrum
* Tìm DEX với giá ETH → USDC tốt nhất

{% hint style="success" %}
**Với intents — hệ thống xử lý tất cả tự động.**
{% endhint %}

**Lợi ích của thiết kế dựa trên intent:**

* Trải nghiệm người dùng liền mạch
* Thời gian giao dịch nhanh hơn
* Giao dịch một cú nhấp chuột, đơn lẻ

***

### 🔐 Kiểm Toán

Chúng tôi đã thực hiện nhiều vòng kiểm toán với các tên tuổi uy tín trong lĩnh vực bảo mật chuỗi chéo:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
