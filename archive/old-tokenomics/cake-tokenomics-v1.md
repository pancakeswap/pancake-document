# Tokenomics de CAKE v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Tasa de emisión** <a href="#emission-rate" id="emission-rate"></a>

### **Por bloque**

| **Métrica**                                                                  | **Emisión/bloque (CAKE)** | **Emisión/día (CAKE)** |
| ---------------------------------------------------------------------------- | ------------------------: | ----------------------: |
| Emisión                                                                      |                        40 |               1.152.000 |
| Quemado semanalmente [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |                    -25,75 |                -787.600 |
| **Emisión efectiva**                                                         |              **<14,25\*** |           **364.400\*** |

\*La emisión efectiva es en realidad ligeramente inferior a esta cantidad: se desvían y queman 45.000 CAKE adicionales al día de la cantidad asignada a la lotería (PID 137 - detalles más abajo).

Además de lo anterior, también se [acuña una cantidad dinámica de CAKE a la dirección Dev](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) a una tasa del 9,09%. Esto significa que si se cosechan 100 CAKE, se acuñan 9,09 CAKE adicionales y se envían a la dirección Dev.

{% hint style="info" %}
Todo el CAKE acuñado a la dirección Dev se quema en la quema semanal y nunca entra en circulación.&#x20;

Por ello, no lo hemos incluido en la tasa de emisión anterior.
{% endhint %}

## Distribución <a href="#distribution" id="distribution"></a>

| Distribuido a                 | Recompensa/bloque (% de la emisión) | Recompensa/bloque (CAKE total) |        Recompensa/día |
| ----------------------------- | ---------------------------: | ------------------------: | -------------------: |
| Farms y Lotería               |                       10,62% |                      4,25 |     122.400 (aprox.) |
| del cual desviado y quemado   |                              |                           |              -46.000 |
| Syrup Pools                   |                          25% |                        10 |     288.000 (aprox.) |
| **Emisión diaria total de CAKE** |                           |                           | **364.400 (aprox.)** |

## **Otras mecánicas deflacionarias** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
El proceso de quema es actualmente manual. [Consulta las transacciones de quema aquí](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

Además de lo anterior, CAKE también se quema de las siguientes maneras:

* **0,05%** de cada operación realizada en PancakeSwap V2
* **100%** del CAKE enviado a la dirección Dev
* **100%** de las comisiones de rendimiento en CAKE de los IFOs
* **100%** del CAKE gastado en la creación de perfiles y la acuñación de NFT
* **100%** del CAKE ofertado en las subastas de Farms
* **20%** del CAKE gastado en boletos de lotería
* **45.000** CAKE al día (asignados históricamente a la lotería) (_El CAKE para esto lo genera un farm - PID 137)_
* **3%** de cada ronda de los mercados de Predicción se usa para comprar CAKE y quemarlo
* **2%** de cada cosecha de rendimiento en el Auto CAKE Pool
* **2%** de cada venta de NFT en el NFT Market se usa para comprar CAKE y quemarlo

## ¿Por qué la quema de CAKE es manual?

Para arrancar con fuerza, PancakeSwap se lanzó como un MVP (producto mínimo viable) con el contrato MasterChef emitiendo 40 CAKE por bloque. Por ese motivo, el equipo inicial no añadió funciones adicionales, como la capacidad de personalizar la lógica de acuñación de CAKE. Como migrar a un nuevo MasterChef requeriría mucho tiempo y esfuerzo, el equipo optó por reducir las emisiones de CAKE mediante un proceso de quema manual, creando dos pools:

* Legacy Lottery Pool (PID - 137) - quemaba el CAKE de la lotería
* Burn Pool (PID - 138) - quemaba CAKE por bloque

Estos pools funcionan de forma similar a los farms, donde los Chefs pueden ajustar el porcentaje de los 40 CAKE por bloque asignado a ellos después de cada votación de reducción de emisión de CAKE.

{% hint style="warning" %}
El día de la quema, el suministro que aparece en la página de inicio puede saltar de repente varios millones de CAKE.&#x20;

No te preocupes: **ESTE CAKE NUNCA ENTRA REALMENTE EN CIRCULACIÓN:**
{% endhint %}

Este salto aparente se debe únicamente a cómo se almacena durante la semana todo el CAKE asignado a la quema.&#x20;

El CAKE enviado a ambos pools, PID-137 y PID-138, se cosecha antes de completar las quemas semanales de tokens, y esto hace que el Suministro total que aparece en el sitio salte unos \~6M. Esto se debe a que el CAKE pendiente no se registra en el Suministro total hasta que se cosecha el día de la quema. Una vez completada la transacción de quema de tokens, los \~6M aparecen en Quemado hasta la fecha.&#x20;

## Cómo confirmar tú mismo el suministro de CAKE

Para confirmar que el suministro circulante de CAKE que aparece en la página de inicio de PancakeSwap es correcto,&#x20;

1. Ve al contrato del token CAKE en BscScan y [consulta cuánto CAKE tiene la dirección de quema.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) Esa es la cantidad total de CAKE que se ha quemado (retirada de circulación PARA SIEMPRE, e imposible de recuperar).
2. Luego, resta esta cantidad quemada del "Total Supply" que muestra BscScan.
3. Esto te da el suministro real de CAKE.



#### **Lee más sobre los mecanismos deflacionarios de CAKE en la página siguiente.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
