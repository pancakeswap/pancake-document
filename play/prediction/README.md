# 🔮 Predicción

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Prediction es un mercado de predicción descentralizado, divertido y sencillo.

> **Predice si el precio de BNB, BTC o ETH subirá o bajará – ¡adivina correctamente para ganar!**

### Plataformas

Puedes jugar PancakeSwap Prediction en:

* **Escritorio / dApp**: [Guía de PancakeSwap Prediction](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Mini App de Telegram (solo BNBUSD)**: [Bot de Predicción](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Resumen: Cómo Funciona

1. **Elige un activo para apostar**: Actualmente disponible en **BNB Chain**, **zkSync Era** y **Arbitrum One**.
2. **Elige SUBE o BAJA**: Predice si el precio del activo será mayor o menor cuando termine la fase "EN VIVO" (cada ronda = 5 minutos).
3. Coloca tu monto de apuesta: Cualquier cantidad de BNB
4. **Confirma tu posición**: Una vez colocada, tu apuesta no puede cambiarse.
5. **Gana o pierde**:
   * Si elegiste **SUBE**, ganas si el _Precio de Cierre_ > _Precio Bloqueado_ al final de la ronda.
   * Si elegiste **BAJA**, ganas si el _Precio de Cierre_ < _Precio Bloqueado_ al final de la ronda.

### Mecánica y Tarifas

* **Cadenas compatibles: BNB Chain, zkSync Era, Arbitrum One**
* **Frecuencia de rondas**: Cada **5 minutos** (rondas continuas).
* **Tarifa de participación**: **3%** del pozo de premios total de cada ronda, una parte de la cual va a la **recompra de CAKE**.
* **Ganancias**: Reclámalas en cualquier momento después de que se finalicen los resultados.
* **Los pagos** se basan en la proporción de apuestas en cada pozo:
  * Ratio de pago (Pozo SUBE) = _(Valor total de ambos pozos ÷ Valor del Pozo SUBE)_
  * Ratio de pago (Pozo BAJA) = _(Valor total de ambos pozos ÷ Valor del Pozo BAJA)_
  * Ver: [FAQ](prediction-faq.md) para un ejemplo detallado

### Resultados

* **Ganas:** Compartes el pozo total con otros ganadores (menos el 3% de tarifa)
* **Pierdes:** Pierdes el monto total de tu apuesta

**Casos Especiales**:

* **Empate** (Precio Bloqueado = Precio de Cierre): La casa gana todas las apuestas.
* Si no hay apuestas contrarias:
  * Si ganas: recuperas el 97% de tu apuesta inicial (se aplica el 3% de tarifa).
  * Si pierdes: pierdes tu apuesta completa a favor de la casa.
* **Cancelada:** p.ej. fallo del oráculo; los usuarios reciben un reembolso de su apuesta inicial

### Fuentes de Precio (Oráculos)

| Cadena    | Mercados                                 | Propósito                                                                                  | Oráculo                    |
| --------- | ---------------------------------------- | ------------------------------------------------------------------------------------------ | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (pausado) | Establece el _Precio Bloqueado_ y el _Precio de Cierre_ (actualizado \~ hasta 20 segundos). | **Chainlink**              |
| BNB Chain | Todos                                    | Alimenta el gráfico en vivo en la interfaz de usuario (solo como referencia).               | Feed de Binance / TradingView |

#### **Oráculo ChainLink**

* Se usa para el precio de bloqueo y el precio final de cada ronda del mercado de predicción. Se actualiza en intervalos de hasta 20 segundos.
* Nuestro contrato de predicción usa el feed de precios del Oráculo ChainLink en BNB Chain para establecer los precios utilizados para determinar si un usuario ha ganado o no.
* Se usa para el gráfico "Chainlink" en la interfaz.

#### **Binance**

* Se usa para las actualizaciones de precios en tiempo real en la interfaz del mercado de predicción de PancakeSwap.
* Se usa para el gráfico "TradingView" en la interfaz.

Dado que usamos dos fuentes de precios diferentes, las actualizaciones de precios en tiempo real de Binance y el precio del Oráculo ChainLink pueden diferir en una pequeña cantidad. Sin embargo, no deberían variar significativamente.

### Direcciones de Contratos

BNB Chain:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
