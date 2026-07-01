# Infinity CLAMM y LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

CLAMM permite a los proveedores de liquidez asignar su capital dentro de **rangos de precio específicos**. Esto lleva a:

* **Mayor eficiencia de capital**: Más liquidez a los precios de trading activos.
* **Liquidez más profunda**: Mejor ejecución para los traders.
* **Gestión activa de LP**: Los LPs necesitan ajustar sus posiciones a medida que los precios se mueven.
* Mayor potencial de **pérdida impermanente** para las posiciones fuera del rango.

{% hint style="info" %}
CLAMM opera bajo la fórmula de producto constante (X \* Y = K). Cada posición de liquidez es no fungible y está representada como un NFT.
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM o "Pool de Bins")

LBAMM implementa **bins de precio discretos**, cada uno con liquidez a un nivel de precio específico. LBAMM sigue la **fórmula de suma constante (X + Y = K).**



**Características principales:**

* Trades con **0 impacto en el precio** dentro de un bin.
* **Liquidez fungible** (la liquidez dentro de cada bin es un token ERC-20).
* **Menores costos de gas** para ajustar posiciones LP.
* **Soporte para diferentes formas de liquidez** (p. ej., sesgada, uniforme).
* Más adecuado para pares de **baja volatilidad** debido a la curva de precios plana por bin.

> 🥞 **PancakeSwap es el primer protocolo en ofrecer pools LBAMM con hooks.**

{% hint style="success" %}
Tanto los pools CLAMM como LBAMM admiten **hooks**, que permiten a los desarrolladores personalizar el comportamiento del pool. Los tipos de pool son extensibles mediante nuevos Pool Managers, que pueden añadirse sin redespliegue del protocolo.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Característica</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Curva de Precios</strong></td><td>Producto Constante (X * Y = K)</td><td>Suma Constante (X + Y = K)</td></tr><tr><td><strong>Token de Liquidez</strong></td><td>No fungible (NFT)</td><td>Fungible (ERC-20 por bin)</td></tr><tr><td><strong>Mejor Para</strong></td><td>Pares de alta y baja volatilidad</td><td>Pares de baja volatilidad</td></tr><tr><td><strong>Ventajas</strong></td><td><ol><li>Eficiencia de capital</li><li>Eficiente en gas en rango amplio/completo</li><li>Ampliamente adoptado</li></ol></td><td><ol><li>0 impacto en el precio dentro del bin</li><li>Gestión LP más económica</li><li>Formas de liquidez flexibles</li></ol></td></tr><tr><td><strong>Soporte de Hooks</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Comisiones

PancakeSwap Infinity admite un sistema de comisiones flexible y extensible mediante configuraciones de comisiones Estáticas y Dinámicas. Esta configuración le proporciona tanto a los creadores de pools como a los LPs herramientas poderosas para optimizar según diferentes estrategias de trading y perfiles de riesgo.

#### 🔁 Comisiones Dinámicas

* Las Comisiones Dinámicas se determinan en tiempo real a través de contratos de hooks.
* Estas comisiones pueden fluctuar según factores externos como la volatilidad, el volumen de trading, el estado del usuario (p. ej., tenencias de CAKE) u cualquier lógica personalizada codificada en el hook.
* Los pools con comisiones dinámicas deben habilitar la configuración al momento de la creación del pool y adjuntar un hook capaz de modificar las comisiones mediante `beforeSwap`.
* Una vez que se inicializa un pool, el tipo de comisión (dinámica o estática) es inmutable.

Las comisiones dinámicas ofrecen máxima flexibilidad y optimizan las estructuras de comisiones tanto para LPs como para los que intercambian según las condiciones del mercado.

#### 📌 Comisiones Estáticas

* Los pools de Comisión Estática tienen una comisión fija establecida durante la creación del pool.
* Estas comisiones no pueden cambiarse después de que el pool esté inicializado.
* Adecuadas para casos de uso más simples o donde es importante la previsibilidad de la estructura de comisiones.<br>

**🔒 Límites Máximos de Comisión:**

* Pools CLAMM: Hasta el 100% (principalmente para casos de uso especializados o experimentales)
* Pools LBAMM: Limitado al 10%<br>

**🏛 Comisión de Protocolo (para pools de comisión estática):**

* PancakeSwap aplica una comisión de protocolo en los pools de Infinity
* 33% de la comisión LP, limitada al 0,4%

| **Comisión LP**        | **Comisión de Protocolo** |
| ---------------------- | ------------------------- |
| 1%                     | 0,33%                     |
| 2%                     | 0,4% (limitada)           |
| Pool de Comisión Dinámica | 0%                     |

#### 🛠️ Notas de Configuración para Creadores de Pools

* Al inicializar un pool mediante PoolManager, el creador debe elegir:
  * Si el pool usa una comisión estática o dinámica
  * Si se adjunta un contrato de hook (requerido para comisiones dinámicas)

Estas configuraciones son permanentes y definen cómo se comporta el pool durante toda su vida útil.
