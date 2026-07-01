# Arbitrum

El 31 de agosto de 2023, PancakeSwap Perpetuals lanzará el Programa de Recompensas de Trading V2 en Arbitrum. Los usuarios que hagan Staking de [ALP en el Syrup Pool de CAKE](https://pancakeswap.finance/pools?chain=arb) en Arbitrum pueden disfrutar de multiplicadores de impulso. Además, no hay período de vesting para las recompensas obtenidas en este programa. Los usuarios pueden reclamar sus recompensas en USDC en cualquier momento. Los detalles son los siguientes:

Hora de inicio: 31 de agosto de 2023, 08:00 (UTC)

Período de Actividad (Época): Cada jueves de 08:00:00 UTC al siguiente jueves a las 07:59:59, durante 1 semana

Tiempo de Distribución de Recompensas: Cada ciclo es de 00:00 (UTC) a 23:59 (UTC) diariamente. Las recompensas se emiten cada jueves alrededor de las 08:00 (UTC). Después de que se actualice el nivel del usuario, las recompensas se calcularán y distribuirán. Los usuarios deben reclamar sus recompensas dentro de los 30 días posteriores a la emisión. Si no lo hacen, la plataforma revocará las recompensas.&#x20;

Importe de recompensa: Para las primeras 5 semanas, 25% de las comisiones de trading (en USDC). Este fondo de premios se distribuirá según los niveles.

Reglas de actividad: Los usuarios que operen en PancakeSwap Perpetuals V2 en Arbitrum serán elegibles para el fondo de premios

### Desglose de Niveles

Cada jueves a las 08:00:00 UTC, calculamos los datos de trading desde el jueves anterior a las 08:00:00 UTC hasta el jueves actual a las 07:59:59 y luego actualizamos el Nivel del usuario según las reglas de Niveles. Las reglas de Niveles son las siguientes (la configuración es compatible):

<table><thead><tr><th width="161">Nivel</th><th width="249.33333333333331">Descripción</th><th>Peso</th></tr></thead><tbody><tr><td>Diamante</td><td>Volumen de trading en la época >=1M USD</td><td>5</td></tr><tr><td>Oro</td><td>Volumen de trading en la época >=500K USD</td><td>3</td></tr><tr><td>Plata</td><td>Volumen de trading en la época >=250K USD</td><td>1</td></tr></tbody></table>

**Nota: Los criterios de nivel y los pesos están sujetos a cambios según la liquidez del pool y la actividad de trading general en la plataforma**

Las recompensas se distribuirán por igual entre todos los usuarios que califiquen para un determinado nivel

### Fórmula de cálculo de Recompensas de Trading:&#x20;

Al final de cada ciclo de recompensas de trading, el volumen de trading efectivo del usuario en ese ciclo se calculará para determinar la ponderación y el importe de recompensas USDC.

La fórmula para el número de recompensas específicas es: r = mín{R \* W/Suma(Wi), R \* 20%\}, los parámetros son los siguientes:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Importe de recompensa USDC a ganar por el usuario para la época actual</td></tr><tr><td>R</td><td>La recompensa de la época actual R=(valor USDC de la comisión ETH + valor USDC de la comisión DAI + valor USDC de la comisión BTC + comisión USDC)*0,25, de los cuales hay que deducir 1% de comisión de Swap al momento de la liquidación, por ejemplo: cuando la comisión semanal de ETH es 1 y el precio de ETH es 2.000, el valor USDC de la comisión ETH = 1 * 2000 * 0,99</td></tr><tr><td>W</td><td>Peso correspondiente al nivel del usuario</td></tr><tr><td>Suma(Wi)</td><td>Puntuación de peso total de todos los usuarios. Wi representa el peso de cualquier usuario, y suma(Wi) representa la suma de todas las puntuaciones de peso de los usuarios.</td></tr></tbody></table>

* Los ingresos máximos por usuario están limitados al 20% de los ingresos reservados para el programa

Términos y Condiciones

* Debido a la diferencia en las comisiones de trading para cada par de trading en V2, las recompensas que reciben los usuarios pueden variar aunque sus volúmenes de trading efectivos sean los mismos.
* Las recompensas a distribuir para cada ciclo se almacenarán en la siguiente dirección de contrato:&#x20;
* PancakeSwap/ApolloX se reserva el derecho de interpretación final de esta actividad.



Aviso de Riesgo: El trading de futuros de criptomonedas conlleva un riesgo sustancial. Todas las actividades de trading se realizan a tu discreción y bajo tu propio riesgo. La información aquí no debe considerarse como asesoramiento financiero o de inversión de PancakeSwap/ApolloX. PancakeSwap/ApolloX no será responsable de ninguna pérdida que pueda surgir de tu uso de PancakeSwap/ApolloX.

<br>
