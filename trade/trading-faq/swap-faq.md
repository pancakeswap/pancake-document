# FAQ de Intercambio

## Intercambio

### ¿Qué hay de nuevo en Exchange V3?

* Liquidez concentrada — la liquidez se concentrará en el rango de precios con más actividad de trading, lo que significa:
  * Menor deslizamiento de trading para los traders
  * Potencialmente más recompensas por comisiones LP para los proveedores de liquidez
* Una estructura de comisiones de trading flexible — los proveedores de liquidez pueden elegir entre múltiples niveles de comisiones de trading al crear pares de liquidez o proporcionar liquidez
* Rango de precios personalizable — los proveedores de liquidez también pueden elegir en qué rangos de precios quieren proporcionar liquidez
* Posiciones de liquidez no fungibles — cada posición de liquidez tendrá su propio ID único correspondiente a sus configuraciones (como el rango de precios). Por lo tanto, podrás crear y mantener múltiples posiciones con el mismo par de trading pero con diferentes configuraciones y cantidades de liquidez
* Compatible con versiones anteriores — Exchange v3 también utilizará los pares de liquidez heredados v2 y stable swap para siempre proporcionar la mejor ruta de trading
* Orden límite incorporada — los usuarios avanzados pueden utilizar el nuevo rango de precios personalizable en la provisión de liquidez para crear efectivamente una orden límite que convertirá todos los tokens al deseado cuando el precio alcance el objetivo



### ¿Puedo añadir mis propios tokens a Exchange V3?

Cualquiera puede crear pools de liquidez depositando liquidez en V3.

Sin embargo, los siguientes tokens NO están admitidos actualmente:

* Tokens con comisión en la transferencia
* Tokens de rebase

Para estos tokens, por favor NO añadas liquidez en Exchange V3. Tus activos pueden quedar atrapados en la posición de liquidez.



### **¿Por qué mi transacción no se procesa?**

PancakeSwap es una aplicación DeFi que interactúa con la billetera para completar transacciones en cadena para intercambios, creación de LPs, Staking en granjas y pools, etc.

**Comisiones de Gas**

