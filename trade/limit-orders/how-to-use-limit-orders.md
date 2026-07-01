---
hidden: true
---

# Cómo usar las Órdenes Límite

## ¿Qué son las Órdenes Límite?

Una orden límite es una herramienta que permite a los usuarios comprar o vender activos a un precio especificado o mejor, en lugar de depender del precio de mercado en el momento de la ejecución. En una orden límite, aunque el precio está garantizado, la ejecución de la orden no lo está — las órdenes límite solo se ejecutarán si el precio cumple con las condiciones de la orden.

## Cómo configurar una orden límite

1. Ve a la página de Intercambio y selecciona la opción de orden límite haciendo clic en "LÍMITE", o usa este enlace: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. Selecciona los tokens "Desde" y "Hasta" que deseas intercambiar. En este ejemplo elegimos USDC y ETH respectivamente, lo que significa que queremos comprar ETH con USDC.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. Introduce el importe que deseas intercambiar. Observa que el precio límite mostrará el precio de mercado actual, que estimará el importe de salida de los tokens de destino (ETH)
2. Establece el precio límite deseado. Las operaciones SOLO se ejecutarán cuando el precio de mercado disponible sea igual o mejor que el precio límite. El importe de salida del token de destino se actualizará en consecuencia.

En el siguiente ejemplo, queremos comprar ETH cuando el precio sea $1.900 o mejor. La cantidad de ETH recibida será igual o mayor a 0,037 ETH. Solo las ofertas iguales o mejores que este importe serán elegibles para completar la orden. Este importe tiene en cuenta los costos de gas y las comisiones. &#x20;

{% hint style="info" %}
Nota importante: Como las comisiones se pagan con el importe del token de salida, el precio límite incluye las comisiones de gas y trading, por lo que los usuarios deben tenerlo en cuenta al configurar el precio. Por ejemplo, las comisiones de gas de una orden muy pequeña pueden representar un porcentaje muy alto de la salida de la orden, reflejando un precio límite real que no es competitivo con el precio spot del mercado.
{% endhint %}

3.  Presiona "Colocar orden". Verifica los detalles de tu orden, acepta el aviso legal y presiona "Confirmar orden".

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. Una vez procesada la transacción, podrás ver tu orden en la sección de historial de órdenes, bajo "Órdenes abiertas". \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. Las órdenes abiertas pueden cancelarse en cualquier momento expandiendo la orden y haciendo clic en el botón "Cancelar orden".

Cosas a tener en cuenta:

* Tu orden puede no ejecutarse si el precio de mercado disponible es peor que el precio límite que has establecido.
* Las operaciones se basan en un protocolo descentralizado que utiliza ejecutores off-chain que compiten para completar las órdenes. Estos ejecutores tienen derecho a solicitar una comisión, que el protocolo descuenta del ejecutor ganador de los tokens de salida.&#x20;
* Los ejecutores pueden tener en cuenta las comisiones de gas de tus transacciones al establecer sus comisiones, lo que puede resultar en fluctuaciones en los importes de las comisiones.
* Al especificar un precio límite, los usuarios verán en la interfaz el importe mínimo de tokens de destino que recibirán si la orden se completa. Solo los ejecutores que ofrezcan importes iguales o mejores serán elegibles para completar la orden. Este importe tiene en cuenta los costos de gas y las comisiones de trading.
