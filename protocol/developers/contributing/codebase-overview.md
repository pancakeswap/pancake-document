---
description: Tìm hiểu về Github của Pancake
---

# Tổng quan về codebase

## Giới thiệu

Tất cả các repository của chúng tôi được lưu trữ trên [Github](https://github.com/pancakeswap). Hầu hết đều là công khai, và bạn có thể tự do gửi issue hoặc pull request. Hãy đảm bảo bạn đọc toàn bộ hướng dẫn này và các hướng dẫn dành riêng cho từng repository trước.

## Các repository trên Github

* Frontend: Frontend chính. Chứa tất cả các tính năng không được liệt kê bên dưới.
  * [sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk) - SDK để xây dựng các ứng dụng trên nền tảng PancakeSwap
  * [aptos-swap-sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/aptos-swap-sdk) - Phiên bản Aptos của Swap SDK
  * [swap-sdk-core](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk-core) - Code dùng chung của Swap SDK
  * [wagmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/wagmi) - Extension cho [wagmi](https://github.com/wagmi-dev/wagmi), bao gồm chuỗi bsc và binance wallet connector
  * [awgmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/awgmi) - Kết nối với Aptos bằng các React hook tương tự wagmi. Bao gồm các wallet adapter.
* Smart Contract: Tất cả các smart contract được triển khai trên BSC và ETH.
* Smart Contract: Tất cả các smart contract phiên bản Move được triển khai trên Aptos.
* Subgraph: Endpoint GraphQL để truy vấn các sự kiện và thực thể.



<table><thead><tr><th width="227">Dự án</th><th>Github</th><th data-hidden>Website</th></tr></thead><tbody><tr><td>Frontend Monorepo</td><td><a href="https://github.com/pancakeswap/pancake-frontend">https://github.com/pancakeswap/pancake-frontend</a></td><td><a href="https://pancakeswap.finance">🔗PancakeSwap</a></td></tr><tr><td>Smart Contract</td><td><a href="https://github.com/pancakeswap/pancake-smart-contracts">https://github.com/pancakeswap/pancake-smart-contracts</a></td><td></td></tr><tr><td>Smart Contract Move</td><td><a href="https://github.com/pancakeswap/pancake-contracts-move">https://github.com/pancakeswap/pancake-contracts-move</a></td><td></td></tr><tr><td>Subgraph</td><td><a href="https://github.com/pancakeswap/pancake-subgraph">https://github.com/pancakeswap/pancake-subgraph </a></td><td></td></tr></tbody></table>
