# Cách Sử Dụng TWAP

## TWAP là gì?

TWAP (Time-weighted Average Price - Giá bình quân theo thời gian) là loại lệnh phổ biến trong CeFi giúp chia nhỏ lệnh thành các giao dịch nhỏ hơn và thực hiện chúng theo các khoảng thời gian đều đặn. Mục tiêu chính của lệnh TWAP là giảm tác động giá của lệnh. Nó cũng hữu ích nếu bạn muốn thực hiện chiến lược trung bình hóa chi phí đô la (DCA) và mua một token nhất định theo lịch trình đều đặn (ví dụ: mỗi tháng một lần).

Do đó, TWAP phù hợp nhất khi kích thước lệnh lớn so với thanh khoản hiện có, hoặc khi bạn dự đoán một giai đoạn biến động giá cao mà không có xu hướng tăng hay giảm rõ ràng.

## Cách đặt lệnh TWAP?

1. Đến trang Swap và chọn tùy chọn lệnh TWAP bằng cách nhấp vào TWAP
2. Chọn token "Từ" và "Đến" rồi nhập số lượng bạn muốn giao dịch.
3. Giao diện cho phép cả lệnh dTWAP theo thị trường, thực hiện tất cả giao dịch ở giá thị trường hiện có, và lệnh dTWAP giới hạn, chỉ thực hiện từng giao dịch riêng lẻ nếu chúng nằm trong giới hạn giá do người dùng đặt. \
   Trong ví dụ này, chúng tôi chọn thực hiện các lệnh TWAP theo giá thị trường.
4. Tiếp theo, chúng tôi chỉ định các thông số TWAP. Có 3 thông số chính kiểm soát hiệu quả của lệnh dTWAP:
   1. Tổng giao dịch: Cho phép bạn chỉ định số lượng giao dịch riêng lẻ mà lệnh sẽ được chia thành. Thanh trượt trong giao diện bắt đầu với 1 giao dịch và cho phép bạn tăng số lượng giao dịch riêng lẻ, hoặc cho phép bạn nhập trực tiếp tổng số giao dịch vào trường nhập liệu.\
      Bạn nên lưu ý rằng có sự đánh đổi nhất định khi chỉ định thông số này: nhiều giao dịch hơn có nghĩa là kích thước giao dịch riêng lẻ nhỏ hơn, đồng nghĩa với tác động giá nhỏ hơn. Tuy nhiên, nhiều giao dịch hơn cũng có nghĩa là nhiều giao dịch hơn và phí gas tổng thể cao hơn.&#x20;
   2. Khoảng Thời Gian Giao Dịch: Đặt khoảng thời gian giữa mỗi giao dịch riêng lẻ. Giao diện bắt đầu với mức tối thiểu được phép (2 phút), để lại thời gian tối thiểu cho cuộc đấu thầu taker và quyết toán khối giữa mỗi phần. Bạn có thể đặt thời gian bất kỳ mong muốn. Một giao dịch sẽ không bao giờ thực hiện trước khi thời gian này trôi qua sau giao dịch trước.\
      Bạn cũng nên lưu ý khi đặt thông số này: khoảng thời gian dài hơn sẽ cho phép các nhà kinh doanh chênh lệch giá có cửa sổ dài hơn để đóng bất kỳ sự chênh lệch giá nào trên các pool bị ảnh hưởng và đưa dự trữ trở lại cân bằng (ngang bằng với giá giao ngay). Tuy nhiên, sẽ mất nhiều thời gian hơn để lệnh được khớp và sẽ tạo thêm sự không chắc chắn về giá khớp cuối cùng, đặc biệt trong thời điểm biến động tăng cao
   3. Thời Gian Tối Đa: Thời gian tối đa trong đó tổng số tất cả các giao dịch riêng lẻ cấu thành toàn bộ lệnh dTWAP có thể được thực thi. Sau thời hạn này, giao dịch hết hạn, bất kể số lượng thực tế đã hoán đổi.\
      Lưu ý rằng trong lệnh giới hạn, không phải tất cả các phần đều có thể được thực thi, tùy thuộc vào việc giá có nằm trong các thông số đã đặt hay không. \
      Thời hạn đề xuất mặc định được tính bằng cách nhân số lượng khoảng thời gian với khoảng thời gian giao dịch, sau đó nhân đôi số lượng này để làm bộ đệm cho phép đủ thời gian cho hoạt động trên chuỗi. (Lưu ý rằng việc đặt thời hạn ngắn hơn mức mặc định này có thể dẫn đến lệnh chỉ được khớp một phần).

Như có thể thấy, các thông số này cung cấp sự linh hoạt đáng kể trong việc tùy chỉnh từng lệnh, tính đến các yếu tố như điều kiện thị trường, phí gas hiện tại, v.v.

8. Nhấn "Place order". Kiểm tra lại chi tiết lệnh, chấp nhận tuyên bố từ chối trách nhiệm và nhấn "Confirm order".
9. Sau khi giao dịch được xử lý, bạn sẽ có thể xem trạng thái lệnh trong phần lịch sử lệnh, dưới "Open orders".
10. Các lệnh đang mở có thể được hủy bất cứ lúc nào bằng cách mở rộng lệnh và nhấp vào nút "Cancel Order".

Những điều cần xem xét

* Các lệnh được thực hiện trong các giao dịch nhỏ hơn trong một khoảng thời gian cụ thể và phụ thuộc vào điều kiện thị trường cùng các rủi ro khác.
* Giao dịch của bạn có thể được thực hiện ở mức giá khác đáng kể so với giá thị trường hiện tại (mặc dù không tệ hơn giá giới hạn của bạn, nếu bạn đã đặt một mức), điều này có thể dẫn đến tổn thất đáng kể. Nếu giá thị trường hiện có kém hơn giá giới hạn bạn đã đặt, một số giao dịch trong lệnh của bạn có thể không được thực thi, dẫn đến lệnh chỉ được khớp một phần.
* Các giao dịch dựa trên một giao thức phi tập trung sử dụng các taker ngoài chuỗi cạnh tranh để khớp lệnh. Các taker này có quyền yêu cầu phí, giao thức sẽ trừ phí cho taker thắng từ token đầu ra.&#x20;
* Các taker có thể tính đến phí gas cho giao dịch của bạn khi đặt phí của họ, điều này có thể dẫn đến biến động trong số tiền phí.

<br>
