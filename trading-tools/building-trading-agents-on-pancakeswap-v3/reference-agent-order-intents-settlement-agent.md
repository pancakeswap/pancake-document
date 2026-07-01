# Agente de Referencia — Agente de Liquidación de Órdenes/Intenciones

> Un agente Provider de ERC-8183 que cumple un único Job de intención de intercambio a la vez, enrutándolo a través de la agregación de PancakeSwap y entregando el token objetivo directamente al Client.

### 0. Cómo se mapea a ERC-8183

ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation) define un **Job** con tres roles y estados Open → Funded → Submitted → Terminal. El **BNBAgent SDK** de BNB es la implementación en producción.

| Rol                                                      | En este agente                                                                                                                           |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Client** (Agent-A)                                     | publica una intención de intercambio: "intercambia X del token A → token B, entrégame ≥ `minOut`", deposita en escrow el input + propina |
| **Provider** (Agent-B) — **este es nuestro agente de referencia** | cotiza vía **agregación de PancakeSwap** y, si puede cumplir/superar `minOut`, ejecuta el intercambio y entrega el token B al Client    |
| **Evaluator**                                            | verifica que el Client recibió una cantidad de token-B ≥ `minOut`; libera la propina (o reembolsa al Client)                             |

El entregable es objetivo ("¿recibió el Client ≥ `minOut`?"), que es exactamente por qué esto se adapta a ERC-8183 donde el rebalanceador no lo hacía.

***

### 1. Propósito y alcance en una línea

> Un agente **Provider** que cumple un único Job de intención de intercambio a la vez enrutándolo a través de la agregación de PancakeSwap y entregando el token objetivo directamente al Client — y nada más.

***

### 2. Lo que el agente tiene PERMITIDO hacer (lista de capacidades permitidas)

| # | Capacidad                | Superficie                                                         | Notas                                                                          |
| - | ------------------------ | ------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| A | Descubrir Jobs abiertos  | BNBAgent SDK (registro ERC-8183)                                    | Solo lectura; filtrar a Jobs de intención de intercambio que pueda servir       |
| B | Cotizar una ruta         | **Agregación de PancakeSwap** (Aggregator API / Smart Router)       | Solo lectura; mejor precio en V3                                                |
| C | Aceptar un Job           | BNBAgent SDK (Funded → committed)                                   | Solo si su cotización reciente ≥ `minOut` y propina ≥ mínimo                   |
| D | Ejecutar el intercambio  | Router de PancakeSwap                                               | Input tomado del escrow del Job; **destinatario del output = el Client**, en una tx |
| E | Enviar el entregable     | BNBAgent SDK (→ Submitted)                                          | El hash de la tx de liquidación como prueba                                     |
| F | Reclamar la propina      | Escrow ERC-8183 / x402                                              | Solo después de que el Evaluator marque el Job como Terminal                    |

**El output de cada liquidación va directamente al Client. La única ganancia del agente es la propina del Job.**

***

### 3. Salvaguardas estrictas (la puerta para ser destacado)

| Salvaguarda                               | Regla                                                                                                                                                                       |
| ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nunca aceptar lo que no puede cumplir** | Acepta un Job solo si una cotización _reciente_ supera `minOut`. Si no puede, deja el Job en Funded para otro Provider.                                                     |
| **Recotizar al ejecutar**                 | Recotiza inmediatamente antes de liquidar; aborta si la ruta ya no supera `minOut` (sin cotizaciones obsoletas).                                                             |
| **Liquidación atómica**                   | Tomar-del-escrow → intercambiar → entregar al Client en **una transacción**, destinatario del output = Client. El agente nunca debe retener los fondos del Client tras un paso fallido. |
| **Deslizamiento**                         | Deslizamiento de ejecución acotado; la cantidad entregada debe seguir siendo ≥ `minOut` después del deslizamiento, o la tx revierte. Nunca `amountOutMin = 0`.              |
| **Plazo límite**                          | Plazo corto en la tx de liquidación (≤ 5 min); respetar el plazo propio del Job.                                                                                            |
| **Propina mínima / valor máximo**         | No aceptar Jobs por debajo de un umbral mínimo de propina ni por encima de un límite de valor por Job.                                                                      |
| **Lista segura de tokens**                | Solo servir Jobs cuyos tokens estén en la lista de tokens de PancakeSwap (anti-honeypot / token falso).                                                                     |
| **Concurrencia de Job único (v1)**        | Cumplir un Job a la vez; sin sobre-comprometerse.                                                                                                                           |
| **Precondición de gas**                   | Confirmar suficiente BNB para la liquidación completa antes de aceptar.                                                                                                     |
| **Idempotente**                           | Nunca hacer doble envío ni volver a cumplir un Job ya en estado Submitted/Terminal.                                                                                         |

