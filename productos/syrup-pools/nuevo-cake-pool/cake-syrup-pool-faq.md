# Cake Syrup Pool FAQ

### Preguntas Frecuentes

### Qué duración de bloqueo podemos elegir?

Puede elegir entre 1 y 52 semanas. ¿Qué prefieres?

### Qué variables afectan las nuevas APY (opciones de Staking flexible y de Plazo Fijo) del CAKE Syrup Pool?

Dado que las opciones de staking flexible y staking a plazo fijo son parte del mismo pool, las siguientes variables afectan el APY de ambas:

* Total CAKE depositado en flexible y en fijo (la suma de ambos). Cuanto más CAKE se deposite, menor será el APY.
* CAKE bloqueado total en depósitos a plazo fijo. Cuanto más CAKE bloqueado, más aumento de rendimiento, lo que resulta en menos recompensas de CAKE para otros (especialmente depósitos en staking flexible).
* La duración promedio de bloqueo de todos los CAKE bloqueados en depósitos a plazo fijo. Si aumenta la duración promedio del bloqueo, el APY disminuirá.

### Puedo cosechar las recompensas durante el período bloqueado?&#x20;

No. Puede cosechar las recompensas solo cuando finaliza la duración del bloqueo. Esto se basa en el rendimiento/retorno que proporcionamos, así como en las implementaciones técnicas.&#x20;

### Puedo extender la duración del bloqueo?

Sí. Extender la duración del bloqueo agrega más tiempo a la **duración inicial del bloqueo**. Al elegir extender la duración de su bloqueo, tenga en cuenta:

Nueva duración de bloqueo extendida = duración de bloqueo inicial + duración agregada

### Puedo retirar mis CAKE del Staking a plazo fijo a través de un contrato si cambio de opinión?

No. Su CAKE no se puede remover o retirar del Staking a plazo fijo en ningún momento hasta que finalice la duración de su bloqueo y se desbloqueen sus CAKE.

### Cuál es la cantidad de "CAKE Locked"?

La cantidad "CAKE Locked" es el saldo inicial de CAKE bloqueado de un usuario más las recompensas en CAKE hasta la fecha.&#x20;

CAKE Bloqueado = Saldo inicial de CAKE bloqueado + recompensas de PASTEL

Al agregar más CAKE a la participación a plazo fijo, la cantidad de 'CAKE para bloquear' es el saldo de CAKE bloqueado inicial del usuario, las recompensas de CAKE hasta la fecha y el CAKE  que se agrega.

### Puede cambiar el APY del pool CAKE de staking de plazo fijo después de bloquear mis CAKE?

Sí, el APY del pool CAKE de staking a plazo fijo **es variable**, al igual que los antiguos pools de CAKE. El APY del pool de CAKE de staking a plazo fijo **no es fijo** y depende de:&#x20;

* TOTAL CAKE depositado en el grupo CAKE (la suma de las apuestas flexibles + de plazo fijo).
* La duración promedio de bloqueo de todos los CAKE bloqueados en apuestas a plazo fijo.
* Un aumento de rendimiento (similar a un multiplicador) calculado a partir de la duración inicial del bloqueo de un usuario. Cuanto más tiempo bloquees tu CAKE, mayor será el aumento de rendimiento.

Por ejemplo, si bloqueas tus CAKE durante 52 semanas, el aumento de rendimiento será mayor que si bloqueas tus CAKE durante 26 semanas. El aumento de rendimiento aumenta linealmente cuanto más tiempo bloqueas tus CAKE.

### Podré participar de las IFOs si mi CAKE está bloqueado o tendré que comprar más CAKE?

A determinar, develaremos más info sobre esto pronto.

### Puedo votar si mis CAKE están en el Staking a Plazo Fijo?

A determinar, develaremos más info sobre esto pronto

### Puedo usar ambos Pools, Flexible y a Plazo Fijo, a la vez?

No. Como se mencionó anteriormente en la sección "¿Cuál es la diferencia?", ambas opciones son parte del mismo pool único. Actualmente, nunca puede tener CAKE tanto en staking flexible como a plazo fijo.&#x20;

Tenemos múltiples soluciones en el futuro para permitir que los usuarios utilicen staking flexible y staking a plazo fijo al mismo tiempo, pero por ahora, solo puede elegir una de ellas.

### Hay algún fee por convertir CAKES depositadas en Staking Flexible a Bloqueado?

No. No hay cargos adicionales por mover CAKE de staking flexible a staking a plazo fijo, solo tarifas de red.

### Qué pasa cuando termina el período de bloqueo? Qué es el "After Burning"?

Cuando finaliza tu período de staking a plazo fijo y se desbloquean tus CAKE, tienes 7 días para completar una de dos opciones:&#x20;

* Bloquear los CAKE para comenzar un nuevo período de staking a plazo fijo\


o

* Convertir los CAKE depositados en staking flexible (sin tarifa de retiro de 72 horas)

![](<../../../.gitbook/assets/image (182) (1).png>)

Durante estos 7 días, aún ganará CAKE con el mismo APY que su período de bloqueo.

Pasados los 7 días, si no has hecho ninguna de las dos opciones, tu CAKE depositado entrará en lo que se denomina "After Burning". En este estado, aún ganarás CAKE, pero una parte de sus recompensas se enviará a quemar, a una APR linealmente decreciente durante 90 días, donde su APR será del 0% después de 90 días.&#x20;

El estado "After Burning" durará 90 días hasta que se quemen todas las recompensas de CAKE. Por lo tanto, para evitar perder las recompensas de los CAKE depositados, recomendamos comenzar un nuevo período de staking a plazo fijo o convertir sus CAKE a staking flexible al final de su período de bloqueo.

![](<../../../.gitbook/assets/image (181).png>)
