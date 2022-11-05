# Glosario

**Aquí encontrará las definiciones de todos los términos relacionados con el trading de futuros (perpetuo).**

### **Trading Perpetuo**

Perpetuos, perpetual swaps, o perps son un tipo especial de contratos de futuros sin fecha de vencimiento.

### Apalancamiento

Apalancamiento es un mecanismo del trading. Los traders pueden usarlo para aumentar su exposición al mercado, permitiéndoles pagar menos que el importe total de la inversión. En resumen, pides dinero prestado para apalancar tu inversión.

<figure><img src="../../../.gitbook/assets/image (4) (2).png" alt=""><figcaption></figcaption></figure>

### Margen

Es la garantía (en valores) que pones para tus posiciones apalancadas. Tiene dos modalidades de uso:

* Cross Margin (Cruzado): Todas las posiciones utilizando la misma moneda como margen, comparten el mismo balance de margen cruzado. En el caso de una liquidación, la totalidad de su balance de la moneda de margen, incluyendo las demás posiciones abiertas, podría perderse.
* Isolated Margin (Aislado): Controla el riesgo de sus posiciones individualmente restringiendo la cantidad de margen asignado a cada una. Siel porcentaje de margen de una posición alcanza el 100%, sólo esa posición será liquidada. en esta modalidad, puede agregarse o quitarse margen sin cerrar la posición.

<figure><img src="../../../.gitbook/assets/image (191).png" alt=""><figcaption></figcaption></figure>

**Margin Ratio (% de margen)**: Margin Ratio = Margen de mantenimiento / Balance del margen. Sus posiciones serán liquidadas una vez que se alcance el 100%.

**Maintenance Ratio (Margen de mantenimiento)**: La cantidad mínima de balance necesario para mantener la posición abierta.

**Margin Balance (Balance)** = Balance en wallet + PNL no realizado. Su posición será liquidada cuando el Balance de margen sea <= que el de mantenimiento.

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

### Activos

**Deposit**: Deposita sus fondos en su cuenta de futuros.

**Withdraw**: Retira sus fondos de la cuenta de futuros a su wallet.

**Unrealized PNL (No realizado)**: Ganancias o pérdidas no realizadas de la posición, calculadas en base al Precio de Marca.

**Modalidades**:

* Modo Activo único: Permite tradear Futuros USDⓈ-M utilizando solo el activo de margen único del símbolo. El PNL de las mismas posiciones de activos de margen se puede compensar. Admite el modo de margen cruzado y el modo de margen aislado.
* Modo de múltiples activos: trade de futuros de USDⓈ-M en múltiples activos de margen. El PNL se puede compensar entre las diferentes posiciones de activos de margen. Solo admite el modo de margen cruzado.

{% hint style="info" %}
Nota: Si hay posiciones abiertas u órdenes abiertas en Futuros USDⓈ-M, no se puede activar el Modo de Activos Múltiples. El Modo de Activos Múltiples solo se aplica a Futuros USDⓈ-M. Antes de activar el modo de activos múltiples, lea la guía en detalle para administrar mejor el riesgo de la cuenta de futuros USDⓈ-M en consecuencia cuando utilice el modo de activos múltiples.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### Órdenes

**Comprar/Long**: abre una orden en long. En esta orden, usted compra un activo y espera para venderlo cuando sube el precio. "Comprar" y "long" se usan indistintamente.&#x20;

**Vender/Short**: abre una orden en short. En esta orden, toma prestado un activo, lo vende y espera volver a comprarlo cuando el precio baje. "Vender" y "short" se usan indistintamente.&#x20;

**Orden Límite**: Una orden límite es una orden para comprar o vender a un precio específico o mejor. No se garantiza que las órdenes límite se ejecuten.&#x20;

**Orden de Mercado**: Una orden de mercado es una orden para comprar o vender al mejor precio actual disponible. Se ejecuta contra las órdenes límite que se colocaron previamente en el libro de órdenes. Al colocar una orden de mercado, pagará tarifas como tomador de mercado.&#x20;

**Orden Stop Limit**: La forma más fácil de entender una orden stop limit es dividirla en precio stop (de activación) y precio límite. El precio stop es simplemente el precio que activa la orden límite, y el precio límite es el precio de la orden límite que se activa. Esto significa que una vez que se haya alcanzado su precio stop, su orden límite se colocará inmediatamente en el libro de órdenes.&#x20;

**Orden Stop Market**: Similar a una orden stop limit, una orden stop market utiliza un precio stop como disparador. Sin embargo, cuando se alcanza el precio stop, en su lugar se activa una orden de mercado.&#x20;

**Trailing Stop**: Un trailing stop es un tipo de orden diseñado para asegurar ganancias o limitar pérdidas a medida que una operación se mueve favorablemente. Los stop dinámicos solo se mueven si el precio se mueve favorablemente. Una vez que se mueve para asegurar una ganancia o reducir una pérdida, no retrocede en la otra dirección.&#x20;

**Solo publicación**: el modo de solo publicación significa que los traders solo pueden realizar una orden si ésta iría al libro de órdenes como una orden Maker. Se rechazará una orden que se publicaría como una orden de tomador (Taker). No se pueden colocar Órdenes de Mercado y no se ejecutarán Órdenes. Las órdenes en espera pueden cancelarse en el modo de solo publicación.

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

**Reduce Only:** Las órdenes de "Sólo reducir" sólo podrán reducir su posición, no incrementarla.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

**Instrucciones TIF (Time in Force)** son las que especifican cuánto tiempo estará activa una orden hasta que sea ejecutada o se venza. puede seleccionar una de las siguientes opciones para instrucciones TIF:

<figure><img src="../../../.gitbook/assets/image (200).png" alt=""><figcaption></figcaption></figure>

* **GTC** (Good Till Cancel): La orden permanecerá activa hasta que se cumpla totalmente o bien sea manualmente cancelada.
* **IOC** (Immediate Or Cancel): La orden deberá ser ejecutada inmediatamente (total o parcialmente). De no ser así, se cancela. En el caso de que se ejecute parcialmente, el remanente no ejecutado se cancelará.
* **FOK** (Fill Or Kill): La orden debe ejecutarse inmediatamente por completo, aso contrario no se ejecutará (ni siquiera parcialmente).
