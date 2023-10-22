# Cómo usar Farms

![](../../.gitbook/assets/como-yield-farms.png)

Hacer Yield Farming en Farms es una excelente manera de ganar recompensas en Cake dentro de PancakeSwap.

A diferencia de los Syrup Pools, el Farming requiere que deposites **dos tokens** para conseguir LP Tokens, que luego colocarás en el Farm para ganar recompensas. ¡Esto te permite ganar CAKE mientras mantienes posición en tus otros tokens!

{% hint style="warning" %}
El Yield farming puede dar mejores recompensas que los Syrup Pools, pero viene con un riesgo de **Impermanent Loss**. No es tan aterrador como parece, pero vale la pena aprender sobre el concepto antes de comenzar.

Echa un vistazo a este gran [artículo sobre Impermanent Loss de Binance Academy](https://academy.binance.com/es/articles/impermanent-loss-explained) para obtener más información.
{% endhint %}

## Farm V3

### **Preparación**

![](<../../.gitbook/assets/image (1) (1) (3).png>)

Necesitarás una posición de liquidez para colocarla en un Farm. Los Farms sólo aceptan posiciones de liquidez de su par de trading exacto, con el exacto tier de fee; por ejemplo, el Farm CAKE-BNB 0.25% sólo aceptará las posiciones de liquidez de CAKE-BNB con el tier de fee seleccionado en 0.25%. No aceptará:

* Otros pares, como CAKE-BUSD
* El mismo par pero con otro tier de fee, como CAKE-BNB con un tier de 0.05%

Para crear la posición LP exacta, necesitarás aportar liquidez de ese par de trading con el tier de fee correcto. Es decir que para tener una posición LP de CAKE-BNB 0.25%, primero deberás aportar liquidez al par CAKE-BNB seleccionando el tier de fee en 0.25%.

Puede sonar intimidante, pero no es tan complicado. Vayamos paso a paso.



### **Determinar tu Farm**

![](<../../.gitbook/assets/image (2) (1) (1) (3).png>)

Antes de proceder, deberás elegir el Farm correcto para ti. Before you proceed, you'll want to choose a Farm that's right for you. [Visita la sección de Farms](https://pancakeswap.finance/farms) para ver la lista de los Farms disponibles.

Puedes elegir cualquier filtro para ordenar los Farms, como por APR, para ver los que tienen mejor rendimiento al momento. Ten en cuenta que los APRs se calculan de manera general para posiciones individuales; puede variar dependiendo el rango de precios que se configure.

Cuando eencuentres un Farm que quieras usar, anota el par y su porcentaje de fee, por ej. BNB-CAKE y 0.25%, para recordarlo luego.



### **Aportar liquidez para crear una posición**

Una vez decidido el Farm para invertir, necesitas aportar liquidez:

1 - Si no tienes una posición disponible, verás el botón “Add Liquidity” (Agregar Liquidez), simplemente haz clic para abrir la ventana para hacerlo, sin salir de la página de Farms.

![](<../../.gitbook/assets/image (7) (6) (1).png>)

2 - Otra manera de hacerlo, es con clic en la columna del Farm que elijas de la lista. Se abrirá para mostrar más detalles. O en la vista por tarjetas, clic en "Detalles" para abrir la ventana con los mismos. Luego clic en el link de “Add XXX-YYY LP” dentro de la sección detalles, para agregar liquidez.

![](<../../.gitbook/assets/image (8) (5).png>)



### **Deposita tus posiciones en un farm**

![](<../../.gitbook/assets/image (5) (4).png>)

Luego de aportar liquidez, deberías ver tu posición listada debajo del farm que quieres usar.

Si tienes varias posiciones, puedes hacer clic en “View All” (ver todo) para verlas en una nueva ventana emergente.

![](<../../.gitbook/assets/image (2) (1) (1).png>)![](<../../.gitbook/assets/image (9) (3).png>)

Clic en “Stake” en la posición listada, y tu wallet te pedirá confirmaciónon.

![](<../../.gitbook/assets/image (6) (6) (1).png>)

Un momento después, la ventana se cerrará, y verás tu posición depositada en los detalles.

Puedes repetir los pasos mencionados para depositar múltiples posiciones rápidamente con diferentes configuraciones de rango de precios. Cada posición pagará en CAKE y debe ser cosechada de manera separada.



### **Cosechar las recompensas de farming**

En Farm V3, puedes depositar varias posiciones en el mismo farm.you can stake multiple positions on the same farm. Cada posición pagará en CAKE y debe ser cosechada de manera separada.

![](<../../.gitbook/assets/image (7).png>)

Para cosechar las recompensas en CAKE de una posición depositada, simplemente regresa a la página de Farms, y encuentra el farm y posición del que quieres cosechar. Puedes usar la opción de “Staked Only” para filtrar rápidamente los farms en los que estás participando.

Si tienes varias posiciones depositadas, puedes hacer clic en “View All” para verlas en una nueva ventana emergente.

![](<../../.gitbook/assets/image (3) (1).png>)

Clic en “Harvest” en la posición, y tu wallet te pedirá confirmación. Un momento después, las recompensas en CAKE serán enviadas a tu wallet.



### **Agregar o remover liquidez que está depositada en un Farm**

Aún estando depositada en un farm, puedes agregar o retirar liquidez sin necesidad de retirar la posición.

![](<../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png>)

Para hacerlo, simplemente regresa a la página de Farms, y encuentra el farm y posición que quieres ajustar. Puedes usar la opción de “Staked Only” para filtrar rápidamente los farms en los que estás participando.

![](<../../.gitbook/assets/image (4) (1).png>)

Haz clic en la posición con el par, % de fee, ID de posición y la flecha  “>”. Eso te llevará a la página de detalles de la posición.

Simplemente usa los botones “Add” o “Remove” (Añadir o Remover) para ajustar la liquidez en la posición depositada.

Ten en cuenta que todos los CAKE por reclamar serán cosechados y enviados a tu wallet al momento de ajustar una posición.



### **Retiro de tus posiciones de un Farm**

Puedes retirar tu posición en cualquier momento.

Para hacerlo, simplemente regresa a la página de Farms, y encuentra el farm y posición que quieres retirar. Puedes usar la opción de “Staked Only” para filtrar rápidamente los farms en los que estás participando.

Si tienes varias posiciones depositadas, puedes hacer clic en “View All” para verlas en una nueva ventana emergente.

Haz clic en “Unstake” en la posición, y tu wallet te pedirá confirmación. Enseguida, tu NFT de la posición retornará a tu wallet, junto con todas las recopensas pendientes en CAKE.

## Farm V2

## Preparación <a href="#getting-prepared" id="getting-prepared"></a>

El Yield Farming requiere un poco de trabajo para configurarse.

Vas a necesitar algunos "Tokens LP" para entrar en un Farm. Los Farms solo pueden aceptar su propio token LP exacto; por ejemplo, el farm CAKE-BNB solo aceptará tokens LP CAKE-BNB.

Para obtener el token LP exacto, deberá proporcionar liquidez para ese par. Por lo tanto, para obtener tokens LP CAKE-BNB, primero tendrá que proporcionar liquidez para el par CAKE-BNB.

Puede sonar intimidante, pero no es demasiado complicado. Vamos a ir paso a paso.

### Encontrando tu Farm <a href="#finding-your-farm" id="finding-your-farm"></a>

Antes de continuar, querrá elegir un Farm adecuado para usted. [Visite la página de Farms](https://pancakeswap.finance/farms) y verá una lista de Farms disponibles.

<div align="left">

<figure><img src="../../.gitbook/assets/image (4) (1) (2).png" alt="" width="362"><figcaption></figcaption></figure>

</div>

CAKE-BNB y BUSD-BNB están anclados a la parte superior de la lista con la clasificación **Hot (**predeterminada). Después de los Farms anclados, Hot mostrará otros Farms en orden de qué tan nuevos son.

Puedes elegir otra opción de clasificación si lo deseas, como por APR para los Farms con la tasa de recompensa más alta actualmente.

### Proveer liquidez para obtener LP Tokens <a href="#providing-liquidity-to-get-lp-tokens" id="providing-liquidity-to-get-lp-tokens"></a>

Ahora que ha encontrado un Farm, deberás agregar liquidez para obtener tus tokens LP.

1. Haga clic en la fila del Farm que ha elegido de la lista. Se abrirá para mostrar más detalles.
2. A la izquierda, verás algunos enlaces. Haz clic en la parte de **Get (your pair) LP** link.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-Ma7L32Nr0z6VnrNnAQW%2F-Ma7UI8WPxQFNL1V\_zAZ%2Fimage.png?alt=media\&token=137ec648-a7e3-44cc-ab9d-0fbaebecdb5c)

Esto abrirá la página de Add Liquidity para agregar liquidez para el par elegido.&#x20;

Tenemos una [guía para agregar liquidez](../pancakeswap-exchange/anadir-remover-liquidez.md) que puede seguir para obtener sus tokens LP.

## Poniendo los LP Tokens dentro de un Farm <a href="#putting-your-lp-tokens-into-a-farm" id="putting-your-lp-tokens-into-a-farm"></a>

Ahora que tienes tus tokens LP, ¡estás listo para comenzar a depositarlos en un Farm y ganar recompensas!

### &#x20;<a href="#putting-your-lp-tokens-into-the-farm" id="putting-your-lp-tokens-into-the-farm"></a>

1 - Vuelva a la página de [Farms ](https://pancakeswap.finance/farms)y localice la suya. Haz clic en cualquier parte de la fila que muestre a tu par. Se expandirá para mostrar más detalles.

![](<../../.gitbook/assets/image (7) (5) (1).png>)

Cuando esté listo, haga clic en el botón **Enable** y confirme su acción en su billetera.

2 - Después de una breve espera, el botón Enable cambiará a **Stake LP.** Haga clic en él y aparecerá una nueva ventana.

![](<../../.gitbook/assets/image (5) (4) (1).png>)

3 - Escriba la cantidad de tokens LP con los que desea ingresar al Farm, o simplemente haga clic en **Max** para usar todos sus tokens LP.

![](<../../.gitbook/assets/image (2) (4).png>)

4 - Cuando haya introducido la cantidad, el botón **Confirm** se iluminará. Haga clic en él. Su billetera le pedirá que confirme su acción.

5 - Después de una breve espera, la ventana se cerrará, y verá su nuevo saldo de LP tokens depositado en los detalles.

![](<../../.gitbook/assets/image (3) (1) (2).png>)

{% hint style="info" %}
Cuando esté farmeando un una red diferente a BNB Chain, deberá esperar unos 30 minutos para que se confirmen las transacciones cross-chain.

![](<../../.gitbook/assets/image (2) (2).png>)

Para monitorear el progreso de una transacción cross-chain, clic en el ícono circular junto a su balance, o revise la sección de "transacciones recientes" en la esquina superior derecha.
{% endhint %}

{% hint style="warning" %}
Cuando esté farmeando un una red diferente a BNB Chain por primera vez, necesitará una pequeña cantidad del token nativo (por ejemplo, ETH para Ethereum) para la primera configuración. Así que la primera transacción siempre tendrá un costo un poquito mayor.
{% endhint %}

## Añadir o Remover LP Tokens de un Farm <a href="#adding-or-removing-lp-tokens-from-a-farm" id="adding-or-removing-lp-tokens-from-a-farm"></a>

Puede decidir que desea agregar más tokens LP a un Farm en una fecha posterior, o remover sus LP. Puedes hacer esto muy fácilmente cuando quieras.

1 - Vuelva a la página de [Farms](https://pancakeswap.finance/farms). En la parte de arriba de la web verás el botón **Staked only** . Haz clic ahí

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-Ma3HempyvangCy4COPO%2F-Ma6l8PjIIxUc4rV91Lc%2Fimage.png?alt=media\&token=90270272-1ab2-41a9-8c2c-fbeefefe3785)

Ahora solo debería ver los pares en los que tiene tokens LP depositados, lo que facilita la búsqueda.

2 - Busque el Farm en el que tiene tokens LP y haga clic en la fila para ver los detalles. Verá botones **-** y **+** en el lado derecho. Haga clic en **-** para eliminar tokens LP o  **+** para agregar más tokens LP.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2Fsync%2F32ead761ffca6e60b5d44631e5a8603506542f5c.png?alt=media)

3 - Se abrirá una ventana que se parece a la que usó anteriormente para depositar primero sus tokens LP. Al igual que la última vez, escriba la cantidad que le gustaría recuperar / depositar, o haga clic en **Max** para eliminar / agregar todos los tokens LP disponibles.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-M\_yHqZ-iQ7MbYTxgAV0%2F-Ma2ohBGgl\_Ja\_jXUIj3%2Fimage.png?alt=media\&token=13ec22b5-2054-40bc-a23a-cfefd8ee9dd4)

4 - Asegúrese de que su información es correcta. Cuando esté listo, haga clic en el botón **Confirm** y confirme la acción en su billetera.

5 - Después de una breve espera, su nuevo saldo se mostrará en la sección de detalles de su par de tokens LP. Si retirado tus Tokens LP, cualquier recompensa no recolectada que hayas tenido se habrá recolectado automáticamente.

## Recolectar las Recompensas de Farming <a href="#collecting-your-farming-rewards" id="collecting-your-farming-rewards"></a>

El Farming le traerá recompensas CAKE con el tiempo. Puedes recoger estas recompensas y usarlas para obtener más tokens LP, depositarlos en los Syrups Pools, usarlos para jugar a la lotería o cualquier otra cosa que desees.

### Volviendo a su Farm para cosechar recompensas <a href="#returning-to-your-farm-to-harvest" id="returning-to-your-farm-to-harvest"></a>

Puede cosechar sus recompensas de Farms y Syrup Pools juntos desde la página de inicio. Si desea recoger sus recompensas de Farm solamente, siga adelante.

Para recoger sus recompensas, tendrás que visitar tu Farm elegido y recoger los CAKE que te esperan.

1. Vuelva a la página de [Farms](https://pancakeswap.finance/farms).
2. Busca el Farm en la que depositaste tus tokens LP y haz clic en la fila para ver los detalles. Deberías ver una estimación de sus recompensas en "Cake Earned"\
   ![](<../../.gitbook/assets/image (6) (1) (3) (2).png>)
3. Haga clic en el botón **Harvest** y confirme la acción en su billetera. Después de una corta espera, los CAKE serán reclamados a su billetera para que los use como desee.

{% hint style="info" %}
Cuando esté farmeando un una red diferente a BNB Chain, deberá cambiar siempre a BNB Smart Chain para cosechar sus recompensas.

![](<../../.gitbook/assets/image (1) (2) (1).png>)
{% endhint %}

### Con qué frecuencia debo cosechar mis recompensas? <a href="#how-often-should-i-harvest-my-rewards" id="how-often-should-i-harvest-my-rewards"></a>

La frecuencia con la que cosecha sus recompensas depende de usted, pero ayuda a recordar que hay una pequeña tarifa involucrada en la cosecha.

Puede ver esta tarifa en su billetera al confirmar después de hacer clic en **Harvest**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-M\_yHqZ-iQ7MbYTxgAV0%2F-Ma2keRoF\_mzhyD-3x64%2Fimage.png?alt=media\&token=ee7bd789-7ead-468a-b286-cb2be51034fc)

Esto muestra la tarifa por la cosecha tal como aparece en la billetera MetaMask. Diferentes billeteras mostrarán la información de manera un poco diferente. Considere dejar que sus recompensas crezcan por un tiempo para que pague tarifas con menos frecuencia.

¡Y eso es todo lo que hay que hacer! También es posible que desee ver cómo utilizar los Syrup Pools de PancakeSwap.

Feliz farming!
