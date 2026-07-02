# Como o APR do v3 é calculado

{% hint style="info" %}
No V3 de Liquidez e Farms, com a nova liquidez não fungível e a capacidade de intervalo de preços personalizável. Cada posição LP terá seu próprio APR de taxa LP e de farming de CAKE.
{% endhint %}

O APR total é composto pelo APR de taxa LP e pelo APR de recompensa de CAKE

### Taxa LP

Teoricamente falando, dado um intervalo de preços e a liquidez que o usuário está prestes a adicionar, podemos estimar a taxa esperada para os próximos 7 dias da seguinte forma&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Valor de taxa acumulado no intervalo de preços especificado pelo usuário nos últimos 7 dias
* $$L_{in}$$: Liquidez atual no intervalo de preços especificado pelo usuário
* $$\Delta{L}$$: Liquidez que o usuário quer adicionar ao intervalo de preços

#### Taxa no intervalo

Para $$fee_{in}$$, usamos os dados históricos de volume de negociação, nível de taxa e dados históricos de preços para estimar o preço no intervalo

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Nível de taxa
* $$V_{7d}$$: Volume total de negociação dos últimos 7 dias
* $$T_{in}$$: Duração, medida em segundos, dos preços permanecendo dentro do intervalo de preços nos últimos 7 dias
* $$T_{7d}$$: 7 dias medidos em segundos

### APR de CAKE

#### Alocação do Pool

A recompensa total de CAKE por segundo no MC v3 usando upkeep pode ser derivada por `latestPeriodCakePerSecond`&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

Em cada pool, podemos usar `poolInfo` para obter o `poolWeight` dividindo `poolInfo.allocPoint / totalAllocPoint`

#### APR Global de CAKE

APR global calculado usando o total de liquidez ativa e em Staking com as emissões de recompensa de CAKE do pool.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` representa a liquidez total ativa em Staking do pool atual em USD, composta por todos os ticks de posição dentro do intervalo em Staking no MasterChef v3.

#### APR de CAKE por Posição

Os APRs para posições individuais podem variar dependendo das configurações de intervalo de preços.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: Recompensa de CAKE ganha em USD por ano no pool
* $$USD_p$$: Valor total em USD na posição
* $$L_{p}$$: Liquidez da posição
* $$L_{lm}$$: Liquidez total de Staking rastreada pelo LMPool
