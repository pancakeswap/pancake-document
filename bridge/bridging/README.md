---
description: Kết nối chuỗi CAKE giữa Ethereum, BNB Chain, Aptos và nhiều mạng khác
---

# 🌉 Kết nối chuỗi

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Kết nối chuỗi đến/từ EVM (Trang mới): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Kết nối chuỗi đến/từ Aptos (Cầu nối V1): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## Kết nối chuỗi trong crypto là gì?

* Kết nối chuỗi trong crypto là quá trình chuyển tài sản giữa các mạng blockchain khác nhau.
* Nó tăng cường khả năng tương tác, cho phép truyền dữ liệu và tài sản qua nhiều mạng khác nhau.

\
Dưới đây là một số lý do bạn có thể muốn kết nối chuỗi:

* Mua các token tiền điện tử khác nhau
* Đúc NFT chỉ có trên một mạng cụ thể
* Tiết kiệm tiền với các giao dịch rẻ hơn
* Sử dụng dapp chỉ có trên mạng khác

***

## CAKE, một token đa chuỗi

Với việc mở rộng và triển khai đa chuỗi của chúng tôi, CAKE hiện là một token đa chuỗi có nguồn gốc từ BNB Chain, nhưng cũng có sẵn trên Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB và Aptos.

CAKE trên bất kỳ chuỗi nào khác đều tương đương với CAKE trên BNB Smart Chain. Nó luôn có thể được kết nối chuỗi giữa các chuỗi này theo tỷ lệ 1:1 và không mất phí CAKE.

**Xin lưu ý rằng chỉ có một CAKE duy nhất.** Không có các phiên bản CAKE khác nhau trên các chuỗi khác nhau. Tổng nguồn cung CAKE trên tất cả các blockchain được giới hạn ở mức 400 triệu, như được nêu trong [đề xuất bỏ phiếu](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5) này.

***

## Cầu nối PancakeSwap là gì?

Cầu nối PancakeSwap là một công cụ tiện lợi tích hợp trong ứng dụng, cho phép bạn di chuyển tài sản giữa các blockchain khác nhau trực tiếp thông qua giao diện PancakeSwap. Thay vì truy cập các trang cầu nối bên ngoài, bạn có thể kết nối chuỗi các token được hỗ trợ giữa các chuỗi như BNB Chain, Ethereum, Base, Arbitrum và nhiều hơn nữa—tất cả từ một nơi.

Cầu nối PancakeSwap được hỗ trợ bởi các nhà cung cấp bên thứ ba đáng tin cậy và hoạt động như một **bộ tổng hợp**—chọn tuyến đường tốt nhất dựa trên giá cả, tốc độ và độ tin cậy.

Để tìm hiểu cách kết nối chuỗi CAKE, hãy xem các hướng dẫn và FAQ trong các phần tiếp theo.

***

## 🔗 Cách hoạt động

### Kết nối chuỗi qua Bộ tổng hợp

Cầu nối PancakeSwap hoạt động như một lớp thông minh trên các giao thức cầu nối bên thứ ba đáng tin cậy. Khi bạn khởi tạo một giao dịch kết nối chuỗi, PancakeSwap:

* Kiểm tra nhiều cầu nối được tích hợp để tìm tuyến đường tối ưu
* Gửi giao dịch của bạn đến nhà cung cấp được chọn

Kết nối chuỗi không có tính chất lưu ký—tài sản của bạn không qua quyền giám sát của PancakeSwap. Các giao dịch chuyển được xử lý trực tiếp bởi các nhà cung cấp cầu nối.

### Các Nhà Cung Cấp Cầu Nối Được Hỗ Trợ

Hiện tại chúng tôi tích hợp với:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Lưu ý: Mỗi nhà cung cấp có cơ chế kết nối chuỗi, chuỗi được hỗ trợ, phí và giới hạn khác nhau.

***

### Các Chuỗi và Token Được Hỗ Trợ

#### Các Chuỗi Hiện Được Hỗ Trợ

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (Trang V1)

#### Các Token Có Thể Kết Nối Chuỗi

Các token có sẵn khác nhau tùy theo chuỗi và tuyến đường. Các token được hỗ trợ phổ biến bao gồm (nhưng không giới hạn ở):

* CAKE
* USDT
* USDC
* ETH

***

#### Giới Hạn & Ngoại Lệ

Một số token có thể không được hỗ trợ do giới hạn cầu nối hoặc hạn chế thanh khoản. Những token này đã được lọc ra để có trải nghiệm người dùng tốt nhất. Ví dụ:

**Đối với cBridge:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**Đối với deBridge:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_Trên đây là các ví dụ. Các token thực tế có sẵn theo từng chuỗi được hiển thị trực tiếp trong giao diện Cầu nối._

***

### 💸 Phí và Chi Phí

#### Phí Cầu Nối

* Được tính bởi nhà cung cấp cầu nối cơ sở
* Thông thường bao gồm một khoản phí nhỏ cho mỗi giao dịch chuyển
* Được hiển thị rõ ràng trước khi bạn xác nhận cầu nối

***

#### Chi Phí Gas

* Bạn trả phí gas trên **chuỗi nguồn** để khởi tạo giao dịch
* Một số nhà cung cấp cũng có thể yêu cầu gas trên **chuỗi đích**
* **Mẹo:** Luôn giữ token gốc (ví dụ: ETH, BNB) ở cả hai phía của cầu nối

***

#### Số Lượng Tối Thiểu & Hạn Chế

Một số tuyến đường cầu nối áp dụng:

* **Số lượng cầu nối tối thiểu/tối đa** (ví dụ: tối thiểu 10 USDC)
* **Định dạng hoặc số thập phân token được hỗ trợ** (ví dụ: chỉ token ERC-20)

Giao diện sẽ tự động phát hiện và hiển thị các giao dịch chuyển không hợp lệ.

***

### ⏳ Thời Gian Giao Dịch & Theo Dõi

#### Kết Nối Chuỗi Mất Bao Lâu?

Các giao dịch chuyển cầu nối thường hoàn thành trong vài **phút**, tùy thuộc vào:

* Chuỗi nguồn và chuỗi đích
* Tình trạng tắc nghẽn mạng
* Hiệu quả của nhà cung cấp cầu nối

#### Theo Dõi Giao Dịch Của Bạn

Sau khi gửi, bạn có thể xem trạng thái giao dịch qua các trình duyệt khối dành riêng cho từng nhà cung cấp:

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

Nếu một giao dịch bị kẹt trong thời gian dài, hãy kiểm tra trình duyệt khối liên quan hoặc liên hệ với các quản trị viên của chúng tôi qua [các kênh mạng xã hội](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) để được [trợ giúp](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help).

***

### 🧠 Mẹo Trước Khi Kết Nối Chuỗi

* **Giữ token gas trên cả hai chuỗi** (ví dụ: ETH + BNB)
* **Bắt đầu với số lượng nhỏ** nếu đây là lần đầu tiên bạn kết nối chuỗi
* Tránh kết nối chuỗi trong các giai đoạn có hoạt động chuỗi cao (có thể dẫn đến phí gas cao hơn)
* Xác nhận tính tương thích của token trên cả hai chuỗi
* Luôn kiểm tra kỹ mạng nguồn và mạng đích

***

### Bổ sung: Địa Chỉ CAKE Omni-chain Fungible Token (OFT)

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
