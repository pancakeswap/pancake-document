# FAQ về Solana Farming

### 1. SOL Farming hoạt động như thế nào?

* V3 Farming dựa trên **chiến dịch**, nghĩa là farms chỉ hoạt động trong một khoảng thời gian nhất định.
* Trong chiến dịch:
  * Token phần thưởng được phân phối **mỗi giây** cho **các vị thế thanh khoản đang hoạt động**.
  * APR Farming sẽ được hiển thị trên trang danh sách pool và trang vị thế của tôi
* Sau khi chiến dịch kết thúc:
  1. **Không còn phần thưởng** được phân phối.
  2. **APR Farming sẽ không còn được hiển thị** trên trang danh sách pool và trang vị thế của tôi
  3. Farm trở nên **không hoạt động**, nhưng có thể được khởi động lại bởi người tạo bằng cách thêm phần thưởng.

### 2. Tôi có cần stake LP NFT để kiếm phần thưởng farming không?

* **Không cần staking**.
* Miễn là vị thế thanh khoản của bạn **đang hoạt động (trong phạm vi)** trong pool có farm đang hoạt động, bạn sẽ tự động kiếm phần thưởng.

### 3. Có bộ tăng cường farm nào không?

* **Không**, V3 farms **không** hỗ trợ bất kỳ cơ chế tăng cường nào.
* Phần thưởng chỉ dựa trên cổ phần thanh khoản đang hoạt động của bạn trong pool.

### 4. Có thể tạo nhiều farm cho cùng một pool không?

* **Không**, chỉ có thể tồn tại **một farm cho mỗi cặp token và mức phí**.

### 5. SOL farms được cấu hình như thế nào?

#### A. Token Phần thưởng

* Tối đa **3 loại token phần thưởng khác nhau** có thể được gán cho mỗi farm.
* Khi được thiết lập, các loại token phần thưởng **không thể thay đổi**.
* Người tạo farm có thể:
  * **Nạp thêm** các token phần thưởng đã phân bổ.
  * **Gia hạn thời gian farming** sau khi chiến dịch kết thúc.

#### B. Thời gian Chiến dịch

* Các chiến dịch phải kéo dài tối thiểu **7 ngày** và tối đa **90 ngày**.

### 6. Farm có thể được chỉnh sửa sau khi tạo không?

Người tạo farm có thể chỉnh sửa các thông số sau **sau khi tạo farm**:

1. Tỷ lệ phân phối phần thưởng (mỗi giây)
2. Ngày kết thúc chiến dịch
3. Thêm token phần thưởng và số lượng phần thưởng tương ứng (chỉ khi ban đầu được gán ít hơn 3 token)
