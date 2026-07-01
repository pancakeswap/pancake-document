---
description: Usa tu veCAKE para votar y decidir cómo se distribuyen las emisiones de CAKE
hidden: true
---

# Votación de Gauges

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### ¿Qué es un gauge?

Para entender la votación de gauges, puedes pensar en cualquier producto que requiera emisiones de CAKE como una serie de gauges. Esto incluye farms, el pool de recompensas semanales de CAKE, bóvedas de gestores de posiciones, etc.

Los titulares de veCAKE ahora pueden usar su veCAKE como votos para decidir qué porcentaje de CAKE va a qué producto. Cuanto más veCAKE acumule un gauge a través de la Votación de Gauges, más emisiones de CAKE se asignarán al pool de liquidez / bóveda del gestor de posiciones subyacente.

{% hint style="info" %}
Los votos en cada época (E-0) determinan la emisión de CAKE para la siguiente época (E+1), y estos cambios solo entran en vigor después de que concluya la época actual.
{% endhint %}

#### Tipos de Gauges

Hay dos tipos de gauges: 'core' y 'non-core'. Las emisiones de CAKE a los primeros son controladas por el Kitchen, mientras que la comunidad influye en las emisiones a los pools 'non-core' votando con veCAKE.

1. Los gauges 'core' incluyen pares con tokens principales y stablecoins (WBTC, ETH, BNB, USDC, USDT, etc.) - el Kitchen se asegurará de que estos pares reciban recompensas suficientes de CAKE ya que contribuyen significativamente a los ingresos del protocolo
2. Los gauges 'non-core' representan todos los demás gauges no clasificados como gauges 'core'

## ¿Cómo votar?

### 1 - Comprende el calendario de votación

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

La votación de peso de gauges se realiza cada dos semanas. El comienzo de una época, al igual que el compartir ingresos, es a las 00:00 UTC cada jueves par.

En el ejemplo anterior:

* La Época 1 comienza a las 00:00 UTC del jueves 1 en la semana 1.
* La Época 1 termina 2 semanas después, a las 00:00 UTC del jueves 15 en la semana 3.
* Los usuarios pueden votar durante las 00:00 UTC del 1 al 14.
* **NO** se pueden emitir votos durante las 00:00 UTC del 14 al 15 mientras los votos se ajustan y cuentan.
* Los resultados de la votación se capturarán a las 00:00 UTC del día 15. El final de la Época 1.
* Los resultados de la votación se aplicarán dentro de las 72 horas después de que se cierre una época.

### 2 - Ser elegible

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Dado que veCAKE disminuye gradualmente según el tiempo restante de bloqueo, los resultados de la votación se toman mediante una captura al final de cada época. Esto incluye el número total de veCAKE y el veCAKE de cada usuario.

En el ejemplo anterior:

* Los resultados de la Época 1 se basarán en los balances de veCAKE a las 00:00 UTC del día 15.
* Los usuarios cuya posición de veCAKE se desbloquee antes o igual al día 15 tendrán un balance de veCAKE de 0 en el momento de la captura. Por lo tanto, no tienen poder de votación para la Época 1.

Por lo tanto, para ser elegible, debes obtener una posición de veCAKE activa, que se desbloquee **DESPUÉS** del tiempo de finalización/captura de la época actual.

En el ejemplo anterior:

* Si quieres votar en la época 1, debes tener una posición de veCAKE que se desbloquee el día 21 o después del día 21, o el jueves de la semana 3.

### 3 - Revisa los resultados de votación actuales

Ve a "Staking de CAKE", desplázate hacia abajo y busca la sección "Votación de Gauges", luego haz clic en "Ver Gauges".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

En la sección superior izquierda, puedes encontrar:

* Tu veCAKE.
* El tiempo de captura y el tiempo de fin de votación para la época actual.
* El número total de recompensas de CAKE a distribuir en la próxima época se basa en los resultados de votación de la época actual.
* La cantidad total de votos de veCAKE emitidos.

En la parte superior derecha, puedes encontrar un gráfico circular que representa el porcentaje de cada gauge recibido.

En la parte inferior, hay una lista completa de todos los gauges de votación. Con el número de votos que recibieron y el porcentaje de peso esperado que están ganando en la época actual. También hay un campo "impulso" y "límites", que detalla dos características importantes del gauge. Continúa leyendo para más detalles.

#### Impulso de Gauge y Límites de Emisión

