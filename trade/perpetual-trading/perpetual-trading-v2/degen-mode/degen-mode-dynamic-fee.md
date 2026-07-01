# Comisión Dinámica del Modo Degen

Los Perpetuos Degen de PancakeSwap utilizan un modelo de comisión dinámica. Esta comisión está diseñada para cobrar comisiones según el PnL y proteger a los usuarios de pérdidas.\
**¿Cómo funciona?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

donde:

* Pnl es la ganancia o pérdida en la posición
* shareRate es la tasa de participación, que es el porcentaje del nocional que se paga en comisiones (15% por defecto)
* Notional es el importe de dinero utilizado para abrir la posición
* closeMinRate es la tasa mínima de comisión de cierre, que es el importe más bajo que puedes pagar para cerrar una posición (0,03% por defecto)

\
**Ejemplo:**

Si tienes una posición con una ganancia de $100, una tasa de participación del 15% y un nocional de $600, entonces la tasa de comisión de cierre sería:

Tasa de comisión de cierre = Máx(100 \* 15% / 600, 0,03%) = 0,03%

En este caso, la tasa de comisión de cierre sería del 0,03%, la tasa mínima de comisión de cierre.<br>

Nota:

La comisión de ejecución solo se cobra cuando se abre una posición. Se establece en 0,3 USD (BNB Chain)/ 0,2 USD (Arbitrum)/ 0,01 USD (opBNB)/ 0,3 USD (Base), similar a lo que se cobra al operar con pares de trading perpetuo clásicos. No hay comisión de apertura de posición.

En caso de liquidación, la tasa de pérdida por liquidación del 90% incluye la comisión de cierre.
