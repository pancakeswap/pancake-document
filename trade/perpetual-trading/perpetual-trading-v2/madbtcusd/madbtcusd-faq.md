# FAQ MADBTCUSD

### Как рассчитывается индекс MADBTCUSD?

MADBTCUSD рассчитывается по следующей формуле:

**Индекс MADBTCUSD**

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



где:

* Начальное Sn=1000 &#x20;
* dt=1
* ожидаемая волатильность：100% (ожидаемая временная волатильность MADBTC)
* «**Случайное число**» рассчитывается на основе текущей **цены BTC с точностью до 8 знаков после запятой**

**Расчёт случайного числа:**

```python
import hashlib
from decimal import Decimal

# Предположим, текущая цена Bitcoin составляет 48923.56789101
bitcoin_price = Decimal("48923.56789101")

# Рассчитываем SHA-256 хеш цены Bitcoin
price_hash = hashlib.sha256(str(bitcoin_price).encode('utf-8')).hexdigest()

# Извлекаем первые 8 шестнадцатеричных символов хеша
hash_substring = price_hash[:8]

# Конвертируем шестнадцатеричную строку в целое число
hash_integer = int(hash_substring, 16)

# Делим целое число на 4294967296 (десятичное число, соответствующее шестнадцатеричному FFFFFFFF) для получения числа
random_number = hash_integer / 4294967296
# Выводим случайное число
print(random_number)
```

Если определённое случайное число равно 0, расчёт повторяется.

### Где можно верифицировать исторические цены BTC и MADBTCUSD?

Ценовые потоки BTC и MADBTCUSD можно найти здесь:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### Исторические данные бэктестирования BTC & MADBTC

Для верификации исторических цен BTC & MADBTC мы предоставляем ниже график бэктестирования.&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
