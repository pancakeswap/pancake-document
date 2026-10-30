# Shared Inventory Hook

Shared Inventory Hook (SIH) chính thức của PancakeSwap được thiết kế để cho phép một nhóm vốn duy nhất làm market-make trên mọi nhóm có chung token, thay vì khóa thanh khoản riêng vào từng nhóm. Hook mang lại báo giá sâu hơn và tác động giá thấp hơn cho trader, đồng thời cho phép nhà cung cấp thanh khoản triển khai ít vốn hơn mà vẫn đạt cùng mức độ bao phủ.

Được xây dựng bởi đội ngũ cốt lõi của PancakeSwap, hook này dành cho các nhà phát hành tài sản và market maker muốn báo giá nhiều cặp trên on-chain mà không làm phân mảnh nguồn vốn dự trữ của mình.

#### 🔍 Tại sao lại là Shared Inventory?

Cung cấp thanh khoản cho nhiều cặp theo cách thông thường đồng nghĩa với việc khóa vốn riêng vào các nhóm riêng biệt, phần lớn số vốn đó nằm không giữa các giao dịch. Thay vào đó, SIH giữ một số dư cho mỗi token và chỉ đưa vào làm thanh khoản khi một giao dịch hoán đổi cần đến, nhờ vậy cùng một khoản vốn có thể hỗ trợ mọi nhóm có chung token đó.

#### 📊 Khác biệt so với các mô hình khác như thế nào?

Thanh khoản tập trung thông thường yêu cầu cam kết toàn bộ vốn gốc vào một nhóm duy nhất. Các cách tiếp cận xuyên nhóm khác, chẳng hạn các lớp thanh toán dựa trên số dư ảo, thường nằm bên ngoài chính AMM, nên thanh khoản có thể không hiển thị như độ sâu nhóm on-chain và không được các aggregator định tuyến trực tiếp.

Thanh khoản của SIH được hook đưa vào và rút ra khỏi nhóm PancakeSwap Infinity CLAMM ở mỗi giao dịch hoán đổi, vì vậy nó xuất hiện như độ sâu nhóm thực sự mà các router có thể nhìn thấy và khớp lệnh.

#### ⚙️ Cách hoạt động

* **Just-in-time (JIT) injection**\
  Trước mỗi giao dịch hoán đổi, hook mint một vị thế thanh khoản tập trung đã được cấu hình vào nhóm; sau khi giao dịch được thực thi, hook burn vị thế và thanh toán kết quả ròng. Vị thế chỉ tồn tại trong thời gian một giao dịch hoán đổi, số dư được giải phóng để phục vụ ngay nhóm tiếp theo cần đến.
* **One balance, many pools**\
  Nguồn vốn dự trữ chính là số dư token của hook, không có khoản nạp riêng cho từng nhóm. Bất kỳ token nào được dùng trong nhiều hơn một nhóm sẽ được chia sẻ cho tất cả các nhóm đó.

{% hint style="success" %}
Điều này tách độ sâu mà một nhóm báo giá khỏi lượng vốn mà nhóm trực tiếp nắm giữ: một hook được cấp vốn có thể báo giá thanh khoản sâu và sát trên nhiều nhóm có chung một token.
{% endhint %}

* **Configurable hook**\
  Với mỗi nhóm mà hook phục vụ, hook giữ một cấu hình độc lập, có thể điều chỉnh cho khoảng giá và độ sâu. Việc dịch chuyển dải giá chỉ cần cập nhật cấu hình, giúp dễ dàng căn lại báo giá quanh mức giá tham chiếu đang biến động.

#### 📌 Những điểm chính

* Một số dư token dùng chung hỗ trợ mọi nhóm sử dụng token đó. Thêm một nhóm mới không tốn thêm vốn gốc.
* Hoàn toàn on-chain và có khả năng kết hợp: thanh khoản SIH là độ sâu nhóm thực, có thể được PancakeSwap và các aggregator bên thứ ba định tuyến.
* Trader nhận được báo giá sâu hơn và tác động giá thấp hơn với khối lượng lớn; các operator kiếm được cùng mức phí giao dịch chỉ với một phần nhỏ vốn so với cách thông thường.
