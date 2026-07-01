# FAQ de Predicción

{% hint style="info" %}
¡Usa la barra lateral para encontrar rápidamente las respuestas a tus preguntas!
{% endhint %}

## A) Preguntas Generales

### **1. ¿Cuáles son las tarifas?**

El 3% del pozo total de cada ronda irá al tesoro, del cual el 100% se usará para recomprar y quemar CAKE.

### 2. ¿Cómo se calcula el pago?

* Ratio de pago para el Pozo SUBE = Valor Total de Ambos Pozos ÷ Valor del Pozo SUBE
* Ratio de pago para el Pozo BAJA = Valor Total de Ambos Pozos ÷ Valor del Pozo BAJA

**Ejemplo - Apuesta 2 BNB en "BAJA", resultado = "BAJA":**

* Lado BAJA = 15 BNB, pozo de premios total = 150 BNB&#x20;
* Ratio de pago BAJA = 150 BNB / 15 BNB = 10x
* Monto de pago = Ratio de pago × Posición × (1 - Tarifa del Tesoro)
  * Si apuestas 2 BNB en BAJA, el pago = (2 × 10) × (1 − 0.03) = 19.4 BNB
* Ganancia = 19.4 − 2 = 17.4 BNB

### 3. ¿Hay un límite de tiempo para cobrar mis ganancias?

No, podrás cobrar tus ganancias en cualquier momento en el futuro.

### 4. ¿Cuál es la dirección del contrato de PancakeSwap Prediction?

**BNB Chain**

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Posiciones y Resultados

### 1. **¿Puedo cambiar o cancelar mi posición?**

No. Una vez que entras en una posición, NO puedes cambiar la dirección, agregar a ella ni retirarla. Está bloqueada, así que asegúrate de estar 100% satisfecho con la dirección de tu posición antes de confirmar.&#x20;

### 2. ¿Cuándo se cancelarán los mercados? ¿Qué sucede entonces?

* **Cuándo:** Fallo del oráculo o del servicio de backend, u otras circunstancias extraordinarias.
* **Resultado:** Los usuarios pueden reclamar el 100% del monto original de su apuesta (sin tarifa).

### 3. ¡El resultado de la ronda cambió después de que terminó! ¿Por qué?

A veces, después de que una ronda termina, el resultado final puede ser diferente del último resultado mostrado mientras la ronda estaba en vivo. Si ves que una ronda termina en "BAJA", puede parecer que cambia a "SUBE" unos segundos después.

Esto se debe a que usamos el feed de precios del Oráculo para determinar el resultado final de una ronda. El período entre el final de una ronda y el inicio de la siguiente es de 30 segundos, pero el Oráculo se actualiza cada 20 segundos. Es posible que durante este breve período, el Oráculo envíe una actualización mientras la transacción para iniciar la siguiente ronda está siendo procesada. Esto puede parecer que "invierte" el resultado de la ronda anterior.

### 4. ¿Qué es el Precio Bloqueado y el Precio de Cierre?

* **Precio Bloqueado:** Precio al inicio de la fase EN VIVO.
* **Precio de Cierre:** Precio al final de la ronda, usado para determinar los ganadores.

**Ejemplo – Ronda 400 (Predicción BNB):**

1. **12:00–12:05:** Colocar Apuesta → El usuario apuesta 0.1 BNB en "SUBE"
2. **12:05–12:10:** Fase de Bloqueo → Precio Bloqueado = $850
3. **12:10:** Fase de Cierre → Precio de Cierre = $860
4. **Resultado: "SUBE"** gana la apuesta

**Notas:**

* El precio del Oráculo puede tardar hasta 20 segundos en actualizarse.
* Victoria de la casa: Todas las apuestas van a la Casa

### 5. ¿Qué situaciones se consideran una VICTORIA DE LA CASA?

**Escenarios:**

1. No existen apuestas contrarias y el usuario pierde (p.ej., solo un usuario apuesta SUBE y el resultado = BAJA)
2. Precio Bloqueado = Precio de Cierre

**Qué sucede:**

* PancakeSwap toma el 100% del pozo; todos los fondos van a la quema de CAKE.
* Los usuarios de cualquier lado pierden el monto inicial de su apuesta.

**Ejemplo - Sin apuestas contrarias:**

* El Usuario A apuesta SUBE, no existen apuestas BAJA, resultado = BAJA → El Usuario A pierde; el 100% de los fondos va al tesoro.
* El Usuario B apuesta SUBE, no existen apuestas BAJA, resultado = SUBE → El Usuario B recupera el 97% de su depósito.



## C) Pausas del Mercado

### 1. ¿Qué significa cuando los mercados están pausados?

Los mercados se pausan cuando hay condiciones que afectan la confiabilidad del contrato. Que los mercados estén pausados significa que no se realizarán apuestas en ninguna ronda.

### 2. ¿Qué hace que el mercado de PancakeSwap Prediction se pause?

