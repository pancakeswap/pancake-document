# 🚜 Yield Farming

![](<../../.gitbook/assets/0 (2) (1)>)

Las Yield Farms permiten a los usuarios ganar CAKE mientras apoyan a PancakeSwap depositando sus LP tokens.

Mira nuestra guía de[ Cómo usar Farms](https://docs.pancakeswap.finance/v/espanol/productos/yield-farming/como-usar-yield-farm-en-pancakeswap) para empezar.

Aprende[ cómo usar Farms desde BscScan](https://docs.pancakeswap.finance/v/espanol/productos/yield-farming/farms-bscscan)

⚠ El Yield farming puede dar mejores recompensas que los Syrup Pools, pero viene con un riesgo de **Impermanent Loss**. No es tan aterrador como parece, pero vale la pena aprender sobre el concepto antes de comenzar.

Echa un vistazo a este gran[ artículo sobre Impermanent Loss de Binance Academy](https://academy.binance.com/es/articles/impermanent-loss-explained) para obtener más información.

### **Cálculo de Recompensas** <a href="#_d38qg1pd06qi" id="_d38qg1pd06qi"></a>

El cálculo de la tasa de APR del Yield Farm incluye:

* El APR por las recompensas de LP obtenidas al proveer liquidez.
* El APR por las recompensas en CAKE del farm obtenidas dejando en staking los tokens LP en el farm correspondiente.

¿Por qué? Porque cuando dejas en stake tus tokens LP en un farm para ganar CAKE, todavía estás proporcionando liquidez al pool de liquidez, ¡así que también ganas recompensas de LP!

![](<../../.gitbook/assets/1 (2)>)

Entonces, ¿cómo calculamos estas cifras?

### **Calculando el APR base por recompensas del Farm** <a href="#_ewjp9lz4obuf" id="_ewjp9lz4obuf"></a>

El **APR base del Farm** se calcula de acuerdo con el multiplicador del farm y la cantidad total de liquidez en el farm, esta es la cantidad de CAKE distribuida en el farm.

### **Calculando el APR por recompensas de LP** <a href="#_y5jn658sg3qf" id="_y5jn658sg3qf"></a>

Los poseedores de los tokens LP reciben **recompensas de LP** por proveer liquidez. A continuación, se muestra una explicación básica de cómo se calcula la tasa:

![](<../../.gitbook/assets/2 (1) (2)>)

En la imagen de arriba del par WBNB/BUSD, vemos estos valores:

**Liquidity (Liquidez):** $387.42M

**Volume 24H (Volumen 24hs):** $96.97M

**Volume 7D (Volumen 7D):** 709.73M

* Calcular los fees anuales\

  *   Tomamos el volumen de 24 horas, $96,970,000, calculamos los **fees compartidos** de los LP-holders multiplicándose por 0.17% (comisión por cada swap que se reparte a los LP-holders):

      \[**$96,970,000\*0.17/100 = $164,849]**\

  * A continuación, estimamos los **fees anuales** en base a los **fees compartidos:** \[**$164,849\*365 = $60,169,885**].\

*   Ahora podemos calcular la tasa APR, usando los **fees anuales** y dividiéndolo por la liquidez del par:

    \[**$60,169,885/$387,420,000) \*100 = 15.53%**]

El APR TOTAL del farm, lo calculamos entonces, simplemente sumando el **APR base** + **APR por recompensas de LP** (20.08% + 15.53% = **35.61%**).
