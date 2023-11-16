# Perguntas Frequentes do MADBTCUSD

## Como o índice MADBTCUSD é calculado?&#x20;

MADBTCUSD é calculado com base na seguinte fórmula:&#x20;

**Índice MADBTCUSD**

$$
\begin{align*}
\text{drift} &= \left( \frac{\text{btcCurrentPrice} - 1}{\text{btcLastSecondPrice}} \right) \times 3 \\
\\
\sigma &= \frac{\text{expectedvol}}{\sqrt{3600 \times 24 \times 365}} \\
\\
norm &= \text{norminv}(\text{Random}, 0, 1) \\
\\
S_{n+1} &= S_{n} \times e^{\left[\left(\text{drift} - \frac{\sigma^2}{2}\right) \times \text{dt} + \sigma \times \sqrt{\text{dt}} \times norm\right]}
\end{align*}
$$

Onde:

* Initial Sn=1000&#x20;
* dt=1&#x20;
* vol esperado: 100% (vol esperado é a volatilidade de tempo esperada do MADBTC)&#x20;
* o "número aleatório" é calculado com base no preço atual do BTC com 8 casas decimais de precisão&#x20;
* Cálculo do número aleatório:

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

Se o número aleatório determinado for 0, ele será recalculado novamente&#x20;

## Onde posso verificar o preço histórico do BTC e do MADBTCUSD?&#x20;

O feed de preços BTC e MADBTCUSD pode ser encontrado aqui:&#x20;

[BitcoinUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)&#x20;

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)&#x20;

## Dados históricos de backtest de BTC e MADBTC&#x20;

Para verificar os preços históricos do BTC e MADBTC, fornecemos um gráfico de backtest abaixo.

<figure><img src="../../../../.gitbook/assets/image (187).png" alt=""><figcaption></figcaption></figure>
