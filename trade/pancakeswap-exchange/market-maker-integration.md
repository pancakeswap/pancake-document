---
hidden: true
---

# Tích Hợp Nhà Tạo Lập Thị Trường

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Tích Hợp Nhà Tạo Lập Thị Trường trên Ethereum

PancakeSwap tích hợp với các nhà tạo lập thị trường trên Ethereum và Binance Smart Chain để giúp trader thực hiện giao dịch với chi phí thấp hơn.

Ngoài AMM, các giao dịch trên PancakeSwap hiện có thể được định tuyến đến các nhà tạo lập thị trường được đưa vào danh sách trắng nếu họ cung cấp mức thực hiện giao dịch tốt hơn so với giá AMM hiện tại. Việc định tuyến này được thực hiện tự động bởi [Smart Router](smart-router-v2/) để giao dịch chỉ được định tuyến đến nhà tạo lập thị trường khi họ đang chủ động báo giá tốt hơn. Khi AMM cạnh tranh hơn, trader sẽ được định tuyến đến AMM để thực hiện.

Có 2 kịch bản trong đó nhà tạo lập thị trường hoạt động trên PancakeSwap.

**Kịch bản 1: Đã có pool thanh khoản AMM**

Nếu PancakeSwap đã có thanh khoản cho một token nhất định (ví dụ: WETH/USDC) trong AMM, PancakeSwap sẽ yêu cầu nhà tạo lập thị trường báo giá cho cùng giao dịch đó. Smart router của PancakeSwap sau đó sẽ định tuyến yêu cầu giao dịch đến AMM hoặc nhà tạo lập thị trường tùy thuộc vào nguồn thanh khoản nào đang cung cấp giá tốt nhất tại bất kỳ thời điểm nào.

**Kịch bản 2: Không có pool thanh khoản AMM**

Trong kịch bản như vậy, smart router sẽ tự động định tuyến giao dịch đến nhà tạo lập thị trường. Tuy nhiên, điều này không ngăn các dự án thiết lập pool thanh khoản AMM sau đó và hợp tác với chúng tôi để duy trì thanh khoản DEX phi tập trung.

### Phí

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap không tính bất kỳ phí nào từ trader được thực hiện qua chúng tôi và được thực hiện bởi nhà tạo lập thị trường. Tuy nhiên, PancakeSwap nhận **0,05%** **phí giao dịch** từ các nhà tạo lập thị trường trong danh sách trắng cho khối lượng được thực hiện bởi họ. PancakeSwap nhận mức phí giao dịch giảm **0,01%** nếu các giao dịch được thực hiện là giữa các cặp stablecoin. Vui lòng tham khảo bảng phân tích phí dưới đây:<br>

<table><thead><tr><th width="178">Giao Dịch</th><th width="138">Phí Giao Dịch</th><th width="182">Phí PCS từ MM</th><th width="147">Đốt CAKE</th><th align="center">Kho Bạc PancakeSwap</th></tr></thead><tbody><tr><td>Coin kết nối từ mạng khác</td><td>N/A</td><td>0,25%</td><td>0,083%</td><td align="center">0,167%</td></tr><tr><td>Non-stablecoin trên Ethereum (ví dụ: ETH/USDC)</td><td>N/A</td><td>0,05%</td><td>0,017%</td><td align="center">0,033%</td></tr><tr><td>Non-stablecoin trên BSC (ví dụ: BNB/USDT)</td><td>N/A</td><td>0,05%</td><td>0,017% </td><td align="center">0,033%</td></tr><tr><td>Stablecoin sang Stablecoin trên Ethereum</td><td>N/A</td><td>0,01%</td><td>0,003%</td><td align="center">0,007%</td></tr></tbody></table>

#### Các tài sản hiện được hỗ trợ

Các tài sản sau hiện được hỗ trợ và có thể tăng/giảm tùy thuộc vào nhà tạo lập thị trường:

**Trên Ethereum**

* **Majors:** WETH, WBTC
* **Stablecoins:** USDT, USDC, DAI, BUSD
* **Các tài sản ERC-20 phổ biến khác:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**Trên Binance Smart Chain:**

* **Majors:** BNB, ETH, BTCB
* Token BNB không phải bản địa: ARB, OP

Lưu ý rằng không giống như AMM, nhà tạo lập thị trường sẽ không thể giao dịch ở bất kỳ số lượng nào và số lượng họ sẵn sàng thực hiện phụ thuộc vào thanh khoản riêng của họ. Không phải lúc nào các lệnh rất lớn cũng được thực hiện đầy đủ. Chúng tôi khuyên người dùng hãy xem xét kỹ các báo giá để đảm bảo mỗi giao dịch phản ánh đúng giá và số lượng theo nhu cầu của họ.

**Thời gian ngừng hoạt động của nhà tạo lập thị trường**

Các nhà tạo lập thị trường không bắt buộc phải báo giá 24/7. Có một số trường hợp (ví dụ: các sự kiện kinh tế quan trọng, nâng cấp hệ thống) mà nhà tạo lập thị trường có thể tạm thời không thể cung cấp báo giá. Lưu ý rằng trong những khoảng thời gian này, các token này đơn giản sẽ không thể giao dịch được, và chúng tôi khuyên người dùng đợi một thời gian trước khi nhà tạo lập thị trường hoạt động trở lại.

#### FAQ

**H.** Các nhà tạo lập thị trường có được tích hợp trên Aptos không?

**Đáp:** Có thể, chúng tôi chỉ ra mắt tích hợp nhà tạo lập thị trường trên Ethereum và Binance Smart Chain lúc này để tăng cường thanh khoản cho trải nghiệm người dùng tốt hơn. Chúng tôi sẽ tiếp tục theo dõi các chuỗi khác.

**H.** PancakeSwap sẽ tạo doanh thu như thế nào nếu không thu phí người dùng?

**Đáp:** PancakeSwap sẽ không thu bất kỳ phí nào từ người dùng, nhưng PancakeSwap sẽ nhận một khoản hoa hồng nhỏ từ nhà tạo lập thị trường và sử dụng khoản đó để tài trợ cho việc mua lại và đốt CAKE.

**H.** Nhà cung cấp thanh khoản có tiếp tục kiếm phí LP không?

**Đáp:** Có, nhà cung cấp thanh khoản sẽ tiếp tục kiếm phần thưởng phí giao dịch 0,17% (phí LP) và lợi nhuận từ các Farm CAKE.

**H.** Các nhà tạo lập thị trường có thêm thanh khoản vào AMM không? Điều đó có làm giảm APR không?

**Đáp:** Các nhà tạo lập thị trường duy trì thanh khoản riêng của họ, và do đó sẽ không kiếm được APR từ các giao dịch trên AMM. Chỉ LP mới kiếm phí và APR từ việc cung cấp thanh khoản cho các pool AMM.

**H.** Tôi đang cung cấp thanh khoản trên PancakeSwap Ethereum. Tôi có cần làm gì không?

**Đáp:** Không, bạn không cần làm gì. Bạn sẽ tiếp tục kiếm phí LP cho các giao dịch được thực hiện qua AMM và tiếp tục kiếm lợi nhuận bằng CAKE.

**H.** Làm thế nào để trở thành nhà tạo lập thị trường?

**Đáp:** Chúng tôi sàng lọc và hợp tác với nhà tạo lập thị trường trên cơ sở cá nhân. Vui lòng liên hệ trực tiếp với chúng tôi hoặc qua admin của chúng tôi nếu bạn quan tâm đến việc hợp tác.
