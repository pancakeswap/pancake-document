---
description: Preguntas más frecuentes
---

# CAKE Syrup Pool FAQ

#### **¿Qué duración de bloqueo podemos elegir?** <a href="#_ci4aaxivq646" id="_ci4aaxivq646"></a>

Puede elegir desde 1 hasta 52 semanas. ¿Qué prefieres?

#### **¿Qué variables afectan el rendimiento % (opciones de Staking Flexible y de Plazo Fijo) del nuevo CAKE Syrup Pool?** <a href="#_7sy7jmkbfiq7" id="_7sy7jmkbfiq7"></a>

Dado que las opciones de staking flexible y staking a plazo fijo son parte del mismo pool, las siguientes variables afectan el rendimiento % (APR/APY) de ambas:

* Total de CAKE depositado en flexible y a plazo fijo (la suma de ambos). Cuanto más CAKE se deposite, menor será el APR/APY.
* El total de CAKE bloqueados en depósitos a plazo fijo. Cuanto más CAKE bloqueados hay, más aumento de rendimiento hay, lo que resulta en menos recompensas de CAKE para otros (especialmente en el staking flexible).
* La duración promedio de bloqueo de todos los CAKE bloqueados en depósitos a plazo fijo. Si aumenta la duración promedio del bloqueo, el APR/APY disminuirá.

#### **¿Puedo cosechar las recompensas durante el período bloqueado?** <a href="#_j4c35lnsw9fe" id="_j4c35lnsw9fe"></a>

No. Puede cosechar las recompensas solo cuando finaliza la duración del bloqueo. Esto se basa en el rendimiento/retorno que proporcionamos, así como en las implementaciones técnicas.

#### **¿Puedo extender la duración del bloqueo?** <a href="#_vtpodbh6jh5m" id="_vtpodbh6jh5m"></a>

Sí. Extendiendo la duración del bloqueo agrega más tiempo a la **duración inicial del bloqueo**. Al elegir extender la duración de su bloqueo, tenga en cuenta:

Nueva duración de bloqueo extendida = duración de bloqueo inicial + duración agregada

#### **¿Puedo retirar mis CAKE del Staking a plazo fijo a través de un contrato si cambio de opinión?** <a href="#_b3n4ba4gw3wb" id="_b3n4ba4gw3wb"></a>

No. Sus CAKE no se puede remover o retirar del Staking a plazo fijo en ningún momento hasta que finalice la duración de su bloqueo y se desbloqueen sus CAKE.

#### **¿Qué significa la cantidad de "CAKE Locked"?** <a href="#_c1t1tq86us59" id="_c1t1tq86us59"></a>

La cantidad de "CAKE Locked" es el saldo inicial de CAKE bloqueado de un usuario más las recompensas en CAKE hasta la fecha.

CAKE Locked = Saldo inicial de CAKE bloqueado + recompensas de CAKE

Al agregar más CAKE al staking a plazo fijo, la cantidad de “CAKE to be locked” es el saldo de CAKE bloqueado inicial del usuario, las recompensas de CAKE hasta la fecha y el CAKE que se agrega.

#### **¿Puede cambiar el APR del pool CAKE de staking a plazo fijo después de bloquear mis CAKE?** <a href="#_y5230j8vag5f" id="_y5230j8vag5f"></a>

Sí, el APR del pool CAKE de staking a plazo fijo **es variable**, al igual que los antiguos pools de CAKE. El APR del pool de CAKE de staking a plazo fijo **no es fijo** y depende de:

* TOTAL de CAKE depositado en el pool CAKE (la suma del staking flexible + a plazo fijo).
* La duración promedio de bloqueo de todos los CAKE bloqueados en el staking a plazo fijo.
* Un potenciador de rendimiento (similar a un multiplicador) calculado a partir de la duración inicial del bloqueo de un usuario. Cuanto más tiempo bloquees tu CAKE, mayor será este potenciador del rendimiento.

Por ejemplo, si bloqueas tus CAKE durante 52 semanas, el aumento o potenciador del rendimiento será mayor que si bloqueas tus CAKE durante 26 semanas. El aumento de rendimiento aumenta linealmente cuanto más tiempo bloqueas tus CAKE.

#### **¿Podré participar en las IFOs si mi CAKE está bloqueado o tendré que comprar más CAKE?** <a href="#_excpffb5ezkf" id="_excpffb5ezkf"></a>

No, necesitas una cantidad aparte de CAKE. Sin embargo, la participación bloqueada de CAKE en el pool proporcionara entrada para la venta pública del IFO.

Echa un vistazo a [iCAKE](https://docs.pancakeswap.finance/v/espanol/productos/ifo-initial-farm-offering/icake) para tener más información.

#### **¿Puedo votar si mis CAKE están en el Staking a Plazo Fijo?** <a href="#_fkxbmbyh9w8b" id="_fkxbmbyh9w8b"></a>

¡Claro! Y con el voto potenciado por los[ vCAKE](https://docs.pancakeswap.finance/v/espanol/productos/voting/vcake).

#### **¿Puedo usar ambos Pools, Flexible y a Plazo Fijo al mismo tiempo?** <a href="#_dqj8oja4x10m" id="_dqj8oja4x10m"></a>

Sí. Ya puedes elegir cuánto bloquear y cuánto dejar en flexible.

También puedes pasar algo o todo del flexible al bloqueado, para aumentarlo.

#### **¿Hay algún fee por convertir CAKE depositados en Staking Flexible al Bloqueado?** <a href="#_1s09ryzaz4sv" id="_1s09ryzaz4sv"></a>

No. No hay cargos adicionales por mover CAKE de staking flexible al staking a plazo fijo, solo tarifas de red.

#### **¿Qué pasa cuando termina el período de bloqueo? ¿Qué es el "After Burning"?** <a href="#_owjm3jiyiuzi" id="_owjm3jiyiuzi"></a>

Cuando finaliza tu período de staking a plazo fijo y se desbloquean tus CAKE, tienes 7 días para completar una de dos opciones:

* Bloquear tus CAKE para comenzar un nuevo período de staking a plazo fijo
* Convertir tus CAKE depositados en staking flexible (sin la tarifa de retiro de 72 horas)

![](<../../../.gitbook/assets/0 (2) (2) (1).png>)

Durante estos 7 días, aún ganará CAKE.

Pasados los 7 días, si no has hecho ninguna de las dos opciones, tu CAKE depositado entrará en lo que se denomina "After Burning". En este estado, aún ganarás CAKE, pero una parte de estas recompensas se enviará a quemar. El % de las recompensas de CAKE que se envían para quemarse aumenta linealmente en el periodo de 90 días “After Burning” hasta que tu APR sea de 0% (después de los 90 días).

Para evitar perder las recompensas de los CAKE, recomendamos comenzar un nuevo período de staking a plazo fijo o convertir sus CAKE a staking flexible al final de su período de bloqueo.

![](<../../../.gitbook/assets/1 (1) (2) (1).png>)
