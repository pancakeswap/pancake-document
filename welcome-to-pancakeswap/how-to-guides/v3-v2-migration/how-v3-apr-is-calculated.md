# Cómo se calcula el APR en V3

{% hint style="info" %}
En la Liquidez y los Farms de V3, con la nueva liquidez no fungible y la capacidad de rango de precios personalizable, cada posición LP tendrá su propio APR de comisión LP y APR de Yield Farming de CAKE.
{% endhint %}

El APR total se combina por el APR de comisión LP y el APR de recompensa CAKE.

### Comisión LP

Teóricamente hablando, dado un rango de precios y la liquidez que el usuario está a punto de agregar, podemos estimar la comisión esperada para los próximos 7 días de la siguiente manera:

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Cantidad de comisión acumulada en el rango de precios especificado por el usuario en los últimos 7 días
* $$L_{in}$$: Liquidez actual en el rango de precios especificado por el usuario
* $$\Delta{L}$$: Liquidez que el usuario quiere agregar al rango de precios

#### Comisión en rango

Para $$fee_{in}$$, usamos los datos históricos de volumen de trading, el nivel de comisión y los datos históricos de precios para estimar el precio dentro del rango:

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Nivel de comisión
* $$V_{7d}$$: Volumen total de trading de los últimos 7 días
* $$T_{in}$$: Duración, medida en segundos, de los precios que se mantienen dentro del rango de precios en los últimos 7 días
* $$T_{7d}$$: 7 días medidos en segundos

### APR de CAKE

#### Asignación del pool

La recompensa total de CAKE por segundo en MC v3 usando upkeep puede derivarse de `latestPeriodCakePerSecond`&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

En cada pool, podemos usar `poolInfo` para obtener el `poolWeight` dividiendo `poolInfo.allocPoint / totalAllocPoint`

#### APR global de CAKE

El APR global se calcula usando la cantidad total de liquidez activa y en Staking con las emisiones de recompensas de CAKE del pool.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` representa la liquidez activa del pool en Staking en USD, compuesta por todos los ticks de posición en rango en Staking en MasterChef v3.

#### APR de CAKE por posición

Los APRs para posiciones individuales pueden variar según la configuración de su rango de precios.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: Recompensa de CAKE ganada en USD por año en el pool
* $$USD_p$$: Valor total en USD de la posición
* $$L_{p}$$: Liquidez de la posición
* $$L_{lm}$$: Liquidez total de Staking rastreada por LMPool
