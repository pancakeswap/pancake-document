# Errores y Preguntas Frecuentas

{% hint style="info" %}
Utilice la barra lateral para encontrar rápidamente las respuestas a sus preguntas!
{% endhint %}

### Por qué no puedo ver las ganancias en mi wallet? <a id="why-cant-i-see-my-winnings-in-my-wallet"></a>

Cuando juntas ganancias, es posible que no aparezcan en los registros de transacciones de tu billetera como de costumbre. Esto se debe a que utilizan un tipo diferente de transacción: transacciones internas. Ingrese la dirección de su billetera en BscScan, luego marque la pestaña "Txns internas" para confirmar que han llegado.

![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### Por qué no se muestran los resultados de mi ronda? <a id="why-arent-the-results-of-my-round-showing"></a>

Hay un búfer de 15 bloques en cada ronda, que puede causar retrasos de hasta 45 segundos después del final de una ronda. Este búfer es para acomodar el hecho de que es posible que no podamos obtener un precio de manera confiable y terminar una ronda de inmediato: varios factores de la blockchain afectan la velocidad a la que se confirman las transacciones en la red.

### No puedo recolectar mis ganancias! <a id="i-cant-collect-my-winnings"></a>

Asegúrese de tener suficiente BNB en su billetera para pagar las tarifas de gas. Necesitará un poco de BNB para activar el contrato inteligente.

## Pausas del Mercado <a id="market-pauses"></a>

### Qué significa cuando los mercados están en pausa? <a id="what-does-it-mean-when-markets-are-paused"></a>

Los mercados se pausan cuando hay condiciones que afectan a la fiabilidad del contrato. La pausa de los mercados significa que no habrá apuestas para ninguna ronda.

### Qué hace que el mercado de Predicción en PancakeSwap se detenga? <a id="what-causes-pancakeswap-prediction-market-to-pause"></a>

El mercado de Predicción se detendrá bajo las siguientes condiciones:

1. El contrato de Predicción no ha podido obtener el precio del oráculo ChainLink debido a que el oráculo no ha publicado el precio en el momento en que ha finalizado la ronda.
2. El contrato de Predicción ha sido incapaz de ejecutar una acción \(terminando una ronda o consiguiendo un precio del oráculo\) debido a una tx atascada en el mempool más de 15 bloques.

### Cuándo se reanudarán los mercados después de estar en pausa? <a id="when-will-the-markets-resume-after-being-paused"></a>

Los mercados se reanudarán cuando un administrador \(uno de los chefs\) reanude manualmente el mercado.

### Qué pasa con mi posición si el mercado se detiene? <a id="what-happens-to-my-position-if-the-market-pauses"></a>

Si los mercados se detienen mientras usted tiene una posición en vivo, sus fondos estarán disponibles para reclamar, de la misma manera que normalmente reclamaría sus ganancias.

Para reclamar fondos, tendrá que pagar algunas tarifas de gas. No podemos compensarlo por las tarifas de gas, así que tenga en cuenta este pequeño riesgo antes de participar.

## Acerca de las Posiciones <a id="about-positions"></a>

### Qué sucede si nadie entra en una posición opuesta? <a id="what-happens-if-no-one-enters-an-opposing-position"></a>

Si solo un lado de una ronda tiene posiciones ingresadas en ella, y ese lado pierde, los fondos perdedores se enviarán al tesoro. 

  
Por ejemplo: el usuario A introduce una posición UP, y nadie más entra en una posición DOWN. El usuario A pierde, y no hay posiciones opuestas para las ganancias a las que pagar. Entonces, los fondos se envían a la tesorería.

### Qué sucede si el precio bloqueado y el precio cerrado son exactamente iguales? <a id="what-happens-if-the-locked-price-and-closed-price-are-the-exact-same"></a>

En la muy rara ocurrencia de que el Precio Bloqueado es exactamente el mismo que el Precio Cerrado, nadie gana, y todos los fondos ingresados en posiciones serán enviados al tesoro para ser utilizados para que las recompras de CAKE y se quemen.

### **Puedo cambiar o remover mi posición?** <a id="can-i-change-or-remove-my-position"></a>

No. Una vez que ingrese una posición, NO puede cambiar la dirección, agregar o eliminar su posición. Está bloqueado, así que asegúrese de que está 100% contento con la dirección de su posición antes de confirmar.

## Preguntas Generales <a id="general-questions"></a>

### Cuál es la dirección del contrato de Predicción de PancakeSwap? <a id="whats-the-pancakeswap-prediction-contract-address"></a>

Dirección de contrato Verificada: [https://bscscan.com/address/0x516ffd7D1e0Ca40b1879935B2De87cb20Fc1124b](https://bscscan.com/address/0x516ffd7D1e0Ca40b1879935B2De87cb20Fc1124b)​

### Hay un límite de tiempo para cobrar mis ganancias? <a id="is-there-a-time-limit-before-i-can-collect-my-winnings"></a>

No, podrás recoger tus ganancias en cualquier momento en el futuro.

### Cómo se calcula el pago? <a id="how-is-the-payout-calculated"></a>

* Ratio de pago para UP Pool = Valor total de ambos pools ÷ Valor de UP Pool
* Ratio de pago para DOWN pool = valor total de ambos pools ÷ valor de DOWN pool

 Por ejemplo, si hay 15 BNB en el lado DOWN de una ronda, y el premio acumulado general es de 150BNB, la relación de pago DOWN será \(150/15\)=10x.

* Importe de pago = Ratio de pago × posición × \(1 - Comisión del Tesoro\)

En el caso anterior, si la ronda termina en un resultado DOWN, si comprometió 2 BNB en una posición DOWN, obtendría un pago de \(2 \* 10\) × \(1-0.03\) = 19.4 BNB. Su beneficio sería 17.4 BNB \(19.4 - 2\).

La tasa que va al tesoro está fijada actualmente en el 3%: esto puede estar sujeto a cambios, que se anunciarían en los canales de comunicación oficiales de PancakeSwap. Las tarifas del Tesoro se utilizan para recomprar y quemar tokens CAKE.

### Cuáles son los fees? <a id="what-are-the-fees"></a>

El 3% del bote total de cada ronda irá al tesoro, que se utilizará para recomprar y quemar CAKE todos los lunes.

### Qué se utiliza para el feed de precios? <a id="what-are-you-using-for-your-price-feed"></a>

PancakeSwap utiliza dos fuentes para nuestros feeds de precios. Cada uno de ellos tiene su propio propósito dentro del mercado de Predicción:

#### Oráculo ChainLink <a id="chainlink-oracle"></a>

* Se utiliza para el precio de bloqueo y el precio final de cada ronda de mercado de predicción. Esto se actualiza en intervalos de 5 minutos.
*  ****Nuestro contrato de Predicción utiliza el feed de precios del oráculo ChainLink para establecer los precios utilizados para definir si un usuario ha ganado o no.

#### Binance BNB/USDT <a id="binance-bnb-usdt"></a>

* Se utiliza para actualizaciones de precios en tiempo real en la interfaz de mercado de Predicción en PancakeSwap.

Dado que estamos utilizando dos fuentes de precios diferentes, las actualizaciones de precios en tiempo real de Binance y el precio de ChainLink pueden diferir en una pequeña cantidad. Sin embargo, no deben variar significativamente.

### El resultado de la ronda cambió después de que terminó la ronda! ¿Por qué? <a id="the-rounds-result-changed-after-the-round-ended-why"></a>

A veces, después de que se cierra una ronda, el resultado final puede ser diferente del último resultado mostrado mientras la ronda estaba en vivo. Si observa un final redondo en "DOWN", puede parecer que se voltee a "UP" unos segundos más tarde.

Esto se debe a que utilizamos el feed de precios de ChainLink Oracle para determinar el resultado final de una ronda. El período entre el final de una ronda y el inicio de la siguiente es de 30 segundos, pero Oráculo se actualiza cada 20 segundos. Es posible que durante este corto período, el Oráculo pueda enviar una actualización mientras se acuña la transacción para desencadenar la siguiente ronda. Esto puede aparecer y voltear el resultado de la ronda anterior.

