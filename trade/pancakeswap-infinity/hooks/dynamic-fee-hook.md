# Dynamic Fee Hook

Dynamic Fee Hook chính thức của PancakeSwap được thiết kế để tạo ra sự trao đổi giá trị công bằng hơn giữa Nhà Cung Cấp Thanh Khoản và Trader. Nó bảo vệ LP khỏi tổn thất tạm thời (IL) quá mức trong khi vẫn giữ cho thị trường hiệu quả với trader.

Được xây dựng bởi nhóm cốt lõi PancakeSwap, hook này được tùy chỉnh đặc biệt để cung cấp thay thế thông minh, thích ứng cho các mô hình phí cố định thông thường.

#### 🔍 Tại Sao Cần Phí Động?

Các giao dịch chênh lệch giá lớn gây ra sự phân kỳ giá lớn hơn trong các pool, làm tăng IL cho LP. Mô hình phí động của chúng tôi tính phí tỷ lệ thuận cao hơn cho các giao dịch chênh lệch giá lớn hơn để bù đắp rủi ro này — trong khi vẫn để đủ dư địa cho các nhà chênh lệch giá kiếm lợi nhuận và giữ cho giá được căn chỉnh.

#### 📊 Điều Này Khác Với Các Mô Hình Khác Như Thế Nào?

Các mô hình khác trong quá khứ đã sử dụng dữ liệu lịch sử để ước tính biến động, các yếu tố khác để điều chỉnh phí. Tuy nhiên:

* Dữ liệu lịch sử là chỉ số trễ và có thể không dự đoán chính xác biến động tương lai.
* Các sự kiện thị trường bên ngoài (như thay đổi quy định hoặc biến động kinh tế) có thể làm cho xu hướng trong quá khứ trở nên không đáng tin cậy.
* Các mô hình phức tạp, nhiều tham số có nguy cơ overfitting — hoạt động tốt trên dữ liệu quá khứ nhưng kém trên các điều kiện mới, chưa thấy.

Cách tiếp cận của chúng tôi đơn giản hơn, thích ứng hơn và dựa trên hành vi giao dịch thực tế.

#### ⚙️ Cách Hoạt Động

* **Chúng tôi không dự đoán biến động hay các yếu tố vĩ mô khác**\
  Thay vào đó, mô hình của chúng tôi vốn được hưởng lợi từ hành vi của các nhà chênh lệch giá trong các chế độ thị trường khác nhau:
  * **Biến động cao:** Nhiều giao dịch chênh lệch giá với quy mô lớn hơn → Phí cao hơn cho LP, bù đắp một phần lớn hơn của IL.
  * **Biến động thấp:** Ít giao dịch nhỏ hơn → IL thấp hơn theo bản chất, nhưng LP vẫn kiếm phí cao hơn so với mô hình phí cố định.
* **Mô hình của chúng tôi sử dụng**
  * Giá pool có trọng số mũ để phát hiện giao dịch chênh lệch giá.
  * Đường cong phí mũ dựa trên tác động giá của mỗi hoán đổi.
  * Mức phí tối đa là 5% để duy trì sự công bằng với trader.

{% hint style="success" %}
Điều này đảm bảo phí tăng động theo tác động giao dịch trong khi tự động thích ứng với điều kiện thị trường thay đổi.
{% endhint %}

* **Cân Bằng Động Lực**\
  Các nhà chênh lệch giá vẫn giữ lại \~50% lợi nhuận sau phí động, đảm bảo họ có động lực để duy trì giá pool phù hợp với thị trường.

#### 📌 Điểm Chính

* Không phụ thuộc vào dự đoán biến động hay các yếu tố vĩ mô khác.
* Tự động thích ứng với biến động thị trường dựa trên hành vi giao dịch thực tế.
* Bảo vệ LP khỏi IL trên cơ sở từng giao dịch.
* Duy trì động lực mạnh mẽ cho các nhà chênh lệch giá để thu hẹp khoảng cách giá.
* Mang lại lợi ích cho trader với thanh khoản sâu hơn và phí cơ bản thấp hơn.
