# FAQ

{% hint style="info" %}
¡Usa la barra lateral para encontrar rápidamente las respuestas a tus preguntas!
{% endhint %}

## Órdenes Límite y TWAP

Consulta el FAQ proporcionado por Orbs:

[https://www.orbs.com/dtwap-and-dlimit-faq/](https://www.orbs.com/dtwap-and-dlimit-faq/)

## Límite V2 (Discontinuado)

### ¿Por qué no puedo encontrar mis órdenes?

Las órdenes límite V2 están ahora discontinuadas, accede usando este enlace:

[https://pancakeswap.finance/limit-orders](https://pancakeswap.finance/limit-orders)

### ¿Por qué no se ejecutó mi orden?

Las órdenes límite se ejecutan cuando alcanzan el precio deseado; sin embargo, debido a las fluctuaciones de gas, el precio real de ejecución puede diferir del precio que especificaste en la interfaz. Normalmente, el precio de ejecución y el precio deseado deberían ser casi idénticos; sin embargo, si enviaste una orden particularmente pequeña (\~<1000$), el precio de ejecución podría ser ligeramente más alto para tener en cuenta las comisiones.&#x20;

Por lo tanto, tu orden puede no haberse ejecutado porque:

* No fue posible completar toda la orden al precio y cantidad deseados debido al impacto en el precio.
* Uno de los tokens en la orden límite tiene comisión en la transferencia (ver a continuación).

**Antes de enviar una orden, consulta la interfaz que indica el precio real de ejecución.**

{% hint style="info" %}
Ten en cuenta: la tabla de historial de órdenes obtiene los datos del Subgraph y puede mostrar información con ligero retraso.
{% endhint %}

### ¿Puedo enviar una orden límite para tokens con comisión en la transferencia?

**No.** Los tokens con comisión en la transferencia no deben usarse con órdenes límite. Procede bajo tu propio riesgo.

### ¿Cómo configuro el deslizamiento al usar órdenes límite?

El deslizamiento no es relevante en las órdenes límite. Especificas el importe de entrada (p. ej., 1000 CAKE) y el importe de salida (p. ej., 20 BNB). Las órdenes límite garantizan que recibirás no menos que el importe de salida especificado (20 BNB) por tu importe de entrada (1000 CAKE) si el precio para el par alcanza el precio deseado. **Ten en cuenta que los tokens con comisión en la transferencia no deben usarse con órdenes límite** (ver arriba)

### El precio real de ejecución muestra "nunca se ejecuta". ¿Qué significa esto?

Básicamente significa que estás intentando intercambiar una cantidad muy pequeña de tokens por lo que no hay suficientes tokens para cubrir la comisión de gas. En general, necesitas aumentar el importe del campo "entrada" para deshacerte de este error.&#x20;

### ¿Hay fecha de vencimiento para mis órdenes límite?

Las órdenes abiertas tienen una fecha de vencimiento de 90 días. Después de que tu orden venza, puede que nunca se ejecute. Cancela tu orden una vez que venza.&#x20;

Se planea una función de fecha de vencimiento personalizable para el futuro próximo.

### ¿Por qué no puedo crear órdenes límite por debajo del precio de mercado?

Para vender por debajo del precio de mercado, necesitas **Órdenes Stop Límite**, no órdenes límite. La función de Órdenes Stop Límite llegará próximamente.

### Hice una orden y no aparece en la tabla de órdenes o está atascada en estado "pendiente".

El historial de órdenes proviene del subgraph y por tanto puede mostrar información con ligero retraso. Normalmente, los retrasos no superan un par de minutos como máximo. Consulta el indicador del subgraph en la esquina inferior derecha de la tabla de historial de órdenes.
