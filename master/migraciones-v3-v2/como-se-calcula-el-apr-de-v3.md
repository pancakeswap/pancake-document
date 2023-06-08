# Cómo se calcula el APR de V3

{% hint style="info" %}
En la liquidez y Farms de V3, con la nueva liquidez no fungible y la posibilidad de personalizar el rango, cada LP tendrá su propia recompensa de fees, y su APR de CAKE por farming.
{% endhint %}

El APR total es la combinación del APR de los fee de LP y el APR de las recompensas en CAKE

### LP fee

En teoría, para determinado nivel de rango de precios y liquidez que el usuario quiera agregar, se puede estimar el fee a recibir en los próximos 7 días, de la siguiente manera:

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Cantidad de Fee acumulado en el rando de precios determinado por el usuario en los últimos 7 días
* $$L_{in}$$: Liquidez actual en el rango de precios determinado por el usuario
* $$\Delta{L}$$: Liquidez que el usuario quiere agregar a ese rango de precios

#### Fee en rango

Para el $$fee_{in}$$, usamos el histórico de volumen de trading, fee tier y precio histórico para estimar precio en rango

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Fee tier
* $$V_{7d}$$: Volumen de trading total de los últimos 7 días
* $$T_{in}$$: Duración, medida en segundos, del nivel de precios dentro del rango determinado en los últimos 7 días
* $$T_{7d}$$: 7 días medidos en segundos

### Cake APR

#### Asignación del Pool

El total de recompensas en CAKE por segundo en MC V3, usando Upkeep, y puede ser derivado con `latestPeriodCakePerSecond`&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

En cada pool, podemos usar `poolInfo` para obtener el `poolWeight` dividiendo  `poolInfo.allocPoint / totalAllocPoint`

#### APR Global de Cake&#x20;

El APR Global calculado usando la cantidad total de la liquidez activa y depositada con las emisiones de las recompensas del pool de CAKE.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` representa la liquidez depositada activa actual en el pool en USD, compuesta por todas las posiciones en rango depositadas en el MasterChef v3.

#### APR de la posición de Cake

Los APRs para posiciones individuales pueden variar, dependiendo de la configuración del rango de precios.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: Recompensa de CAKE por año en el pool
* $$USD_p$$: Valor total de la posición en USD
* $$L_{p}$$: Liquidez de la posición
* $$L_{lm}$$: Liquidez total depositada, monitoreada por LMPool
