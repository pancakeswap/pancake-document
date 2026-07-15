# MADBTCUSD FAQ

### MADBTCUSD Index की गणना कैसे की जाती है?

MADBTCUSD की गणना निम्नलिखित सूत्र के आधार पर की जाती है:

**MADBTCUSD Index**

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



जहां:

* Initial Sn=1000 &#x20;
* dt=1
* expected vol：100%(expected vol MADBTC की अपेक्षित समय अस्थिरता है)
* "**यादृच्छिक संख्या**" की गणना **8 दशमलव स्थानों की सटीकता के साथ वर्तमान BTC मूल्य** के आधार पर की जाती है

**यादृच्छिक संख्या की गणना:**

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

यदि निर्धारित यादृच्छिक संख्या 0 है, तो इसे फिर से गणना की जाएगी

### मैं BTC और MADBTCUSD ऐतिहासिक मूल्य को क्रॉस-वेरीफाई कहां कर सकता/सकती हूं?

BTC और MADBTCUSD मूल्य फ़ीड यहां पाई जा सकती है:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### BTC & MADBTC का ऐतिहासिक backtest डेटा

BTC & MADBTC ऐतिहासिक मूल्यों को क्रॉस-वेरीफाई करने के लिए, हमने नीचे एक backtest graph प्रदान किया है।&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
