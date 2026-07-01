# Glosario de Perpetuos V1

**Aquí encontrarás definidos todos los términos inherentes al trading de futuros**

### **Trading Perpetuo**

&#x20;Los perpetuos, swaps perpetuos o perps son un tipo especial de contrato de futuros sin fecha de vencimiento.



### **Apalancamiento**

El apalancamiento es un mecanismo de trading. Los traders pueden usarlo para aumentar su exposición al mercado al permitirles pagar menos que el importe total de la inversión. En palabras simples, pides dinero prestado para apalancar tu inversión.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCx0eFDX3CvN4Q1OomBqQ4oNpQ)

### **Margen**

Es la garantía que depositas para tus posiciones apalancadas. Tiene dos Modos de uso:

* Modo de Margen Cruzado: Todas las posiciones cruzadas bajo el mismo activo de margen comparten el mismo saldo de margen cruzado del activo. En caso de liquidación, el saldo de margen completo de tus activos junto con cualquier posición abierta restante bajo el activo puede perderse.
* Modo de Margen Aislado: Gestiona tu riesgo en posiciones individuales restringiendo el importe de margen asignado a cada una. Si el ratio de margen de una posición alcanza el 100%, la posición será liquidada. El margen puede añadirse o retirarse de posiciones usando este modo.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Ratio de Margen**: Ratio de Margen = Margen de Mantenimiento / Saldo de Margen. Tus posiciones serán liquidadas cuando el Ratio de Margen alcance el 100%.

**Ratio de Mantenimiento**: El importe mínimo de saldo de margen requerido para mantener tus posiciones abiertas.

**Saldo de Margen** = Saldo de Billetera + PNL No Realizado. Tus posiciones serán liquidadas cuando el Saldo de Margen <= Margen de Mantenimiento.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Activos:

**Depósito**: Deposita tus fondos en tu cuenta de futuros

**Retiro**: Retira tus fondos de tu cuenta de futuros a tu billetera

**Saldo**: Saldo de Billetera = Total de Transferencias Netas + Total de Ganancias Realizadas + Total de Comisiones de Financiamiento Netas - Total de Comisiones.

**PNL No Realizado**: Ganancia y pérdida no realizadas en esta posición calculadas basándose en el Precio de Marca, y porcentaje de retorno sobre el capital.

**Modos:**&#x20;

* Modo de Activo Único: Admite el trading de Futuros USDⓈ-M usando solo el activo de margen único del símbolo. El PNL de las posiciones del mismo activo de margen puede compensarse. Admite el Modo de Margen Cruzado y el Modo de Margen Aislado.
* Modo Multi-Activos: Trading de Futuros USDⓈ-M en múltiples activos de margen. El PNL puede compensarse entre las diferentes posiciones de activos de margen. Solo admite el Modo de Margen Cruzado.

{% hint style="info" %}
Nota: Si hay posiciones abiertas u órdenes abiertas en Futuros USDⓈ-M, el Modo Multi-Activos no puede activarse. El Modo Multi-Activos solo aplica a los Futuros USDⓈ-M. Antes de activar el Modo Multi-Activos, lee la guía en detalle para gestionar mejor el riesgo de la cuenta de Futuros USDⓈ-M al usar el Modo Multi-Activos.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpq1OD6Cg6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Órdenes

**Compra/Long:** Abre una orden Long. En esta orden compras un activo y esperas a vender cuando el precio suba. "Comprar" y "long" se usan indistintamente.

**Venta/Short:** Abre una orden Short. En esta orden pides prestado un activo, lo vendes y esperas comprarlo de vuelta cuando el precio baje. "Vender" y "short" se usan indistintamente.

**Orden Límite:** Una orden límite es una orden de compra o venta a un precio específico o mejor. Las órdenes límite no están garantizadas de ejecutarse.

**Orden de Mercado:** Una orden de mercado es una orden de compra o venta al mejor precio disponible actual. Se ejecuta contra las órdenes límite que se colocaron previamente en el libro de órdenes. Al colocar una orden de mercado, pagarás comisiones como tomador de mercado.

**Orden Stop Límite:** La forma más sencilla de entender una orden stop límite es desglosarla en precio stop y precio límite. El precio stop es simplemente el precio que activa la orden límite, y el precio límite es el precio de la orden límite que se activa. Esto significa que una vez que se alcanza tu precio stop, tu orden límite se coloca inmediatamente en el libro de órdenes.

**Orden Stop de Mercado:** Similar a una orden stop límite, una orden stop de mercado usa un precio stop como disparador. Sin embargo, cuando se alcanza el precio stop, activa una orden de mercado en su lugar.

**Stop Móvil:** Un stop móvil es un tipo de orden diseñado para asegurar ganancias o limitar pérdidas a medida que una operación se mueve favorablemente. Los stops móviles solo se mueven si el precio se mueve favorablemente. Una vez que se mueve para asegurar una ganancia o reducir una pérdida, no retrocede en la otra dirección.

**Solo Post:** El Modo Solo Post significa que los Traders solo pueden colocar una Orden si se publicará en el Libro de Órdenes como una Orden de Creador de Mercado. Una Orden que se publicaría como Orden de Tomador será rechazada. No se pueden colocar Órdenes de Mercado y no se completará ninguna Orden. Las órdenes en reposo pueden cancelarse en el modo solo post.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**Solo Reducir:** Una orden Solo Reducir solo reducirá tu posición, no la aumentará.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

Las **instrucciones TIF** te permiten especificar el tiempo que tus órdenes permanecerán activas antes de ser ejecutadas o vencer. Puedes seleccionar una de estas opciones para las instrucciones TIF:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Válida Hasta Cancelar): La orden permanecerá activa hasta que se complete o se cancele.&#x20;
* **IOC** (Inmediata O Cancelar): La orden se ejecutará inmediatamente (total o parcialmente). Si solo se ejecuta parcialmente, la parte no completada de la orden será cancelada.&#x20;
* **FOK** (Completar O Cancelar): La orden debe completarse totalmente de inmediato. Si no, no se ejecutará en absoluto.
