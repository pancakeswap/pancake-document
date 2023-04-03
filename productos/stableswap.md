# 🔄 StableSwap

![](<../.gitbook/assets/0 (4).png>)

StableSwap en PancakeSwap es una función para negociar pares estables con un deslizamiento más bajo basado en una función de deslizamiento de curva invariable. Está diseñado para intercambiar activos específicos que tienen un precio cercano, como monedas estables en USD (p. ej., HAY, BUSD y USDT) o tokens de staking liquido (p. ej., stkBNB y aBNBc).

StableSwap es una implementación de Curve Finance en el AMM de PancakeSwap. Agrega una curva de suma constante invariante lineal (x+y=k) además de la fórmula del producto constante (x\*y=k) para mantener los precios más iguales (similares) siempre que el fondo de liquidez no esté extremadamente desequilibrado. Como resultado, dado que los StableSwaps están restringidos a activos de precio similar, el impermanent loss no es tan preocupante (excepto en casos extremos de depeg) y el deslizamiento es menor que el AMM normal que solo usa la fórmula de producto constante.

Si realiza un intercambio de tokens (swap) en StableSwap, pagará tarifas (fees) de negociación más bajas que el 0.25% habitual del PancakeSwap AMM normal. La tarifa se desglosa de la siguiente manera:

* 50% al LP como recompensas
* 40% para recomprar y quemar CAKE
* 10% al Tesoro de PancakeSwap

### **Tarifas del Stableswap** <a href="#_t420txdbiizg" id="_t420txdbiizg"></a>

Las tarifas (fees) para los pares se desglosan en la siguiente tabla:

![](../.gitbook/assets/1.png)

La cocina implementará gradualmente los pares de StableSwap y revisará las tarifas para probar y mejorar aún más el producto.

### **¿Por qué debo usar StableSwap en lugar del Swap AMM normal?** <a href="#_i7oaqlsdnttr" id="_i7oaqlsdnttr"></a>

* Intercambie sus monedas estables u otros pares de activos de precio similar de manera más eficiente con los mismos pasos del swap
* Con la función StableSwap, el deslizamiento es más bajo que en el AMM normal
* Los fees de trading también son más bajos en comparación con el AMM normal

### **¿Cuáles son algunas de las características que todavía están cocinando?** <a href="#_c7evr84kq4lb" id="_c7evr84kq4lb"></a>

* Mejores guías en la interfaz de usuario con respecto a StableSwap y LPs estables
* Página de información de StableSwap
* Agregar más pares estables y el proceso de migración de los LPs existentes
