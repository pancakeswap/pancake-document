---
description: Staking de veCAKE y asignaciones de IFO
hidden: true
---

# iCAKE

### **¿Qué es el nuevo iCAKE?**

Después de la transición a veCAKE, el nuevo iCAKE se basará en el balance de veCAKE

* Al igual que el antiguo iCAKE, determina el límite máximo de compromiso de CAKE en las ventas públicas de IFO de PancakeSwap. Por ejemplo, si tienes 200 iCAKE, puedes comprometer 200 CAKE en las ventas públicas de IFO.
* El nuevo número de iCAKE se calcula usando el balance de veCAKE al final de cada IFO. Por lo tanto, tendrás diferentes números de iCAKE para cada IFO.
* Dado que el balance de veCAKE disminuye gradualmente con tu tiempo restante de bloqueo, tu iCAKE en futuros IFOs disminuirá con tu balance de veCAKE. Para mantener tu número de iCAKE, agrega más CAKE al Staking, o renueva/extiende tu bloqueo.

**iCAKE NO es un nuevo token, es una métrica numérica utilizada por el sistema IFO de PancakeSwap.**

### ¿Cómo se calcula iCAKE?

El número de iCAKE que tienes se basa en el balance de veCAKE al final de cada IFO, multiplicado por un ratio predefinido.

veCAKE es un valor calculado dinámicamente según cuánto CAKE bloqueas y cuánto tiempo queda en el bloqueo. Para aprender más sobre cómo se calcula veCAKE, consulta [aquí](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef).

Se aplica un ratio adicional encima del balance de veCAKE, que es ajustado por el Kitchen para cada IFO. Por ejemplo, si el ratio es 2x, y tienes 1 veCAKE al final del próximo IFO, puedes comprometer hasta 2 CAKE.

Ejemplo:

* Bloqueaste 100 CAKE por 2 años.
  * Tu tiempo restante de bloqueo es: `2 * 52 * 7 * 24 * 60 * 60 = 62899200`  (segundos)
  * El tiempo máximo de bloqueo es: `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (segundos)
  * En el momento actual, tienes: `100 * (62899200 / 126403199) ~= 49.76` veCAKE
* El próximo IFO está programado; su tiempo de finalización es exactamente 1 semana después, que son `604800` segundos después del momento actual.
  * En ese momento, tu tiempo restante de bloqueo es: `62899200 - 604800 = 62294400` (segundos)
  * En ese momento, tienes: `100 * (62294400 / 126403199) ~= 49.28` veCAKE
* Para este IFO, el ratio está establecido en `3x`
* Por lo tanto, para este IFO, tienes: `49.28 * 3 = 147.84` iCAKE, lo que significa que puedes comprometer hasta 147.84 CAKE en la venta pública.

### ¿Cómo verificar el número de iCAKE que tengo?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

Puedes verificar el número de iCAKE que tienes en la página IFO [aquí](https://pancakeswap.finance/ifo).

Ten en cuenta que cuando no hay un IFO próximo, tu iCAKE se calculará usando el balance de veCAKE en tiempo real, que disminuye gradualmente segundo a segundo.

Cuando hay un IFO próximo, tu iCAKE se calculará usando el balance de veCAKE en el momento de la captura, que es el final del IFO. Tu iCAKE no disminuirá ni cambiará hasta que termine el IFO.

### **¿Cómo aumentar el número de iCAKE que tengo?**

Puedes aumentar el número de iCAKE en cualquier momento:

* Agregando más CAKE a tu posición de Staking de veCAKE.
* Extendiendo tu posición de Staking de veCAKE.

en la [Página de Staking de CAKE](https://pancakeswap.finance/cake-staking)

### ¿Qué es el "Ratio" en el cálculo de iCAKE?

El Ratio es un factor de control adicional que se aplica encima del balance de veCAKE al calcular iCAKE.

Por ejemplo, si el ratio es 2x, y tienes 1 veCAKE al final del próximo IFO, puedes comprometer hasta 2 CAKE.

Entre cada IFO, el kitchen optimizará el "Ratio" basándose en varias métricas. El ajuste se publicará en todos los canales sociales.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

Puedes verificar el número de "Ratio" actual para los cálculos de iCAKE yendo a [la página IFO](https://pancakeswap.finance/ifo).
