# CAKE Tokenomics v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Tốc độ phát hành** <a href="#emission-rate" id="emission-rate"></a>

### **Mỗi khối**

| **Chỉ số**                                                                   | **Phát hành/khối (CAKE)** | **Phát hành/ngày (CAKE)** |
| ---------------------------------------------------------------------------- | ------------------------: | ------------------------: |
| Phát hành                                                                    |                        40 |                 1,152,000 |
| Đốt hàng tuần [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |                    -25.75 |                  -787,600 |
| **Phát hành thực tế**                                                        |              **<14.25\*** |             **364,400\*** |

\*Phát hành thực tế trên thực tế thấp hơn một chút so với mức này: thêm 45,000 CAKE mỗi ngày được chuyển hướng từ lượng phân bổ cho xổ số và bị đốt (PID 137 - Chi tiết bên dưới).

Ngoài ra, một lượng CAKE động cũng được [mint cho địa chỉ Dev](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) với tỷ lệ 9.09%. Điều này có nghĩa là nếu 100 CAKE được thu hoạch, thì 9.09 CAKE sẽ được mint thêm và gửi đến Địa chỉ Dev.

{% hint style="info" %}
Toàn bộ CAKE được mint cho địa chỉ Dev đều bị đốt trong đợt đốt hàng tuần và không bao giờ lưu thông.&#x20;

Do đó, chúng tôi không đưa khoản này vào tốc độ phát hành ở trên.
{% endhint %}

## Phân phối <a href="#distribution" id="distribution"></a>

| Phân phối cho                 | Phần thưởng/khối (% phát hành) | Phần thưởng/khối (tổng CAKE) |         Phần thưởng/ngày |
| ----------------------------- | -----------------------------: | ---------------------------: | -----------------------: |
| Farm và Xổ số                 |                         10.62% |                         4.25 |       122,400 (xấp xỉ)   |
| trong đó được chuyển hướng và đốt |                            |                              |                  -46,000 |
| Syrup Pools                   |                            25% |                           10 |       288,000 (xấp xỉ)   |
| **Tổng lượng CAKE phát hành hàng ngày** |                      |                              |   **364,400 (xấp xỉ)**   |

## **Các cơ chế giảm phát khác** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
Quá trình đốt hiện đang được thực hiện thủ công. [Xem các giao dịch đốt tại đây](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

Ngoài những điều trên, CAKE còn bị đốt theo các cách sau:

* **0.05%** của mỗi giao dịch thực hiện trên PancakeSwap V2
* **100%** CAKE gửi đến địa chỉ Dev
* **100%** phí hiệu suất CAKE từ các IFO
* **100%** CAKE chi cho việc Tạo hồ sơ và mint NFT
* **100%** CAKE đặt giá trong Farm Auctions
* **20%** CAKE chi cho vé xổ số
* **45,000** CAKE mỗi ngày (trước đây được phân bổ cho xổ số) (_CAKE cho khoản này được tạo ra bởi một farm - PID 137)_
* **3%** của mỗi vòng thị trường Dự đoán được dùng để mua CAKE đem đốt
* **2%** của mỗi lần thu hoạch lợi suất trong Auto CAKE Pool
* **2%** của mỗi lần bán NFT trên NFT Market được dùng để mua CAKE đem đốt

## Tại sao việc đốt CAKE lại thủ công?

Để khởi động nhanh chóng, PancakeSwap ra mắt dưới dạng MVP (sản phẩm khả dụng tối thiểu) với hợp đồng MasterChef phát hành 40 CAKE mỗi khối. Vì lý do đó, đội ngũ ban đầu đã không thêm các chức năng bổ sung như khả năng tùy chỉnh logic mint CAKE. Do việc di chuyển sang MasterChef mới đòi hỏi nhiều thời gian và công sức, đội ngũ đã chọn giảm lượng phát hành CAKE thông qua quy trình đốt thủ công bằng cách tạo hai pool:

* Legacy Lottery Pool (PID - 137) - đốt CAKE từ xổ số
* Burn Pool (PID - 138) - đốt CAKE mỗi khối

Các pool này hoạt động tương tự như các farm, trong đó các Chef có thể điều chỉnh tỷ lệ phần trăm trong 40 CAKE mỗi khối được phân bổ cho chúng sau mỗi lần bỏ phiếu giảm phát hành CAKE.

{% hint style="warning" %}
Vào ngày đốt, nguồn cung hiển thị trên trang chủ có thể đột ngột tăng thêm vài triệu CAKE.&#x20;

Đừng lo - **SỐ CAKE NÀY THỰC SỰ KHÔNG BAO GIỜ LƯU THÔNG:**
{% endhint %}

Mức tăng rõ rệt này chỉ là do cách toàn bộ CAKE được phân bổ cho việc đốt được lưu trữ trong tuần.&#x20;

CAKE gửi đến cả hai pool PID-137 và PID-138 được thu hoạch trước khi hoàn tất các đợt đốt token hàng tuần, và điều này khiến Tổng nguồn cung hiển thị trên trang web tăng \~6M. Đó là vì CAKE đang chờ xử lý không được ghi nhận vào Tổng nguồn cung cho đến khi nó được thu hoạch vào ngày đốt. Sau khi giao dịch đốt token hoàn tất, \~6M được hiển thị trong mục Đã đốt đến nay.&#x20;

## Cách tự xác nhận nguồn cung CAKE

Để xác nhận rằng nguồn cung CAKE lưu thông hiển thị trên trang chủ PancakeSwap là chính xác,&#x20;

1. Truy cập hợp đồng token CAKE trên BscScan và [xem Địa chỉ Đốt đang nắm giữ bao nhiêu CAKE.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) Đó là tổng lượng CAKE đã bị đốt (bị loại khỏi lưu thông VĨNH VIỄN và không thể lấy lại).
2. Sau đó, trừ lượng đã đốt này khỏi "Total Supply" mà BscScan hiển thị.
3. Kết quả là nguồn cung CAKE thực tế.



#### **Đọc thêm về cơ chế giảm phát của CAKE ở trang tiếp theo.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