Por lo tanto, lo primero es **asegurarte de tener suficiente BNB para pagar la comisión de gas** de las transacciones en cadena. Normalmente, las comisiones de gas fluctúan dependiendo del número de transacciones en cola; si hay más transacciones, puede ser necesaria una comisión de gas más alta para procesar la transacción. En BNB Smart Chain, las comisiones de gas típicamente oscilan entre céntimos y un dólar USD en BNB. Aprende más sobre las [comisiones de gas aquí](https://academy.binance.com/en/glossary/gas).

**Comisiones de Transacción**

Si tu acción de intercambio todavía no se procesa y muestra un error para revisar el deslizamiento — puede que quieras verificar si los tokens que intentas intercambiar tienen **alguna comisión y restricción en las transacciones**.

No es raro que los tokens en BNB Smart Chain incluyan una **comisión de transacción** en sus contratos; usualmente estas comisiones podrían usarse para quema, financiar el tesoro de un proyecto de lanzamiento justo — por ejemplo, este [token APX tiene un impuesto del 1% en cada transacción](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) para enviar a una dirección de quema, de modo que más transacciones significarían más quema, acumulando valor para los poseedores del token APX.

Con la comisión de transacción, ya sea inclusiva (una parte del importe del intercambio se envía a otro lugar que no sea tu dirección, por lo que la salida es menor de lo esperado para la entrada estimada) o exclusiva (requiriendo una transferencia adicional desde tu dirección para enviar tokens extra, por lo que la entrada es mayor de lo esperado para la salida estimada), afecta a los importes de entrada y salida que aceptas al firmar la transacción. En muchos casos, la transacción no puede cumplir los requisitos de entrada y salida debido al impuesto.

**Intercambio con Comisiones de Transacción**

Antes de intercambiar cualquier token, asegúrate de haber visitado su sitio web para entender si tienen un mecanismo de comisión de transacción (o _impuesto_ como muchos proyectos lo llaman). Si lo hay, asegúrate de establecer un deslizamiento que sea suficiente para acomodar la comisión de transacción — p. ej., si hay una comisión de transacción del 5%, tu deslizamiento tendrá que establecerse al menos al 5% más el deslizamiento de trading normal dependiendo de tu importe de trading y la liquidez del token, digamos 5,5%-6%.

En algunos casos extremos incluyendo algunas estafas, algunos tokens incluso tienen un bloqueo en la mayoría o todas las transferencias en cadena, o solo permiten que ciertas direcciones vendan; en tal caso es imposible intercambiar el token con éxito. ¡Aprende sobre el token que intentas intercambiar y sé consciente de cualquier comisión y restricción!



### ¿La nueva interfaz de Intercambio usa liquidez v2 o stable swap?

Sí. El nuevo Swap v3 usa liquidez de PancakeSwap v3, v2 y stable swap para obtener la mejor ruta de trading.



### ¿Qué es el enrutamiento dividido?

En Swap v3, tu operación puede dividirse en múltiples rutas para ejecutar tu operación con la mejor tasa.

Para ver más detalles sobre cómo se enruta tu operación, toca el botón "v" en la sección "Ruta" para expandir y ver los detalles.

Aprende más [aquí](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences).



### ¿Cómo personalizar o deshabilitar ciertas fuentes de liquidez?

El nuevo Swap v3 usa liquidez de PancakeSwap v3, v2 y stable swap para obtener la mejor ruta de trading. Sin embargo, puedes personalizar o deshabilitar ciertas fuentes de liquidez si no quieres que tu operación se enrute a través de ellas.

Al ver una ruta de trading, haz clic en el botón "Personalizar Enrutamiento". O haz clic en el botón de engranaje ⚙️ en la esquina superior derecha de la interfaz de Intercambio y elige "Personalizar Enrutamiento".

Dentro de la ventana emergente "Personalizar Enrutamiento", puedes elegir qué fuente de liquidez quieres utilizar. O deshabilitar los multisaltos completamente.

Nota: deshabilitar los multisaltos podría llevar a un mayor deslizamiento o peor tasa de trading en pares de trading específicos. Procede con precaución.

Aprende más [aquí](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources).



## Liquidez

### ¿Qué son los niveles de comisiones y cómo elegir el correcto?

En Exchange v3, al proporcionar liquidez, puedes elegir entre varias comisiones de trading diferentes (0,01%, 0,05%, 0,25% y 1%) para el mismo par de tokens.

Por ejemplo, para CAKE-BNB, podría haber un par de 0,25%, lo que significa que se aplica una comisión de trading del 0,25% en cada operación. Sin embargo, algunos proveedores de liquidez podrían elegir proporcionar liquidez a un par de trading CAKE-BNB con una tasa de comisión del 0,05%, ofreciendo una mejor cotización y atrayendo más volumen de trading.

No hay una respuesta "correcta" sobre qué configuración de comisión de trading elegir. Depende de los tokens dentro del par de trading. Normalmente, los tokens volátiles deberían tener una comisión de trading más alta para compensar mejor la pérdida impermanente provocada por la volatilidad. Por otro lado, los tokens como las stablecoins tienen movimientos de precios más pequeños y menores pérdidas impermanentes, por lo tanto su comisión de trading debería ser más baja.

Al seleccionar un par de tokens, la interfaz "Añadir Liquidez" elegirá automáticamente el nivel de comisión más popular para ti.



### ¿Por qué mis dos tokens de depósito no son iguales en valor USD?

En Exchange V3, los activos subyacentes en una posición de liquidez no siempre tendrán un valor igual en USD. Dependerá de la configuración del rango de precios de una posición y el precio actual del par.

De hecho, si tu posición sale del rango, todos los tokens se convertirán a un único activo. Además, puedes proporcionar liquidez a un rango de precios que no cubra el precio actual y depositar solo un único activo. Continúa leyendo para obtener más información ⬇️



### ¿Qué ocurre si mi posición de liquidez sale del rango?

No ganarás ninguna recompensa por comisiones de trading si el precio actual sale del rango de precios definido en tu posición.

Además de eso, todos los tokens se convertirán a un único activo dependiendo de la dirección de la condición del precio.

Por ejemplo, si una posición de CAKE/BUSD está configurada con un rango de precios de 3 BUSD por CAKE a 5 BUSD por CAKE. Y todos los activos en la posición se convertirán a BUSD si el precio de CAKE es mayor o igual a 5 BUSD por CAKE, y viceversa.

Ten en cuenta que si el precio vuelve al rango, comenzarás a recibir recompensas por comisiones de trading de nuevo. No se requieren acciones adicionales.



### ¿Es mejor siempre proporcionar liquidez con un rango más pequeño?

Proporcionar liquidez a un rango de precios más pequeño ayudará a concentrar tu liquidez en un rango de precios específico, impulsando tus participaciones relativas frente a la liquidez total dentro del rango de precios, potencialmente ganando más recompensas por comisiones de trading.

Sin embargo, ten en cuenta que solo las posiciones de liquidez activas ganarán recompensas por comisiones de trading de las operaciones. Esto significa que solo ganarás recompensas cuando el precio de trading actual esté dentro del rango de precios definido en la posición de liquidez.



### ¿Hay alguna forma de ajustar automáticamente mi posición para que siempre esté en rango y ganando recompensas por comisiones?

PancakeSwap v3 admite depósito de liquidez con un clic a través de Zap, disponible en BNB Chain y Ethereum.



### ¿Cuál será el desglose de comisiones de trading para Exchange v3?

|                       | 0,01% | 0,05% | 0,25% | 1%  |
| --------------------- | ----- | ----- | ----- | --- |
| Proveedor de Liquidez | 67%   | 66%   | 68%   | 68% |
| Quema CAKE            | 15%   | 15%   | 23%   | 23% |
| Tesoro                | 18%   | 19%   | 9%    | 9%  |

### ¿Las recompensas por comisiones LP se acumulan automáticamente como en Exchange v2?

No.

En Exchange v3 necesitarás reclamar las recompensas por comisiones de trading manualmente. Puedes hacerlo en la página de detalles de la posición. Puedes encontrar todas tus posiciones de liquidez v3 en la página de liquidez.



### ¿Qué afecta el APR de LP?

En Exchange v3, el APR de recompensas por comisiones LP puede variar entre posiciones de liquidez. Se basa en los siguientes factores:

* Volumen de trading\
  \- más volumen genera más recompensas por comisiones
* Nivel de comisiones del par de liquidez\
  \- un nivel de comisión más alto genera más recompensas por comisiones de operaciones individuales
* El número de tokens depositados\
  \- más tokens en la posición se traduce en una mayor participación relativa frente a la liquidez activa total, lo que obtiene más recompensas por comisiones de trading de las operaciones
* El rango de precios seleccionado\
  \- un rango de precios más pequeño permite una mayor concentración para la misma cantidad de tokens depositados, lo que se traduce en una mayor participación relativa frente a la liquidez activa total, y obtiene más recompensas por comisiones de trading de las operaciones
* La cantidad de liquidez actualmente activa\
  \- si hay más usuarios que depositan y concentran su liquidez con el mismo rango que tú, ganarás menos comisiones de trading debido a una menor participación relativa frente al total
* Si la posición de liquidez está activa\
  \- solo las posiciones de liquidez activas ganarán recompensas por comisiones de trading



### ¿Puedo proporcionar liquidez v2?

Proporcionar liquidez v2 ya no es aconsejable. Recomendamos usar liquidez v3 para aprovechar las nuevas características para mejorar la eficiencia.

Si quieres continuar añadiendo liquidez v2:

* Si el par de tokens no tiene un pool v3, o tiene más liquidez en v2 que el pool más grande en v3, aparecerá "Añadir Liquidez V2". Simplemente haz clic para cambiar a añadir liquidez v2
* Alternativamente, usa `/v2` en la URL para siempre usar la provisión de liquidez v2



### ¿Por qué no puedo añadir liquidez a un par que acabo de crear?

Debido a un error del Exchange V2 heredado (presente en cada bifurcación de UniSwap V2), no podrás añadir liquidez a un par usando la interfaz de liquidez normal de PancakeSwap y sus llamadas de contrato si un par es:

* Creado llamando a `createPair` en FactoryV2 sin depositar liquidez inicial y acuñar los tokens LP iniciales
* Luego, uno de los tokens en el par fue transferido manualmente al contrato del pool mientras se llama a `sync`

{% hint style="info" %}
Recientemente, se ha observado un mayor número de estos ataques en PancakeSwap Exchange V2 en BNB Chain.&#x20;

Recomendamos encarecidamente usar nuestra interfaz para crear el par de trading para tu token añadiendo la liquidez inicial con la creación del par.
{% endhint %}

Mientras el equipo trabaja arduamente en una solución para resolver este problema, aquí hay una guía paso a paso para resolverlo usando BscScan:

#### Localiza la dirección del pool y su página en BscScan

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

Si tu par está afectado, verás el enlace a la página de BscScan para el par de trading/pool en el aviso de error.

Alternativamente, puedes ir a Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)), ir a "Leer Contrato", "6. getPair", ingresar la dirección de los dos tokens en tu par de trading y hacer clic en "Consultar". Deberías ver la dirección del par en el campo de retorno.

