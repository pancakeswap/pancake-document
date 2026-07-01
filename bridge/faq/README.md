# ❓ FAQ de Puenteo

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Antes de puentear

1.  **¿Puedo usar billeteras móviles u otras billeteras distintas a MetaMask para puentear CAKE?**

    Actualmente, el Puenteo de CAKE de PancakeSwap admite Coinbase Wallet, MetaMask y billeteras compatibles con MetaMask. Próximamente habrá soporte para más billeteras.

    _Consejo:_ Para evitar el riesgoso copiar y pegar de claves privadas o frases semilla, recomendamos crear nuevas billeteras mediante extensiones de billetera de escritorio para puentear.
2.  **¿Por qué una ruta o token no está disponible?**

    Algunas rutas dependen de la capacidad del puente, el soporte de tokens o la liquidez. Por favor, vuelve a intentarlo más tarde o prueba con un proveedor diferente. Los tokens disponibles por cadena se muestran directamente en la interfaz del Puente.
3.  **Recibo un error al enviar la transacción de puenteo.**

    Intenta ingresar el monto manualmente en lugar de usar el botón "MAX", y elimina los decimales del monto si es necesario.
4.  **¿Por qué mi cotización de puenteo muestra "Insufficient X to cover native fee"?**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    El puenteo requiere comisiones de gas pagadas en el token nativo de la cadena de origen, por ejemplo:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    Asegúrate de tener suficientes tokens nativos en tu billetera de origen para cubrir las comisiones y completar la transacción.
5.  **¿Por qué el botón muestra "X CAKE Exceeded"?**

    Hay un límite de capacidad diaria para puentear CAKE entre BSC y Aptos para garantizar la seguridad. Intenta con un monto menor o espera y vuelve a intentarlo más tarde. Los límites son ajustados dinámicamente por los Chefs según la demanda.
6.  **¿Por qué no puedo encontrar un token específico?**

    Es posible que el token no sea compatible con tu ruta elegida o que carezca de liquidez. Prueba con otra cadena o un monto diferente.
7.  **¿Puedo puentear desde BNB Chain a Ethereum pero a una dirección diferente?**

    No, por razones de seguridad, el puenteo solo funciona entre la misma dirección en cadenas EVM.
8.  **¿Por qué no puedo puentear menos de 0.00000001 CAKE?**

    Los tokens de Aptos, incluido CAKE en Aptos, tienen un máximo de 8 decimales. Las transacciones por debajo de 0.00000001 serán rechazadas o redondeadas hacia abajo. Esto también aplica al puenteo de Ethereum. Cualquier monto restante permanece en tu billetera de origen.

***

## Después de puentear

1.  **¿Puedo cancelar una transferencia de puente después de confirmarla?**

    No, una vez iniciada, la transacción del puente es manejada por el proveedor y no puede cancelarse. Para revertir, puentea los activos de vuelta mediante una nueva transacción.
2.  **¿Qué pasa si mi transacción está atascada como "pendiente"?**

    El puenteo puede tardar hasta 30 minutos. Verifica el estado de tu transacción buscando su hash en el explorador del proveedor del puente correspondiente:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    Si sigue pendiente después de 60 minutos, comunícate con nuestros administradores a través de los [canales sociales](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
3. **No he recibido mi CAKE. ¿Qué debo hacer?**
   * Al puentear CAKE a Aptos por primera vez, es posible que necesites **reclamar tu CAKE manualmente**. Asegúrate de que tu billetera de Aptos tenga suficiente APT para gas. Consulta la [guía de puenteo de Aptos](https://docs.pancakeswap.finance/bridge/bridging/aptos) y la [explicación de Aptos](https://theaptosbridge.com/faq#registering-claiming-assets).
   * Al puentear a BNB Chain o Ethereum, algunas billeteras requieren que agregues manualmente la dirección del token de CAKE para ver tu saldo. Por ejemplo, sigue esta [guía de MetaMask](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/); otras billeteras deberían tener flujos similares.
   * Si aún no ves tu CAKE después de 60 minutos, comunícate con nuestros administradores a través de los [canales sociales](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
