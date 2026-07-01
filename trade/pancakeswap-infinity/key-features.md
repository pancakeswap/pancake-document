# Características Principales

### 1️⃣ Singleton

En PancakeSwap v3, cada pool de liquidez tenía su propio contrato, lo que hacía más costoso crear pools e intercambiar entre múltiples pools.

Infinity soluciona esto implementando el modelo Singleton. Ahora, todos los pools viven dentro de un único contrato llamado PoolManager. Este cambio reduce los costos de gas de creación de pools hasta en un 99% y hace que los intercambios de múltiples saltos (intercambios que pasan por múltiples pools) sean mucho más económicos al evitar transferencias de tokens innecesarias.

#### ⚙️ **Cómo funciona:**

* Los datos de cada pool se almacenan en un contrato compartido usando un ID de pool único.
* Crear un nuevo pool ahora es simplemente una actualización de estado, no un despliegue completo de contrato.
* Intercambiar entre pools es más rápido y usa menos gas.<br>

Este enfoque Singleton, junto con otras optimizaciones como Flash Accounting y ERC-6909, ayuda a hacer de PancakeSwap Infinity una de las plataformas DEX más eficientes en gas disponibles hoy en día.

***

### ⚡️ Flash Accounting

Flash Accounting es una potente optimización en PancakeSwap Infinity que ayuda a reducir las comisiones de gas durante transacciones complejas como los intercambios de múltiples saltos y los cambios de liquidez.

En versiones anteriores (como v3), los tokens se movían hacia y desde cada pool en cada paso de una transacción. Esto generaba altos costos de gas, especialmente para los intercambios de múltiples saltos.

Con Flash Accounting, eso ya no es necesario. En lugar de mover tokens después de cada paso, PancakeSwap Infinity rastrea todos los movimientos de tokens internamente y solo realiza una transferencia final al final de toda la transacción. Esto ahorra mucho gas.

#### ⚙️ **Cómo Funciona:**

* Cuando interactúas con Infinity (p. ej., intercambiando o añadiendo liquidez), el sistema calcula el saldo neto de tokens que debes o recibes.
* Estos saldos netos de tokens se almacenan temporalmente usando Almacenamiento Transitorio, una nueva función introducida con la actualización Cancun de Ethereum (EIP-1153).
* El Almacenamiento Transitorio es más económico que el almacenamiento tradicional porque solo dura la duración de la transacción — no se necesita escritura o lectura permanente.

***

### 🪙 Soporte de Token Nativo

Con la introducción de la arquitectura Singleton y Flash Accounting, PancakeSwap Infinity ahora admite tokens de gas nativos (p. ej., BNB, ETH) directamente en los pools de liquidez — sin necesidad de envolver y desenvolver.

#### ✅ Puntos Destacados

* **Pools de Token Nativo Directos:** Ahora puedes crear pools como ETH/USDC, BNB/CAKE sin necesitar WETH o WBNB.
* **Eficiencia en Gas:** Las transferencias de tokens nativos son \~50% más económicas que las transferencias de tokens ERC-20, lo que lleva a menores costos de gas para intercambios y acciones de liquidez.<br>

**Previamente Eliminado, Ahora Rehabilitado:** El soporte de tokens nativos estaba ausente en versiones anteriores debido a la complejidad de implementación y la fragmentación de liquidez.

***

### 📈 Curvas de Precios Personalizadas

PancakeSwap Infinity le da a los desarrolladores el poder de crear modelos de precios personalizados para pools — yendo más allá del modelo tradicional usado en la mayoría de los AMMs.

{% hint style="success" %}
**Los desarrolladores pueden construir comportamientos de intercambio y modelos de liquidez completamente nuevos adaptados a tipos de activos o estrategias de trading específicas.**
{% endhint %}

#### 🔧 ¿Qué son las Curvas de Precios Personalizadas?

Las curvas de precios personalizadas permiten a los desarrolladores:

* Omitir la lógica nativa del gestor de pools, creando pools con comportamientos de intercambio definidos a medida.
* Alterar cómo se calculan los montos de tokens para intercambios o modificaciones de liquidez.
* Incorporar mecánicas de comisiones personalizadas, tales como:
  * Comisiones de retiro de liquidez
  * Descuentos o penalizaciones basados en estrategia

Todo esto es posible a través de callbacks de hooks antes / después del intercambio, que pueden interceptar y modificar los parámetros del intercambio dinámicamente.

#### 🛠 Ejemplos de Casos de Uso

* **Curvas StableSwap:** Diseñar curvas más planas alrededor de una relación de precios 1:1, reduciendo el impacto en el precio entre activos como USDC y USDT.
* **RWAs:** Crear comportamientos personalizados para diferentes tipos de activos con suministro dinámico.
* **Comisiones a Nivel de Hook:** Cobrar comisiones únicas que difieran de las comisiones a nivel de pool, como comisiones para desarrolladores.
* **Modelos de Riesgo Personalizados:** Ajustar los precios para reflejar la volatilidad, datos de oráculos u otras métricas externas.