#### Verifica qué token fue depositado y transfiere el otro token al par manualmente

![](<https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png>)

Del campo de saldo de token en BscScan, puedes verificar qué token fue depositado en el pool. Normalmente debería ser el token emparejado. (Como WBNB, USDT, etc...)

Una vez confirmado, debes transferir manualmente el otro activo al contrato del pool. Puedes hacerlo en la aplicación de billetera que prefieras ingresando la dirección del pool como receptor.

Puedes transferir cualquier importe, pero dado que esto es efectivamente "donar" activos a un pool, estarás transfiriendo tus activos a una liquidez sin acuñar tokens de liquidez. Por lo tanto recomendamos mantener este importe al mínimo.

{% hint style="warning" %}
IMPORTANTE: Una vez que hayas transferido el token, debes llamar a `sync()` inmediatamente en el pool.
{% endhint %}

Puedes hacerlo yendo a la página de BscScan para el par de trading, yendo a "Escribir Contrato", "8. Sync", y haciendo clic en el botón "Escribir". Necesitarás conectar tu billetera antes de realizar la transacción.

Una vez confirmada la transacción, puedes añadir la liquidez subsiguiente en la interfaz de PancakeSwap.

#### ¿Qué pasa si quiero definir el precio de lanzamiento?

Debes ajustar el pool al precio de lanzamiento mientras transfieres el token y corriges el pool.

El importe a transferir puede calcularse usando:

* `tokenInside`: el token que ya fue transferido al pool. Normalmente debería ser el token emparejado. (Como WBNB, USDT, etc...)
* `tokenToSend`: el token que está a punto de enviarse al pool. Normalmente debería ser tu token de proyecto
* `tokenInside.price`: el precio USD de tokenInside
* `tokenToSend.price`: el precio USD de tokenToSend (el precio de lanzamiento)
* `pool`: el pool V2

Con la siguiente fórmula:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

Si el resultado es menor que 0 (generalmente ocurre cuando el precio de lanzamiento es muy grande, puede que necesites depositar primero más `tokenInside` en el pool)



### ¿Cómo gestionar LP estable y LP v2 heredado?

Puedes gestionarlos como de costumbre yendo a la página de [Liquidez](https://pancakeswap.finance/liquidity).



### ¿Por qué necesito restablecer la aprobación en USDT antes de habilitar/aprobar?

Al operar en la red principal de Ethereum, el token USDT sigue una lógica diferente para gestionar las aprobaciones y la asignación de tokens.&#x20;

Por lo tanto, cuando las asignaciones de gasto son demasiado bajas, se requiere restablecer la aprobación antes de establecer una nueva.
