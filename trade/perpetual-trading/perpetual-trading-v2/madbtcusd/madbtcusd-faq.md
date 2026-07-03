# FAQ MADBTCUSD

### Bagaimana Cara Menghitung Indeks MADBTCUSD?

MADBTCUSD dihitung berdasarkan rumus berikut:

**Indeks MADBTCUSD**

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



di mana:

* Sn awal=1000 &#x20;
* dt=1
* vol yang diharapkan：100% (vol yang diharapkan adalah volatilitas waktu yang diharapkan dari MADBTC)
* "**Angka acak**" dihitung berdasarkan **harga BTC saat ini dengan presisi 8 desimal**

**Perhitungan Angka Acak:**

```python
import hashlib
from decimal import Decimal

# Asumsikan harga Bitcoin saat ini adalah 48923.56789101
bitcoin_price = Decimal("48923.56789101")

# Hitung hash SHA-256 dari harga Bitcoin
price_hash = hashlib.sha256(str(bitcoin_price).encode('utf-8')).hexdigest()

# Ambil 8 angka heksadesimal pertama dari hash
hash_substring = price_hash[:8]

# Mengonversi string heksadesimal ke bilangan bulat
hash_integer = int(hash_substring, 16)

# Bagi bilangan bulat dengan 4294967296 (angka desimal yang sesuai dengan angka heksadesimal FFFFFFFF) untuk mendapatkan angka
random_number = hash_integer / 4294967296
# Cetak angka acak
print(random_number)
```

Jika angka acak yang ditentukan adalah 0, maka akan dihitung ulang

### Di mana saya dapat memverifikasi silang harga historis BTC dan MADBTCUSD?

Umpan harga BTC dan MADBTCUSD dapat ditemukan di sini:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### Data backtest historis BTC & MADBTC

Untuk memverifikasi silang harga historis BTC & MADBTC, kami telah menyediakan grafik backtest di bawah ini.&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
