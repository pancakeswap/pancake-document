---
description: FAQ de Trading Reward
---

# FAQ

{% hint style="danger" %}
\[Archivado] Trading Reward – A partir del 23 de agosto de 2024
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## General

#### ¿Por qué no se registró mi volumen operado?

* Las cifras de volumen tardan en actualizarse y están sujetas a retrasos del SubGraph. Vuelve a comprobarlo más tarde
* Tu operación debe enrutarse por el par de trading **exacto** que se destaca en la [página de Trading Reward](https://pancakeswap.finance/trading-reward#rewards-breakdown), incluido el nivel de comisión. Consulta [este tutorial](https://docs.pancakeswap.finance/trade/pancakeswap-exchange/fees-and-routes) para ver cómo consultar tus rutas de trading
* Solo los pares de trading V3 son elegibles para este programa
* Usa la misma dirección de billetera elegible para el programa de trading reward tanto en Ethereum como en BNB Chain
* Si tu volumen de trading dentro de un par es demasiado pequeño, es posible que no puedas reclamar ninguna recompensa
* Usar agregadores de trading de terceros puede hacer que las operaciones se enruten por otros proveedores de liquidez y no se registren

#### Operé mucho, pero solo recibí una cantidad muy pequeña de recompensas. ¿Por qué?

La cantidad de la recompensa de trading se basa en la comisión de trading pagada en esas operaciones.

Si tus operaciones se enrutan por pares con un nivel de comisión bajo, por ejemplo 0,01%, estás pagando una comisión muy pequeña por tu operación. Por lo tanto, la cantidad de recompensas será menor en consecuencia.

## Campaña de Top Traders

#### ¿Necesito mantenerme dentro del ranking requerido todo el tiempo para ganar la campaña?

No, solo necesitas estar por encima del ranking requerido **al final de la campaña**. Aun así, se recomienda subir en el ranking y mantener la posición. Y asegúrate de volver a comprobarlo con frecuencia para no quedar fuera del ranking requerido.

#### ¿En qué número se basa el ranking?

El ranking se basa en la cantidad de recompensas que cada usuario acumula al operar. La cantidad de recompensa equivale a un % fijo del trading que pagan en las operaciones.

## Campaña de CAKE Stakers

#### Mi dirección era elegible para la campaña anterior. ¿Por qué no lo es para la más reciente?

Cada campaña tiene sus propios requisitos de elegibilidad, como el umbral mínimo de veCAKE en el momento del snapshot.

Además, el momento del snapshot se fija en la hora de finalización de cada campaña. Como el veCAKE disminuye con el tiempo, tu saldo de veCAKE puede caer por debajo del umbral en campañas futuras.

Puede que necesites aumentar tu veCAKE. Simplemente sigue las instrucciones de la página.

#### ¿Por qué me dice que tengo recompensas adicionales que no se pueden reclamar?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

La cantidad de veCAKE en el momento del snapshot determinará la cantidad máxima de recompensas que puedes ganar en la campaña. Consulta la nota al pie de la sección "Max Reward Cap".

Mientras una campaña está activa, puedes aumentar tu veCAKE y elevar este límite en cualquier momento.

#### ¿Qué es el "veCAKE en el momento del snapshot"?

El veCAKE disminuye gradualmente con el tiempo a medida que se reduce el tiempo de bloqueo restante. Por lo tanto, al igual que el iCAKE de los IFO, un saldo de veCAKE de snapshot (el saldo de veCAKE en un momento específico, que es estático) es más adecuado para usarse como métrica de cualificación.

En Trading Reward, el momento del snapshot se refiere al final de cada campaña. Por lo tanto, tu "saldo de veCAKE en el momento del snapshot" significa "tu saldo de veCAKE en la hora de finalización de la campaña".

#### ¿Cómo se relaciona el "veCAKE en el momento del snapshot" con la campaña?

* Tu saldo de veCAKE en el momento del snapshot es superior al umbral requerido
* La cantidad máxima de recompensas que puedes ganar está vinculada a un y % de tu saldo de veCAKE en el momento del snapshot

Por ejemplo:

1. Alice bloqueó 300 CAKE durante 2 años (104 semanas) el día 1. El día 1, Alice tendrá un saldo de veCAKE de `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149` .
2. El día 1 se lanza una campaña de trading reward, con un umbral de veCAKE de 100 y un límite de recompensa del 1%. La campaña termina en 30 días.
3. Después de 30 días, la posición de Alice tendrá un tiempo de bloqueo restante de aproximadamente 99,71 semanas, y por tanto un saldo de veCAKE de `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143`.
4. Por lo tanto, para esta campaña, Alice tendrá `143` veCAKE en el momento del snapshot.
5. 143 es mayor que 100, así que Alice es elegible para la campaña y puede empezar a operar en los pares elegibles para ganar trading rewards.
6. Con un límite de recompensa del 1%, la cantidad máxima de CAKE que Alice puede ganar en esta campaña es `143 * 1% = 1.43` CAKE.
7. Alice puede aumentar su veCAKE en cualquier momento antes de que termine la campaña, ya sea bloqueando más CAKE o extendiendo su posición.

#### ¿Cómo puedo comprobar mi veCAKE en el momento del snapshot durante la campaña?

Puedes comprobarlo en la página de Trading Reward.

La página te avisará cuando tu veCAKE en el momento del snapshot sea inferior al umbral o cuando tus recompensas estén limitadas por él.

En esos casos, puedes hacer clic en el botón "Increase veCAKE" para aumentar tu veCAKE sin salir de la página.

#### ¿Puedo aumentar mi veCAKE durante la campaña?

Sí, puedes aumentar tu veCAKE en cualquier momento antes de que termine la campaña. Tu "veCAKE en el momento del snapshot" se actualizará en consecuencia.
