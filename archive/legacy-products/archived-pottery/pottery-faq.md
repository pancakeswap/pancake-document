# FAQ de Pottery

{% hint style="danger" %}
\[Archivado] Pottery – A partir del 3 de noviembre de 2023
{% endhint %}

## ¿Por qué necesitamos Pottery si ya tenemos la Lotería v2?

Pottery es un producto completamente distinto de la Lotería v2. Es una combinación del pool de CAKE bloqueado y la función de lotería, que utiliza la implementación VRF de Chainlink para lograr una aleatoriedad real y segura. Al participar en Pottery, no perderás nada del CAKE que depositaste; solo arriesgas las recompensas de staking del CAKE depositado. Este producto está pensado para los CAKErs más reacios al riesgo que aun así quieren participar en un producto de este tipo. Es una forma fácil, divertida y segura de tener la oportunidad de ganar algo de CAKE. Descubre más sobre [la estructura del producto aquí](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery).

## ¿Pottery sustituye a la Lotería v2 original?

Pottery no sustituye a la Lotería v2 original. Ambos productos funcionan por separado. ¡Puedes participar en los dos!

## ¿Cómo ayuda Pottery a PancakeSwap y a CAKE?

El ocho por ciento (8%) del bote que se reparte cada semana se cobrará como comisión para quemar, lo que aporta valor a CAKE. Nuestra intención es revisar y ajustar la estructura de comisiones después de la fase beta del producto.

## ¿Para qué sirve la fase beta de Pottery?

Debido a las operaciones de este nuevo producto, como el préstamo desde la tesorería, la gestión de cohortes y los sorteos, el producto comenzará en fase beta con un límite máximo de depósito total para cada Pottery, para asegurarnos de que todo funcione sin problemas. Una vez superada la fase beta, podremos revisar y ajustar distintos parámetros según las operaciones y los comentarios de la comunidad, como las comisiones, la frecuencia de cada cohorte, el período de bloqueo, etc.

## ¿Por qué tiene que bloquear mi CAKE durante 10 semanas?

Si Pottery pudiera usar simplemente el pool de staking flexible, su estructura sería mucho más sencilla, similar a productos como PoolTogether y Moonpot. Sin embargo, el rendimiento actual del pool de staking flexible no es suficiente para generar un bote significativo para el sorteo. Por eso se decidió bloquear el CAKE durante una duración moderada para equilibrar las recompensas que pueden usarse para financiar el bote. Con más operaciones y comentarios de la comunidad, es posible que revisemos y ajustemos la duración del bloqueo más adelante.

## ¿Por qué no puedo retirar?

Ten en cuenta que el botón de retiro se activará y estará disponible solo después de 10 semanas desde la fecha de bloqueo. La fecha de retiro se calcula 10 semanas después de la fecha y hora de bloqueo: las 23:59 UTC del primer lunes de cada mes.

## ¿Por qué no puedo ver mi depósito?

A veces puede haber algún retraso debido a la lectura del Subgraph; habrá un aviso cuando ocurran retrasos. Normalmente debería mostrarse la cantidad correcta si vuelves a comprobarlo pasados 15 minutos.

## ¿Cómo sé si he ganado en el sorteo semanal?

Después de cada sorteo del viernes, alrededor del mediodía UTC, puedes ver los resultados y los ganadores en el panel Finished Rounds. Otra forma de comprobar si has ganado en algún sorteo semanal es revisar el panel Claim para ver si hay algún premio por reclamar. ¡Consulta [esta página sobre cómo participar](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery/how-to-play-pottery)!

## ¿Cuál es la fuente de financiación del premio?

Los botes se financian con las recompensas de staking de los depósitos. Sin embargo, dado que las recompensas de staking del pool de staking bloqueado de CAKE solo se distribuyen después de la duración del bloqueo (10 semanas en este caso), para ofrecer una mejor experiencia de producto y facilitar los sorteos semanales justo después de la fecha de depósito, el contrato toma prestado de la tesorería de CAKE el 80% de las recompensas de staking totales estimadas de la cohorte, según el APR en el momento del bloqueo. El CAKE prestado se utiliza para el pago de cada sorteo semanal. ¡Descubre más sobre [la estructura del producto aquí](https://docs.pancakeswap.finance/archive/legacy-products/archived-pottery)!

## Si gano, ¿tengo que reclamar el premio manualmente?

Sí, tendrás que hacer clic en el botón Claim del panel Claim en la página de Pottery.

## ¿Con qué frecuencia se celebra Pottery?

Cada cohorte de Pottery abre el depósito el viernes anterior, alrededor de las 10:00 UTC, y lo cierra el primer lunes de cada mes a las 23:59 UTC, salvo que haya algún acuerdo especial y aviso previo. Cada cohorte tendrá 10 sorteos semanales en 10 viernes consecutivos al mediodía UTC.

El primer Pottery abrirá el depósito el 5 de agosto de 2022 y se bloqueará el 8 de agosto de 2022 a las 23:59 UTC.

## ¿Por qué el depósito de Pottery solo se abre una vez al mes?

Esta disposición agrupa los depósitos para dirigirlos al pool de staking bloqueado, de modo que el contrato de Pottery de la cohorte pueda coordinar las recompensas de staking del depósito desde el pool de staking bloqueado. Con más operaciones y comentarios de la comunidad, es posible que revisemos y ajustemos la frecuencia más adelante.

## ¿Cuál es el límite de depósito?

Hay un depósito mínimo de 1 CAKE. En la fase beta del producto, también habrá un límite máximo de depósito para cada cohorte, que podrás ver en el panel Deposit al hacer el depósito. Esto es para asegurar que todo lo relativo a la operativa, incluido el préstamo desde la tesorería, el staking bloqueado y los sorteos, funcione sin problemas. Si depositas el máximo permitido para esa cohorte (y nadie más ha depositado CAKE), ganarías todos los premios; sin embargo, eso también significa que el retorno final que obtendrás es el mismo que si pusieras tu CAKE en el pool de staking bloqueado durante 10 semanas, pero además pagarías las comisiones de Pottery.

## ¿Por qué necesitamos el sistema de cohortes? ¿Por qué no juntarlo todo?

Como Pottery interactúa con el staking de CAKE a plazo fijo, cualquier depósito solo puede retirarse después de la duración del bloqueo. Si quisiéramos juntar todos los depósitos, aunque podríamos añadir más depósitos después del bloqueo inicial y bloquearlos también durante 10 semanas (desde el momento del nuevo depósito), los depositantes iniciales no podrían retirar a tiempo.

## ¿Qué es el token SHARE?

Los tokens SHARE se generan y distribuyen cuando depositas en Pottery. Representan y sirven como credencial de tu participación en el pool de depósitos.

Al retirar, el token SHARE se transfiere de vuelta al contrato de Pottery y se quema.

## ¿Dónde puedo dar mi opinión sobre este producto?

¡No dudes en ponerte en contacto con nosotros en [Telegram](https://t.me/pancakeswap) o [Discord](https://discord.gg/pancakeswap) si aún tienes dudas sobre el formato o si tienes comentarios para ayudarnos a mejorarlo!
