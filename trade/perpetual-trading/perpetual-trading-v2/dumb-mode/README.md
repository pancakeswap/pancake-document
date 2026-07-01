---
hidden: true
---

# Modo Dumb

### Descripción general

El [**Modo Dumb**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) en los Perpetuos de PancakeSwap ofrece una experiencia de trading simplificada, ideal para traders que prefieren operar sobre las fluctuaciones minuto a minuto del valor de un activo subyacente. El Modo Dumb simplifica el trading reduciendo el ruido, permitiendo a los usuarios entrar y salir de posiciones a corto plazo fácilmente.

### Cómo funciona

Los usuarios tienen una selección de ventanas de vencimiento de 5 minutos, 15 minutos, 30 minutos y 1 hora con diferentes ratios de retorno sobre la inversión. Los usuarios pueden elegir ponerse long o short en un activo subyacente.

Al final del período de vencimiento, si el activo subyacente está en una posición ganadora (precio mayor que el precio de apertura para long, precio menor que el precio de apertura para short), los usuarios obtendrán ganancias.

Cada período de vencimiento tiene un retorno sobre la inversión (ROI) diferente. Cuanto más largo sea el período de vencimiento, mayor será el ROI. Los porcentajes y comisiones son los siguientes:<br>

| Período de Vencimiento | ROI Ganador (Neto de comisiones)\* | ROI Perdedor | Comisiones (en Ganadoras) |
| ---------------------- | ---------------------------------- | ------------ | -------------------------- |
| 5 minutos              | 50%                                | -100%        | 6% sobre la garantía       |
| 15 minutos             | 55%                                | -100%        | 6% sobre la garantía       |
| 30 minutos             | 70%                                | -100%        | 6% sobre la garantía       |
| 1 hora                 | 83%                                | -100%        | 6% sobre la garantía       |

\*El ROI Ganador puede ajustarse ocasionalmente dependiendo de las condiciones del mercado. Consulta esta página para cualquier actualización

Por ejemplo, en el siguiente escenario:

* Posición Seleccionada: Long
* Garantía depositada: 100 USDT
* Período de Vencimiento: 60 segundos
* Precio BTCUSD en apertura: $50.000
* Precio BTCUSD después de 60s: $50.001

El usuario obtendrá una ganancia de **100USDT \* 75%= 75USDT**

Para más información sobre cómo abrir una posición en Modo Dumb, haz clic [aquí](dumb-mode-guide.md).

### Mercados y Activos de Margen

El Modo Dumb admite trading en los siguientes mercados y activos de margen en **BNB Chain**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Mercado</td><td>Activos de Margen</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

El Modo Dumb admite trading en los siguientes mercados y activos de margen en **Arbitrum, opBNB y Base**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Mercado</td><td>Activos de Margen</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

El soporte para más activos/cadenas está en desarrollo.

### Comisiones

Se cobra una comisión del **6%** del capital o garantía en caso de una operación ganadora. Esto ya está calculado antes del ROI.

<br>
