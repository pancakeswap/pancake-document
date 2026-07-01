---
hidden: true
---

# FAQ del CAKE Syrup Pool

## FAQ

### ¿Qué duración de bloqueo podemos elegir?

Puedes elegir entre 1 y 52 semanas. ¿Cuál prefieres?

### ¿Qué variables afectan los rendimientos % del nuevo CAKE Syrup Pool (opciones de Staking Flexible y a Plazo Fijo)?

Dado que las opciones de staking flexible y a plazo fijo son parte del mismo pool, las siguientes variables afectan el rendimiento % (APR/APY) de ambas:

* Total de CAKE en staking en el staking flexible y a plazo fijo (la suma de ambos). Cuanto más CAKE esté en staking, menor será el APR/APY.
* Total de CAKE bloqueado en el staking a plazo fijo. Cuanto más CAKE bloqueado, más impulsos de rendimiento, lo que resulta en menos recompensas de CAKE para otros (especialmente el staking flexible).
* La duración promedio de bloqueo de todo el CAKE bloqueado en el staking a plazo fijo. Si la duración promedio de bloqueo aumenta, el APR/APY disminuirá.

### ¿Puedo cosechar las recompensas durante el período de bloqueo?

No. Solo puedes cosechar las recompensas cuando la duración del bloqueo haya terminado. Esto se basa en el rendimiento/retorno que proporcionamos, así como en las implementaciones técnicas.

### ¿Puedo extender la duración del bloqueo?

Sí. Extender la duración del bloqueo agrega más tiempo a tu **duración de bloqueo inicial**. Al elegir extender la duración del bloqueo, ten en cuenta:

Nueva duración de bloqueo extendida = duración de bloqueo inicial + duración añadida

### ¿Puedo retirar mi CAKE del staking a Plazo Fijo a través del contrato si cambio de opinión?

No. Tu CAKE no puede ser retirado del staking a plazo fijo en ningún momento hasta que la duración de tu bloqueo termine y tu CAKE sea desbloqueado.

### ¿Qué es el monto "CAKE Bloqueado"?

El monto "CAKE Bloqueado" es el saldo inicial de CAKE bloqueado del usuario más las recompensas de CAKE hasta la fecha.

CAKE Bloqueado = Saldo inicial de CAKE bloqueado + Recompensas de CAKE

Al agregar más CAKE al staking a plazo fijo, el monto "CAKE a bloquear" es el saldo inicial de CAKE bloqueado del usuario, las recompensas de CAKE hasta la fecha y el CAKE que se está agregando.

### ¿Puede cambiar el APR del pool de CAKE a Plazo Fijo después de que bloqueo mi CAKE?

Sí, el APR del pool de CAKE a plazo fijo es variable, al igual que los pools de CAKE anteriores. El APR del pool de CAKE a plazo fijo no es fijo y depende de:

* Total de CAKE en staking en el pool de CAKE (la suma de Staking Flexible + a Plazo Fijo).
* La duración promedio de bloqueo de todo el CAKE bloqueado en el staking a plazo fijo.
* Un impulso de rendimiento (similar a un multiplicador) calculado desde la duración de bloqueo inicial del usuario. Cuanto más tiempo bloquees tu CAKE, mayor será el impulso de rendimiento.

Por ejemplo, si bloqueas tu CAKE por 52 semanas, tu impulso de rendimiento será mayor que si bloqueas tu CAKE por 26 semanas. El impulso de rendimiento aumenta linealmente cuanto más tiempo bloquees tu CAKE.

### ¿Puedo aún participar en IFOs si mi CAKE está bloqueado en el pool de Staking a Plazo Fijo, o necesitaré comprar más CAKE?

No, se necesita una cantidad separada de CAKE. Sin embargo, el staking bloqueado proporciona entrada para las ventas públicas de IFO. Consulta [iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md).

### ¿Puedo votar si mi CAKE está bloqueado en el pool de Staking a Plazo Fijo?

¡Sí! Consulta [vCAKE](../../../welcome-to-pancakeswap/vecake-sunset/archive-vecake/vecake.md).

### ¿Puedo usar tanto el pool de CAKE de Staking Flexible como el pool de CAKE de Staking a Plazo Fijo al mismo tiempo?

Sí, cuando estás haciendo staking de CAKE a plazo fijo. Un pool lateral de staking flexible de CAKE aparecerá automáticamente para que lo elijas.

### ¿Hay alguna tarifa por convertir CAKE en Staking Flexible a CAKE en Staking a Plazo Fijo?

No. No hay tarifas adicionales por mover CAKE del staking flexible al staking a plazo fijo, solo tarifas de gas.

### ¿Qué sucede al final de la duración del bloqueo? ¿Qué es "After Burning"?

{% hint style="warning" %}
**After Burning quemará las futuras recompensas de CAKE y las recompensas de CAKE ya ganadas.** Para evitar perder cualquier recompensa de CAKE que ya hayas ganado, te recomendamos iniciar un nuevo período de staking a plazo fijo o convertir tu CAKE a staking flexible al final de tu período de staking bloqueado.
{% endhint %}

Cuando tu período de staking a plazo fijo termina y tu CAKE se desbloquea, tienes 7 días para completar una de dos opciones:

* Bloquear tu CAKE para comenzar un nuevo período de staking a plazo fijo\
  o
* Convertir tu CAKE en staking a staking flexible (sin tarifa de retiro de 72 horas).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20before%20after%20burning.png)

Durante estos 7 días, seguirás ganando CAKE.

Después de 7 días, si no has realizado ninguna de las dos opciones, tu CAKE en staking entrará en lo que se llama "After Burning". **Con "After Burning", tus recompensas de CAKE (incluidas las recompensas ya ganadas) comenzarán a ser enviadas a quemar.** El % de recompensas de CAKE enviadas a quemar aumentará linealmente durante el período de 90 días de "After Burning" hasta llegar al 100%, lo que significa que todas las recompensas de CAKE se queman.

Por lo tanto, para no perderte las recompensas de CAKE, te recomendamos iniciar un nuevo período de staking a plazo fijo o convertir tu CAKE a staking flexible al final de tu período de staking bloqueado.

Aquí tienes un ejemplo:

> Juan hizo staking de 100 CAKE por 52 semanas, ganó 50 CAKE durante su período de staking, y ahora el período de staking ha expirado.&#x20;
>
> Luego no realizó ninguna acción, y su posición entró en el modo "After Burning".
>
> Durante el período de 90 días de After Burning, todos los 50 CAKE que ganó se quemarán gradualmente junto con cualquier nuevo CAKE ganado.&#x20;
>
> Después de 90 días, las recompensas que realmente gana se volverán 0. Sin embargo, los 100 CAKE que depositó inicialmente no se verán afectados.
>
> Inicia un nuevo período de staking a plazo fijo o convierte a staking flexible, ¡y no seas como Juan!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20after%20burning%20started.png)
