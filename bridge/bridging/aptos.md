---
description: Puentea CAKE entre cadenas EVM y Aptos
---

# Cómo puentear - EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
La siguiente guía usa BNB Chain como ejemplo de cadena EVM. El mismo proceso puede aplicarse a Ethereum.
{% endhint %}

## Puentea CAKE de BNB Smart Chain a Aptos

1 - Asegúrate de que tu billetera sea compatible con BNB Smart Chain y Aptos Mainnet. O que tengas ambas billeteras instaladas en tu navegador.

Luego abre el [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Primero, necesitamos conectar nuestra billetera de BNB Smart Chain.

Haz clic en "Connect" y elige la billetera que prefieras en la sección "EVM". Luego confirma y aprueba en la ventana emergente de tu billetera.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Luego, necesitamos conectar nuestra billetera de Aptos.

En el modal de conexión de billetera, elige la billetera que prefieras en la sección "Aptos". Luego confirma y aprueba en la ventana emergente de tu billetera.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Haz clic en la "v" en el campo de selección de token superior y elige "CAKE".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - Ingresa la cantidad de CAKE que deseas puentear a Aptos.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Si tu billetera de Aptos es nueva y no tiene saldo de APT (Aptos Coin), te recomendamos mantener la opción "gas on destination" en su valor predeterminado. El puente depositará una pequeña cantidad de APT en tu billetera, no solo para ayudarte a comenzar tu camino en Aptos, sino que también necesitarás APT para gas y así registrar y reclamar tu CAKE puenteado.

Modificar esta opción podría causar que el puenteo falle.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - Haz clic en "Transfer" para iniciar la transacción de puenteo y confirma mediante la ventana emergente de confirmación de tu billetera.

Ten en cuenta que, dependiendo del estado de tu billetera de BNB Smart Chain y tu billetera de Aptos, es posible que necesites aprobar **múltiples** confirmaciones de billetera. Por ejemplo, si puenteas CAKE a Aptos por primera vez, necesitarás:

* Aprobar el gasto de CAKE en el contrato de puenteo (desde tu billetera de BNB Smart Chain)
* Registrar CAKE (desde tu billetera de Aptos)

Para más detalles, consulta [este desglose](aptos.md#bridging-cake-to-aptos-for-the-first-time).

8 - Relájate. Solo tomará unos pocos minutos. Una vez completado el puenteo, CAKE se depositará en tu billetera de Aptos. Puedes hacer seguimiento del progreso mediante la barra de progreso.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## Puentear CAKE a Aptos por primera vez

Puentear CAKE a billeteras de Aptos requiere transacciones de registro y reclamación. Esto se hace para mejorar la seguridad del usuario y es exclusivo de Aptos.

### **Si ya tienes APT (Aptos Coin) en tu billetera:**

Se te pedirá que registres CAKE en tu billetera de Aptos si aún no está registrado. En este caso no se necesita ninguna transacción de reclamación adicional.

### **Si no tienes APT (Aptos Coin) en tu billetera:**

Después de que se complete la transacción del puente, deberás reclamar tu CAKE manualmente. Para cubrir las comisiones de gas del reclamo, se enviarán tokens APT a tu billetera de Aptos desde tu billetera de origen.

Estos pasos de registro y reclamación solo aplican la primera vez que interactúas con un token en Aptos. Las transferencias posteriores del mismo token no requerirán estas acciones.

Antes de puentear CAKE a Aptos por primera vez, asegúrate de que tu dirección de Aptos tenga suficiente APT para comisiones de gas. Para más detalles, consulta la explicación de Aptos aquí: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Puentea CAKE de Aptos a BNB Smart Chain

1 - Asegúrate de que tu billetera sea compatible con BNB Smart Chain y Aptos Mainnet. O que tengas ambas billeteras instaladas en tu navegador.

Luego abre el [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Primero, necesitamos conectar nuestra billetera de BNB Smart Chain.

Haz clic en "Connect" y elige la billetera que prefieras en la sección "EVM". Luego confirma y aprueba en la ventana emergente de tu billetera.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Luego, necesitamos conectar nuestra billetera de Aptos.

En el modal de conexión de billetera, elige la billetera que prefieras en la sección "Aptos". Luego confirma y aprueba en la ventana emergente de tu billetera.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Haz clic en la "v" en el campo de selección de token superior y elige "CAKE". Luego haz clic en el botón de doble flecha en el centro de la página para invertir la dirección del puenteo.

Asegúrate de que la red "Aptos" esté en el campo superior.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - Ingresa la cantidad de CAKE que deseas puentear a BNB Smart Chain.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - Si tu billetera de BNB Smart Chain es nueva y no tiene saldo de BNB (token de gas), te recomendamos mantener la opción "gas on destination" en su valor predeterminado. El puente depositará una pequeña cantidad de BNB en tu billetera. Te ayudará a comenzar tu camino en BNB Smart Chain y explorar el vibrante ecosistema de PancakeSwap.

7 - Haz clic en "Transfer" y aprueba las transacciones desde la ventana emergente de tu billetera.

8 - Relájate. Solo tomará unos pocos minutos. Una vez completado el puenteo, CAKE se depositará en tu billetera de BNB Smart Chain. Puedes hacer seguimiento del progreso mediante la barra de progreso.
