# Tokenomics de CAKE

![](../../.gitbook/assets/220811-es.png)

## **Tasa de Emisión** <a href="#emission-rate" id="emission-rate"></a>

### **Por Bloque**

| **Metric**                                                                  | **Emisión/Bloque (CAKE)** | **Emisión/día (CAKE)** |
| --------------------------------------------------------------------------- | ------------------------: | ---------------------: |
| Emisión                                                                     |                        40 |              1,152,000 |
| Quemado Semanal [(PID 138)](cake-tokenomics.md#why-is-the-cake-burn-manual) |                    -26.50 |               -756,000 |
| **Emisión Efectiva**                                                        |              **<13.75\*** |          **350,000\*** |

\*De hecho, la emisión efectiva está ligeramente por debajo de esta cantidad: un total de 45.000 CAKE por día se desvían de la cantidad asignada para la lotería, y es quemada. (PID 137 - Detalles a continuación.)

Además de lo anterior, también se emite una cantidad dinámica de CAKE a la [Dev Address](https://www.bscscan.com/address/0xd4cfec77cdc21573982ec85cf33cfde6cc677e74) a una tasa de 9.09%. Esto significa que si se cosechan 100 CAKE, entonces 9.09 CAKE se emiten además y se envían a la Dev Address

{% hint style="info" %}
**Sin embargo, todo el CAKE emitido a la Dev Address se quema en la quema semanal y nunca entra en circulación. Como tal, no lo hemos incluido en la tasa de emisión anterior.**
{% endhint %}

## Distribución <a href="#distribution" id="distribution"></a>

| Distribuido a                    | Reward/bloque (% de emisión) | Reward/bloque (CAKE Total) | Reward/Día          |
| -------------------------------- | ---------------------------- | -------------------------- | ------------------- |
| Farms y Lotería                  | 9.37%                        | 3.75                       | 108,000 (aprox)     |
| Desviadas y quemadas             | ​                            | ​                          | -46,000             |
| Syrup Pools                      | 25%                          | 10                         | 288,000 (aprox)     |
| **Emisión Diaria Total de CAKE** | ​                            | ​                          | **350,000 (aprox)** |

{% hint style="info" %}
El proceso de quema es manual. [Ve las transacciones aquí](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

## Por qué es manual la quema?

Para comenzar a funcionar, PancakeSwap se lanzó como MVP (producto mínimo viable) con el contrato de MasterChef emitiendo 40 CAKE por bloque. Por esa razón, el primer equipo no agregó funciones adicionales, como la capacidad de personalizar la lógica de emisión de CAKE. Como migrar a un nuevo MasterChef requeriría mucho tiempo y esfuerzo, el equipo optó por reducir las emisiones de CAKE a través de un proceso de quema manual mediante la creación de dos pools:

* Legacy Lottery Pool (PID - 137) - CAKE quemada de la Lotería
* Burn Pool (PID - 138) - CAKE quemada por bloque

Estos pools funcionan de manera similar a los Farms, donde los Chefs pueden ajustar el porcentaje de los 40 CAKE por bloque asignados después de cada voto de reducción de emisiones de CAKE.

{% hint style="warning" %}
El día de la quema, el supply que se muestra en la página de inicio podría saltar repentinamente en varios millones de CAKE.&#x20;

No te preocupes, este **CAKE NUNCA ENTRA EN CIRCULACIÓN**
{% endhint %}

Este salto aparente se debe a cómo se almacena todo el CAKE que se asigna para la quema durante la semana.

El CAKE enviado a ambos grupos PID-137 y PID-138 se cosecha antes de completar las quemas semanales de tokens, y esto hace que el supply total que se muestra en el sitio salte en \~ 6M. Esto se debe a que el CAKE pendiente no se registra en el Suministro Total hasta que se cosecha el día de la quema. Una vez que se completa la transacción de quema de tokens, el \~6M se muestra en Quemado hasta la fecha.

## **Otros Mecanismos Deflacionarios** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

En la actualidad, también se quema CAKE de las siguientes maneras:

* **0.0575%** de cada trade en PancakeSwap V2
* **100%** de CAKE enviada a la Dev address
* **100%** de CAKE obtenida en IFOs
* **100%** de CAKE gastada en creación de Perfiles y NFTs emitidos
* **100%** of CAKE obtenida en las Subastas de Farm
* **20%** de CAKE gastada en Tickets de Lotería
* **45,000** CAKE por día (históricamente asignadas a la lotería) (_Las CAKE para esto son generadas a través de un Farm - PID 31)_
* **3%** de cada ronda Predicción con BNB se utiliza para comprar CAKE y quemar
* **3%** de cada ronda de Predicción con CAKE
* **2%** de cada cosecha en el Pool de CAKE Flexible
* **2%** de cada venta del NFT Market es usada para comprar y quemar CAKE

## Cómo confirmar el Supply por uno mismo

Para confirmar que el supply de CAKE que se muestra en la página de inicio de PancakeSwap es correcto:

1. Ve al contrato de token CAKE en BscScan y mira [cuánto CAKE tiene la dirección de burn](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances). Esa es la cantidad total de CAKE que se ha quemado (eliminado de la circulación PARA SIEMPRE, e imposible de recuperar).
2. Luego, reste esta cantidad quemada del "Supply total" que muestra BscScan.
3. Eso brinda el Supply actual de CAKE



**Lea más sobre la mecánica deflacionaria de CAKE en la página siguiente.**
