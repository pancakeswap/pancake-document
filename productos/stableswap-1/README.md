# 🔄 StableSwap

StableSwap en PancakeSwap es una función para negociar pares estables con un deslizamiento más bajo basado en una función de deslizamiento de curva invariable. Está diseñado para intercambiar activos específicos que tienen un precio cercano, como monedas estables en USD (p. ej., HAY, BUSD y USDT) o tokens de participación de liquidez (p. ej., stkBNB y aBNBc).

StableSwap es una implementación del AMM de Curve Finance en PancakeSwap. Agrega una curva de suma constante invariante lineal (x+y=k) además de la fórmula del producto constante (x\*y=k) para mantener los precios más iguales (similares) siempre que el fondo de liquidez no esté extremadamente desequilibrado. Como resultado, dado que los StableSwaps están restringidos a activos de precio similar, el impermanent lost no es tan preocupante (excepto en casos extremos de depeg) y el deslizamiento es menor que el AMM normal que solo usa la fórmula de producto constante.

Si realiza un intercambio de tokens (swap) en StableSwap, pagará una tarifa (fee) del swap de 0,04%, que es más baja que el 0,25% habitual en PancakeSwap AMM normal. La tarifa se desglosa de la siguiente manera:

* 0.02% al LP como recompensas (50%)
* 0.016% para recompra y quema de CAKE (40%)
* 0.004% a la Tesorería PancakeSwap (10%)

En el lanzamiento, la cocina implementará pares de StableSwap gradualmente para probar y mejorar aún más el producto. El primer par que se lanzará será HAY-BUSD.

[HAY](https://helio.money/) de Helio Protocol es una [destablecoin](https://docs.helio.money/) con BNB sobrecolateralizada totalmente descentralizada. Las razones por las que se selecciona el par HAY-BUSD como el primero son:

* Ser uno de los primeros centros importantes de comercialización, para que HAY absorba volumen con el tiempo.
* Dado que HAY se lanzó recientemente (mediados de agosto de 2022) en comparación con otras monedas estables, el volumen y el impacto operativo de la transferencia de liquidez son más manejables para lanzar en el producto StableSwap
* Según el progreso de este par y los comentarios de la comunidad, la cocina puede agregar gradualmente otros pares estables.

## **¿Por qué debo usar StableSwap en lugar del swap AMM normal?**

* ¡Intercambie sus monedas estables u otros pares de activos de precio similar de manera más eficiente con los mismos pasos del swap!
* Con la función StableSwap, el deslizamiento es más bajo que en el AMM normal que solo usa la fórmula de producto constante
* Los fees de trading también son más bajos en comparación con el AMM normal.

## **¿Cuáles son algunas de las características que la cocina todavía está arreglando y cocinando?**

* Mejores guías sobre la interfaz de usuario con respecto a StableSwap y LP estables
* Página de información de StableSwap
* Agregar pares de trading más estables y el proceso de migración de los LP existentes

## **Timeline:**

* Lanzamiento de StableSwap y provisión de liquidez HAY-BUSD habilitada: **22 de septiembre de 2022 11:00 UTC**
* Migración de Farm (las recompensas de CAKE se redirigen de HAY-BUSD LP Farm a HAY-BUSD Stable LP Farm): **23 de septiembre de 2022 a las 11:00 UTC.**
