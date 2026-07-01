# FAQ

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### ¿Cómo se calculan los multiplicadores de bCAKE?

Es posible que notes que obtienes diferentes multiplicadores de impulso de bCAKE al hacer Staking en diferentes farms.

Eso se debe a que los multiplicadores de bCAKE - Farm Boosters se calculan usando las siguientes métricas al activarse o actualizarse:

* `userLpBalanceInFarm` : La cantidad de liquidez que estás apostando en la farm.&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : La cantidad total de liquidez apostada en la farm o la cantidad activa actual de liquidez en el pool de LP V3. bCAKE elegirá el número más pequeño entre los dos.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : El número en tiempo real de veCAKE que tienes
* `veCAKE.totalSupply` : El suministro total en tiempo real de veCAKE

El multiplicador se calcula usando el siguiente método:

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` y `constantB` son establecidos por el kitchen y están sujetos a ajustes futuros según los comentarios de la comunidad y las condiciones del mercado. `constantB` varía entre diferentes farms para compensar las diferencias de precio de LP.

`constantA` y `constantB` pueden obtenerse mediante:

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

Pero:

{% hint style="info" %}
**En resumen**

Cuanto más LP (liquidez) quieras impulsar

Más CAKE necesitas bloquear por duraciones más largas
{% endhint %}

### ¿Por qué mis multiplicadores cambian incluso después de la activación?

Ten en cuenta que **cualquier acción del usuario en la posición de farming o el pool de Staking de CAKE actualizará automáticamente tu multiplicador de impulso** basándose en los últimos datos y estadísticas de las farms y el pool de Staking de CAKE, incluyendo pero no limitado a:

* Apostar/Retirar posición de/hacia la farm
* Cosechar recompensas de CAKE de la farm
* Extender tu duración de Staking de CAKE
* Agregar más CAKE a tu posición de Staking a plazo fijo
* Convertir tu posición de Staking de CAKE a flexible

{% hint style="warning" %}
Ten en cuenta:&#x20;

Para garantizar la equidad y prevenir el posible abuso y trampa usando datos desactualizados. El Farm Booster está diseñado para ser sin permisos y gobernanza comunitaria. Por lo tanto, **cualquiera** puede llamar a la función `updateLiquidity(address _tokenId)` en el contrato MasterChef V3 para actualizar los multiplicadores de impulso de cualquier usuario usando los últimos datos.

Además, el kitchen también monitoreará todas las posiciones de farming habilitadas para bCAKE y actualizará cualquier posición con un multiplicador desactualizado.
{% endhint %}

### ¿Por qué no puedo impulsar una posición?

1. El Farm Booster solo está disponible para farms seleccionadas. Se habilitarán más farms en el futuro. Por ahora, **busca la figura APR verde con un ícono de cohete verde.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. Debido a la participación de múltiples contratos, algunas interacciones de contrato requieren un poco más de tokens de gas (BNB). Así que asegúrate de tener suficiente BNB en tu billetera. Si el error persiste, intenta aumentar manualmente el límite de gas de la transacción.

### ¿Cuál es el multiplicador máximo de bCAKE que puedo obtener?

Actualmente, el impulso máximo que un usuario puede obtener para un farm booster es 2.5x, lo que les ofrece 2.5x los APRs originales.

Ten en cuenta que el impulso máximo que puedes obtener varía según el tipo de liquidez que estés tratando de apostar:

* V3: máximo 2x
* V2, StableSwap: máximo 2.5x
* Gestores de posiciones: máximo 2.5x

### ¿Cómo puedo aumentar mis multiplicadores de bCAKE?

* Agregar más CAKE a la posición de Staking de veCAKE
* Extender o renovar la duración de tu posición de Staking de veCAKE

En pocas palabras:

**Apuesta más CAKE, apuesta por más tiempo**

[Aprende más sobre cómo se calculan los multiplicadores de impulso de bCAKE](faq.md#how-are-the-bcake-multipliers-calculated).

### ¿De dónde provienen las recompensas adicionales de CAKE impulsadas?

**Tranquilo, no se asignan emisiones adicionales para hacer posible bCAKE.**

Similar al Staking de CAKE de veCAKE. bCAKE aumenta la participación individual de los usuarios contra otros.

Aunque el APR base puede bajar después del despliegue de bCAKE. Los chefs creen que es una buena compensación ya que beneficia a los fieles amantes de CAKE al impulsar su rendimiento de farming, crea más demanda de CAKE y sirve como un gran incentivo para el Staking de CAKE.

### ¿Por qué el multiplicador que recibo es bajo?&#x20;

bCAKE - Farm Booster funciona evaluando tanto tu posición de Staking de veCAKE como tu posición de farming de liquidez contra otros usuarios. En pocas palabras:

> Si los usuarios quieren impulsar más liquidez en la farm, deben bloquear más CAKE por duraciones más largas en el pool.

Este diseño garantiza que los beneficios no solo se ofrezcan a los grandes tenedores, sino a cualquier usuario que tenga una posición de Staking de CAKE de tamaño considerable en comparación con la posición de farming.

Aprende más sobre cómo se calcula el multiplicador [aquí](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated).

### ¿Por qué solo hay x cantidad de farms disponibles para el booster?

Dado que bCAKE implica actualizar uno de los productos principales de PancakeSwap, que es el farming de liquidez. Los chefs quieren adoptar un enfoque más lento y constante para el lanzamiento.

Por lo tanto, en la fase inicial de lanzamiento del producto. Muchos de los parámetros son muy conservadores. Incluyendo el número de farms que los usuarios pueden impulsar, qué farms pueden impulsar, así como el parámetro de dificultad para recibir el multiplicador de impulso.

**Los chefs ajustarán los parámetros basándose en los comentarios de la comunidad.**

### **¿Está auditado bCAKE V3?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE ha sido auditado tanto por auditores internos como externos.

Consulta los informes de auditoría aquí: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