El mercado de predicción se pausará bajo las siguientes condiciones:

1. El contrato de predicción no pudo obtener el precio del oráculo ChainLink porque el oráculo no publicó el precio en el momento en que terminó la ronda.
2. El contrato de predicción no pudo ejecutar una acción (finalizar una ronda u obtener un precio del oráculo) debido a que la transacción quedó atascada en el mempool durante más de 15 bloques.
3. PancakeSwap decidió descontinuar la predicción para ese mercado / activo.

### 3. ¿Qué sucede con mi posición si el mercado se pausa?

Si los mercados se pausan mientras tienes una posición en vivo, tus fondos estarán disponibles para reclamar, de la misma manera en que normalmente reclamarías tus ganancias.

Para reclamar fondos, deberás pagar algunas tarifas de gas. No podemos compensarte por las tarifas de gas, así que ten en cuenta este pequeño riesgo antes de participar.

### 4. ¿Cuándo se reanudarán los mercados después de una pausa?

Los mercados se reanudarán cuando un administrador (uno de los chefs) reanude manualmente el mercado.



## D) Solución de Problemas y Reclamaciones

### 1. ¿Cómo reclamo ganancias pasadas del mercado CAKEUSD en BNB Chain?&#x20;

* Ve a [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc)
* Revisa la pestaña de historial para ver las ganancias de rondas históricas

### 2. ¿Por qué no puedo ver mis ganancias en mi billetera?

Cuando cobras ganancias, es posible que no aparezcan en los registros de transacciones de tu billetera como de costumbre.\
Esto se debe a que usan un tipo diferente de transacción: Transacciones Internas.\
Ingresa tu dirección de billetera en BscScan, luego revisa la pestaña "Internal Txns" para confirmar que han llegado.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. ¿Por qué no aparecen los resultados de mi ronda?

Hay un buffer de 15 bloques en cada ronda, que puede causar retrasos de hasta 45 segundos después del final de una ronda.\
Este buffer existe para contemplar el hecho de que es posible que no podamos obtener un precio de forma confiable y finalizar una ronda inmediatamente: varios factores de la blockchain afectan la velocidad con la que las transacciones se confirman en la red.

### 4. No puedo cobrar mis ganancias, ¿qué debo hacer?

Asegúrate de tener suficiente BNB en tu billetera para pagar las tarifas de gas. Necesitarás un poco de BNB para activar el contrato inteligente.

### **5. ¿Qué pasa si no puedo reclamar ganancias desde el sitio web?**

Es posible que puedas reclamar tus ganancias directamente desde el contrato. Sigue los pasos en las 3 pestañas a continuación.

{% tabs %}
{% tab title="Verificar rondas en las que jugaste" %}
Cómo verificar el historial de rondas en las que jugaste

1. Ve a la página de BscScan del [contrato de Predicción](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (p.ej. BNBUSD).
2. Desplázate hacia abajo hasta "8. getUserRounds".
3. Escribe tu dirección de billetera en "user(address)".
4. Establece "cursor(uint256)" en 0 y "size(uint256)" en 1000.
5. Toca "Query"
6. Las rondas en las que participaste aparecerán abajo en la primera fila. (después de "uint256\[]:")
{% endtab %}

{% tab title="Verificar si puedes reclamar" %}
Primero, verifica si realmente deberías poder reclamar de la ronda en la que jugaste.

1. Ve a la página de BscScan del [contrato de Predicción](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (p.ej. BNBUSD), y ve a la pestaña Read
2. Desplázate hacia abajo hasta "4. claimable".
3. Escribe el ID de la ronda que quieres verificar en "epoch(uint256)".
4. Escribe tu dirección de billetera en "user(address)".
5. Toca "Query"
6. Si una ronda es reclamable, mostrará "true".
7. Si el resultado es "false". Por favor repite los pasos anteriores e intenta con "19. refundable".&#x20;
8. Nota: ⬆️ Si ves que una ronda devuelve "false" tanto en "4. claimable" como en "19. refundable", pero se muestra en el sitio web, probablemente ya fue reclamada y el sitio web tiene un retraso.
{% endtab %}

{% tab title="Reclamar de una ronda" %}
Cómo reclamar

1. Ve a la página de BscScan del [contrato de Predicción](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (p.ej. BNBUSD), y ve a la pestaña Write
2. Toca "🔴 Connect to Web3"
3. Usa MetaMask o WalletConnect para conectarte.
4. Desplázate hacia abajo hasta "3. claim"
5.  Escribe el número de ronda que quieres reclamar en este formato, incluyendo los corchetes \[]: `[12345]`&#x20;

    Si quieres reclamar de múltiples rondas a la vez, separa las rondas con una coma así: `[12345,12346,12347]`
6. Toca "Write"
7. Confirma en tu billetera&#x20;
{% endtab %}
{% endtabs %}
