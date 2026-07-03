# FAQ MADBTCUSD

### Come viene calcolato l'Indice MADBTCUSD?

MADBTCUSD viene calcolato sulla base della seguente formula:

**Indice MADBTCUSD**

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



dove:

* Sn iniziale=1000 &#x20;
* dt=1
* vol attesa：100% (la vol attesa è la volatilità temporale attesa di MADBTC)
* il "**Numero casuale**" viene calcolato in base al **prezzo BTC corrente con 8 cifre decimali di precisione**

**Calcolo del Numero Casuale:**

```python
import hashlib
from decimal import Decimal

# Assume the current price of Bitcoin is 48923.56789101
bitcoin_price = Decimal("48923.56789101")

# Calculate the SHA-256 hash of the Bitcoin price
price_hash = hashlib.sha256(str(bitcoin_price).encode('utf-8')).hexdigest()

# Extract the first 8 hexadecimal numbers from the hash
hash_substring = price_hash[:8]

# Converts a hexadecimal string to an integer
hash_integer = int(hash_substring, 16)

# Divide the integer by 4294967296 (the decimal number corresponding to the hexadecimal number FFFFFFFF) to get a num
random_number = hash_integer / 4294967296
# Print the random number
print(random_number)
```

Se il numero casuale determinato è 0, verrà ricalcolato

### Dove posso verificare il prezzo storico di BTC e MADBTCUSD?

Il feed del prezzo di BTC e MADBTCUSD si trova qui:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### Dati di backtest storici di BTC & MADBTC

Per verificare incrociando i prezzi storici di BTC & MADBTC, abbiamo fornito un grafico di backtest di seguito.&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
