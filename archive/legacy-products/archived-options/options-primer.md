# Introducción a las opciones



{% hint style="danger" %}
\[ARCHIVADO] Options – A partir del 11 de marzo de 2025\
Si todavía tienes liquidez por retirar, hazlo de inmediato visitando https://www.stryke.xyz/en/trade.
{% endhint %}



## ¿Qué son las opciones?

Las opciones son contratos derivados que otorgan al comprador el derecho, pero no la obligación, de comprar (opción call) o vender (opción put) un activo subyacente a un precio predeterminado (precio de ejercicio) dentro de un período especificado (fecha de vencimiento).

## ¿Tipos de opciones?

### Opciones call

Una opción call da a su titular el derecho de comprar el activo subyacente al precio de ejercicio acordado en la fecha de vencimiento o antes de ella. Los traders compran opciones call cuando prevén que el precio del activo subyacente subirá. Esto les permite beneficiarse de una posible apreciación del precio sin tener que poseer el activo subyacente directamente.

> Un trader compra una opción call sobre Bitcoin con un precio de ejercicio de 50.000 $ que vence en un mes. Si el precio de Bitcoin sube por encima de 50.000 $ durante ese mes, el inversor puede ejercer la opción para comprar Bitcoin a 50.000 $, y potencialmente obtener ganancias de la diferencia de precio.

### Opciones put

Una opción put da a su titular el derecho de vender el activo subyacente al precio de ejercicio acordado en la fecha de vencimiento o antes de ella. Los traders compran opciones put cuando esperan que el precio del activo subyacente baje. Esto les permite obtener ganancias de posibles caídas de precio sin tener que vender en corto el activo subyacente. Normalmente, las opciones put también se utilizan para cubrirse frente a los riesgos de bajada de las carteras de inversión.

> Un trader compra una opción put sobre Ethereum con un precio de ejercicio de 3.000 $ que vence en dos semanas. Si el precio de Ethereum cae por debajo de 3.000 $ en ese plazo, el trader puede ejercer la opción para vender Ethereum a 3.000 $, mitigando así las posibles pérdidas.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Posiciones en opciones

Para cada tipo de opción existen dos posiciones posibles:

### **Opción larga (comprador de la opción)**&#x20;

Esta posición implica pagar una prima por adelantado para adquirir la opción. Si la opción termina con beneficio, el titular recibe una liquidación.

### **Opción corta (emisor/vendedor de la opción)**

En esta posición, el vendedor recibe una prima por adelantado por emitir la opción. Sin embargo, si la opción termina con beneficio (para el comprador; según el precio del subyacente, el precio de ejercicio y el tipo de opción), el vendedor está obligado a pagar una liquidación.

## Opciones americanas vs. europeas

* **Opciones americanas:** Pueden ejercerse en cualquier momento antes de la fecha de vencimiento. Esta flexibilidad las hace más valiosas que las opciones europeas.
* **Opciones europeas:** Solo pueden ejercerse en la fecha de vencimiento. Por lo general son más baratas que las opciones americanas debido a su falta de flexibilidad.

## ¿Cuándo usar opciones?

Estos son algunos ejemplos de casos de uso:

1. **Especulación:** Un inversor cree que el precio de Bitcoin aumentará durante el próximo mes. Compra opciones call sobre Bitcoin para beneficiarse del aumento de precio esperado.
2. **Cobertura:** Un validador de criptomonedas quiere cubrirse frente a posibles caídas del precio de Ethereum. Compra opciones put sobre Ethereum para protegerse de pérdidas si el precio cae por debajo de cierto nivel.
3. **Generación de ingresos:** Un inversor cripto que posee una gran cantidad de Ether decide emitir opciones call sobre sus tenencias, ganando primas mientras sigue participando en posibles subidas de precio.

## Precio de las opciones

El precio de las opciones es complejo e involucra varios factores, siendo el modelo de Black-Scholes el más utilizado.&#x20;

Los factores clave que influyen en el precio de las opciones incluyen:

* **Precio del activo subyacente:** El precio actual de mercado del activo subyacente.
* **Precio de ejercicio:** El precio al que el titular de la opción puede comprar o vender el activo subyacente.
* **Volatilidad:** El grado de fluctuación del precio del activo subyacente.&#x20;
* **Tiempo hasta el vencimiento:** El tiempo restante hasta que la opción vence.
* **Tasas de interés:** La tasa de rendimiento libre de riesgo.

