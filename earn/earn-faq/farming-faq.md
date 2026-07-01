---
hidden: true
---

# FAQ de Farming

### ¿Por qué hay múltiples APRs?

En V3, puedes concentrar tus activos al proporcionar liquidez para aumentar tu participación frente a la liquidez total disponible, ganando un mayor % de recompensas.

Por lo tanto, dependiendo de la configuración del rango de precios de la posición, cada posición de liquidez tendrá su propio APR de comisión LP y su propio APR de farming.

El APR global se calcula con el monto total de recompensas de CAKE en USD, dividido por el monto total de activos en las posiciones activas que están actualmente en staking en la granja. Por lo tanto, el APR global de farming es solo una referencia genérica y no representará los APRs individuales para cada posición.

Para ver tu APR de farming, revisa tus posiciones listadas en cada granja.

###

### ¿Qué sucede si mi posición de liquidez sale del rango mientras estoy en staking en la Granja?

En V3, solo las posiciones de liquidez activas (dentro del rango) ganarán CAKE de las granjas.

La posición dejará de recibir recompensas de CAKE cuando el precio salga del rango.

Si el precio vuelve al rango, la posición comenzará a recibir recompensas de CAKE nuevamente. No se requieren acciones adicionales de los participantes en staking.



### ¿Hay alguna forma de ajustar automáticamente mi posición para que siempre esté en rango y ganando recompensas de comisiones?

PancakeSwap v3 admite depósito de liquidez con un clic a través de Zap, disponible en BNB Chain y Ethereum.



### ¿Es mejor siempre hacer farming con una posición de liquidez con un rango más pequeño?

Proporcionar liquidez a un rango de precios más pequeño ayudará a concentrar tu liquidez, aumentando tus participaciones relativas frente a la liquidez total dentro del rango de precios, ganando potencialmente más recompensas de CAKE.

Sin embargo, ten en cuenta que solo las posiciones de liquidez activas ganarán recompensas de CAKE. Esto significa que solo ganarás recompensas cuando el precio de trading actual esté dentro del rango de precios definido en la posición de liquidez.

Si necesitas ajustar el rango de precios de tu posición, deberás retirar el staking, eliminar la liquidez y crear una nueva posición con el rango de precios actualizado. Ten en cuenta que los ajustes frecuentes no siempre son la estrategia más óptima ya que realiza la pérdida impermanente y cuesta cierta cantidad de gas para completar múltiples transacciones.



### ¿Cuántas posiciones puedo poner en staking en una sola granja?

No hay un límite máximo de posiciones que puedes poner en staking en una granja.

Pero ten en cuenta que necesitarás gastar gas para cosechar manualmente desde cada una de las posiciones. Por favor, siempre factoriza el costo de gas en las operaciones de rendimiento.



### ¿Con qué frecuencia debo cosechar mis recompensas?

La frecuencia con la que cosechas tus recompensas depende de ti, pero ayuda recordar que hay una pequeña tarifa involucrada en la cosecha. Puedes ver esta tarifa en tu billetera al confirmar después de hacer clic en "Harvest"**.**

Esto muestra la tarifa de cosecha tal como aparece en la billetera MetaMask. Las diferentes billeteras mostrarán la información de manera ligeramente diferente. Considera dejar que tus recompensas crezcan por un tiempo para pagar tarifas con menos frecuencia.



### ¿Qué sucede si quiero ajustar mi posición mientras estoy en staking en la granja?

Mientras estás en staking en la granja, puedes agregar o eliminar liquidez sin retirar el staking. Simplemente localiza la posición de liquidez que deseas ajustar, haz clic en su título/id, y deberías ver la página de detalles de la posición donde puedes usar los botones "Agregar" y "Eliminar".

Si deseas ajustar las configuraciones del rango de precios de una posición de liquidez, deberás retirar el staking de la granja, eliminar toda la liquidez y recrear una nueva posición agregando liquidez.



### ¿Qué afecta el APR de Farming?

En Farm v3, el APR de recompensas de CAKE puede variar entre posiciones de liquidez. Se basa en los siguientes factores:

* Tasa de emisión de CAKE a las Granjas\
  \- más CAKE generará un mayor rendimiento para todas las granjas. Lee más en [nuestra página de tokenomics](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics)
* Multiplicador de la Granja\
  \- las granjas con un multiplicador mayor obtendrán más CAKE proporcional a todas las granjas. Ten en cuenta que las granjas v3 y v2 + stable swap usan dos conjuntos separados de multiplicadores. Y las granjas en Ethereum y BNB Chains también usan dos conjuntos separados de multiplicadores.
* La cantidad de tokens depositados en la posición\
  \- más tokens en la posición se traduce en una mayor participación relativa frente a la liquidez activa total en el pool de la granja y obtiene más recompensas de CAKE
* El rango de precios seleccionado\
  \- un rango de precios más pequeño permite una mayor concentración para la misma cantidad de tokens depositados, lo que se traduce en una mayor participación relativa frente a la liquidez activa total en el pool de la granja, y obtiene más recompensas de CAKE
* La cantidad de liquidez actualmente activa\
  \- si hay más usuarios que depositan y concentran su liquidez con el mismo rango que tú, ganarás menos recompensas de CAKE debido a una menor participación relativa frente al total
* Si la posición de liquidez está activa\
  \- solo las posiciones de liquidez activas ganarán recompensas de CAKE de la granja



### ¿Por qué veo un mensaje emergente de "Actualizar Posiciones"?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28321%29.png)

Poco después del lanzamiento de V3, los Chefs implementaron una actualización en las Granjas para hacer los cálculos de recompensas más precisos y confiables. Si ves este mensaje emergente, significa que algunas de tus posiciones requerirán una actualización.

Simplemente haz clic en "Actualizar Todo" y confirma en el mensaje emergente de tu billetera.

Ten en cuenta que los Chefs también están aplicando esta actualización a los datos históricos de staking entre el lanzamiento de Farm V3 y cuando se implemente esta actualización. Si hay recompensas adicionales de CAKE, se enviarán como airdrop a tu billetera antes del 1 de mayo de 2023.



### ¿Por qué una granja 2x en V3 tiene menos APR que una granja 1x en V2?

Primero, al comparar APRs, debes asegurarte de que la liquidez total en staking entre dos granjas sea igual.

Además de eso, ahora tenemos múltiples grupos de granjas que tienen su propio flujo de emisiones de CAKE. Y cada grupo de granjas comparte conjuntos separados de multiplicadores.

Una granja individual recibirá emisiones de CAKE basadas en:

* A = Total de CAKE por segundo/bloque para el grupo de granjas al que pertenece
* B = Número total de multiplicadores dentro del grupo al que pertenece
* C = El multiplicador que tiene

`CAKE por bloque/segundo = C / B * A`

Los números anteriores se pueden encontrar en cada uno de los contratos [MasterChef](/broken/pages/-MeTWzQOSmb1ej51HT0I).



### ¿Puedo usar bCAKE en las Granjas v3?

Sí

bCAKE para las Granjas V3 llegará muy pronto después del despliegue de PancakeSwap Farm V3. Mantente atento.
