# Cách dùng Farm với BscScan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Vì cần nhiều bước, việc dùng Farm trên PancakeSwap thoạt đầu có thể hơi đáng ngại. Hướng dẫn này sẽ giúp bạn dùng trực tiếp hợp đồng Farm thông qua BscScan.

{% hint style="warning" %}
Hãy lưu ý rằng không nên dùng BscScan để tương tác với hợp đồng nếu bạn là người mới. Nếu chưa thật tự tin, chúng tôi khuyên bạn dùng [hướng dẫn Cách dùng Farm](https://docs.pancakeswap.finance/earn/yield-farming/how-to-use-farms/how-to-use-farms) thay thế.
{% endhint %}

## Tìm mã định danh quy trình của Farm

Để tương tác đúng với hợp đồng thông minh của farm, bạn cần mã định danh quy trình (PID) tương ứng với cặp LP của mình. Hiện tại, cách dễ nhất để tìm là kiểm tra trên GitHub.

1\. Mở [mã Farms của website PancakeSwap trên GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Nhấn **Control**/**command** + **F** và tìm cặp của bạn theo ký hiệu (không phải tên dự án). Ví dụ: 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. Ghi lại hoặc sao chép số PID (trong trường hợp này là 389) ở nơi bạn dễ truy cập. Bạn sẽ cần đến nó sau.

## Gửi LP Token qua BscScan

Việc gửi LP Token bằng BscScan gồm một vài bước. Chúng tôi đã chia nhỏ thành từng bước để bạn dễ làm theo.

### Lấy địa chỉ Main Staking Contract

Địa chỉ của hợp đồng staking chính là: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Nhưng nếu bạn muốn xác nhận lại, hãy truy cập [trang BscScan của PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Bạn sẽ thấy địa chỉ ở góc trên bên trái. Nhấp vào **biểu tượng trang giấy** để sao chép vào bộ nhớ tạm. Bạn sẽ cần đến nó ngay sau đây.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### Mở hợp đồng của LP Token

Bạn cần phê duyệt hợp đồng thông minh cho LP Token mà bạn muốn đưa vào farm trước khi có thể chi tiêu nó.

### Từ mã nguồn

1\. Trước tiên, mở [farms.ts trên GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Nhấn **Control**/**command** + **F** và tìm cặp của bạn theo ký hiệu (không phải tên dự án). Ví dụ: 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Khi đã mở được mã của cặp LP bạn cần tìm, hãy tìm địa chỉ nằm sau "56:". Đây sẽ là địa chỉ hợp đồng của bạn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### Từ giao diện (UI)

1\. Trước tiên, truy cập [trang Farms của PancakeSwap](https://pancakeswap.finance/farms) và tìm cặp bạn chọn bằng ô "SEARCH" ở góc trên bên phải. Chúng tôi dùng CAKE-BUSD làm ví dụ.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Nhấp **Details** để mở rộng hàng và xem thêm thông tin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Nhấp **View Contract** để mở hợp đồng thông minh trên BscScan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### Cấp quyền cho hợp đồng LP Token

Khi đã mở hợp đồng của LP Token trên BscScan, bạn sẽ phê duyệt việc chi tiêu LP Token của mình vào Farm.

1\. Trên trang hợp đồng của LP Token, vào **Contract**, rồi chọn **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Nhấp **Connect to Web3** để kết nối MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Xác nhận kết nối.

3\. Ở hàm số 1, “approve”, bạn sẽ thấy “spender:address”. Dán địa chỉ hợp đồng của Main Staking Contract mà bạn đã sao chép trước đó.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. Bạn cũng cần phê duyệt số lượng LP Token mà hợp đồng được phép chi tiêu. Trong ô giá trị, bạn cần nhập số lượng theo đơn vị Wei. Bạn có thể dùng [BscScan Unit Converter](https://www.bscscan.com/unitconverter) để dễ dàng đổi số lượng sang Wei. Ở đây chúng tôi dùng 5 CAKE-BUSD LP Token.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
Bạn cũng có thể dùng `-1` làm giá trị để cấp quyền chi tiêu không giới hạn. Điều này không có nghĩa là bạn sẽ mặc định chi tiêu tất cả, mà chỉ có nghĩa là ví của bạn sẽ cho phép giao dịch có kích thước bất kỳ sử dụng hợp đồng này.
{% endhint %}

6\. Nhấp **Write** và chấp nhận thao tác trong ví MetaMask của bạn. Giờ bạn có thể đưa LP Token vào Farm, tối đa bằng số lượng bạn đã phê duyệt.

### Gửi LP Token bằng hợp đồng thông minh Main Staking Contract

Khi Main Staking Contract đã được phê duyệt để chi tiêu LP Token của bạn, đã đến lúc gửi.

1\. Quay lại [trang BscScan của PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vào **Contract**, rồi chọn **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Nhấp **Connect to Web3** để kết nối MetaMask.

3\. Cuộn đến hàm số 2, "deposit", và nhập PID của bạn vào ô "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

Nếu bạn chưa ghi lại PID trước đó, bạn có thể tìm hiểu cách lấy nó ở phần **Tìm mã định danh quy trình của Farm** phía trên trang này.

4\. Bên dưới \_pid bạn sẽ thấy "\_amount". Nhập số lượng LP mà hợp đồng được chi tiêu mà bạn đã phê duyệt trước đó.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Kiểm tra thông tin và nhấp **Write**. Xác nhận thao tác trong MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Bạn có thể xác nhận khoản gửi đã thành công bằng cách nhấp **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Rút khỏi Pool

Rút LP Token khỏi Pool rất giống với việc gửi. Điểm khác biệt là hàm mà bạn tương tác.

1\. Quay lại [trang BscScan của PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vào **Contract**, rồi chọn **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Nhấp **Connect to Web3** để kết nối MetaMask.

3\. Cuộn xuống tận hàm số 15, "withdraw", và nhập PID của bạn vào ô "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

Nếu bạn chưa ghi lại PID trước đó, bạn có thể tìm hiểu cách lấy nó ở phần **Tìm mã định danh quy trình của Farm** phía trên trang này.

4\. Bên dưới \_pid bạn sẽ thấy "\_amount". Nhập số lượng LP bạn muốn rút khỏi Pool.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Kiểm tra thông tin và nhấp **Write**. Xác nhận thao tác trong MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Bạn có thể xác nhận việc rút đã thành công bằng cách nhấp **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Rút khẩn cấp**

‌Dùng hàm rút khẩn cấp cho phép bạn rút toàn bộ tiền khỏi pool khi không còn cách nào khác hiệu quả.

{% hint style="danger" %}
**Dùng hàm rút khẩn cấp sẽ làm bạn mất phần thưởng CAKE!**

Đội ngũ PancakeSwap thực sự khuyên bạn tránh dùng hàm này, trừ khi được đội ngũ PancakeSwap chính thức hướng dẫn, hoặc bạn rất thành thạo việc tương tác với hợp đồng thông minh và hiểu rõ mã bên dưới.
{% endhint %}

‌1. Trên [trang BscScan của PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), vào **Contract**, rồi chọn **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Nhấp **Connect to Web3** để kết nối MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Cuộn xuống hàm số 4, "emergencyWithdraw", và nhập PID của bạn vào ô "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

Nếu bạn chưa ghi lại PID trước đó, bạn có thể tìm hiểu cách lấy nó ở phần **Tìm mã định danh quy trình của Farm** phía trên trang này.

5\. Kiểm tra thông tin và nhấp **Write**. Xác nhận thao tác trong MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Bạn có thể xác nhận việc rút đã thành công bằng cách nhấp **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
