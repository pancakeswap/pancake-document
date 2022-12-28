# Aptos FAQ (preguntas más frecuentes)

<figure><img src="../.gitbook/assets/image (10) (2).png" alt=""><figcaption></figcaption></figure>

Esta página de FAQ responde a algunas de las preguntas más frecuentes de la comunidad de PancakeSwap sobre nuestra implementación en Aptos.

### ¿Cómo pasar de BSC (BnB Smart Chain) a Aptos?&#x20;

Revise nuestra [guía sobre los puentes de Aptos](como-conseguir-aptos-coins.md) para varias soluciones.

### ¿Qué billeteras puedo usar para Aptos Chain?&#x20;

Revise nuestra [guía de billeteras](crea-una-wallet.md) para descargar y configurar su billetera para Aptos.

### Me muestra "Price Impact Too High" al intercambiar tokens/monedas&#x20;

Esto es probablemente por una mala conexión con los nodos de la blockchain. Actualice la página y revise su conexión a la red.

Si el error persiste, significa que el par de monedas que intentas intercambiar no tiene suficiente liquidez para la cantidad que intentas intercambiar. La liquidez para los principales pares de monedas mejorará lenta y constantemente con el tiempo y el problema de liquidez probablemente se solucionará cuando nuestros Farms en Aptos inicien. (¡PRONTO!)

### No puedo encontrar la moneda que quiero intercambiar&#x20;

La lista predeterminada para intercambiar en Aptos solo muestra las monedas de proyectos conocidos con una cantidad suficiente de liquidez.

Si tú quieres intercambiar otras monedas que no están en la lista predeterminada, importalas utilizando la dirección del contrato de la moneda.

### ¿Por qué no puedo intercambiar CAKE en Aptos?&#x20;

_actualizado 13-12-2022_

El token/moneda CAKE está disponible ahora en Aptos. Echa un vistazo a nuestra [Guia del Puente de CAKE](guia-del-puente-de-cake.md) para obtener más información sobre cómo enviar CAKE entre Aptos y BNB Smart Chain.

### Necesito tener CAKE en STAKE en Aptos para participar en las IFOs de Aptos?&#x20;

Las IFOs de PancakeSwap no han sido implementadas aún en Aptos. (¡PRONTO!) Sigue haciendo staking de tus CAKE y estén atentos para más noticias.

## Puente de CAKE

### ¿Por qué la ventana emergente y la barra de progreso muestran un gran tiempo de espera?

Tenga en cuenta que para los activos que no sean CAKE, las transferencias salientes de Aptos están sujetas a confirmaciones de 1M de bloques, que se estima que duran \~4 días. El tiempo puede cambiar debido a las fluctuaciones en los tiempos de los bloques en la red.

**Para el envío de CAKE por el puente, el tiempo de espera debe ser de alrededor de 3-10 minutos.**

### ¿Puedo usar billeteras móviles para enviar CAKE por el puente? ¿Puedo usar billeteras que no sean MetaMask?

Al momento de escribir esto, PancakeSwap Aptos Bridge solo admite MetaMask (y cualquier billetera compatible con MetaMask) en el navegador del escritorio. Muy pronto se agregará más soporte a otras billeteras.

Para evitar copiar y pegar claves privadas o frases semilla entre sus dispositivos. Recomendamos para enviar por el puente crear un conjunto de carteras nuevas con las extensiones de wallets en PC.

### ¿Por qué el botón muestra "X CAKE Exceeded"?

Por seguridad, hay un límite en la cantidad diaria de CAKE que puede ser enviado entre BSC y Aptos. Inténtelo de nuevo con una cantidad menor de CAKE o inténtelo de nuevo más tarde.

Los chefs ajustarán este límite dinámicamente en función de las demandas.

### ¿Qué pasa si la transacción está atascada y sale como "pendiente"?

Las transacciones del puente tardarán hasta 30 minutos en procesarse. Espere e intente buscar su tx ingresando su hash / id en[ LayerZero Scan](https://layerzeroscan.com/).

Si la transacción del puente sigue apareciendo pendiente después de 60 minutos. Por favor, póngase en contacto con nuestros administradores a través de nuestros[ grupos y canales oficiales](https://docs.pancakeswap.finance/v/espanol/contacto) para[ ayuda](https://docs.pancakeswap.finance/v/espanol/click-here-for-help).

Tenga en cuenta que para los activos que no sean CAKE, las transferencias salientes de Aptos están sujetas a confirmaciones de 1 M de bloques, que se estima que duran \~4 días. El tiempo puede cambiar debido a las fluctuaciones en los tiempos de los bloques en la red.

### No recibí nunca mis CAKE

Las transacciones puente tardarán hasta 30 minutos en procesarse. Espere e intente buscar su tx ingresando su hash / id en [LayerZero Scan](https://layerzeroscan.com/).

Al enviar CAKE a Aptos por primera vez, debe hacer claim de su CAKE manualmente. Asegúrese de haber habilitado la función "Gas on destination", o que su dirección de Aptos tenga suficiente APT para gas. Echa un vistazo a nuestra [Guía](https://docs.pancakeswap.finance/v/espanol/empezando-en-pancakeswap-aptos/guia-del-puente-de-cake) para el paso a paso detallado en el puente.

Al enviar CAKE a BNB Smart Chain, para algunas billeteras, deberá agregar manualmente la dirección del token CAKE en su billetera para verificar su saldo.

Si no ha recibido su CAKE después de 60 minutos. Por favor, póngase en contacto con nuestros administradores a través de nuestro [grupos y canales oficiales](https://docs.pancakeswap.finance/v/espanol/contacto) para[ ayuda](https://docs.pancakeswap.finance/v/espanol/click-here-for-help).

### Por qué no puedo enviar por el puente menos de 0.00000001 CAKE?

Las monedas en Aptos tienen máximo 8 decimales. Esto se aplica al token CAKE en Aptos. Entonces, cuando está enviando CAKE a Aptos, las txs con una cantidad inferior a 0.00000001 serán rechazadas.

\
