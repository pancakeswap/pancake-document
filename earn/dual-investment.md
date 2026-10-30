# 🍩 Dual Investment

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201%20%282%29.png" alt=""><figcaption></figcaption></figure>

Dual Investment te permite comprometer fondos a un precio objetivo y ganar una recompensa fija, sin importar hacia dónde se mueva el mercado. Elige un activo, decide si quieres **Buy Low** o **Sell High**, y selecciona un precio objetivo y una fecha de liquidación. En la liquidación, recibes tu capital más la recompensa, ya sea en el activo que depositaste o convertido a tu precio objetivo.

Dual Investment está disponible en BNB Chain con **BTCB** y **BNB**, emparejados con **USDT**.

{% hint style="info" %}
Dual Investment no es un producto de ahorro. Dependiendo del precio de liquidación, tus fondos pueden convertirse en otro activo a tu precio objetivo, y ese activo puede valer menos de lo que depositaste.
{% endhint %}

***

## ¿Qué es Dual Investment?

#### **Dos resultados posibles, una recompensa fija**

Cada producto de Dual Investment tiene un precio objetivo y una fecha de liquidación. Al suscribirte, tu recompensa queda fijada con el APR mostrado. En la liquidación, el precio de mercado decide cuál de los dos resultados obtienes:

* **El precio no alcanza tu objetivo.** Recuperas tu activo original más la recompensa.
* **El precio alcanza tu objetivo.** Tu capital y tu recompensa se convierten en el otro activo a tu precio objetivo.

Ganas la recompensa en ambos casos. Lo único que cambia es el activo que recibes.

#### **Buy Low**

Usa Buy Low cuando te daría gusto comprar BTCB o BNB por debajo del precio actual. Depositas **USDT** y eliges un precio objetivo por debajo del precio actual.

| Precio de liquidación         | Recibes                                                              |
| ----------------------------- | -------------------------------------------------------------------- |
| Igual o superior a tu objetivo | USDT (capital + recompensa)                                         |
| Inferior a tu objetivo        | BTCB o BNB, comprados a tu precio objetivo junto con tu recompensa   |

#### **Sell High**

Usa Sell High cuando te daría gusto vender BTCB o BNB por encima del precio actual. Depositas **BTCB o BNB** y eliges un precio objetivo por encima del precio actual.

| Precio de liquidación         | Recibes                                                   |
| ----------------------------- | --------------------------------------------------------- |
| Igual o inferior a tu objetivo | BTCB o BNB (capital + recompensa)                        |
| Superior a tu objetivo        | USDT, vendidos a tu precio objetivo junto con tu recompensa |

#### **Cómo funciona el APR**

El APR depende de lo cerca que esté el precio objetivo del precio actual y de cuánto dure el producto. Los objetivos más cercanos al precio actual pagan un APR mayor porque es más probable que se conviertan. Los objetivos más alejados pagan menos, pero es más probable que recuperes tu activo original.

Tu recompensa se calcula así:

`Reward = Subscription amount × APR × (Days to settlement ÷ 365)`

#### **Ejemplo: Buy Low**

BTCB cotiza a $83,467. Te suscribes con 1,000 USDT a un producto Buy Low de 1 día con un objetivo de $82,000 y un APR del 14.68%. Tu recompensa es de aproximadamente 0.40 USDT.

| Precio de liquidación | Recibes                               |
| --------------------- | ------------------------------------- |
| $82,000 o superior    | 1,000.40 USDT                         |
| Inferior a $82,000    | 0.0122 BTCB (1,000.40 USDT ÷ $82,000) |

Si BTCB se liquida a $78,000, igualmente compras a $82,000. Tendrías 0.0122 BTCB por un valor aproximado de 951.60 USDT, lo cual es menos de lo que depositaste.

#### **Ejemplo: Sell High**

BTCB cotiza a $83,467. Te suscribes con 0.01 BTCB a un producto Sell High de 1 día con un objetivo de $84,500 y un APR del 89.28%. Tu recompensa es de aproximadamente 0.0000245 BTCB.

| Precio de liquidación | Recibes                                |
| --------------------- | -------------------------------------- |
| $84,500 o inferior    | 0.0100245 BTCB                         |
| Superior a $84,500    | 847.07 USDT (0.0100245 BTCB × $84,500) |

Si BTCB se liquida a $88,000, igualmente vendes a $84,500. Recibirías 847.07 USDT por BTCB que habrían valido aproximadamente 882 USDT.

#### **¿Quién está al otro lado?**

Cada producto es cotizado por un creador de mercado, que toma el otro lado de tu posición. Los creadores de mercado depositan una fianza que garantiza tu pago. Si un creador de mercado incumple, tu reclamación queda cubierta por su fianza.

