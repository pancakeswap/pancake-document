# 🎁 Pancake Gifts

### 🎯 ¿Qué es Pancake Gifts?

**Pancake Gifts** permite que cualquiera envíe tokens — incluyendo gas opcional — a amigos, usuarios o comunidades usando simplemente un **enlace** o **código QR**. Es una experiencia simple, segura y sin gas para el destinatario.

Está diseñado para hacer que la incorporación al mundo cripto sea tan fácil como enviar un mensaje — sin necesidad de financiar la billetera, hacer puenteo ni pagar tarifas iniciales.

### 🤝 Por qué construimos Pancake Gifts

Incorporarse a Web3 sigue siendo un proceso lleno de fricciones. Los nuevos usuarios a menudo se rinden antes de empezar debido a:

* **Sin gas en la billetera** → No se puede realizar ninguna acción on-chain
* **Sin fondos en la cadena correcta** → Se requiere puentear antes de usar dApps
* **Necesidad de comprar cripto solo para empezar** → Requiere registro en un intercambio centralizado o rampa de entrada de dinero fiat

Pancake Gifts elimina estos obstáculos al:

* ✅ **Incluir tokens de gas nativos** en el regalo para que los destinatarios puedan interactuar de inmediato
* ✅ **Patrocinar la tarifa de gas por adelantado** (el remitente paga una pequeña tarifa)
* ✅ **Habilitar el reclamo mediante un enlace o QR simple** — sin proceso de incorporación complejo



Es una herramienta tanto para:

* Nuevos usuarios que se inician on-chain
* Comunidades nativas de Web3 que buscan **impulsar la adopción, recompensar usuarios o ejecutar campañas** de una manera más amigable

***

### ⚙️ Resumen de características

| Característica              | Descripción                                                              |
| --------------------------- | ------------------------------------------------------------------------ |
| **Soporte de cadenas**      | BNB Chain (lanzamiento inicial)                                          |
| **Tipos de código de regalo** | Enlace **o** código QR                                                 |
| **Uso único**               | Cada código solo puede ser reclamado una vez                             |
| **Soporte de tokens**       | Máx. 2 tokens: 1 BEP-20 (obligatorio), 1 token de gas nativo (opcional) |
| **Cantidades personalizadas** | Establece valores diferentes por token                                  |
| **Tarifa de gas del regalo** | El remitente paga el gas por adelantado (\~$0.05 en BNB)                |
| **Historial de regalos**    | Los usuarios pueden ver todos los regalos enviados, estado de reclamo, vencimiento |
| **Verificaciones de seguridad** | Los tokens con tarifa de transferencia y con lógica compleja no están permitidos |

### 🚫 Limitaciones

1. **Un regalo por código** — Los regalos masivos aún no son compatibles.
2. **Los regalos no se pueden restablecer** — Una vez cancelados o vencidos, no pueden reutilizarse.
3. **Los tokens no soportados son bloqueados** — Los tokens con tarifas de transferencia o lógica especial mostrarán un error al crearlos.
4. **Los reclamos fallidos se reintentarán** — El backend reintenta algunas veces. Si aún falla, el regalo se marca como **no reclamable** y debe cancelarse manualmente para recuperar los fondos.
5. **El regalo debe reclamarse en la misma cadena** — Por ejemplo, un regalo en ETH debe reclamarse en Ethereum. El reclamo entre cadenas aún no está soportado.

***

### 🕒 Lógica de cancelación y vencimiento

Los regalos siguen un ciclo de vida definido según el estado y el tiempo:

#### Cancelación manual

* El **creador** puede cancelar cualquier regalo que aún esté **sin reclamar** y **dentro del período de vencimiento**.
* Los tokens (menos la tarifa inicial de gas del regalo) serán devueltos al remitente.
* Los regalos cancelados **no** pueden reactivarse ni reutilizarse.

#### Vencimiento automático

* Los regalos **vencen automáticamente** después de un período definido por el usuario (predeterminado: 7 días).
* Los tokens no reclamados serán **devueltos automáticamente** a la billetera del remitente.
* Los regalos vencidos tampoco son reutilizables.

***

### 🔄 Estados del regalo y su significado

| Estado          | Descripción                                                                     |
| --------------- | ------------------------------------------------------------------------------- |
| **Pendiente**   | El regalo ha sido creado y está esperando ser reclamado                         |
| **Reclamado**   | El regalo fue reclamado exitosamente por un destinatario                        |
| **Cancelado**   | El regalo fue cancelado manualmente por el remitente                            |
| **Vencido**     | El regalo superó el tiempo de vencimiento sin ser reclamado                     |
| **No reclamable** | Número de reintentos superado; el regalo debe cancelarse para recuperar los fondos |

***

### ⚠️ Manejo de errores y casos límite

1. **Token no soportado**
   * La creación del regalo está bloqueada para tokens con tarifas de transferencia o lógica especial.
2. **Desajuste de gas**
   * Si el **costo real del gas del reclamo ≥** la tarifa prepagada por el remitente, el reclamo falla automáticamente para evitar un uso excesivo. Se reintentará una vez que los niveles de la tarifa de gas estén dentro del rango.
3. **Intentos de reclamo fallidos**
   * Se intentarán reintentos ante el primer reclamo fallido.
   * Si sigue sin tener éxito:
     * El destinatario ve "No reclamable"
     * El remitente debe cancelar manualmente el regalo para recuperar los fondos y el destinatario tendrá que solicitar un nuevo código de regalo.
