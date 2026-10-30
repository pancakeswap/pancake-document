# MADBTCUSD 자주 묻는 질문 (FAQ)

### MADBTCUSD 지수는 어떻게 계산되나요?

MADBTCUSD는 다음 공식을 기반으로 계산됩니다.

**MADBTCUSD 지수**

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

여기서:

* 초기 Sn=1000
* dt=1
* expected vol：100%(expected vol은 MADBTC의 예상 시간 변동성입니다)
* "**난수(Random number)**"는 현재 **소수점 8자리 정밀도의 BTC 가격**을 기반으로 계산됩니다

**난수 계산:**

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

산출된 난수가 0이면 다시 계산합니다.

### BTC와 MADBTCUSD의 과거 가격은 어디에서 교차 검증할 수 있나요?

BTC와 MADBTCUSD 가격 피드는 다음에서 확인할 수 있습니다.

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### BTC 및 MADBTC 과거 백테스트 데이터

BTC와 MADBTC의 과거 가격을 교차 검증할 수 있도록 아래에 백테스트 그래프를 제공합니다.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
