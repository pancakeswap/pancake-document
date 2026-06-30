# FAQ MADBTCUSD

### Chỉ Số MADBTCUSD được Tính Thế Nào?

MADBTCUSD được tính dựa trên công thức sau:

**Chỉ Số MADBTCUSD**

$$
\begin{align*}
\text{drift} &= \left( \frac{\text{btcCurrentPrice} - 1}{\text{btcLastSecondPrice}} \right) \times 5 \\
\\
\sigma &= \frac{\text{expectedvol}}{\sqrt{3600 \times 24 \times 365}} \\
\\
norm &= \text{norminv}(\text{Random}, 0, 1) \\
\\
S_{n+1} &= S_{n} \times e^{\left[\left(\text{drift} - \frac{\sigma^2}{2}\right) \times \text{dt} + \sigma \times \sqrt{\text{dt}} \times norm\right]}
\end{align*}
$$



trong đó:

* Sn ban đầu=1000 &#x20;
* dt=1
* expected vol：100% (expected vol là độ biến động thời gian kỳ vọng của MADBTC)
* "**Số ngẫu nhiên**" được tính dựa trên **giá BTC hiện tại với độ chính xác 8 chữ số thập phân**

**Tính Toán Số Ngẫu Nhiên:**

```python
import hashlib
from decimal import Decimal

# Giả sử giá Bitcoin hiện tại là 48923.56789101
bitcoin_price = Decimal("48923.56789101")

# Tính hash SHA-256 của giá Bitcoin
price_hash = hashlib.sha256(str(bitcoin_price).encode('utf-8')).hexdigest()

# Trích xuất 8 số thập lục phân đầu tiên từ hash
hash_substring = price_hash[:8]

# Chuyển đổi chuỗi thập lục phân thành số nguyên
hash_integer = int(hash_substring, 16)

# Chia số nguyên cho 4294967296 (số thập phân tương ứng với số thập lục phân FFFFFFFF) để lấy một số
random_number = hash_integer / 4294967296
# In số ngẫu nhiên
print(random_number)
```

Nếu số ngẫu nhiên được xác định là 0, nó sẽ được tính toán lại

### Tôi có thể xác minh chéo dữ liệu lịch sử giá BTC và MADBTCUSD ở đâu?

Nguồn cấp giá BTC và MADBTCUSD có thể tìm thấy tại đây:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### Dữ liệu backtest lịch sử của BTC & MADBTC

Để xác minh chéo giá lịch sử BTC & MADBTC, chúng tôi đã cung cấp biểu đồ backtest dưới đây.&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
