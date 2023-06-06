# FAQ

### ¿Por qué hay múltiples APR?&#x20;

En V3, puede concentrar sus activos mientras proporciona liquidez para aumentar su participación frente a la liquidez total disponible, obteniendo un mayor porcentaje de recompensas.&#x20;

Por lo tanto, dependiendo de la configuración del rango de precios de la posición, cada posición de liquidez tendrá su propio APR de fee por LP y su propio APR de farm.&#x20;

El APR global se calcula con la cantidad total de recompensas de CAKE en USD, dividida por la cantidad total de activos, en las posiciones activas, que están depositadas actualmente en la granja. Por lo tanto, el APR de farm global es solo una referencia genérica y no representará APR individuales para cada posición.&#x20;

Para ver su APR de farm, consulte sus posiciones enumeradas debajo de cada farm.

### ¿Qué sucede si mi posición de liquidez se sale del rango mientras hago staking en Farm?&#x20;

En V3, solo las posiciones de liquidez activas (dentro del rango) obtendrán CAKE de los farms.&#x20;

La posición dejará de recibir recompensas en CAKE cuando el precio salga del rango.&#x20;

Si el precio vuelve a estar dentro del rango, la posición comenzará a recibir recompensas en CAKE nuevamente. No se requieren acciones adicionales por parte del usuario.

### ¿Hay alguna forma de ajustar automáticamente mi posición para que siempre esté dentro del rango y gane recompensas de tarifas?&#x20;

La función de gestión automática de posiciones llegará pronto a PancakeSwap v3 con depósito de liquidez con un solo clic (¡Zap!) y farming. Estén atentos para más detalles.

### ¿Es mejor farmear siempre con una posición de liquidez con un rango más pequeño?&#x20;

Proporcionar liquidez a un rango de precios más pequeño ayudará a concentrar su liquidez, potenciando su participación frente a la liquidez total dentro del rango de precios, lo que podría generar más recompensas en CAKE.&#x20;

Sin embargo, tenga en cuenta que solo las posiciones de liquidez activas obtendrán recompensas en CAKE. Esto significa que solo obtendrá recompensas cuando el precio de negociación actual se encuentre dentro del rango de precios definido en la posición de liquidez.&#x20;

Si necesita ajustar el rango de precios de su posición, deberá retirar la participación, remover la liquidez y crear una nueva posición con el rango de precios actualizado. Tenga en cuenta que los ajustes frecuentes no siempre son la estrategia más óptima, ya que se ven afectados por el Impermanent Loss y cuesta una cierta cantidad de gas para completar múltiples transacciones.

### ¿Cuántas posiciones puedo depositar en un mismo farm?

No hay un límite máximo de posiciones que puede depositar en un farm.&#x20;

Pero tenga en cuenta que necesitará gastar gas para cosechar manualmente desde cada una de las posiciones. Tenga siempre en cuenta el costo del gas en todas las transacciones.

### ¿Con qué frecuencia debo cosechar mis recompensas?&#x20;

Depende de usted la frecuencia con la que cosecha sus recompensas, pero es útil recordar que hay una pequeña tarifa involucrada en la cosecha. Puede ver esta tarifa en su billetera al confirmar después de hacer clic en "Cosechar".&#x20;

Esto muestra la tarifa por la recolección tal como aparece en la billetera MetaMask. Diferentes billeteras mostrarán la información de manera un poco diferente. Considere dejar que sus recompensas crezcan por un tiempo para que pague tarifas con menos frecuencia.

### ¿Qué pasa si quiero ajustar mi posición mientras está en el Farm?

Mientras participa en un farm, puede agregar o eliminar liquidez sin retirarla. Simplemente ubique la posición de liquidez que desea ajustar y haga clic en su título/id, y se le presentará la página de detalles de la posición donde puede usar los botones "Agregar" y "Eliminar".&#x20;

Si desea ajustar las configuraciones del rango de precios de una posición de liquidez, deberá retirarla del farm, remover toda la liquidez y volver a crear una nueva posición agregando liquidez.

### ¿Qué afecta el APR del Farm?&#x20;

En Farm v3, el APR de recompensa de CAKE podría variar entre las distintas posiciones de liquidez. Se basa en los siguientes factores:&#x20;

* Tasa de emisión de CAKE a los Farms (más CAKE generará un mayor rendimiento para todas las Farms). Lea más en nuestra [página de tokenomics](../../gobernanza-y-tokenomics/cake-updated-10-29-2020/tokenomics-de-cake.md)&#x20;
* Multiplicador de Farm (los farms con un multiplicador más alto obtendrán más CAKE proporcional a todas los farms. Tenga en cuenta que los farms v3 y v2 más los de stableswap están utilizando dos tipos diferentes de multiplicadores. Y los farms en Ethereum y BNB Chains también usan dos tipos diferentes de multiplicadores).&#x20;
* El número de tokens depositados en la posición. (más token en la posición se traduce en una mayor participación relativa frente a la liquidez activa total en el pool del farm y obtiene más recompensas en CAKE)
* El rango de precios seleccionado (un rango de precios más pequeño permite una mayor concentración por la misma cantidad de token depositado, lo que se traduce en una mayor participación relativa frente a la liquidez activa total en el pool del farm, y obtiene más recompensas en CAKE)
* La cantidad de liquidez actualmente activa (si hay más usuarios que depositan y concentran su liquidez con el mismo rango que tú, ganarás menos CAKE debido a una menor participación relativa contra el total)
* Que la posición de liquidez esté activa (solo las posiciones de liquidez activas obtendrán recompensas en CAKE del farm)

### ¿Por qué veo una ventana emergente "Update Positions" (Actualizar Posiciones)?

<figure><img src="../../.gitbook/assets/image (16) (2).png" alt=""><figcaption></figcaption></figure>

Poco después del lanzamiento de v3, se realizó una actualización para que los cálculos de recompensas sean más precisos y confiables.&#x20;

Si ves esta ventana emergente, significa que alguna de tus posiciones necesitan actualización. Simplemente haga clic en "Actualizar todo" y confirme en la ventana de la wallet.&#x20;

Tenga en cuenta que los Chefs también están aplicando esta actualización a los datos históricos, por lo que si hubieran recompensas adicionales, se enviarán directamente a su wallet antes del 1 de mayo.

### ¿Por qué un farm con 2x en V3 tiene menos APR que uno con 1x en V2?

Primero, cuando comparamos APRs, debe asegurarse de que el total de liquidez depositada entre los dos farms sea igual.

Además de ello, ahora tenemos múltiples grupos de farms que tienen su propia asignación de emisiones de CAKE. Y cada grupo de farms comparte diferentes tipos de multiplicadores.

Un farm individual recibirá emisiones de CAKE en base a:

* A = Total de CAKE por segundo/block para el grupo de farms al que pertenezca
* B = Número total de multiplicadores dentro del grupo al que pertenezca
* C = El multiplicador tiene

`CAKE por block/segundo = C / B * A`

Los números arriba mencionados puede encontrarlos en cada uno de los contratos [MasterChef](https://docs.pancakeswap.finance/code/smart-contracts/main-staking-masterchef-contract).



### ¿Puedo usar bCAKE en los Farms v3?

Sí

bCAKE para los Farms V3 Farms llegarán muy pronto luego del despliegue de PancakeSwap Farm V3. Manténgase atento.