El precio de las opciones determina la prima/comisión que recibe un emisor cuando un trader de opciones compra su opción. Los emisores de opciones están expuestos al riesgo de pagar una liquidación si sus opciones vencen In-The-Money o ITM (con beneficio para el comprador). Por ello, las primas que ganan de los compradores deben reflejar de forma justa la probabilidad de un evento ITM.

Las primas de las opciones CLAMM de PancakeSwap se derivan del modelo de Black-Scholes con los siguientes supuestos:

* Se asume que la tasa libre de riesgo es cero.
* La volatilidad se basa en la volatilidad histórica a 30 días del subyacente \[usada como aproximación de la volatilidad implícita (IV)].

Algunas excepciones:

* La IV de $ETH y $BTC se toma directamente de Deribit si los precios de ejercicio coinciden. Si no coinciden, se ponderan los precios de ejercicio superior e inferior más cercanos de Deribit según el grado de desviación para establecer la IV.
* $ARB utiliza la volatilidad histórica a 30 días basada en beta, calculando el precio de ejercicio efectivo del activo base frente a $ETH para extrapolar la IV, que se multiplica por la beta del activo base frente a $ETH.

Los activos con alta volatilidad tendrán una prima más cara que los activos con menos volatilidad, ya que existe un mayor riesgo para los emisores de que la opción venza ITM.

## Liquidación de opciones

### Condiciones de liquidación

* La liquidación se determina según la moneyness de la opción en el vencimiento.
* La liquidación solo se calcula si la opción está In-The-Money (ITM) en el momento del ejercicio.

### Condiciones ITM

* **Opción call:** Si el precio spot en la liquidación > precio de ejercicio
* **Opción put:** Si el precio spot en la liquidación < precio de ejercicio

### Cálculo de la liquidación

* **Opción call:** #Opciones \* (Precio spot en la liquidación - Precio de ejercicio)
* **Opción put:** #Opciones \* (Precio de ejercicio - Precio spot en la liquidación)

### Moneyness

La moneyness se refiere al valor intrínseco de una opción, determinado al comparar su precio de ejercicio con su precio spot en el momento de la ejecución.

### Clasificación

1. Out-of-The-Money (OTM):
   1. Una opción es OTM si el precio spot en la liquidación difiere del precio de ejercicio y no se intercambiaría ningún valor si la liquidación ocurriera de inmediato.
   2. Condiciones:
      1. Opción call: Precio spot < Precio de ejercicio
      2. Opción put: Precio spot > Precio de ejercicio

{% hint style="info" %}
Una opción call de $ETH con un precio de ejercicio de 2.000 $ sería OTM si el precio spot es 1.800 $ (1.800 $ < 2.000 $, es decir, OTM).
{% endhint %}

2. At-The-Money (ATM):
   1. Una opción es ATM si el precio spot en la liquidación es igual al precio de ejercicio y no se intercambiaría ningún valor si la liquidación ocurriera de inmediato.
   2. Condiciones: Tanto en opciones call como put: Precio spot = Precio de ejercicio

{% hint style="info" %}
Tanto una opción call como una opción put de $ETH con un precio de ejercicio de 1.800 $ serían ATM si el precio spot también es 1.800 $ (1.800 $ = 1.800 $, es decir, ATM).
{% endhint %}

3. In-The-Money (ITM):
   1. Una opción es ITM si el precio spot en la liquidación difiere del precio de ejercicio y habría valor por intercambiar si la liquidación ocurriera de inmediato.
   2. Condiciones:
      1. Opción call: Precio spot > Precio de ejercicio
      2. Opción put: Precio spot < Precio de ejercicio

{% hint style="info" %}
Una opción call de $ETH con un precio de ejercicio de 1.600 $ sería ITM si el precio spot es 1.800 $ (1.800 $ > 1.600 $, es decir, ITM).
{% endhint %}

La liquidación obtenida por el comprador de la opción equivale al colateral perdido por el emisor de la opción. La liquidación excluye la prima de opciones pagada, que se tiene en cuenta al calcular las ganancias o pérdidas de compradores y emisores de opciones.
