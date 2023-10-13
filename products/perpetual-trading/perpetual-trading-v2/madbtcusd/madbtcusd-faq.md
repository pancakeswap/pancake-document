# MADBTCUSD FAQ

### How is MADBTCUSD Index Calculated?

MADBTCUSD is calculated based on the following formula:

**MADBTCUSD Index**

$$
\begin{align*}
\text{drift} &= \frac{\text{btcCurrentPrice} - 1}{\text{btcLastSecondPrice}} \\
\\
\sigma &= \frac{\text{expectedvol}}{\sqrt{3600 \times 24 \times 365}} \\
\\
\text{norm} &= \text{norminv}(\text{Random}, 0, 1) \\
\\
S_{n+1} &= S_n \times \exp\left( \left(\text{drift} - \frac{\sigma^2}{2}\right) \times dt + \sigma \times \sqrt{dt} \times \text{norm} \right)
\end{align*}
$$



where:

* Initial Sn=1000 &#x20;
* dt=1
* expected vol：250%(expected vol is the expected time volatility of the MADBTC)
* the "**Random number**" is calculated based on the current **BTC price with 8 decimal places of precision**

**Calculation of Random Number:**

```python
import hashlib
from decimal import Decimal

# Assume the current price of Bitcoin is 48923.56789101
bitcoin_price = Decimal("48923.56789101")

# Calculate the SHA-256 hash of the Bitcoin price
price_hash = hashlib.sha256(str(bitcoin_price).encode('utf-8')).hexdigest()

# Extract the first 4 hexadecimal numbers from the hash
hash_substring = price_hash[:4]

# Converts a hexadecimal string to an integer
hash_integer = int(hash_substring, 16)

# Divide the integer by 65536 (the decimal number corresponding to the hexadecimal number FFFF) to get a num
random_number = hash_integer / 65536
# Print the random number
print(random_number)

```

If the random number determined is 0, it will be recalculated again

### Where can I cross-verify the BTC and MADBTCUSD historical price?

The BTC and MADBTCUSD price feed can be found here:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

