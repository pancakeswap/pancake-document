---
description: '2026-08-21'
---

# Giới thiệu Shared Inventory Hook

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

Báo giá năm cặp không nên tốn gấp năm lần vốn. Nhưng on-chain, đó lại là thỏa thuận mà mọi nhà phát hành tài sản đều phải chấp nhận: thanh khoản bị gắn với từng cặp, nên mỗi cặp mới đồng nghĩa với việc phải bỏ thêm một khoản vốn nữa - phần lớn chỉ nằm đó, không sinh lời cho đến khi chính cặp đó được giao dịch trong đúng khoảng giá. Mỗi lần bạn muốn báo giá một cặp mới, bạn lại phải cung cấp thanh khoản mới cho cặp đó — số vốn này sau đó bị khóa vào đúng một cặp và không thể dùng ở nơi nào khác.

Shared Inventory Hook (SIH) phá vỡ ràng buộc đó. Đây là hook mới nhất trên PancakeSwap Infinity — và là hook đầu tiên được xây dựng cho hiệu quả vốn.

_💡 Tóm tắt: Hook là một hợp đồng thông minh (giống như một tiện ích bổ sung) được cắm vào một nhóm Infinity và chạy logic tùy chỉnh ngay giữa quá trình hoán đổi — không cần dựng một địa điểm giao dịch mới._

Vậy nó hoạt động như thế nào?

Thay vì khóa một khoản vốn riêng trong mỗi nhóm, nhà phát hành tài sản RWA nạp **một kho dự trữ chung**, và shared inventory hook sẽ báo giá độ sâu từ kho đó cho bất kỳ cặp nào đang được giao dịch — đúng lúc (just-in-time), ngay khi giao dịch hoán đổi diễn ra. Hãy hình dung như một kho nguyên liệu duy nhất cung cấp cho mọi món trong nhà bếp, thay vì mỗi món một kho riêng. Một số dư làm công việc của nhiều số dư.

Chính sự thay đổi đó giúp SIH đạt hiệu quả vốn, và nó thể hiện qua ba mặt:

* **Vốn luôn hoạt động và sinh lời.** Thanh khoản từ kho của hook được đưa vào đúng lúc khi có giao dịch hoán đổi, nên nó luôn hoạt động và kiếm phí cho bạn thay vì nằm im.
* **Cơ hội thu phí từ một số dư, trên nhiều cặp.** Một kho dự trữ sinh lời trên tất cả các cặp mà nó phục vụ, nhờ đó bạn thu được dòng phí với lượng vốn triển khai ít hơn nhiều.
* **Tác động giá thấp hơn.** Vì thanh khoản được báo giá tại thời điểm hoán đổi sâu hơn, các giao dịch lớn chịu tác động giá thấp hơn mỗi khi SIH đưa ra mức giá tốt nhất.
* **Hiệu quả vốn cao hơn.** Nạp một lần; cùng một khoản vốn hỗ trợ độ sâu cho mọi cặp có bật SIH. Ngoài ra, bạn có thể bật SIH cho một cặp mới mà không cần thêm vốn.

> \*\*Đã bị thuyết phục? Đưa tài sản của bạn lên on-chain theo cách hiệu quả vốn — điền vào biểu mẫu này → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**Bằng chứng nằm trên on-chain**

SIH đã ra mắt cùng bStocks vào tháng 8 này, và con số quan trọng nhất là mức độ vốn được sử dụng hiệu quả. Theo ảnh chụp hook mới nhất (21 tháng 8 năm 2026), 75% kho dự trữ chung đang được triển khai tích cực trên ba cặp (kho của hook \~$297K, đang hoạt động \~$224K). Trên hai cặp đã trưởng thành, CRCLB và MUB, tỷ lệ sử dụng đạt \~99% (98,96% / 98,95%). Lượng vốn mà trong các nhóm V3 CLAMM truyền thống sẽ nằm im thì ở đây đang nằm trong phạm vi và báo giá.

Trong những tuần đầu tiên (đến ngày 21 tháng 8), ba cặp đã giao dịch \~$710K qua 5.713 giao dịch hoán đổi — được phục vụ từ kho dự trữ chung khoảng \~$297K, kiếm phí LP ở mức 0,25%.

_**Nguồn:** Dune Dashboard nội bộ_ **Các nhóm đang hoạt động:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**Hướng đi tiếp theo**

Mô hình này được xây dựng để mở rộng — nhiều cặp hơn, một số dư chung trải rộng trên hàng nghìn thị trường giao dịch 24/7. Đây là con đường nhanh nhất mà chúng tôi từng thấy để đưa toàn bộ danh sách cặp của một token lên on-chain mà không phải nhân bội lượng vốn đứng sau.

Các nhóm SIH đang hoạt động nằm trên [trang PancakeSwap Earn](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001) — mở **Infinity** và tìm **Shared Inventory** trong phần tính năng của nhóm. SIH hiện được bật trên CRCLB / USDT, MUB / USDT và GMEB / USDT.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_Lưu ý: Các LP nhỏ lẻ đã có thể thêm thanh khoản vào các nhóm này từ Earn — khoản gửi đó trở thành thanh khoản thường trú của nhóm, được giữ tách biệt với kho dự trữ chung._

_**Quan trọng:**_

_SIH ít chịu ảnh hưởng của biến động giá hơn một vị thế LP tiêu chuẩn vì kho dự trữ chỉ được đưa vào hoạt động tại thời điểm hoán đổi. Nó không phải là không có rủi ro. Nhà vận hành vẫn nắm giữ kho dự trữ biến động theo thị trường. Như với mọi chiến lược on-chain, kết quả phụ thuộc vào khối lượng giao dịch, kho dự trữ, phòng hộ rủi ro và điều kiện thị trường._

Sẵn sàng tối đa hóa hiệu quả vốn? Hãy bật SIH cho các cặp token của bạn ngay → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, The Chefs 🥞

***

_Tuyên bố miễn trừ trách nhiệm: Nội dung này chỉ nhằm mục đích cung cấp thông tin chung và giáo dục. Nội dung này không nên được hiểu là lời khuyên tài chính, pháp lý hoặc chuyên môn khác. Giá tài sản kỹ thuật số có thể biến động. Giá trị khoản đầu tư của bạn có thể giảm hoặc tăng._
