# MADBTCUSD SSS

### MADBTCUSD Endeksi Nasıl Hesaplanır?

MADBTCUSD aşağıdaki formüle göre hesaplanır:

**MADBTCUSD Endeksi**

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



burada:

* Başlangıç Sn=1000 &#x20;
* dt=1
* beklenen vol：%100 (beklenen vol, MADBTC'nin beklenen zaman volatilitesidir)
* "**Rastgele sayı**", **8 ondalık basamak hassasiyetiyle mevcut BTC fiyatı** temel alınarak hesaplanır

**Rastgele Sayının Hesaplanması:**

```python
import hashlib
from decimal import Decimal

# Bitcoin'in mevcut fiyatının 48923.56789101 olduğunu varsay
bitcoin_price = Decimal("48923.56789101")

# Bitcoin fiyatının SHA-256 hash değerini hesapla
price_hash = hashlib.sha256(str(bitcoin_price).encode('utf-8')).hexdigest()

# Hash'ten ilk 8 onaltılık sayıyı çıkar
hash_substring = price_hash[:8]

# Onaltılık dizeyi tam sayıya dönüştür
hash_integer = int(hash_substring, 16)

# Rastgele bir sayı elde etmek için tam sayıyı 4294967296'ya böl
# (FFFFFFFF onaltılık sayısına karşılık gelen onluk sayı)
random_number = hash_integer / 4294967296
# Rastgele sayıyı yazdır
print(random_number)
```

Belirlenen rastgele sayı 0 ise yeniden hesaplanır

### BTC ve MADBTCUSD Geçmiş Fiyatlarını Nereden Çapraz Doğrulayabilirim?

BTC ve MADBTCUSD fiyat akışı burada bulunabilir:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### BTC ve MADBTC Geçmiş Geriye Dönük Test Verileri

BTC ve MADBTC geçmiş fiyatlarını çapraz doğrulamak için aşağıda bir geriye dönük test grafiği sunulmaktadır.&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
