# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

Las Granjas de Yield Farming permiten a los usuarios ganar CAKE mientras apoyan a PancakeSwap haciendo staking de Tokens LP.

Consulta nuestra [guía de Cómo Usar las Granjas](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) para comenzar con el farming.

Aprende [cómo encontrar los contratos inteligentes de las Granjas](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
El Yield Farming puede dar mejores recompensas que los Syrup Pools, pero conlleva el riesgo de **Pérdida Impermanente**. No es tan aterrador como suena, pero vale la pena aprender sobre el concepto antes de comenzar.

Consulta este excelente [artículo sobre Pérdida Impermanente](https://academy.binance.com/en/articles/impermanent-loss-explained) de Binance Academy para obtener más información.
{% endhint %}

## Cálculo de recompensas

Los cálculos de APR de las Granjas de Yield Farming incluyen tanto:

* **APR de recompensas LP** ganado al proporcionar liquidez; y
* **APR de recompensas base de la Granja** ganado al hacer staking de Tokens LP en la Granja.

¿Por qué? Porque cuando pones en staking tus tokens LP en una granja para ganar CAKE, ¡sigues proporcionando liquidez al pool de liquidez, por lo que también ganas recompensas LP!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

¿Cómo calculamos esas cifras?

### Calculando el APR de Recompensa Base de la Granja

El **APR Base de la Granja** se calcula según el multiplicador de la granja y la cantidad total de liquidez en la granja -- esta es la cantidad de CAKE distribuida a la granja.

### Calculando el APR de Recompensa LP

Además de eso, los farmers reciben **recompensas LP** por proporcionar liquidez. Aquí hay un ejemplo de cálculo de **recompensas LP**:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

En el par WBNB/BUSD anterior, vemos estos valores:

**Liquidez:** $387,42M\
**Volumen 24H:** $96,97M\
**Volumen 7D:** 709,73M

* Calcular comisiones anuales
  * Usa el volumen de 24H para calcular la **participación de comisiones** de los proveedores de liquidez en el pool (basado en la estructura de comisión de trading del 0,17%):\
    $96,970,000\*0.17/100 = **$164,849**
  * Luego, usa esa **participación de comisiones** para estimar las **comisiones anuales proyectadas** ganadas por el pool (basadas en el volumen actual de 24h):\
    $164,849\*365 = **$60,169,885**
* Ahora podemos usar las comisiones anuales para calcular el **APR de recompensas LP:** Eso son las **comisiones anuales** divididas por la **liquidez:**\
  ($60,169,885/$387,420,000)\*100 = **15,53% APR de recompensa LP**
