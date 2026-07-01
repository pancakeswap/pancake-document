# ❓ FAQ

### 1. ¿Cómo funciona la tolerancia al deslizamiento en los intercambios multicadena?

Para los intercambios multicadena, el porcentaje de tolerancia al deslizamiento que seleccionas se aplica de forma independiente a los intercambios tanto en la cadena de origen como en la de destino.

**Ejemplo:**

* Intercambiar BNB en BNB Chain a ARB en Arbitrum
* Tolerancia al deslizamiento establecida en 1%
* La ruta podría ser:
  1. Intercambiar BNB por USDC en BNB Chain
  2. Puentear USDC desde BNB Chain a Arbitrum a través de Across
  3. Intercambiar USDC por ARB en Arbitrum
* En este caso, la tolerancia al deslizamiento del 1% se aplica por separado a:
  * El intercambio en BNB Chain
  * El intercambio en Arbitrum

Esto garantiza que estés protegido frente a movimientos de precio excesivos en ambos tramos de la transacción, sin que la configuración de deslizamiento afecte al proceso de puenteo.

### 2. ¿Qué ocurre si mi transacción falla?

Si tu intercambio multicadena encuentra un fallo en alguna etapa, así es como se gestiona:

1.  **Fallo de Intercambio/Transacción en la Cadena de Origen**

    ➝ Recibirás inmediatamente tu token original de vuelta en la cadena de origen.
2.  **Fallo de Transacción de Puente**

    ➝ Across procesará un reembolso en un plazo de 90 minutos a 2 horas, y recibirás el activo puenteado de vuelta en la cadena de origen. Relay procesa el reembolso en menos de un minuto en dichos escenarios entre SOL <> EVM.
3.  **Fallo de Intercambio en la Cadena de Destino**

    ➝ Recibirás el activo puenteado en la cadena de destino, sin el intercambio final por tu token objetivo.

{% hint style="info" %}
**Nota:** Siempre puedes comprobar el estado de tus transacciones a través de la pestaña de historial de transacciones en la interfaz de conexión de billetera.
{% endhint %}

### 3. ¿Mis intercambios multicadena están protegidos contra MEV?

MEV Guard solo es compatible en BNB Chain cuando los intercambios se inician directamente desde una billetera conectada con MEV Guard activado.

* Si tu intercambio multicadena involucra un intercambio en BNB Chain como cadena de origen y tienes MEV Guard activado, ese intercambio estará protegido contra MEV.
* Si BNB Chain es la cadena de destino, el intercambio lo ejecuta el relayer/sistema de puenteo y no estará protegido contra MEV, ya que no lo inicia tu billetera conectada.

{% hint style="info" %}
**Nota:** Otras cadenas como Arbitrum y Base actualmente no admiten la protección MEV Guard en PancakeSwap.
{% endhint %}

### 4. ¿Puedo intercambiar stablecoins entre cadenas?

Sí — puedes intercambiar y puentear stablecoins como USDC, USDT y DAI directamente entre cualquier cadena compatible.

Tienes dos opciones:

1.  **Puente Directo:**

    Puentea stablecoins compatibles (como USDC, USDT, etc.) directamente de una cadena a otra.
2.  **Intercambio por Otros Tokens:**

    También puedes intercambiar una stablecoin por cualquier otro token compatible en la cadena de destino usando los pools de liquidez de PancakeSwap — ya sea antes o después del puenteo.

{% hint style="info" %}
**Nota:** Las stablecoins compatibles para puenteo directo pueden variar según la cadena.
{% endhint %}

### 5. ¿Mis intercambios usarán PCSX?

No — PCSX no es compatible para servir intercambios multicadena.

Los intercambios multicadena en PancakeSwap se enrutan exclusivamente a través de:

* **Los pools de liquidez de PancakeSwap** (v2, v3, Infinity, StableSwap) para intercambios en cadena, y
* **Los protocolos Across y Relay** para puentear activos entre cadenas.

PCSX no puede utilizarse para facilitar o enrutar ninguna parte de una transacción de intercambio multicadena.

### 6. ¿Existe un límite mínimo o máximo en el monto del intercambio?

Sí — tanto los límites mínimos como máximos se aplican a las transacciones multicadena.

* **Límite Máximo:**\
  Depende de la liquidez de puente disponible para el token y la cadena seleccionados. Este valor puede fluctuar en tiempo real según las condiciones de red y liquidez.
* **Límite Mínimo:**\
  Se establece para garantizar que sea económicamente viable para los relayers procesar la transacción de puente.

{% hint style="info" %}
**Nota:** Los límites exactos mínimo y máximo varían según el token de puente. Si el monto de tu transacción está fuera del rango permitido, la interfaz mostrará un mensaje de error claro y te pedirá que ajustes el monto.
{% endhint %}
