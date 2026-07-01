# FAQ de MADBTCUSD

### ¿Cómo se calcula el Índice MADBTCUSD?

MADBTCUSD se calcula basándose en la siguiente fórmula:

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



donde:

* Sn inicial=1000 &#x20;
* dt=1
* volatilidad esperada：100%(la volatilidad esperada es la volatilidad temporal esperada de MADBTC)
* el "**Número aleatorio**" se calcula basándose en el **precio actual de BTC con 8 decimales de precisión**

**Cálculo del Número Aleatorio:**

```python
import hashlib
from decimal import Decimal

# Supón que el precio actual de Bitcoin es 48923.56789101
bitcoin_price = Decimal("48923.56789101")

# Calcula el hash SHA-256 del precio de Bitcoin
price_hash = hashlib.sha256(str(bitcoin_price).encode('utf-8')).hexdigest()

# Extrae los primeros 8 números hexadecimales del hash
hash_substring = price_hash[:8]

# Convierte una cadena hexadecimal a un entero
hash_integer = int(hash_substring, 16)

# Divide el entero por 4294967296 (el número decimal correspondiente al número hexadecimal FFFFFFFF) para obtener un número
random_number = hash_integer / 4294967296
# Imprime el número aleatorio
print(random_number)
```

Si el número aleatorio determinado es 0, se recalculará

### ¿Dónde puedo verificar cruzadamente el precio histórico de BTC y MADBTCUSD?

El feed de precios de BTC y MADBTCUSD se puede encontrar aquí:

[BTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=BTCUSD\&limit=1800)

[MADBTCUSD](https://www.apollox.finance/bapi/futures/v1/public/future/apx/V2MarkPriceKline?symbol=MADBTCUSD\&limit=1800)

### Datos de prueba retrospectiva histórica de BTC y MADBTC

Para verificar cruzadamente los precios históricos de BTC y MADBTC, hemos proporcionado un gráfico de prueba retrospectiva a continuación.&#x20;

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/photo_2023-10-26_19-24-40.jpg" alt=""><figcaption></figcaption></figure>
