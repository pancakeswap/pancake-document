---
description: Staking de CAKE a plazo fijo y asignaciones de IFO
---

# iCAKE

### Qué es **iCAKE?**

CAKE es similar a los "créditos IFO" del pool anterior de IFO CAKE, que se retiró durante la migración de MasterChef v2. A partir de esta actualización, iCAKE determinará el límite máximo de compromiso de CAKE en las ventas públicas de IFO en PancakeSwap. Por ejemplo, si tiene 200 iCAKE, podrá comprometer 200 CAKE en cualquier próxima venta pública de IFO.&#x20;

**iCAKE NO es un token nuevo, es una cálculo numérico utilizado por el sistema PancakeSwap IFO.**

### Cómo se calcula iCAKE?

La cantidad de iCAKE que tiene se basa en la cantidad de CAKE depositados en el pool de CAKE a plazo fijo y el periodo total de su posición de staking a plazo fijo actual.

iCAKE funciona en función de un umbral de duración de participación para todos los usuarios de iCAKE.&#x20;

Si la duración de su pool está por encima del umbral, la cantidad de iCAKE que tiene es igual a la cantidad de CAKE en su posición de stake.&#x20;

Si la duración de su pool está por debajo del umbral, la cantidad de iCAKE que tiene se reducirá linealmente y se ajustará.&#x20;

Si su pool finaliza, el número de iCAKE que tiene es 0.&#x20;



Por ejemplo, si el umbral es de 20 semanas:

* Su pool a plazo fijo tiene una duración de 25 semanas y 200 CAKE en stake. Entonces el número de iCAKE que tienes es 200.
* Su pool a plazo fijo tiene una duración de 10 semanas y 200 CAKE en stake. Entonces el número de iCAKE que tienes es igual a 200 × (10 ÷ 20) = 100.
* Su pool a plazo fijo tiene una duración de 2 semanas y 200 CAKE en stake. Entonces el número de iCAKE que tienes es igual a 200 × (2 ÷ 20) = 20.
* Su pool a plazo fijo tiene una duración de 2 semanas y 200 CAKE en stake. Pero el pool está terminado. Entonces el número de iCAKE que tienes es 0.

|                    | La duración de su pool es igual o mayor que el umbral | La duración de su pool es más corta que el umbral                                   |
| ------------------ | ----------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **iCAKE Cantidad** | Es igual a la cantidad bloqueada de su CAKE           | Es igual a la cantidad bloqueada de su CAKE x (su duración/umbral de participación) |

### Cómo puedo ver cuántos iCAKE tengo?

![](<../../.gitbook/assets/image (172).png>)

Puedes consultar la cantidad de iCAKE que tienes en [la página IFO](https://pancakeswap.finance/ifo)

### Cómo aumentar la cantidad de iCAKE que tengo?

Puede aumentar la cantidad de iCAKE que tiene:

* Agregando más CAKE a plazo fijo en el pool de CAKE.
* Extendiendo tu período a plazo fijo si tu período actual es más corto que el umbral.

****![](<../../.gitbook/assets/image (175).png>)****

Puede obtener una vista previa de la cantidad de iCAKE generado desde su posición de staking al ajustar o inicializar el stake a plazo fijo.

### Cuál es el umbral para los cálculos de iCAKE?

Entre cada IFO, la cocina optimizará el umbral en función de la duración promedio de participación del pool de CAKE de plazo fijo. El ajuste se publicará en todos los canales oficiales.

![](<../../.gitbook/assets/image (174).png>)

Puede verificar el umbral actual para los cálculos de iCAKE al pasar el mouse o tocar el texto subrayado de iCAKE en la ventana del pool de CAKE.
