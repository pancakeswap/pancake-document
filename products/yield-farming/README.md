# 🚜Yield Farming

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-McQraJG25bEh9ufOHLT%2F-McS-Rk4u3IqogZhr2N2%2Fdocs%20masthead%20%281%29.png?alt=media&token=0124644e-2c34-492d-bd66-2710c4dd8869)

Las Yield Farms permiten a los usuarios ganar CAKE mientras apoyan a PancakeSwap depositando sus LP tokens.

Check out our [How to Use Farms guide](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) to get started with farming.

Learn [how to find Farm smart contracts](https://docs.pancakeswap.finance/products/yield-farming)​

El Yield farming puede dar mejores recompensas que los Syrup Pools, pero viene con un riesgo de **Impermanent Loss**. No es tan aterrador como parece, pero vale la pena aprender sobre el concepto antes de comenzar.

Echa un vistazo a este gran [artículo sobre Impermanent Loss de Binance Academy](https://academy.binance.com/es/articles/impermanent-loss-explained) para obtener más información.

## Cálculo de Recompensas <a id="reward-calculations"></a>

El cálculo de la tasa del APR de Yield Farm incluye tanto las recompensas obtenidas al proporcionar liquidez como las recompensas ganadas depositando tokens LP en el Farm.

Anteriormente, las recompensas obtenidas por los titulares de tokens LP generadas a partir de los fees de trading no se incluían en los cálculos de APR. Los cálculos de APR ahora incluyen estas recompensas y reflejan mejor la recompensa esperada para los pares en los Farms

A continuación se muestra una explicación básica de cómo se calcula la tasa.

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

En la imagen de arriba de los pares WBNB/BUSD, vemos estos valores:

**Liquidity \(Liquidez\):** $387.42M **Volume 24H \(Volumen 24hs\):** $96.97M **Volume 7D \(Volumen 7D\):** 709.73M

Para calcular el APR, primero tomamos el volumen de 24 horas, $96,970,000, y calcular los fees compartidos de los LP-holders, 0.17% \[**$96,970,000\*0.17/100 = $164,849\]**.

A continuación, estimamos las tarifas anuales en función del volumen de 24 horas \[**$164,849\*365 = $60,169,885**\].

Ahora podemos calcular la tasa APR con comisiones anuales divididas por liquidez \[\(**$60,169,885/$387,420,000\)\*100 = 15.53%**\]

Con el fee APR, podemos agregarlo \(15.53%\) con el Farm staking APR \(20.08%\) para obtener el nuevo APR total \[**15.53%+20.08% = 35.61%**\].

