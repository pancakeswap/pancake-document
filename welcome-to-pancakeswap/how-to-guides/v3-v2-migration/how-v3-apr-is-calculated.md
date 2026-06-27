# Cách tính APR trong v3

{% hint style="info" %}
Trong V3 Liquidity và Farms, với thanh khoản không thể thay thế mới và khả năng phạm vi giá có thể tùy chỉnh. Mỗi vị thế LP sẽ có APR phí LP và farming CAKE riêng.
{% endhint %}

Tổng APR được kết hợp bởi APR phí LP và APR phần thưởng CAKE

### Phí LP

Về mặt lý thuyết, với phạm vi giá và thanh khoản mà người dùng sắp thêm vào, chúng ta có thể ước tính phí dự kiến trong 7 ngày tới như sau&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Số tiền phí tích lũy trong phạm vi giá do người dùng chỉ định trong 7 ngày qua
* $$L_{in}$$: Thanh khoản hiện tại trong phạm vi giá do người dùng chỉ định
* $$\Delta{L}$$: Thanh khoản người dùng muốn thêm vào phạm vi giá

#### Phí trong phạm vi

Đối với $$fee_{in}$$, chúng ta sử dụng dữ liệu khối lượng giao dịch lịch sử, mức phí và dữ liệu giá lịch sử để ước tính giá trong phạm vi

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Mức phí
* $$V_{7d}$$: Tổng khối lượng giao dịch trong 7 ngày qua
* $$T_{in}$$: Thời gian, tính bằng giây, giá ở trong phạm vi trong 7 ngày qua
* $$T_{7d}$$: 7 ngày tính bằng giây

### APR Cake

#### Phân bổ Pool

Tổng phần thưởng cake mỗi giây trong MC v3 sử dụng upkeep và có thể được lấy bằng `latestPeriodCakePerSecond`&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

Trong mỗi pool, chúng ta có thể sử dụng `poolInfo` để lấy `poolWeight` bằng cách chia `poolInfo.allocPoint / totalAllocPoint`

#### APR CAKE Toàn Cầu

APR toàn cầu được tính bằng cách sử dụng tổng lượng thanh khoản đang hoạt động và đã staking với phần thưởng CAKE của pool.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` đại diện cho thanh khoản đã staking đang hoạt động của pool hiện tại tính bằng USD, bao gồm tất cả các ticks vị thế trong phạm vi đã staking trong MasterChef v3.

#### APR CAKE Theo Vị Thế

APR cho các vị thế riêng lẻ có thể thay đổi tùy thuộc vào cài đặt phạm vi giá của chúng.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: Phần thưởng CAKE kiếm được USD mỗi năm trong pool
* $$USD_p$$: Tổng giá trị USD trong vị thế
* $$L_{p}$$: Thanh khoản vị thế
* $$L_{lm}$$: Tổng thanh khoản staking được theo dõi bởi LMPool
