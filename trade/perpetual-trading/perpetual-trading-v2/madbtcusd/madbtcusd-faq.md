# FAQ do MADBTCUSD

### Como o Índice MADBTCUSD é Calculado?

O MADBTCUSD é calculado com base na seguinte fórmula:

**Índice MADBTCUSD**

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



onde:

* Sn inicial=1000 &#x20;
* dt=1
* vol esperado：100% (o vol esperado é a volatilidade temporal esperada do MADBTC)
* o "**Número aleatório**" é calculado com base no **preço atual do BTC com 8 casas decimais de precisão**

**Cálculo do Número Aleatório:**

```python
import hashlib
from decimal import Decimal

# Assuma que o preço atual do Bitcoin é 48923.56789101
bitcoin_price = Decimal("48923.56789101")

# Calcule o hash SHA-256 do preço do Bitcoin
price_hash = hashlib.sha256(str(bitcoin_price).encode('utf-8')).hexdigest()

# Extraia os primeiros 8 números hexadecimais do hash
hash_substring = price_hash[:8]

# Converte uma string hexadecimal em um inteiro
hash_integer = int(hash_substring, 16)

# Divide o inteiro por 4294967296 (o número decimal correspondente ao número hexadecimal FFFFFFFF) para obter um num
random_number = hash_integer / 4294967296
# Imprima o número aleatório
print(random_number)
```

Se o número aleatório determinado for 0, ele será recalculado novamente

### Onde posso verificar o histórico de preços do BTC e MADBTCUSD?

O feed de preços do BTC e MADBTCUSD pode ser encontrado aqui:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### Dados históricos de backtest do BTC e MADBTC

Para verificar os preços históricos do BTC e MADBTC, fornecemos um gráfico de backtest abaixo.&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
