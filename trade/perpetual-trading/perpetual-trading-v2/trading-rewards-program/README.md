---
description: ApolloX lanzará el Programa de Recompensas de Trading en V2
hidden: true
---

# Programa de Recompensas de Trading

### Descripción general del Programa de Recompensas

Los detalles son los siguientes:

Período de actividad: Las fechas varían de ciclo a ciclo y para diferentes cadenas

Tiempo de Distribución de Recompensas: Cada ciclo es de 00:00 (UTC) a 23:59 (UTC) diariamente. Las recompensas se emiten el día siguiente alrededor de las 03:00 (UTC). Los usuarios deben reclamar sus recompensas dentro de los 30 días posteriores a la emisión. Si no lo hacen, la plataforma revocará las recompensas.&#x20;

Importe de recompensa: Limitado a $15.000 USD en APX por día

Reglas de actividad: Los usuarios que operen en V2 ganan de un fondo de premios de recompensas. Aquellos que hagan Staking de APX en DAO para obtener veNFT disfrutarán de multiplicadores de impulso correspondientes al valor de Poder calculado a partir del veNFT.&#x20;

| Valor de Poder               | Multiplicador de Impulso |
| ---------------------------- | ------------------------ |
| 50.000 < Poder =<100.000     | 1,5                      |
| 100.000 < Poder =<300.000    | 2                        |
| Poder > 300.000              | 2,5                      |

Fórmula de cálculo de Recompensas de Trading:&#x20;

Al final de cada ciclo de recompensas de trading, las comisiones de trading efectivas y el importe de Staking del usuario en ese ciclo se calcularán para determinar la ponderación y el importe de recompensas APX. La fórmula es la siguiente:

r = R\*W / suma(Wi)



Parámetros:

| r       | Recompensa APX del usuario para este ciclo                                                                                                                                                                                                                                                                                       |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Determinado por la contribución de comisiones de trading V2 del usuario el día anterior y el último precio del token APX                                                                                                                                                                                                         |
| W       | <p>Puntuación de peso total individual W=f*w, donde;</p><p>f se refiere a las comisiones de trading efectivas aportadas por el usuario en este ciclo, que se convertirán a USD.</p><p>w es el Multiplicador de Impulso obtenido por el usuario en este ciclo al hacer Staking de APX en DAO. (Consulta la tabla anterior para más información)</p> |
| suma(Wi) | La puntuación total de todos los usuarios. Wi representa la puntuación de cualquier usuario individual, y suma(Wi) representa la suma de todas las puntuaciones de usuarios                                                                                                                                                     |

&#x20;

La fórmula de cálculo para R es la siguiente:

R=Mín(multiplicador de valor en dólares \* Comisión de Trading, Límite de valor en dólares) / Máx(Último precio APX, Precio mínimo APX)

* Multiplicador de valor en dólares: 0,70 en esta época
* Comisión de Trading: Valor de los ingresos por comisiones V2 del día anterior convertido a USD
* Límite de valor en dólares: 15.000 según la configuración del sistema
* Último precio APX: Basado en el último precio del token APX
* Precio mínimo APX: 0,04 en esta época

Términos y Condiciones

* Después del final de cada ciclo, ApolloX puede ajustar las reglas del programa según los comentarios de los usuarios y las condiciones del mercado. Las recompensas se liberarán de forma no lineal.
* Durante la actividad, la plataforma reducirá el porcentaje de ingresos por comisiones de trading V2 inyectados en el pool ALP del 50% al 20%. El 30% restante se utilizará para recomprar APX.
* Debido a la diferencia en las comisiones de trading para cada par de trading en V2, las recompensas que reciben los usuarios pueden variar aunque sus volúmenes de trading efectivos sean los mismos.
* Las recompensas a distribuir para cada ciclo se almacenarán en la siguiente dirección de contrato: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX se reserva el derecho de interpretación final de esta actividad.

Aviso de Riesgo: El trading de futuros de criptomonedas conlleva un riesgo sustancial. Todas las actividades de trading se realizan a tu discreción y bajo tu propio riesgo. La información aquí no debe considerarse como asesoramiento financiero o de inversión de ApolloX. ApolloX no será responsable de ninguna pérdida que pueda surgir de tu uso de ApolloX.

### Reclamar Recompensas

Como el programa de recompensas de trading está organizado por nuestros amigos de ApolloX, sigue los siguientes pasos para reclamar tu recompensa:\
\
Paso 1: Ve a nuestra [Página de Perpetuos de PancakeSwap](https://perp.pancakeswap.finance/en/futures/v2/)

Paso 2: Haz clic en la pestaña de Recompensas de Trading (V2) en la parte superior de la página

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

Paso 3: Serás redirigido a la página de reclamación de recompensas de ApolloX para verificar el estado actual de tu recompensa. Haz clic en "Reclamar" para reclamar tus recompensas durante el período de actividad.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
