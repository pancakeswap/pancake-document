---
description: '2026-08-21'
---

# Presentamos Shared Inventory Hook

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

Cotizar cinco pares no debería costar cinco veces el capital. Pero on-chain, ese es el trato que recibe todo emisor de activos: la liquidez está atada a cada par, así que cada par nuevo significa aportar otro bloque de capital, la mayor parte parada sin ganar nada hasta que ese par exacto se opera dentro del rango de precios exacto. Cada vez que quieres cotizar un par nuevo, aportas capital fresco como LP, capital que queda bloqueado en ese único par y no puede usarse en ningún otro lugar.

El Shared Inventory Hook (SIH) rompe ese vínculo. Es el hook más reciente de PancakeSwap Infinity, y el primero creado para la eficiencia del capital.

_💡 Recordatorio: un hook es un contrato inteligente (como un complemento) que se conecta a un pool de Infinity y ejecuta lógica personalizada durante el intercambio, sin necesidad de crear un nuevo venue._

Entonces, ¿cómo funciona?

En lugar de bloquear una reserva separada en cada pool, un emisor de activos RWA financia **un inventario compartido**, y el shared inventory hook cotiza profundidad desde él en el par que se esté operando, just-in-time, justo en el momento del intercambio. Piénsalo como un único almacén que abastece todos los platos de la cocina, en lugar de un almacén separado para cada uno. Un solo saldo hace el trabajo de muchos.

Ese único cambio es lo que hace eficiente en capital a SIH, y se manifiesta de tres maneras:

* **El capital permanece activo y trabajando.** La liquidez del inventario del hook se inyecta just-in-time en un intercambio, de modo que trabaja activamente y te genera comisiones en lugar de quedarse inactiva.
* **Oportunidad de comisiones desde un solo saldo, en múltiples pares.** Un inventario gana en todos los pares a los que sirve, así que captas el flujo de comisiones con mucho menos capital desplegado.
* **Menor impacto en el precio.** Como la liquidez cotizada en el momento del intercambio es más profunda, las operaciones grandes sufren menor impacto en el precio siempre que SIH esté cotizando el mejor precio.
* **Mayor eficiencia del capital.** Financia una vez; el mismo capital respalda la profundidad en todos los pares con SIH habilitado. Además, puedes habilitar SIH para un nuevo par sin añadir capital.

> \*\*¿Ya te convenciste? Lleva tus activos on-chain de la forma eficiente en capital: rellena este formulario → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**La prueba está on-chain**

SIH se lanzó con bStocks este agosto, y lo más importante es cuánto trabaja ese capital. En la última instantánea del hook (21 de agosto de 2026), el 75% del inventario compartido está desplegado activamente en los tres pares (inventario del hook \~$297K, activo \~$224K). En los dos pares maduros, CRCLB y MUB, la utilización es de \~99% (98.96% / 98.95%). El capital que estaría inactivo en pools CLAMM tradicionales de V3 aquí está en rango y cotizando.

En sus primeras semanas (hasta el 21 de agosto), los tres pares negociaron \~$710K en 5,713 intercambios, servidos desde un inventario compartido de \~$297K, ganando comisiones de LP en un nivel del 0.25%.

_**Fuentes:** Panel interno de Dune_ **Pools en vivo:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**Hacia dónde vamos**

El modelo está pensado para escalar: más pares, un único saldo compartido extendiéndose por miles de mercados que operan 24/7. Es el camino más rápido que hemos visto para llevar toda la gama de pares de un token on-chain sin multiplicar el capital que los respalda.

Los pools SIH en vivo se encuentran en la [página Earn de PancakeSwap](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001): abre **Infinity** y busca **Shared Inventory** en las características del pool. SIH está habilitado actualmente en CRCLB / USDT, MUB / USDT y GMEB / USDT.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_Nota: los LP minoristas ya pueden añadir liquidez a estos pools desde Earn; ese depósito se convierte en liquidez residente del pool, mantenida por separado del inventario compartido._

_**Importante:**_

_SIH está menos expuesto a la deriva de precios que una posición de LP estándar porque el inventario solo se pone a trabajar en el momento de un intercambio. No está libre de riesgo. El operador sigue manteniendo un inventario que se mueve con el mercado. Como con cualquier estrategia on-chain, los resultados dependen del volumen, el inventario, la cobertura y las condiciones del mercado._

¿Listo para maximizar la eficiencia del capital? Habilita SIH en tus pares de tokens ahora → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, The Chefs 🥞

***

_Aviso legal: este contenido es solo para fines informativos y educativos generales. No debe interpretarse como asesoramiento financiero, legal ni profesional de ningún tipo. Los precios de los activos digitales pueden ser volátiles. El valor de tu inversión puede subir o bajar._
