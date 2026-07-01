# FAQ de Social Login

{% hint style="info" %}
Para más información, visita: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 Descripción general

**1. ¿Qué es el Social Login de PancakeSwap y por qué debería usarlo?**

Social Login te permite acceder a PancakeSwap usando tu cuenta de **Google**, **X (Twitter)**, **Discord** o **Telegram** — sin necesidad de extensión de billetera ni frase semilla. Se crea una billetera autocustodiada en segundo plano, para que puedas probar DeFi de inmediato, incluso con pequeñas cantidades. Esto reduce la barrera de entrada, especialmente en momentos urgentes.

**2. ¿Qué cadenas admite el Social Login?**

Tu billetera de Social Login funciona en todas las cadenas actualmente compatibles con PancakeSwap:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

Todas las billeteras son **compatibles con EVM** y pueden usarse en estas redes de forma nativa a través de PancakeSwap. Si quieres ver soporte para otras cadenas (incluidas las no EVM), ¡haznos saber!

**3. ¿Dónde puedo usar la billetera de Social Login?**

Puedes usarla directamente en cualquier **navegador** de escritorio o móvil a través de la aplicación web de PancakeSwap. **No es compatible** con aplicaciones de billetera externas ni navegadores de dApps.



### 🛠️ Configuración y uso de la billetera

**4. ¿Cómo se crea y protege la billetera?**

Tu billetera se crea automáticamente al iniciar sesión y se protege mediante un **sistema de 2 claves compartidas (2-of-2)**. Se requieren ambas partes para reconstruir la clave y generar una firma.

Para más información sobre el cifrado de las partes, visita:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. ¿Cuántas billeteras puedo crear?**

Obtienes **una billetera por cuenta social por dApp**. Por ejemplo, si usas tu inicio de sesión de Google en otra aplicación que también usa Privy, se creará una billetera separada.



### 🔐 Seguridad y privacidad

**6. ¿Puede alguien acceder a mi billetera si roban mi dispositivo?**

No. Incluso si alguien obtiene acceso a tu dispositivo, seguiría necesitando tanto tu **inicio de sesión social** como (si está configurada) tu **contraseña de recuperación**.

**7. ¿Qué datos almacenan PancakeSwap o Privy?**

* PancakeSwap **no almacena** ninguna parte de la clave relacionada con la billetera.
* Privy almacena la **parte de autenticación cifrada y la parte de recuperación (si no se ha configurado el flujo de recuperación)**.

> Si no has completado la configuración de recuperación, tu parte de recuperación permanece almacenada por Privy de forma predeterminada. Para más información, visita: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 Recuperación y gestión de sesiones

**8. ¿Puedo usar la misma billetera en un dispositivo o navegador diferente?**

¡Sí! Simplemente inicia sesión con la misma cuenta social. Si es un dispositivo nuevo, pasarás por el proceso de recuperación usando tu contraseña de recuperación (si la configuraste).

**9. ¿Qué sucede si cambio de dispositivo?**

Se te pedirá que vuelvas a iniciar sesión con tu cuenta social y pases por el flujo de recuperación (configuración de contraseña). Si no configuraste una contraseña de recuperación, el inicio de sesión con la cuenta social es suficiente.

**10. ¿Qué pasa si pierdo acceso tanto a mi Social Login como a mi método de recuperación?**

Si pierdes acceso tanto a tu cuenta social como a tu método de recuperación, **tu billetera no puede recuperarse**. No hay alternativa de frase semilla y la exportación de clave privada no está soportada actualmente.

> ⚠️ Recuerda: exportar tu clave privada, si se habilita en el futuro, otorgaría control total de tu billetera a cualquiera que la tenga — trátala con extrema cautela.

**11. ¿Cuánto duran las sesiones activas?**

Las sesiones duran 30 **días**. Después de eso, se te pedirá que **vuelvas a iniciar sesión** y (si es necesario) vuelvas a ingresar tus credenciales de recuperación. Durante una sesión activa, puedes realizar transacciones sin necesidad de aprobar manualmente cada acción.



### ⚙️ Compatibilidad y limitaciones

**12. ¿Puedo exportar o importar billeteras?**

* **Exportar**: No está soportado de forma predeterminada, por razones de seguridad. Esto puede cambiar en futuras actualizaciones.
* **Importar**: No está soportado. No puedes importar billeteras externas como MetaMask o Phantom.

**13. ¿Puedo conectar esta billetera a otras dApps usando WalletConnect?**

En este momento no. La billetera integrada está **limitada solo a PancakeSwap**. Si estás interesado en usarla de forma más amplia, haznos saber — las expansiones futuras son posibles.



### 🚀 Funciones avanzadas

**14. ¿La billetera de Social Login admite Account Abstraction?**

Sí. Admite **funciones de Account Abstraction** como el agrupamiento de transacciones y el **patrocinio de gas** a través de integraciones como Biconomy, etc.

**15. ¿Cómo se habilitan las transacciones sin firma?**

* Después del inicio de sesión, tu sesión está activa hasta 30 **días**. Durante este tiempo, PancakeSwap puede solicitar a Privy que firme transacciones en tu nombre usando tus credenciales de sesión.&#x20;
* No verás una ventana emergente de billetera para cada acción — todo se gestiona en segundo plano. Después de 30 días, deberás volver a iniciar sesión para continuar usando esta experiencia sin firma.
