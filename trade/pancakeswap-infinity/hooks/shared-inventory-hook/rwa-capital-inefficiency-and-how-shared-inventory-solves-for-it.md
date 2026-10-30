---
description: '2026-09-04'
---

# Ineficiencia de capital en RWA y cómo la solucionan los Shared Inventory

Un experimento de caso de estudio de PancakeSwap (Parte 1: El planteamiento)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

Esta es la primera parte de un caso de estudio en dos partes. En esta parte, exponemos el problema real de eficiencia de capital al que se enfrentan los emisores de activos RWA, presentamos cómo el Shared Inventory Hook (SIH) de PancakeSwap está pensado para resolverlo y presentamos un experimento de caso de estudio en vivo para ponerlo a prueba con datos onchain.

En las próximas semanas publicaremos la Parte 2: Los resultados.

***

### 🧩 ¿Cuál es el problema de eficiencia de capital?

A la industria RWA le encanta una cifra: **cuánto se ha tokenizado.** Es el titular de casi todos los informes: una nueva clase de activos que llega, miles de millones emitidos, crecimientos de cientos por ciento.

Pero hay una segunda cifra que queda enterrada y que quizá sea una señal más relevante: **¿cuánto de eso se puede operar realmente?**

La brecha entre ambas es donde está la clave. En el rastreador de referencia, [rwa.xyz](http://rwa.xyz), el valor _representado_ onchain supera con creces el valor contra el que se puede _operar_ en un momento dado: los datos muestran que el valor bloqueado, de referencia y distribuido es **más de un orden de magnitud mayor que el que está en libros de órdenes negociables.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_Fuente: app.rwa.xyz/stocks_

Para un emisor de RWA, esta es la trampa. Tokenizar una acción, un ETF o un bono del tesoro es la parte fácil; lograr que se opere con spreads ajustados y de forma fiable es el reto, y es donde la eficiencia de capital se gana o se pierde. El objetivo final es que los traders puedan _operar realmente_ el activo tokenizado de forma fácil y barata: de ahí provienen, en última instancia, el volumen y las comisiones.

Y esta es la razón por la que es específicamente un problema de _eficiencia de capital_, y no solo de liquidez.

#### Cada pool cotizado exige su propia reserva exclusiva de USDT

Para que un par RWA sea negociable en un pool tradicional de liquidez concentrada (CLAMM), los emisores necesitan un activo de cotización dedicado, USDT, disponible para que los compradores vendan contra él. Si listas diez pares, el modelo CLAMM requiere financiar **diez reservas de USDT separadas**, una por par, sin que ninguna pueda ayudar a las demás. Así, el capital de cotización se fragmenta en silos exclusivos.

Lo medimos en nuestro propio libro. Tomamos **7 pools de acciones tokenizadas activos en PancakeSwap** (cada uno con un pool CLAMM V3 tradicional) y extrajimos el USDT exclusivo.

Snapshot: **2 de septiembre de 2026.**

<table data-search="false"><thead><tr><th>Par</th><th>USDT exclusivo en el pool</th><th>TVL del pool</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Total</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

Eso son **~$745k de USDT asignados de forma exclusiva.**

Y esto solo incluye los nombres que tienen un libro.

SNXXB, KORUB, SOXSB y DJTB no tienen ningún libro de USDT en CLAMM: están tokenizados, pero son difíciles de operar.

***

### 🎯 ¿Qué debería optimizar un emisor?

Si quitamos la mecánica, un emisor de RWA debe resolver tres cosas fundamentales:

1. **Que su activo sea realmente y eficientemente negociable**: cotizaciones ajustadas en cada activo, no solo en los tokens insignia.
2. **El mínimo capital posible** inmovilizado para lograrlo: el activo de cotización es caro; financiar diez reservas de USDT de forma exclusiva no es muy eficiente.
3. **No tener que gestionar una mesa de trading**: emitir activos sin necesidad de operar infraestructura de liquidez todos los días.

Entonces, la pregunta es si la liquidez puede estructurarse de otra manera, y eso es lo que el Shared Inventory Hook de PancakeSwap está diseñado para resolver.

***

### 🥞 Shared Inventory Hook (SIH)

**SIH es un hook de PancakeSwap Infinity que permite a un emisor de RWA respaldar muchos pares con una sola reserva compartida de USDT en lugar de una reserva exclusiva por par.**

SIH lo logra aportando liquidez just-in-time, lo que permite:

* Cotizaciones más profundas en los pares
* Menor impacto en el precio, especialmente en operaciones grandes
* Capital liberado para los emisores de RWA, ya que con menos capital desplegado se cotizan más pares

Veamos estas afirmaciones en la práctica.

Con el mismo snapshot del **2 de septiembre de 2026**, SIH mantiene **$635,028** de inventario en un solo hook, cotizando **11 pares** con **$180,467** de USDT compartido, con una utilización del **87.7%**. Con esto, SIH ha procesado **$3.56M en 17,299 transacciones.**

Es decir, **un saldo compartido de USDT de ~$700k cotizando ~11 pares frente a ~$745k cotizando solo 7 pares**.

El mismo trabajo, solo que diseñado para dejar de duplicar capital.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

Llevado a lo que le importa a los emisores:

* N saldos de USDT exclusivos tradicionalmente → ✅ una sola reserva compartida con SIH
* Emitido pero no negociable → ✅ negociable\
  El inventario compartido, inyectado just-in-time en torno al precio en vivo, permite que incluso los tokens sin libro de USDT en V3 puedan cotizarse, no solo emitirse.
* Operar una mesa → ✅ un operador con permisos\
  El emisor aporta el inventario; el hook y su operador se encargan de la cotización.

***

### 🔬 Prueba el simulador de Shared Inventory

Comprende cómo se comporta SIH con nuestra herramienta interactiva de comparación **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

Esta es una **comparación de alto nivel y normalizada** de SIH frente a un libro CLAMM tradicional: varios factores del mundo real se mantienen constantes en ambos lados para aislar con claridad la mecánica de eficiencia de capital. Es un modelo para entender, no un estado de resultados.

Tres pestañas:

* **Pestaña Simulator**: juega con el inventario, el ancho de banda y el flujo para ver cómo _se desempeñaría_ SIH frente a un pool CLAMM comparable en distintas condiciones.
* **Pestaña Comparison**: SIH frente a un libro **CLAMM de PancakeSwap V3** en los mismos pools, para que veas lado a lado la diferencia entre la reserva compartida de USDT y la exclusiva en capital comprometido y cobertura.
* **Pestaña Live data**: mide cómo está funcionando SIH _realmente_ ahora mismo, con datos de las consultas onchain que alimentan este estudio.

El simulador busca ayudar a demostrar cómo opera el Shared Inventory Hook. Pruébalo y luego compáralo con los resultados reales que publicaremos en las próximas semanas.

***

### 🧪 El experimento

Durante las **próximas semanas** ejecutaremos SIH en vivo y lo mediremos frente a las afirmaciones de eficiencia de capital anteriores, usando fuentes onchain. Cada semana compartiremos nuevos datos breves sobre el rendimiento de SIH y su arquitectura.

**Pares RWA en vivo en el estudio:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Nota: SNXXB, KORUB, SOXSB y DJTB no tienen ningún libro CLAMM tradicional._

**Publicaremos los resultados en las próximas semanas en el** [**Twitter**](https://x.com/PancakeSwap) **de PancakeSwap.**

Los resultados publicados cubrirán:

* **El conjunto completo de datos de rendimiento**: todos los datos de SIH de las próximas semanas, combinados en una sola imagen.
* **La cuestión de la asignación de capital**: cuánto capital ahorró realmente SIH a un emisor de RWA.
* **Aciertos / fallos**: dónde SIH superó las expectativas y dónde necesita mejorar.
* **El veredicto**: una conclusión fundamentada sobre qué tan eficaz es realmente SIH para la eficiencia de capital de RWA.

_Una nota sobre los datos: las cifras aquí provienen de consultas onchain en vivo y de datos públicos de pares, citados en el texto. Algunas comparaciones usan ventanas de tiempo distintas y las hemos señalado: el estudio está diseñado para medir en igualdad de condiciones, mientras que esta introducción solo pudo plantear la pregunta._

***

### ¿Quieres habilitar SIH en tus activos?

Si eres un emisor de RWA y estás cansado de financiar una reserva de USDT separada para cada pool que cotizas, esto es para ti.

Estamos incorporando emisores de RWA ahora. Rellena este formulario de Google y te guiaremos para que tu activo cotice en SIH - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

¡Gracias por leer! Síguenos en [X](https://x.com/PancakeSwap) para las últimas novedades y únete a la conversación en [Telegram](https://t.me/PancakeSwap) y [Discord](https://discord.gg/pancakeswap).

¡Manos a la obra!\
Los Chefs 🥞

***

_Aviso legal: este contenido es solo para fines informativos y educativos generales. No debe interpretarse como asesoramiento financiero, legal ni profesional de ningún tipo. Los precios de los activos digitales pueden ser volátiles. El valor de tu inversión puede subir o bajar._
