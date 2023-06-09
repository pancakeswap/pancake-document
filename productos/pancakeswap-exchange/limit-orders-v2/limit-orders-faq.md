# Limit Orders FAQ

## Preguntas Generales

&#x20;

### **¿Por qué no se ejecutó mi orden?** 

Las **órdenes limite** se ejecutan cuando alcanzan el precio deseado; sin embargo, debido a las fluctuaciones del gas, el precio de ejecución real puede variar del precio que especificó en la interfaz. Por lo general, el precio de ejecución y el precio deseado deberían ser casi idénticos; sin embargo, si envió una orden pequeña (\~<1000 $), el precio de ejecución podría ser ligeramente más alto para tener en cuenta las tarifas.&#x20;

Por lo tanto, es posible que su orden no se ejecute porque:

1\)      No fue posible completar todo el pedido al precio y la cantidad deseados debido al impacto en el precio.

2\)      Uno de los tokens en la orden límite tiene una tarifa de transferencia (incluye una comisión de compra/venta)

\
Antes de enviar una orden, consulte la interfaz de usuario que indica el precio de ejecución real.

{% hint style="info" %}
Tenga en cuenta: la tabla del historial de pedidos obtiene los datos de Subgraph y puede mostrar información ligeramente retrasada.
{% endhint %}

\


### **¿Puedo enviar una orden límite para tokens con cargo por transferencia?**

No. Los tokens con comisión por transferencia no deben utilizarse con órdenes limitadas. Proceda bajo su propio riesgo.

&#x20;

### **¿Cómo configuro el Slippage (deslizamiento) mientras uso órdenes límite?**

El deslizamiento no es relevante en las órdenes límite. Usted especifica la cantidad de entrada (ej., 1000 CAKE) y la cantidad de salida (ej., 20 BNB). Las órdenes límite garantizan que recibirá no menos de la cantidad de salida especificada (20 BNB) por su cantidad de entrada (1000 CAKE) si el precio del par alcanza el precio deseado. Tenga en cuenta que los tokens con tarifa de transferencia no deben usarse con órdenes de límite (lea arriba)

&#x20;

### **El precio de ejecución real muestra "nunca se ejecuta". ¿Qué es esto?**

Básicamente significa que está tratando de intercambiar una cantidad muy pequeña de tokens, por lo tanto, no hay suficientes tokens para contabilizar la tarifa del gas. En general, debe aumentar la cantidad del campo de "entrada" para eliminar este error.

### &#x20;**¿Hay una fecha de vencimiento para mis órdenes límite?**

Las órdenes abiertas permanecerán abiertas indefinidamente hasta que sean ejecutadas o canceladas por los usuarios. Está prevista una función de fecha de caducidad personalizable para un futuro próximo.

### **¿Por qué no puedo crear órdenes límite por debajo del precio de mercado?**

Para vender por debajo del precio de mercado, necesita órdenes Stop Limit, no órdenes límite. La función Stop Limit Orders llegará pronto.

### &#x20;**Hice un orden y no se muestra en la tabla de pedidos o está atascado en el estado "pendiente".**

El historial de pedidos proviene del Subgraph y, por lo tanto, puede mostrar información ligeramente retrasada. Por lo general, los retrasos no superan un par de minutos en el peor de los casos. Consulte el indicador de Subgraph en la esquina inferior derecha de la tabla del historial de pedidos.
