# Classic StableSwap

El Classic StableSwap es una implementación del AMM de Curve Finance en PancakeSwap. Añade la curva de suma constante invariante lineal (x+y=k) sobre la fórmula de producto constante (x\*y=k) para mantener los precios más iguales siempre que el pool de liquidez no esté extremadamente desequilibrado. Como resultado, dado que los StableSwaps están restringidos a activos con precios similares, la pérdida impermanente no es tan preocupante (excepto en casos extremos de desvinculación) y el deslizamiento es menor que el AMM normal que solo usa la fórmula de producto constante.

Cuando realizas un Intercambio (operación) en el StableSwap pagarás comisiones de trading más bajas que el habitual 0,25% en el AMM normal de PancakeSwap. La distribución de comisiones se desglosa de la siguiente manera:

* 50% para los LP como recompensas&#x20;
* 40% para la recompra y quema de CAKE&#x20;
* 10% para el Tesoro de PancakeSwap

## Comisiones de StableSwap

Las comisiones para los pares se desglosan en la siguiente tabla:

<table><thead><tr><th width="150">Par Estable</th><th width="132">Comisiones de Trading</th><th width="118.33333333333331">Recompensas LP</th><th width="124">Recompra CAKE</th><th>Tesoro PancakeSwap</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-BUSD</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>USDC-USDT</td><td>0,01%</td><td>0,005%</td><td>0,004%</td><td>0,001%</td></tr><tr><td>HAY-BUSD</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>HAY-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>axlUSDC-USDT</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>BNBx-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr><tr><td>stkBNB-WBNB</td><td>0,04%</td><td>0,02%</td><td>0,016%</td><td>0,004%</td></tr></tbody></table>

El equipo de PancakeSwap lanzará gradualmente pares de StableSwap y revisará las comisiones para probar y mejorar aún más el producto.

## ¿Por qué debería usar StableSwap en lugar del Intercambio AMM normal?

* Intercambia tus stablecoins u otros pares con precios de activos similares de manera más eficiente con los mismos pasos de operación&#x20;
* Con la función StableSwap, el deslizamiento de trading es menor que el AMM normal&#x20;
* Las comisiones de trading de StableSwap son más bajas comparadas con el AMM normal
