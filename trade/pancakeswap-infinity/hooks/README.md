# Hooks

{% hint style="info" %}
Si eres desarrollador o buscas documentación técnica detallada sobre cómo desarrollar un hook, visita [aquí](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook).
{% endhint %}

Los hooks son complementos potentes que permiten a los desarrolladores extender y personalizar el comportamiento de los pools de liquidez en PancakeSwap Infinity. Piensa en ellos como "plugins" o "widgets" que añaden nuevas funciones a los pools de liquidez.

#### 🔍 ¿Qué son los Hooks?

* Los hooks son contratos inteligentes externos creados por cualquier persona — desarrolladores, protocolos o miembros de la comunidad — y adjuntados a los pools de liquidez para mejorar o modificar su comportamiento.
* Cada pool solo puede tener un hook adjunto, pero un único hook puede servir a muchos pools.
* Los hooks pueden ejecutar código personalizado antes o después de acciones clave como:
  * Inicializar un pool
  * Intercambiar
  * Añadir/eliminar liquidez
  * Donar<br>

**⛓️ Cómo Funcionan los Hooks:**

* Un hook se selecciona durante la creación del pool y no se puede cambiar posteriormente.
* Un contrato de hook se activa en acciones específicas (intercambio, añadir liquidez, etc.) y ejecuta lógica antes o después de esas acciones según se defina en el contrato.
* Por ejemplo, un hook podría:
  * Ofrecer descuentos en comisiones de intercambio a poseedores de CAKE
  * Cobrar comisiones personalizadas y distribuir recompensas
  * Habilitar nueva lógica de intercambio como stableswaps u órdenes estilo TWAMM<br>

#### ⚙️ Callbacks de Hooks

Los hooks pueden activarse durante diez momentos específicos. Los desarrolladores pueden elegir cuáles quieren implementar:

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

Esto permite implementar un comportamiento altamente personalizable y modular a través de los hooks.

#### 🔧 Dos Tipos de Hooks

**Tipo 1: Sin Autorización Necesaria**

Estos hooks se ejecutan automáticamente y no requieren permiso del usuario. Se activan por acciones como intercambios o cambios de liquidez.



Ejemplos:

* Comisiones Dinámicas: Ajustar las comisiones de intercambio según la volatilidad del mercado
* Descuentos de Comisiones: Dar descuentos a usuarios que tienen CAKE o que hacen trading de grandes volúmenes



Ejemplo de Flujo (Descuento de Comisiones por CAKE):

1. Un usuario inicia un intercambio.
2. El hook comprueba su saldo de CAKE mediante el callback `beforeSwap`.
3. Si el usuario tiene suficiente CAKE según los umbrales definidos, obtiene un 50% de descuento en las comisiones del pool.
4. El resto de la transacción continúa como de costumbre.<br>

{% hint style="success" %}
Estos hooks no necesitan una interfaz especial ni interacción adicional. Los beneficios se aplican automáticamente.
{% endhint %}

**Tipo 2: Autorización del Usuario Requerida**

Estos hooks necesitan que los usuarios interactúen directamente con ellos, proporcionen autorización y pueden requerir la transferencia de fondos, a menudo para crear o gestionar posiciones.



Ejemplos:

* Órdenes Limitadas: Ejecutar un intercambio solo cuando se alcanza el precio objetivo.
* TWAMM: Dividir órdenes grandes en piezas más pequeñas para una mejor ejecución.
* Gestión Activa de Liquidez: Gestionar automáticamente las posiciones LP para obtener rendimientos óptimos.



Ejemplo de Flujo (Hook de Orden Limitada):

1. El usuario interactúa directamente con el contrato de hook (no la interfaz de intercambio habitual).
2. Introduce detalles como el precio límite, el par de tokens y el monto.
3. El hook emite un token de recibo que representa la orden.
4. Más tarde, cuando el precio del pool alcanza el objetivo, el hook ejecuta la orden usando `afterSwap`.
5. El usuario puede devolver el token de recibo para reclamar los activos intercambiados.

{% hint style="info" %}
Estos hooks a menudo necesitan una interfaz personalizada y los usuarios deben confiar y aprobar el contrato de hook para que pueda custodiar sus fondos.
{% endhint %}

#### 🚀 Casos de Uso e Innovación

Los hooks desbloquean posibilidades ilimitadas, incluyendo:

* AMMs personalizados (p. ej., curvas de stablecoins)
* Recompensas de minería de liquidez
* Estrategias de trading automatizado, gestión de liquidez
* Órdenes limitadas en cadena, otros tipos de órdenes
* Ajustes dinámicos de precios y comisiones
* Estrategias LP de mejora de rendimiento<br>

Con los hooks, los desarrolladores pueden crear una experiencia DeFi completamente nueva utilizando la infraestructura existente de PancakeSwap Infinity — acelerando el desarrollo y reduciendo costos.
