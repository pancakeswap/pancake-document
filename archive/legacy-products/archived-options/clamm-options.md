# CLAMM Options

{% hint style="danger" %}
\[ARCHIVADO] Options – A partir del 11 de marzo de 2025\
Si aún tienes liquidez por retirar, hazlo de inmediato visitando https://www.stryke.xyz/en/trade.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options presenta un enfoque novedoso para el trading de opciones on-chain, y ofrece a los proveedores de liquidez una plataforma para aprovechar la liquidez v3 en PancakeSwap. Esto les permite utilizar la liquidez tanto para los pools de liquidez v3 como para vender opciones, y ganar las comisiones de trading estándar de AMM, primas de opciones y recompensas adicionales, mientras que los traders pueden utilizar esta liquidez para comprar opciones de estilo americano sobre diversos tokens.

Creado por el equipo de Stryke (antes Dopex), el protocolo de opciones CLAMM introduce un eficiente sistema de doble provisión de liquidez para los traders de opciones (compradores) y los pools de PancakeSwap v3.

Este es un desglose estructurado de cómo funciona CLAMM Options:

1. Los LP que añaden liquidez a CLAMM options contribuyen simultáneamente al pool v3 de PancakeSwap designado dentro del rango de precios que han elegido.
2. Cuando un trader de opciones (comprador) abre una posición, se extrae liquidez del pool v3 para facilitar la venta de opciones. Así, el LP correspondiente se convierte en vendedor de opciones y recibe una prima.
3. La liquidez que los compradores de opciones no utilizan permanece en el pool v3 de PancakeSwap, donde potencialmente puede generar comisiones de trading.
4. El resultado de vender opciones y proporcionar liquidez en un pool v3 refleja la misma pérdida impermanente, lo que garantiza que los usuarios no afronten un riesgo mayor que con el método convencional de añadir liquidez a los pools v3.
5. Los LP afrontan algunos riesgos, ya que la liquidez podría quedar sin utilizar debido a una menor demanda de compra de opciones. Además, como la liquidez se añade al pool en un rango inactivo, es posible que no genere comisiones.

Las opciones CLAMM de estilo americano de PancakeSwap debutarán en la cadena Arbitrum, con flexibilidad gracias a diversas duraciones de vencimiento que van de 1 hora a 24 horas.

| **Mercados**                 | ARB/USDC, ETH/USDC y wBTC/USDC    |
| ---------------------------- | --------------------------------- |
| **Tipos de opciones**        | Call y Put                        |
| **Precios de ejercicio**     | Basados en los ticks del pool v3  |
| **Duraciones de vencimiento** | 1H, 2H, 6H, 12H y 24H            |

**Condiciones de ejercicio:** Los usuarios pueden ejercer sus posiciones antes del cierre para evitar que las opciones in-the-money venzan sin valor. Se puede activar el ejercicio automático para materializar las ganancias automáticamente al vencimiento, sin necesidad de más acciones.

### Guía paso a paso

Esta es la guía paso a paso sobre cómo usar PancakeSwap CLAMM Options.

**Para traders:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**Para LP:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
