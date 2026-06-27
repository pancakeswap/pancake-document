# Classic StableSwap

Classic StableSwap là triển khai AMM của Curve Finance trên PancakeSwap. Nó thêm đường cong tổng hằng số tuyến tính (x+y=k) lên trên công thức tích hằng số (x\*y=k) để giữ giá cân bằng hơn miễn là pool thanh khoản không mất cân bằng cực độ. Kết quả là, vì StableSwaps bị giới hạn với các tài sản có giá tương đương, tổn thất tạm thời không đáng lo ngại nhiều (ngoại trừ trong các trường hợp mất chốt cực đoan) và trượt giá thấp hơn so với AMM thông thường chỉ sử dụng công thức tích hằng số.

Khi bạn thực hiện Hoán đổi (giao dịch) trên StableSwap, bạn sẽ trả phí giao dịch thấp hơn so với mức phí 0.25% thông thường trên PancakeSwap AMM thông thường. Phân bổ phí như sau:

* 50% cho LP làm phần thưởng&#x20;
* 40% để mua lại và đốt CAKE&#x20;
* 10% cho Kho Bạc PancakeSwap

## Phí StableSwap

Phí cho các cặp được phân tích trong bảng dưới đây:

<table><thead><tr><th width="150">Cặp ổn định</th><th width="132">Phí Giao Dịch</th><th width="118.33333333333331">Phần Thưởng LP</th><th width="124">Mua lại CAKE</th><th>Kho Bạc PancakeSwap</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-USDT</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>HAY-BUSD</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>HAY-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>axlUSDC-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>BNBx-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>stkBNB-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr></tbody></table>

Nhà bếp sẽ dần dần triển khai các cặp StableSwap và điều chỉnh phí để kiểm tra và cải thiện sản phẩm hơn nữa.

## Tại sao tôi nên sử dụng StableSwap thay vì AMM Swap thông thường?

* Hoán đổi các stablecoin hoặc các cặp khác có giá tài sản tương đương một cách hiệu quả hơn với các bước giao dịch tương tự&#x20;
* Với chức năng StableSwap, trượt giá giao dịch thấp hơn so với AMM thông thường&#x20;
* Phí giao dịch StableSwap thấp hơn so với AMM thông thường
