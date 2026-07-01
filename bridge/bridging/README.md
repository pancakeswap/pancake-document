---
description: Puentea CAKE entre Ethereum, BNB Chain, Aptos y muchas más
---

# 🌉 Puentear

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Puentear hacia/desde EVMs (Sitio nuevo): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Puentear hacia/desde Aptos (Puente V1): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## ¿Qué es puentear en cripto?

* Puentear en cripto se refiere al proceso de transferir activos entre diferentes redes blockchain.
* Mejora la interoperabilidad, permitiendo la transferencia de datos y activos a través de distintas redes.

\
Aquí hay algunas razones por las que quizás quieras puentear:

* Comprar diferentes tokens de criptomonedas
* Acuñar un NFT disponible solo en una red específica
* Ahorrar dinero con transacciones más económicas
* Usar una dapp disponible solo en otra red

***

## CAKE, un token multicadena

Con nuestra expansión y despliegue multicadena, CAKE es ahora un token multicadena nativo de BNB Chain, pero también disponible en Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB y Aptos.

CAKE en cualquiera de las otras cadenas equivale a CAKE en BNB Smart Chain. Siempre se puede puentear entre estas cadenas en una proporción 1:1 y sin ninguna comisión en CAKE.

**Por favor, ten en cuenta que solo existe un CAKE.** No hay versiones diferentes de CAKE en distintas cadenas. El suministro total de CAKE en todas las blockchains está limitado a 400M, tal como se describe en esta [propuesta de votación](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5).

***

## ¿Qué es el Puente de PancakeSwap?

El Puente de PancakeSwap es una herramienta conveniente dentro de la aplicación que te permite mover activos entre diferentes blockchains directamente desde la interfaz de PancakeSwap. En lugar de visitar sitios de puentes externos, puedes puentear tokens compatibles entre cadenas como BNB Chain, Ethereum, Base, Arbitrum y más, todo desde un solo lugar.

El Puente de PancakeSwap está impulsado por proveedores de terceros de confianza y funciona como un **agregador**, seleccionando la mejor ruta según precio, velocidad y fiabilidad.

Para aprender cómo puentear CAKE, consulta los tutoriales y la FAQ en las siguientes secciones.

***

## 🔗 Cómo funciona

### Puentear mediante agregadores

El Puente de PancakeSwap actúa como una capa inteligente sobre protocolos de puente de terceros de confianza. Cuando inicias una transferencia de puente, PancakeSwap:

* Verifica múltiples puentes integrados para encontrar rutas óptimas
* Envía tu transacción al proveedor seleccionado

Puentear no es custodial: tus activos no pasan por la custodia de PancakeSwap. Las transferencias son manejadas directamente por los proveedores del puente.

### Proveedores de puente compatibles

Actualmente integramos con:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Nota: Cada proveedor tiene diferentes mecánicas de puenteo, cadenas compatibles, comisiones y límites.

***

### Cadenas y tokens compatibles

#### Cadenas actualmente compatibles

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (sitio V1)

#### Tokens disponibles para puentear

Los tokens disponibles varían según la cadena y la ruta. Los tokens comunes compatibles incluyen (pero no se limitan a):

* CAKE
* USDT
* USDC
* ETH

***

#### Limitaciones y exclusiones

Algunos tokens pueden no estar disponibles debido a limitaciones del puente o restricciones de liquidez. Estos han sido filtrados para ofrecer la mejor experiencia de usuario. Por ejemplo:

**Para cBridge:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**Para deBridge:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_Lo anterior son ejemplos. Los tokens realmente disponibles por cadena se muestran directamente en la interfaz del Puente._

***

### 💸 Comisiones y costos

#### Comisiones del puente

* Las cobra el proveedor de puente subyacente
* Generalmente incluye una pequeña comisión por transferencia
* Se muestran claramente antes de que confirmes tu puente

***

#### Costos de gas

* Pagas comisiones de gas en la **cadena de origen** para iniciar la transacción
* Algunos proveedores también pueden requerir gas en la **cadena de destino**
* **Consejo:** Mantén siempre tokens nativos (p. ej., ETH, BNB) en ambos lados del puente

***

#### Montos mínimos y restricciones

Algunas rutas de puente exigen:

* **Montos mínimos/máximos de puente** (p. ej., mínimo de 10 USDC)
* **Decimales o formatos de token compatibles** (p. ej., solo tokens ERC-20)

La interfaz detectará y mostrará automáticamente las transferencias no válidas.

***

### ⏳ Tiempos de transacción y seguimiento

#### ¿Cuánto tiempo tarda puentear?

Las transferencias de puente suelen completarse en pocos **minutos**, dependiendo de:

* Las cadenas de origen y destino
* La congestión de la red
* La eficiencia del proveedor del puente

#### Seguimiento de tu transferencia

Una vez enviada, puedes ver el estado de la transacción a través de los exploradores específicos de cada proveedor:

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

Si una transacción está bloqueada por mucho tiempo, consulta el explorador correspondiente o comunícate con nuestros administradores a través de los [canales sociales](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) para obtener [ayuda](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help).

***

### 🧠 Consejos antes de puentear

* **Mantén tokens de gas en ambas cadenas** (p. ej., ETH + BNB)
* **Empieza con poco** si es tu primera vez puenteando
* Evita puentear durante períodos de alta actividad en la cadena (puede resultar en comisiones de gas más altas)
* Confirma la compatibilidad del token en ambas cadenas
* Siempre verifica dos veces las redes de origen y destino

***

### Adicional: Direcciones del Token Fungible Omnicadena (OFT) de CAKE

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
