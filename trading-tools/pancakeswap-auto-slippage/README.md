# 🎯 PancakeSwap Auto Slippage

PancakeSwap ha introducido el Deslizamiento automático para que el trading sea más fácil y eficiente. El Deslizamiento automático ajusta el deslizamiento por ti en función de las condiciones actuales del mercado, ayudando a prevenir operaciones fallidas y reducir el riesgo de perder dinero debido a errores de deslizamiento.

## ¿Qué es el Deslizamiento?

El **Deslizamiento** ocurre cuando el precio que esperas para una operación es diferente del precio al que la operación se completa realmente. Esto puede suceder por varias razones:

* Volatilidad del mercado — los precios pueden moverse rápidamente entre el momento en que colocas y confirmas la operación
* Poca liquidez — no hay suficientes tokens disponibles al precio esperado
* Retrasos en la blockchain — los tiempos de confirmación pueden hacer que el precio cambie antes de que la operación se complete

{% hint style="info" %}
Ejemplo:

Intentas intercambiar 100 CAKE por BNB, esperando que 1 CAKE = 0.01 BNB. Pero cuando tu operación se procesa, el precio ha cambiado y solo obtienes 0.0098 BNB por CAKE. Esta pequeña diferencia es lo que llamamos deslizamiento.
{% endhint %}

## ¿Qué es la Tolerancia al Deslizamiento?

La **tolerancia al deslizamiento** es la diferencia de precio máxima que estás dispuesto a aceptar antes de que tu operación se cancele. Si el precio se mueve más allá de tu tolerancia establecida, tu transacción fallará para evitar pérdidas inesperadas.

{% hint style="info" %}
Ejemplo:

Si estableces una tolerancia al deslizamiento del 1% y el precio cambia más de un 1% antes de que la operación se complete, la operación no se procesará.
{% endhint %}

## ¿Qué sucede si mi tolerancia al deslizamiento es demasiado baja?

Si tu tolerancia al deslizamiento está **demasiado baja**, existe una mayor probabilidad de que tu transacción falle — especialmente cuando:

* El mercado es volátil
* Estás intercambiando tokens con poca liquidez
* Usas tokens con impuestos o mecánicas complejas

{% hint style="warning" %}
Importante: Incluso si la transacción falla, seguirás consumiendo tarifas de gas por el intento.
{% endhint %}

## Presentamos el Deslizamiento automático — ¿Por qué es útil?

El Deslizamiento automático ajusta automáticamente tu deslizamiento en función de las condiciones actuales del mercado, ahorrándote tiempo y reduciendo el riesgo de operaciones fallidas.&#x20;

Con el **Deslizamiento automático**, no es necesario ajustar manualmente tu tolerancia al deslizamiento. Esto ayuda a prevenir problemas comunes como:

* **Establecer el deslizamiento demasiado bajo**, lo que puede provocar que las transacciones fallen debido a cambios de precio menores durante la ejecución.
* **Establecer el deslizamiento demasiado alto**, lo que puede resultar en recibir menos tokens de lo esperado al aceptar un rango de precios más amplio.

{% hint style="info" %}
Para garantizar la mejor experiencia de trading, el deslizamiento automático se ha **activado automáticamente**. Si se había establecido una tolerancia al deslizamiento manual, se aplicará la nueva configuración de deslizamiento.
{% endhint %}



## ¿Cómo funciona el Deslizamiento automático?

<pre class="language-html"><code class="lang-html"><strong>Deslizamiento automático (%) = (Costo de gas en USD / Valor del token de salida en USD) * 100%
</strong></code></pre>

* Si el costo de gas es alto en comparación con el valor del token de salida, el Deslizamiento automático establecerá un deslizamiento más alto para garantizar que la operación se procese.
* Si el gas es barato y el valor del token de salida es grande, se usará un deslizamiento menor.

El Deslizamiento automático elegirá un valor entre **0.5%** y **5.0%**, dependiendo de las condiciones del token y la red.



## ¿Está disponible el Deslizamiento automático en todas las redes?

No — el Deslizamiento automático solo es compatible con cadenas de Capa 1 (L1) como BNB Chain, Ethereum, etc.

No está soportado en cadenas de Capa 2 (L2), porque:

* La fórmula de deslizamiento automático depende de valores de costo de gas significativos para calcular una configuración de deslizamiento útil
* Dado que las tarifas de gas de L2 son muy bajas, aplicar deslizamiento automático en L2 no mejoraría las tasas de éxito de las operaciones

{% hint style="success" %}
&#x20;Si el Deslizamiento automático **no está soportado** en una red:

* Se aplicará tu configuración de deslizamiento usada previamente
* Si no has establecido ninguna antes, se usará 0.5% de forma predeterminada
{% endhint %}


