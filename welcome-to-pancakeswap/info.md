# 📈 Analytics (Trang Info)

## Trang Info&#x20;

Xem trang analytics bản địa của PancakeSwap tại đây: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Tất cả dữ liệu chỉ số cốt lõi được lấy từ Bộ Lập Chỉ Mục nội bộ của PCS, đến lượt nó thu thập dữ liệu từ các sự kiện được kích hoạt khi hợp đồng được gọi.&#x20;

Đối với kích thước thời gian trong bộ lập chỉ mục nội bộ của PancakeSwap, chúng tôi sử dụng giờ quốc tế chuẩn (UTC) cho thống kê hàng ngày. Do đó, khi trục ngang trên Bảng Điều Khiển hiển thị ngày tháng, nó đại diện cho ngày theo giờ quốc tế chuẩn (UTC).<br>

## Chỉ Số Cốt Lõi

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Khối Lượng (Khối Lượng Giao Dịch):** Chúng tôi theo dõi dữ liệu hàng ngày cho mỗi cặp giao dịch và dữ liệu giao dịch hàng ngày cho mỗi token. Khối lượng giao dịch hàng ngày được xác định bằng cách nhân khối lượng giao dịch của mỗi token trong ngày với giá của nó.

**Tổng Giá Trị Khóa:** Lấy tất cả các nhóm từ Bộ Lập Chỉ Mục nội bộ và đọc reserve\_usd hoặc total\_value\_locked\_usd từ mỗi nhóm.&#x20;

**Giá:** Trong PCS Internal Indexer, chúng tôi sử dụng một số nhóm cơ sở để tính toán giá liên quan đến USD. Nhóm chính là nhóm giao dịch stablecoin, nơi chúng tôi sử dụng nhóm giao dịch có khối lượng cao nhất làm nhóm cơ sở và tính toán giá USD của stablecoin dựa trên trọng số khối lượng giao dịch. Ngoài ra, nhóm giao dịch của token cơ sở với stablecoin của chuỗi cũng được coi là nhóm cơ sở để cung cấp giá USD.

_Các token không được đưa vào danh sách trắng hoặc không được ghép với các token trong danh sách trắng được loại trừ khỏi các tính toán này._

<br>
