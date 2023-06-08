# Como o APR v3 é calculado

{% hint style="info" %}
Nos Farms e Liquidez V3, com a nova liquidez não fungível e capacidade de faixa de preço personalizável. Cada posição LP terá sua própria taxa LP e APR de farm de CAKE.
{% endhint %}

O APR total é combinado pelo APR da taxa de LP e APR da recompensa de CAKE

### Taxa dos LP

Teoricamente falando, dada uma faixa de preço e usuário de liquidez prestes a adicionar, podemos estimar a taxa futura esperada de 7 dias da seguinte forma:

&#x20;                    <img src="../../.gitbook/assets/image (1).png" alt="" data-size="original">\


* $$fee_{in}$$: Valor da taxa acumulado na faixa de preço especificada pelo usuário nos últimos 7 dias
* ​$$L_{in}$$: Liquidez atual na faixa de preço especificada pelo usuário
* ​$$\Delta{L}$$: Liquidez que o usuário deseja adicionar naquela faixa de preço

#### Taxa na faixa(range)

Para o $$fee_{in}$$ usamos os dados históricos do volume de negociação, nível de taxa e dados históricos de preços para estimar o preço na farixa

​$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* ​$$f_t$$: nível de taxa
* ​​ $$V_{7d}$$: Volume total de negociação dos últimos 7 dias
* ​$$T_{in}$$: Duração, medida em segundos, dos preços dentro da faixa de preço nos últimos 7 dias
* ​$$T_{7d}$$: 7 dias medidos em segundos

### APR de CAKE

#### Alocação da Pool

O total de recompensa de CAKE por segundo no MC v3 usando upkeep e pode ser derivado por `latestPeriodCakePerSecond`

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

Em cada pool, podemos usar `poolInfo` para ter `poolWeight` divindo por `poolInfo.allocPoint / totalAllocPoint`

#### APR de CAKE global

APR global calculado usando a quantidade total de liquidez ativa e stake com as emissões de recompensa da pool de CAKE.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` representa a pool atual de liquidez em stake ativa em USD, composta por todos os ticks de posição na faixa em stake no MasterChef v3.

#### APR da posição de CAKE

APRs para posições individuais podem variar dependendo de suas configurações de faixa de preço.

&#x20;                         ![](<../../.gitbook/assets/image (1) (1).png>)

* ​$$USD_r$$: A recompensa de CAKE ganha USD por ano na pool
* ​$$USD_p$$: Valor total em USD na posição
* ​$$L_{p}$$: Liquidez da posição
* ​$$L_{lm}$$: Liquidez total de staking rastreada pela LMPool