Si alguna regla no puede cumplirse, **omite el Job** — nunca fuerces una liquidación.

***

### 4. Fuera de alcance — el agente NO DEBE

1. **Usar fondos del Client para nada más que el intercambio especificado.** El destinatario del output siempre es el Client.
2. **Usar su propio inventario / asumir riesgo de capital.** v1 es **solo extracción de escrow** — enruta el input en escrow del Client; no rellena desde su propio saldo.
3. **Enrutar a través de contratos que no sean PancakeSwap o no verificados**, ni liquidar fuera de la agregación de PancakeSwap.
4. **Servir Jobs con tokens fuera de la lista segura**, ni (v1) tokens scaled-UI / RWA (§5).
5. **Usar apalancamiento, perpetuos, margen o préstamos.**
6. **Enviar un entregable que no cumplió realmente** (sin atestación falsa) ni **evaluar sus propios Jobs** (conflicto de interés).
7. **Llamar a ninguna función de propietario/administrador** en PancakeSwap o los contratos ERC-8183.
8. **Mantener aprobaciones de tokens permanentes** más allá de una única liquidación; limita las aprobaciones a la cantidad del Job.

***

### 5. Lógica específica de PancakeSwap (corrección de la aplicación)

* **Enrutar vía agregación de PancakeSwap**, no un solo pool — la mejor ejecución en V2 / V3 / Stable es toda la propuesta de valor ("el mejor precio gana la propina").
* **Entregar atómicamente al Client** configurando el `recipient` del router en la dirección del Client; nunca en dos pasos "intercambiar a sí mismo, luego transferir."
* **Frescura de la cotización** — el precio on-chain se mueve entre el descubrimiento y la liquidación; recotiza al ejecutar (salvaguarda §3).
* **`minOut` está en unidades brutas.** Para **tokens scaled-UI / ERC-8056** (Binance Stock Tokens / RWA de renta variable) bruto ≠ mostrado; un manejo incorrecto entrega silenciosamente de forma incorrecta. **Excluye tokens scaled-UI de v1** hasta que ingeniería confirme el manejo de unidades brutas de extremo a extremo.
* **El mínimo de deslizamiento** en el intercambio de liquidación debe derivarse de modo que la cantidad _entregada_ ≥ `minOut`, teniendo en cuenta la división de propina/comisión.

***

### 6. Comportamiento ante fallos y recuperación

* **La cotización no supera `minOut` al ejecutar** → abortar antes/atómicamente con la extracción del escrow; el Job permanece en Funded para otro Provider. Sin estado parcial.
* **Ya en estado Submitted/Terminal** → omitir (idempotente).
* **La tx de liquidación revierte** → el Job permanece reclamable por otros; el agente registra el fallo y continúa.
* **Fallos repetidos en un Job** → poner ese Job en lista negra localmente y alertar, en lugar de reintentar en bucle.

***

### 7. Puntos de integración (la parte de BNB / ERC-8183)

Estos son proporcionados por BNB Agent Studio / BNBAgent SDK, no construidos por PancakeSwap — pero la especificación depende de ellos:

* **Ciclo de vida del Job** (descubrir Open → aceptar Funded → Submitted → reclamar) vía BNBAgent SDK.
* **Identidad del Provider** vía ERC-8004.
* **Escrow + pago** vía el escrow ERC-8183 / x402.
* **Evaluator** — el predicado debe ser "el saldo de token-B del Client aumentó en ≥ `minOut`." Confirma con BNB **quién ejecuta el Evaluator** (neutral/protocolo vs. Client) y que el predicado es aplicable on-chain.

***

### 8. Postura recomendada para v1 y decisiones pendientes

1. **Solo extracción de escrow, un Job a la vez, solo lista segura de tokens, sin tokens scaled-UI.** La superficie más pequeña y segura para lanzar.
2. **Confirmar la interfaz de intercambio de PancakeSwap** — la **API HTTP del Aggregator (`aggr`)** vs el **Smart Router SDK**. La nota de Jerry dice "usar pcs aggr api"; necesita confirmarse cuál llama el agente, ya que cambia la integración (y si la guía necesita una sección de agregación).
3. **Confirmar el mecanismo de escrow** con BNB — ¿puede el Provider extraer el input en escrow del Client para enrutar el intercambio, y es aplicable la entrega al Client como entregable?
4. **Confirmar el propietario del Evaluator y el predicado** (§7).

> Aprobación de ingeniería antes de lanzar: enrutamiento atómico extracción-de-escrow → intercambio → entrega-al-Client; recotización al ejecutar; matemática de `minOut`-después-de-deslizamiento; aplicación de lista segura; manejo idempotente de Jobs.