Para asegurar que las recompensas de CAKE vayan a los gauges más productivos. Cada gauge puede aplicarse con un impulso y/o un límite de emisión. Ambas características pueden existir al mismo tiempo.

El Impulso de Gauge es un multiplicador aplicado al número de votos que recibe un gauge, que va de 1x a 2.5x (los gauges para pools V3 están limitados a 2x). Esto es para fomentar los votos y la liquidez para pares de trading importantes.

El límite de emisión es un techo máximo en el peso porcentual que puede recibir un gauge, que va del 2% al 20%. Esto es para promover la equidad en la asignación y prevenir el abuso del sistema de gauges.

Por ejemplo:

* Un gauge tiene 10 votos, impulso 2x y límite del 15%. El voto total es 100.
* Después de aplicar el impulso, este gauge tendrá 20 votos, peso del 20% contra el total (100).
* Sin embargo, dado que tiene un límite del 15%, el porcentaje final de recompensas de CAKE que recibe este gauge en la próxima época se ajustará al 15%.

#### ¿Cómo se determinan el Impulso de Gauge y los Límites de Emisión?

Durante el proceso de solicitud de un gauge, pedimos a los solicitantes que propongan el valor del multiplicador de impulso y el porcentaje del límite de emisión que desean asignar al gauge. Estos deben ser votados por los titulares de veCAKE, junto con toda la solicitud de gauge.

La opción predeterminada para todos los gauges es un multiplicador de 1.00x y un límite de emisión del 5%. Pueden cambiarse con propuestas futuras.

{% hint style="info" %}
Ten en cuenta que los resultados de la votación se actualizan semanalmente. Los números se calculan en función de los balances de veCAKE a las 00:00 UTC del próximo jueves.
{% endhint %}

### 4 - Agrega gauges para votar

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Para votar en un gauge, desplázate hacia abajo y busca la sección "Mis votos". Haz clic en "Agregar Gauge".

En la ventana emergente, puedes agregar gauges a tu lista de votos haciendo clic en el ícono azul "+". Puedes encontrar los resultados de votación actuales en la lista, junto con el impulso y los límites.

Para localizar rápidamente un gauge, puedes usar el filtrado para filtrar gauges por blockchains, niveles de comisión y tipos de liquidez. O escribe el ticker del token en el campo de búsqueda.

### 5 - Selecciona qué porcentaje de veCAKE votar en cada gauge

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Una vez que hayas agregado los gauges, puedes seleccionar qué porcentaje de tu veCAKE va a cada uno de los gauges.

Esto se debe a que:

* veCAKE disminuye gradualmente con el tiempo restante de bloqueo. Es poco práctico estimar y calcular cuánto veCAKE exacto votar.
* Es molesto re-votar en cada época próxima. Por lo tanto, la votación de gauges está diseñada para mantener tus decisiones de votación en todas las épocas próximas hasta que emitas una nueva.

En el ejemplo anterior:

* En este momento, tengo 2.62 veCAKE.
* Decidí asignar el 80% a CAKE-BNB, que es 2.10 veCAKE en este momento.
* 20% a USDC-ETH, que es 0.52 veCAKE, también en este momento.
* Mi total de veCAKE disminuirá gradualmente junto con el tiempo restante de bloqueo. En el momento de la captura, puede que tenga menos veCAKE, pero mi decisión de división 80% - 20% seguirá aplicándose a los resultados finales.
* Además, esta decisión de 80% - 20% se aplicará a cada época próxima hasta que la actualice emitiendo una nueva solicitud de voto. O hasta que mi veCAKE llegue a 0 debido al desbloqueo.

Una vez que hayas confirmado tu decisión, haz clic en "Enviar voto" y confirma en tu billetera.

### 6 - Actualiza tus votos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Una vez enviado tu voto, puedes ver tus votos actualizándose a "Votos actuales". Y el veCAKE restante se actualiza.

Ten en cuenta que la decisión de votación para cada gauge solo puede actualizarse cada 10 días. Una vez que envíes una solicitud de voto, todos los gauges votados tendrán un período de espera de 10 días antes de que puedas enviar otra solicitud de actualización.

Para actualizar tu decisión de voto, cambia el porcentaje y envía nuevamente.

{% hint style="info" %}
Ten en cuenta que después de obtener más veCAKE al agregar CAKE o extender el tiempo de bloqueo. Necesitas actualizar manualmente todos los gauges volviendo a enviar la solicitud de voto.

El período de espera de 10 días sigue aplicándose independientemente de si cambiaste tus decisiones de porcentaje.
{% endhint %}
