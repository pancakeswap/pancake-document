---
description: Cung cấp thanh khoản đơn giản chỉ với một cú nhấp chuột
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### Zap là gì? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap cho phép cung cấp thanh khoản đơn giản. Thêm thanh khoản chỉ với một token và một cú nhấp chuột, không cần hoán đổi thủ công hoặc cân bằng token.

* Thêm thanh khoản chỉ với một token: Bạn có thể thêm thanh khoản chỉ bằng một token trong cặp giao dịch. Zap sẽ tự động thực hiện hoán đổi bằng token bạn cung cấp và tự động cân bằng cặp giao dịch về tỷ lệ 50/50 trước khi thêm thanh khoản.
* Thêm thanh khoản với số lượng token mất cân bằng trong cặp giao dịch: Bạn có thể thêm thanh khoản ngay cả khi số lượng token bạn cung cấp trong cặp giao dịch không cân bằng hoàn hảo với pool hiện tại. Ví dụ 30:70, khác với trọng số pool mặc định 50:50. Zap sẽ tự động cân bằng lại token về tỷ lệ 50/50 trước khi thêm thanh khoản.
* Xóa thanh khoản và chọn token nào bạn muốn nhận: Khi xóa thanh khoản, Zap cho phép bạn chỉ nhận một token trong cặp giao dịch. Zap sẽ tự động thực hiện hoán đổi trước khi trả lại token.

### Bật Zap <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

Theo mặc định, tính năng Zap được bật cho mỗi người dùng. Nếu bạn không thấy giao diện Zap mới khi thêm hoặc xóa thanh khoản, vui lòng bật trong bảng cài đặt. Bạn có thể mở bảng cài đặt bằng cách nhấp biểu tượng bánh răng.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
Lưu ý: Hiện tại, tính năng Zap đang trong giai đoạn beta. Lưu ý rằng nó không hỗ trợ một số token, chẳng hạn như token có phí khi chuyển nhượng. Nếu bạn gặp bất kỳ vấn đề nào khi thêm hoặc xóa thanh khoản, vui lòng tắt trong bảng cài đặt.
{% endhint %}

### Zap In (Thêm Thanh khoản) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

Truy cập [trang Liquidity](https://pancakeswap.finance/liquidity) và chọn "Add Liquidity".

Chọn cặp giao dịch bạn muốn cung cấp thanh khoản bằng cách chọn hai token đầu vào, xem [hướng dẫn Thanh khoản](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) để tìm hiểu thêm.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

Nhấp nút "Add Liquidity" để tiến hành.

Nếu token trong cặp giao dịch bạn đang thêm thanh khoản có số dư trong ví của bạn. Checkbox cho token đó sẽ tự động được chọn. Nếu cả hai token đều có số dư trong ví của bạn, cả hai checkbox sẽ được chọn.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### Zap bằng một token <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

Bạn có thể thêm thanh khoản chỉ bằng một token trong cặp giao dịch. Chỉ chọn một checkbox cho token bạn muốn sử dụng. Zap sẽ tự động hoán đổi một nửa token đã chọn sang token kia trong cặp giao dịch trước khi thêm thanh khoản. Bạn sẽ thấy thông báo cảnh báo cho biết token nào sẽ được chuyển đổi.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
Nếu tác động giá quá cao, Zap sẽ bảo vệ bạn bằng trượt giá. Nhấp "Reduce TOKEN" để giảm xuống giới hạn ưu tiên.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### Zap bằng hai token với số lượng mất cân bằng <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Nếu cả hai token được chọn, số lượng token đầu vào không khớp với tỷ lệ 50/50. Cân bằng Zap sẽ được áp dụng. Bạn sẽ thấy thông báo "Some of your Token A will be converted to Token B".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
Nếu bạn không muốn Zap cân bằng số lượng token trước khi thêm thanh khoản, chỉ cần nhấp "Don't Convert". Trong trường hợp này, Zap sẽ điều chỉnh số lượng token đầu vào để khớp với tỷ lệ 50/50 thay vì cố hoán đổi và cân bằng lại.
{% endhint %}

### Tiến hành Zap <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

Khi bạn nhấp "Supply", chi tiết của Zap sẽ được hiển thị và chờ bạn xác nhận.

Bạn sẽ thấy:

1. Bạn sẽ nhận được bao nhiêu LP token.
2. Token đầu vào là gì và số lượng token bạn đang nạp.
3. Cách các token đầu vào được giao dịch để khớp với tỷ lệ 50/50.
4. Dung sai trượt giá bạn đang sử dụng.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap out (Xóa Thanh khoản) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap cũng cho phép bạn nhận một token đơn lẻ trong cặp giao dịch khi xóa thanh khoản.

1. Truy cập [trang Liquidity](https://pancakeswap.finance/swap#/pool).
2. Nhấp vào cặp bạn muốn xóa thanh khoản trong "Your Liquidity".
3. Nhấp "Remove". Một cửa sổ pop-up mới sẽ xuất hiện.

Trong phần "You Will Receive", bạn có thể bỏ chọn token bạn không muốn nhận. Zap sẽ tự động hoán đổi và chuyển đổi 100% số tiền trả về thành token đã chọn khi xóa thanh khoản.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
