# 🔁 Các Kịch Bản Hoán Đổi

Có 4 kịch bản cho các giao dịch xuyên chuỗi.

#### 1️⃣ Chỉ Kết Nối Cầu Nối

* Ví dụ: **Kết nối cầu nối ETH trên Base sang ETH trên Arbitrum**
* Chỉ các token được hỗ trợ (USDC, USDT, WETH, v.v.) mới có thể kết nối cầu nối trực tiếp. Các token này khác nhau tùy theo chuỗi nguồn và chuỗi đích.

#### 2️⃣ Hoán Đổi → Kết Nối Cầu Nối

* Ví dụ: **Hoán đổi BNB trên BNB Chain sang USDC trên Arbitrum**
* Hoán đổi BNB sang token cầu nối được hỗ trợ (ví dụ: USDC) sử dụng các pool PancakeSwap trên BNB Chain
* Kết nối cầu nối USDC qua Across sang Arbitrum

#### 3️⃣ Kết Nối Cầu Nối → Hoán Đổi

* Ví dụ: **Hoán đổi USDC trên BNB Chain sang ARB trên Arbitrum**
* Kết nối cầu nối USDC qua Across
* Hoán đổi USDC sang ARB sử dụng các pool PancakeSwap trên Arbitrum

#### 4️⃣ Hoán Đổi → Kết Nối Cầu Nối → Hoán Đổi

* Ví dụ: **Hoán đổi BNB trên BNB Chain sang ARB trên Arbitrum**
* Hoán đổi BNB sang token cầu nối (tối đa hóa đầu ra cho người dùng)
* Kết nối cầu nối qua Across
* Hoán đổi token đã kết nối sang ARB trên Arbitrum sử dụng các pool PancakeSwap

***

### ⚠️ Các Trường Hợp Thất Bại

| Kịch Bản                                      | Kết Quả                                                                                                                                                                                                          |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thất Bại Hoán Đổi/Giao Dịch trên Chuỗi Nguồn** | Người dùng nhận lại ngay lập tức token gốc trên chuỗi nguồn                                                                                                                                                     |
| **Thất Bại Giao Dịch Cầu Nối**                | Across xử lý hoàn tiền trong vòng 90 phút đến 2 giờ, người dùng nhận lại tài sản đã kết nối trên chuỗi nguồn. Trong khi đó Relay xử lý hoàn tiền trong vòng một phút trong kịch bản này giữa SOL <> EVM. |
| **Thất Bại Hoán Đổi trên Chuỗi Đích**        | Người dùng nhận tài sản đã kết nối cầu nối trên chuỗi đích                                                                                                                                                      |