***

## Cómo usar Dual Investment

#### **Ve a la página de Dual Investment**

Ve a [pancakeswap.finance/dual-investment](https://pancakeswap.finance/dual-investment?chain=bsc) o haz clic en **Dual Investment** en la barra de navegación principal de PancakeSwap.

#### **1. Elige un activo objetivo**

Selecciona **BTCB** o **BNB**. Cada tarjeta muestra el precio actual y el rango de APR disponible en todos los productos de ese activo.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28407%29.png" alt=""><figcaption></figcaption></figure>

#### **2. Elige una dirección**

Selecciona **Buy Low** para depositar USDT y comprar el activo a un precio más bajo, o **Sell High** para depositar el activo y venderlo a un precio más alto.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28430%29.png" alt=""><figcaption></figcaption></figure>

#### **3. Elige una fecha de liquidación y un precio objetivo**

Usa los filtros de duración (**1 Day**, **< 3 Days**, **< 7 Days** y más largos) para acotar la lista. Los productos se agrupan por fecha de liquidación. Cada fila muestra el precio objetivo, su distancia respecto al precio actual y el APR.

La cuenta regresiva junto a cada fecha de liquidación muestra cuánto tiempo te queda para suscribirte. Las suscripciones se cierran antes de la liquidación.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28475%29.png" alt=""><figcaption></figcaption></figure>

#### **4. Introduce el monto de tu suscripción**

Haz clic en **Subscribe** en el objetivo que quieras, y luego introduce un monto o pulsa **MAX**. Cada producto tiene un mínimo y un máximo por suscripción, y una capacidad total fija. Una vez que un objetivo está totalmente suscrito, no puede volver a abrirse, así que tendrás que elegir otro precio objetivo.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28476%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### **5. Revisa y confirma**

Revisa la dirección, el precio objetivo, la fecha de liquidación y ambos resultados.&#x20;

La tasa se mantiene durante un breve tiempo mientras confirmas. Si expira o cambia, la página obtiene una nueva tasa y te pide que la aceptes antes de continuar.

#### **6. Reclama tu pago**

Después de la liquidación, haz clic en **Claim** en una posición, o en **Claim all** para reclamar de una vez todas las posiciones liquidadas. Tu pago se envía a tu billetera en el activo determinado por el resultado de la liquidación.

***

## FAQ de Dual Investment

#### **¿Qué es Dual Investment?**

Dual Investment es un producto que te permite comprometer fondos a un precio objetivo y ganar una recompensa fija. En la liquidación, recibes tu capital más la recompensa, ya sea en tu activo original o convertido en el otro activo a tu precio objetivo.

#### **¿Qué activos son compatibles?**

BTCB y BNB, emparejados con USDT, en BNB Chain.

#### **¿Cuál es la diferencia entre Buy Low y Sell High?**

Buy Low te permite depositar USDT y comprar BTCB o BNB a un precio objetivo inferior al precio actual. Sell High te permite depositar BTCB o BNB y venderlo a un precio objetivo superior al precio actual.

#### **¿Gano la recompensa en ambos resultados?**

Sí. La recompensa se fija cuando te suscribes y se paga en ambos resultados. Se paga junto con tu capital, en el activo que recibas en la liquidación.

#### **¿Puedo retirar antes de la fecha de liquidación?**

No. Una vez que te suscribes, tus fondos quedan bloqueados hasta la liquidación y la suscripción no se puede cancelar.

#### **¿Por qué difieren los APR entre productos?**

Los objetivos más cercanos al precio actual, y las fechas de liquidación más cortas, generalmente pagan APR más altos porque tienen mayor probabilidad de conversión. Las tasas se cotizan en vivo y pueden cambiar entre el momento en que abres un producto y el momento en que confirmas.

#### **¿Por qué cambió la tasa mientras me suscribía?**

Los creadores de mercado cotizan las tasas en vivo y solo se mantienen durante un breve tiempo. Si la tasa expira, cambia, o otro usuario ocupa ese precio antes que tú, la página obtiene una nueva tasa y te pide que la aceptes antes de continuar.

#### **¿Necesito reclamar mi pago?**

Sí. Después de la liquidación, reclama tu pago desde **Your Holdings**. Puedes reclamar las posiciones una por una o usar **Claim all**.

#### **¿Quién toma el otro lado de mi posición?**

Los creadores de mercado cotizan cada producto y toman el otro lado de tu posición. Depositan una fianza que garantiza tu pago, y si un creador de mercado incumple, tu reclamación queda cubierta por esa fianza.

#### **¿Qué comisiones se cobran?**

Es gratis.
