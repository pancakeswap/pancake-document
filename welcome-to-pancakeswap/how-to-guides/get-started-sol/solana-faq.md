# FAQ de Solana

### Pools V3 – Preguntas frecuentes (FAQ)

#### 1. ¿Qué niveles de comisión están disponibles?

**Niveles de comisión admitidos:**\
Los siguientes niveles de comisión están disponibles para los pools V3 (liquidez concentrada):

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**Distribución de comisiones (aplica a todos los niveles de comisión):**

* 84% para los proveedores de liquidez (LPs)
* 16% para el protocolo
  * 8% se quema
  * 8% va al tesoro del protocolo

#### 2. ¿Puede cualquiera crear un pool?

Sí. La creación de pools no requiere permisos, con algunas excepciones:

* Solo puede existir un pool para una combinación de **par de tokens + nivel de comisión** determinada (por ejemplo, solo puede existir un pool SOL <> USDC 0.1% a la vez)
* Solo se admiten **tokens SPL** y ciertos tokens **Token-2022** en este momento.

#### 3. ¿Cuánto tiempo tarda en aparecer un pool recién creado?

* Los pools suelen aparecer en la lista de pools aproximadamente **5 minutos** después de su creación.
* Si no aparece:
  * Usa la **barra de búsqueda** para localizarlo manualmente.
  * Los pools pueden filtrarse de la lista debido a un **TVL bajo**.

#### 4. ¿Por qué el APR o TVL de mi pool sigue mostrando cero?

Esto es normal justo después de crear un nuevo pool:

* Los datos de APR y TVL solo se mostrarán una vez que se haya producido **al menos un intercambio** en el pool.
* Después de un intercambio, estas métricas comenzarán a mostrarse en aproximadamente **15 minutos**.

#### 5. ¿Cómo agrego un token personalizado para crear un pool?

Para agregar un nuevo token:

* En la interfaz de creación de pool, abre el selector de tokens.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* Pega la dirección del token en la barra de búsqueda.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* Haz clic en **"Add Token"**.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* El token ahora podrá buscarse en la lista.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* Para gestionar tokens:
  * Haz clic en **"View Token List"**.
  * Activa o desactiva diferentes listas, incluyendo la **User Added Token List**, que incluye cualquier token añadido manualmente.

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. ¿Por qué mi primera transacción en Solana parece más cara?

Solana usa **Cuentas de Token Asociadas (ATAs)** para gestionar los saldos de tokens de cada billetera. Al interactuar con un token por primera vez, tu billetera debe crear una ATA, lo que implica un costo inicial único (pagado en SOL).

* Este costo de creación de ATA es requerido por el protocolo Solana y no es específico de PancakeSwap.
* Si la ATA se cierra posteriormente, el **SOL original utilizado puede ser reembolsado** a tu billetera.
