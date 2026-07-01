# 🔀 Intercambios Multicadena

Los intercambios multicadena permiten a los usuarios intercambiar tokens entre cadenas de forma fluida — todo en una sola transacción optimizada.

Los intercambios multicadena están disponibles entre:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**Las transacciones son extremadamente rápidas — normalmente se completan en segundos o en menos de un minuto.**
{% endhint %}

***

### 🔍 Cómo Funciona

1. El usuario selecciona la cadena y el token de origen y destino
2. El router de PancakeSwap calcula la ruta más eficiente
3. Los intercambios se ejecutan usando los pools de liquidez de PancakeSwap (v2, v3, Infinity, StableSwaps) en las cadenas de origen y destino
4. El puenteo se gestiona a través de nuestros protocolos asociados: [Across](https://across.to/) (para EVM <> EVM), [Relay](https://relay.link/bridge) (para SOL <> EVM)

{% hint style="success" %}
**Los intercambios multicadena están disponibles para cualquier token con liquidez suficiente tanto en la cadena de origen como en la de destino.**
{% endhint %}

***

### 💸 Comisiones

* **PancakeSwap no cobra ninguna comisión por las transacciones multicadena.**
* Las comisiones se componen de:
  1. **Comisión de Trading:** Se genera por los intercambios dentro de los pools de liquidez en las cadenas de origen y destino
  2. **Comisión de Puente:** Se paga a los relayers por el puenteo de activos

***

### 🎯 ¿Qué son los Intents?

Los intents permiten a los usuarios definir el resultado deseado sin preocuparse por cómo se consigue.

Ejemplos de Intents:

* "Intercambiar 1 ETH en Base por al menos 3000 USDC en Arbitrum"

Sin intents, un usuario tendría que hacer manualmente:

* Puentear ETH a Arbitrum
* Encontrar un DEX con el mejor precio ETH → USDC

{% hint style="success" %}
**Con los intents — el sistema lo gestiona todo automáticamente.**
{% endhint %}

**Ventajas del diseño basado en intents:**

* UX fluida
* Tiempos de transacción más rápidos
* Transacciones únicas con un solo clic

***

### 🔐 Auditorías

Hemos realizado múltiples rondas de auditoría con nombres reconocidos en el ámbito de la seguridad multicadena:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
