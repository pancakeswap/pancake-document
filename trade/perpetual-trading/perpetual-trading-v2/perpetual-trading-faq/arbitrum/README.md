---
hidden: true
---

# Arbitrum

### Phí cho PancakeSwap Perpetuals V2 trên Arbitrum là bao nhiêu?

Khi ra mắt trên Arbitrum, phí sẽ là **0.05% cho mở và đóng giao dịch**. 50% phí thu được sẽ được chia sẻ với pool ALP để cung cấp thanh khoản. Các phí khác bao gồm phí thực thi, thanh lý và funding. Thêm thông tin về phí có thể tìm thấy [tại đây](https://blog.pancakeswap.finance/articles/ep-6-4-pancake-swap-perpetuals-v2-fee-structure-a-comprehensive-overview).

### ALP là gì?

Perpetuals v2 trên Arbitrum có một pool thanh khoản riêng, Pool ALP, được hỗ trợ bởi token nhà cung cấp thanh khoản $ALP của nền tảng Aster. Bao gồm các tài sản như USDC, USDT, DAI, ETH và BTC, Pool ALP cho phép người dùng trở thành nhà cung cấp thanh khoản và kiếm lợi nhuận đáng kể bằng cách đúc $ALP với bất kỳ tài sản nào đã đề cập. Đáng chú ý là 50% tổng doanh thu phí nền tảng được phân phối cho các nhà cung cấp thanh khoản ALP, bao gồm các thành phần như phí mở/đóng vị thế, phí thực thi, phí funding và phí thanh lý. Hướng dẫn về staking ALP có thể tìm thấy [tại đây.](alp-syrup-pool-arbitrum/)

### ALP Syrup Pool là gì?

ALP Syrup Pool mới của Aster ($ALP) trên Arbitrum cho phép người dùng kiếm lợi nhuận tăng cường. Người dùng có thể stake token $ALP để kiếm phần thưởng bằng token $CAKE với APY trên 20% khi ra mắt. ALP syrup pool trên PancakeSwap. Để biết thêm chi tiết về syrup pool, bao gồm emissions và ngày bắt đầu và kết thúc, vui lòng tham khảo đề xuất [tại đây](https://pancakeswap.finance/voting/proposal/0x52455da15b4f1ff4d324c1e7645163d6b78b2221a98a4782bff16b27de409ce9).

### Các token khả dụng cho Arbitrum là gì?

Các cặp giao dịch được hỗ trợ trên Arbitrum One là ARBUSD, XRPUSD, DOGEUSD, ETHUSD và BTCUSD. Đối với Degen mode, ETHUSD và BTCUSD được hỗ trợ. Chúng tôi sẽ tìm cách triển khai thêm các cặp trong những tuần tới.

### Tôi đã nạp ví bằng USDC trên Arbitrum; tại sao tôi không thể thấy nó?

Rất có thể bạn đã nạp USDC gốc trên Arbitrum ([0xaf88d065e77c8cC2239327C5EDb3A432268e5831](https://arbiscan.io/token/0xaf88d065e77c8cC2239327C5EDb3A432268e5831)). Tuy nhiên, PancakeSwap Perpetuals hỗ trợ Bridged USDC, USDC.e ([0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8](https://arbiscan.io/token/0xff970a61a04b1ca14834a43f5de4533ebddb5cc8)) vì nó có thanh khoản cao hơn. Bạn có thể hoán đổi USDC sang USDC.e một cách liền mạch [tại đây](https://pancakeswap.finance/swap?chain=arb\&outputCurrency=0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8\&inputCurrency=0xaf88d065e77c8cC2239327C5EDb3A432268e5831). Để biết thêm thông tin về sự khác biệt giữa USDC và USDC.e, vui lòng tham khảo [thông cáo báo chí Circle USDC](https://www.circle.com/blog/arbitrum-usdc-now-available).