{% hint style="info" %}
En versiones anteriores del AMM (p. ej., PancakeSwap v2/v3), la lógica de precios estaba codificada de forma rígida. La arquitectura de PancakeSwap Infinity desbloquea la capacidad de construir pools más eficientes en capital y adaptados.
{% endhint %}

#### 🔍 Flexibilidad para Desarrolladores

* Los desarrolladores pueden desplegar contratos de hooks personalizados para anular la lógica de precios.
* Los callbacks de hooks como `beforeSwap` y `afterSwap` permiten control total sobre cómo se calculan y aplican los deltas de tokens.

***

### 🧮 ERC-6909: Contabilidad Multi-Token Eficiente

PancakeSwap Infinity adopta [ERC-6909](https://eips.ethereum.org/EIPS/eip-6909), un estándar de tokens ligero y eficiente en gas diseñado para la contabilidad interna de múltiples tokens dentro de un único contrato. Reemplaza muchas operaciones ERC-20 tradicionales con primitivas de mint y burn — lo que lleva a un ahorro significativo de gas y flujos de transacción simplificados.

#### ⚙️ Cómo Funciona

En lugar de mover tokens hacia y desde el protocolo en cada interacción, los tokens ERC-6909 representan saldos internos:

* Mint: Cuando los usuarios depositan tokens o realizan un trade, pueden elegir recibir tokens ERC-6909 como reclamaciones.
* Burn: Más tarde, en lugar de transferir tokens ERC-20 nuevamente, los usuarios simplemente pueden quemar estos tokens ERC-6909 para liquidar saldos o financiar nuevas operaciones.

Este modelo reduce drásticamente la necesidad de transferencias externas de tokens, que generalmente incurren en mayores costos de gas e interactúan con lógica de terceros (p. ej., las comprobaciones de lista negra de USDC).

#### 🪙 Beneficios de ERC-6909

<table><thead><tr><th width="262.9921875">Característica</th><th width="497.7421875">Beneficio</th></tr></thead><tbody><tr><td>✅ Reclamaciones de Saldo Interno</td><td>No hay necesidad de transferir tokens repetidamente entre el usuario y el contrato</td></tr><tr><td>✅ Mint/Burn Eficiente en Gas</td><td>Sobrecarga constante independientemente del token, sin llamadas a contratos externos</td></tr><tr><td>✅ Más Simple que ERC-1155</td><td>Menor tamaño de código, sin callbacks, sin requisitos de transferencia por lotes</td></tr><tr><td>✅ Soporte Multi-Token</td><td>Un único contrato puede rastrear múltiples tipos de tokens con saldos aislados</td></tr><tr><td>✅ Integración Perfecta con PoolManager</td><td>Elimina las aprobaciones y transferencias ERC-20 redundantes</td></tr></tbody></table>

#### 🚀 Casos de Uso

* **Traders de alta frecuencia:** Evitar transferencias con alto costo en gas e interactuar directamente usando saldos internos.
* **Gestores de liquidez:** Abrir y cerrar posiciones de manera más eficiente sin movimientos excesivos de tokens.

#### 💡 Notas Clave

* Los usuarios se adhieren al flujo ERC-6909 cuando no necesitan liquidar inmediatamente las transferencias de tokens.
* Los saldos internos pueden consolidarse y liquidarse neto posteriormente, dando a los usuarios avanzados mayor control y flexibilidad.

***

### 💸 Método Donate

El método `donate()` permite a los usuarios incentivar directamente a los proveedores de liquidez activos dentro del rango de un pool donando tokens. Este método depende del sistema de contabilidad de comisiones del pool para facilitar los pagos, garantizando que solo se admitan los tokens del pool.

#### 🔹 Características Principales:

* **Pagos Directos a LPs:** Las donaciones se hacen directamente a los proveedores de liquidez, recompensando a quienes mantienen liquidez dentro del rango activo del pool.
* **Solo Admite Tokens del Pool:** El método `donate()` solo admite donaciones en los tokens del pool, ya que utiliza el sistema de contabilidad de comisiones para garantizar una distribución adecuada.
* **Abierto a Todos los Usuarios:** Cualquier usuario puede llamar al método `donate()`, permitiendo que cualquiera incentive la provisión de liquidez activa.

Aunque el método `donate()` es una herramienta poderosa para incentivar a los LPs, los donantes deben tener en cuenta que sus donaciones pueden ser objeto de frontrunning por otros usuarios. Esto puede ocurrir cuando un usuario añade rápidamente liquidez al pool justo antes de que se realice una donación, recibiendo una parte de los fondos donados.

Para prevenir el frontrunning, los donantes pueden necesitar considerar estrategias adicionales al diseñar sus mecanismos de donación, tales como:

* Asegurarse de que las donaciones se realicen de una manera que minimice la capacidad de frontrunning oportunista.
* Añadir retrasos de tiempo o condiciones específicas (usando callbacks de hooks before / after donate) que garanticen que las donaciones no estén siendo explotadas de esta manera.
