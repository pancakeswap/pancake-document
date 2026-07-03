# FAQ MADBTCUSD

### Comment l'indice MADBTCUSD est-il calculé ?

MADBTCUSD est calculé selon la formule suivante :

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



où :

* Sn initial = 1000 &#x20;
* dt = 1
* vol attendue : 100% (la vol attendue correspond à la volatilité temporelle attendue du MADBTC)
* le "**nombre aléatoire**" est calculé sur la base du **prix BTC actuel avec 8 décimales de précision**

**Calcul du nombre aléatoire :**

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

Si le nombre aléatoire déterminé est 0, il sera recalculé.

### Où puis-je vérifier l'historique des prix BTC et MADBTCUSD ?

Le flux de prix BTC et MADBTCUSD peut être trouvé ici :

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### Données historiques de backtest BTC & MADBTC

Pour vérifier les prix historiques de BTC & MADBTC, nous avons fourni un graphique de backtest ci-dessous.&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
