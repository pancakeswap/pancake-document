# 🔮 Dự đoán

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Prediction là một thị trường dự đoán phi tập trung vui vẻ và đơn giản.

> #### Dự đoán giá BNB, BTC hay ETH sẽ tăng hay giảm – đoán đúng để thắng!

### Nền tảng

Bạn có thể chơi PancakeSwap Prediction trên:

* **Desktop/ dApp**: [Hướng dẫn PancakeSwap Prediction](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram Mini App (chỉ BNBUSD)**: [Prediction Bot](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Tóm tắt: Cách hoạt động

1. **Chọn tài sản để đặt cược**: Hiện có trên **BNB Chain**, **zkSync Era** và **Arbitrum One**.
2. **Chọn LÊN hay XUỐNG**: Dự đoán giá tài sản sẽ cao hơn hay thấp hơn khi giai đoạn "LIVE" kết thúc (mỗi vòng = 5 phút).
3. Đặt số tiền cược: Bất kỳ số lượng BNB nào
4. **Khóa vị thế của bạn**: Sau khi đặt, cược của bạn không thể thay đổi.
5. **Thắng hay thua**:
   * Nếu bạn chọn **LÊN**, bạn thắng nếu _Giá Đóng_ > _Giá Khóa_ vào cuối vòng.
   * Nếu bạn chọn **XUỐNG**, bạn thắng nếu _Giá Đóng_ < _Giá Khóa_ vào cuối vòng.

### Cơ chế & Phí

* **Chuỗi được hỗ trợ: BNB Chain, zkSync Era, Arbitrum One**
* **Tần suất vòng**: Mỗi **5 phút** (các vòng cuốn chiếu).
* **Phí tham gia**: **3%** tổng quỹ thưởng của mỗi vòng, một phần sẽ đi vào **mua lại CAKE**.
* **Tiền thắng**: Nhận bất cứ lúc nào sau khi kết quả được xác định.
* **Tỷ lệ thanh toán** dựa trên tỷ lệ cược trong mỗi bể:
  * Tỷ lệ thanh toán (Bể LÊN) = _(Tổng giá trị cả hai bể ÷ Giá trị Bể LÊN)_
  * Tỷ lệ thanh toán (Bể XUỐNG) = _(Tổng giá trị cả hai bể ÷ Giá trị Bể XUỐNG)_
  * Xem: [FAQ](prediction-faq.md) để biết ví dụ cụ thể

### Kết quả

* **Thắng:** Bạn chia sẻ tổng quỹ với những người thắng khác (trừ phí 3%)
* **Thua:** Bạn mất toàn bộ số tiền cược

**Trường hợp đặc biệt**:

* **Hòa** (Giá Khóa = Giá Đóng): Nhà cái thắng tất cả cược.
* Nếu không có cược đối lập:
  * Nếu bạn thắng: lấy lại 97% tiền cược ban đầu (phí 3% áp dụng).
  * Nếu bạn thua: mất toàn bộ tiền cược về nhà cái.
* **Bị hủy:** ví dụ: lỗi Oracle, người dùng được hoàn lại số tiền cược ban đầu

### Nguồn cấp giá (Oracle)

| Chuỗi     | Thị trường                                | Mục đích                                                                      | Oracle                     |
| --------- | ----------------------------------------- | ----------------------------------------------------------------------------- | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (tạm dừng) | Đặt _Giá Khóa_ và _Giá Đóng_ (cập nhật \~ tối đa 20 giây).                  | **Chainlink**              |
| BNB Chain | Tất cả                                    | Cung cấp biểu đồ trực tiếp trên giao diện người dùng (chỉ để tham khảo).     | Binance / TradingView Feed |

#### **Oracle ChainLink**

* Được dùng cho giá Khóa và giá Kết thúc của mỗi vòng thị trường dự đoán. Cập nhật theo khoảng thời gian tối đa 20 giây.
* Hợp đồng dự đoán của chúng tôi sử dụng nguồn cấp giá Oracle ChainLink trên BNB Chain để đặt các giá quyết định người dùng có thắng hay không.
* Được dùng cho biểu đồ "Chainlink" trên giao diện.

#### **Binance**

* Được dùng để cập nhật giá theo thời gian thực trên giao diện thị trường dự đoán PancakeSwap.
* Được dùng cho biểu đồ "TradingView" trên giao diện.

Vì chúng tôi đang dùng hai nguồn cấp giá khác nhau, cập nhật giá theo thời gian thực từ Binance và giá Oracle ChainLink có thể khác nhau một chút. Tuy nhiên, chúng không nên chênh lệch đáng kể.

### Địa chỉ hợp đồng

BNB Chain:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
