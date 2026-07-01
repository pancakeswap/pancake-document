# FAQ y Solución de Problemas del Syrup Pool

## Solución de Problemas

### **¡No puedo encontrar el Syrup Pool en el que estaba haciendo staking!**

Deberías poder encontrar el Syrup Pool en la pestaña "Terminados" de la página de Syrup Pools.

Al seleccionar "Solo en Staking", será más fácil encontrar tus activos.

### **¿Por qué no puedo retirar el staking de mis tokens de un Syrup Pool?**

Si no puedes retirar el staking del pool Stake Cake, Earn CAKE, asegúrate de no haber vendido los tokens SYRUP en tu billetera. Este token actúa como `prueba de propiedad` de tu CAKE en el pool Manual de CAKE.

### **¿Por qué mis tokens ganados fueron a cero después de hacer/retirar staking?**

¡No te preocupes! Ya están en tu billetera.

Cada vez que haces o retiras staking de un Syrup Pool o granja, tus tokens ganados son cosechados y enviados a tu billetera al mismo tiempo.

## **Preguntas Generales**

### ¿Cómo se calcula el APR para los Syrup Pools?

> APR del Syrup Pool = Recompensas anualizadas (USD) / Fondos del usuario en staking en el Syrup Pool (USD) \* 100

Como ejemplo básico, tomemos un pool de 60 días con 300,000 USD en recompensas y 3,000,000 USD en CAKE en staking.

El APR fluctúa a medida que más CAKE es puesto en staking por los usuarios, y a medida que el precio de CAKE y el token de recompensa varían.

|                                                          | **Cálculo**                      | Monto                                        |
| -------------------------------------------------------- | -------------------------------- | -------------------------------------------- |
| Total de recompensas a distribuir (valor USD)            |                                  | 300,000 USD                                  |
| Período de distribución                                  |                                  | 60 días                                      |
| Distribución diaria                                      | 300,000 / 60 =                   | 5,000 USD diarios                            |
| **Recompensas anualizadas (valor USD)**                  | 5,000 \* 365 =                   | **1,825,000 USD**                            |
| **Valor de CAKE en staking por usuarios en pool (USD)**  |                                  | **3,000,000 USD**                            |
| **APR**                                                  | (1,825,000 / 3,000,000) \* 100 = | <p></p><p><strong>60,833% APR</strong></p>   |

### **¿A qué se refiere el número "Fin" en mi Syrup Pool?**

Esto muestra la cantidad de bloques que quedan hasta que las recompensas para ese pool dejen de distribuirse. Una vez que el pool haya alcanzado ese bloque, deberías retirar el staking de tus tokens, porque no recibirás ninguna recompensa después de eso.

### **¿De dónde provienen las recompensas de los Syrup Pools?**

Hay tres tipos principales de Syrup Pools.

1. Stake CAKE, gana CAKE
2. Stake CAKE, gana otros tokens.
3. Stake otros tokens, gana CAKE

Las recompensas para los Syrup Pools "Stake CAKE, gana CAKE" provienen de las [emisiones de CAKE](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). Cada bloque, se asigna un número de tokens CAKE como recompensas para estos pools.

Las recompensas para el tipo "Stake CAKE, gana otros tokens" son proporcionadas por los equipos de proyecto que patrocinan un Syrup Pool.

Para el tipo "Stake otros tokens, gana CAKE", el tesoro de PancakeSwap recompra CAKE del mercado para distribuirlo como recompensas. Estos pools son financiados por PancakeSwap, no por los proyectos.

### ¿Qué es el Token SYRUP?

El Token SYRUP de PancakeSwap se deposita en tu billetera cuando interactúas con el pool Syrup **Manual** "Stake CAKE, Gana CAKE". No está en staking.

Es básicamente un pagaré que muestra cuánto CAKE has puesto en staking en el pool.

Se devolverá automáticamente cuando retires el staking de tu CAKE de ese pool.

{% hint style="warning" %}
¡No vendas tus tokens SYRUP! Necesitas devolver tu SYRUP para retirar el staking de tu CAKE del pool Manual de CAKE. La cantidad de SYRUP que devuelvas debe ser la misma que la cantidad de CAKE que retiras del staking.
{% endhint %}
