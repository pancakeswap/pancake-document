# Shared Inventory Hook

El Shared Inventory Hook (SIH) oficial de PancakeSwap está diseñado para que un único pool de capital haga de creador de mercado en todos los pools que comparten sus tokens, en lugar de bloquear liquidez separada en cada uno. Ofrece a los traders cotizaciones más profundas y menor impacto en el precio, mientras permite a los proveedores de liquidez desplegar menos capital para la misma cobertura.

Creado por el equipo central de PancakeSwap, este hook está pensado para emisores de activos y creadores de mercado que quieren cotizar varios pares on-chain sin fragmentar su inventario.

#### 🔍 ¿Por qué Shared Inventory?

Proporcionar liquidez a varios pares de la forma convencional implica bloquear capital dedicado en pools separados, y la mayor parte permanece inactivo entre operaciones. En cambio, SIH mantiene un saldo por token y lo inyecta como liquidez solo cuando un intercambio lo necesita, de modo que el mismo capital puede respaldar todos los pools que comparten ese token.

#### 📊 ¿En qué se diferencia de otros modelos?

La liquidez concentrada convencional requiere comprometer todo el capital en un único pool. Otros enfoques entre pools, como las capas de liquidación con saldos virtuales, suelen situarse fuera del propio AMM, por lo que la liquidez puede no ser visible como profundidad de pool on-chain ni ser enrutada directamente por los agregadores.

La liquidez de SIH entra y sale del pool CLAMM de PancakeSwap Infinity mediante el hook en cada intercambio, por lo que aparece como profundidad de pool genuina que los routers pueden ver y con la que pueden ejecutar.

#### ⚙️ Cómo funciona

* **Inyección just-in-time (JIT)**\
  Antes de cada intercambio, el hook acuña en el pool una posición de liquidez concentrada configurada; después de ejecutarse el intercambio, la quema y liquida el resultado neto. La posición solo existe durante un intercambio, y el saldo queda libre para servir al siguiente pool que lo necesite.
* **Un saldo, muchos pools**\
  El inventario es el propio saldo de tokens del hook, no hay depósito por pool. Cualquier token que se vaya a usar en más de un pool se comparte entre todos ellos.

{% hint style="success" %}
Esto desacopla la profundidad que cotiza un pool del capital que mantiene directamente: un hook con fondos puede cotizar liquidez profunda y ajustada en varios pools que comparten un token.
{% endhint %}

* **Hook configurable**\
  Para cada pool al que sirve, el hook mantiene una configuración independiente y ajustable de rango de precios y profundidad. Mover la banda solo requiere una actualización de configuración, lo que facilita recentrar las cotizaciones en torno a un precio de referencia cambiante.

#### 📌 Puntos clave

* Un único saldo compartido de tokens respalda todos los pools que usan ese token. Añadir un nuevo pool no requiere capital nuevo.
* Totalmente on-chain y componible: la liquidez de SIH es profundidad real de pool, enrutable tanto por PancakeSwap como por agregadores de terceros.
* Los traders obtienen cotizaciones más profundas y menor impacto en el precio en operaciones grandes; los operadores ganan las mismas comisiones de trading con una fracción del capital convencional.
