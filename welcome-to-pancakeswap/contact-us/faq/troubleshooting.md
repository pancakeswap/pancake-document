---
description: Mensajes de error comunes. Usa la barra lateral ➡️ para ir al error que estás viendo.
---

# Solución de Errores

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

A veces puedes encontrarte con un problema que no tiene una solución clara. Estos consejos de solución de problemas pueden ayudarte a resolver los problemas que encuentres.

## **Problemas en el Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> La transacción no puede tener éxito debido al error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. Probablemente sea un problema con uno de los tokens que estás intercambiando.
>
> la transacción no puede tener éxito debido al error: execution reverted: pancakerouter: insufficient\_output\_amount.

Estás intentando intercambiar tokens, pero tu tolerancia al deslizamiento es demasiado baja o la liquidez es demasiado baja.

{% tabs %}
{% tab title="Solución" %}
1. Actualiza tu página e inténtalo de nuevo más tarde.
2. Intenta intercambiar una cantidad menor a la vez.
3. Aumenta tu tolerancia al deslizamiento:
   1. Toca el ícono de configuración en la página de liquidez.
   2. Aumenta un poco tu tolerancia al deslizamiento e inténtalo de nuevo. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. Por último, intenta ingresar una cantidad con menos decimales.
{% endtab %}

{% tab title="Razón" %}
**Esto suele suceder cuando se intercambian tokens con poca liquidez.**

Eso significa que no hay suficiente cantidad de uno de los tokens que intentas intercambiar en el Pool de Liquidez: probablemente sea un token de pequeña capitalización que pocas personas están negociando.

Sin embargo, también existe la posibilidad de que estés intentando intercambiar un token estafa que no puede venderse. En este caso, PancakeSwap no puede bloquear un token ni devolver fondos.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT o INSUFFICIENT\_B\_AMOUNT**

> Error con 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> o\
> Error con 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Estás intentando agregar/eliminar liquidez de un pool de liquidez (LP), pero no hay suficiente cantidad de uno de los dos tokens del par.

{% tabs %}
{% tab title="Solución" %}
**Actualiza tu página e inténtalo de nuevo, o inténtalo más tarde.**

¿Sigue sin funcionar?

1. Toca el ícono de configuración en la página de liquidez.
2. Aumenta un poco tu tolerancia al deslizamiento e inténtalo de nuevo.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="Razón" %}
El error se produce al intentar agregar o eliminar liquidez de un pool de liquidez (LP) con una cantidad insuficiente del token A o del token B (uno de los tokens del par).

Puede ser que los precios se estén actualizando demasiado rápido y tu tolerancia al deslizamiento sea demasiado baja.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solución para expertos" %}
De acuerdo, estás muy decidido/a a solucionar esto. Realmente no recomendamos hacer esto a menos que sepas lo que estás haciendo.

Actualmente no hay una forma sencilla de resolver este problema desde el sitio web de PancakeSwap: necesitarás interactuar con el contrato directamente. Puedes agregar liquidez directamente a través del contrato Router, mientras estableces amountAMin en una cantidad pequeña, y luego retirar toda la liquidez.

**Aprobar el contrato LP**

Ve al contrato del token LP que estás intentando aprobar.\
Por ejemplo, aquí está el par ETH/WBNB: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Selecciona **Write Contract**, luego **Connect to Web3** y conecta tu billetera. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. En la **sección "1. approve",** aprueba el token LP para el router ingresando
   1. spender (address): ingresa la dirección del contrato del token LP con el que intentas interactuar
   2. value (uint256): -1

**Consultar "balanceOf"**

1. Cambia a **Read Contract.**
2. En **5. balanceOf**, ingresa la dirección de tu billetera y haz clic en **Query**.
3. Anota el número que se exporta. Muestra tu saldo dentro del LP en formato uint256, que necesitarás en el siguiente paso.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**Agregar o Eliminar Liquidez**

Ve al contrato del router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Selecciona **Write Contract** y **Connect to Web3** como antes.
2. Encuentra **addLiquidity** o **removeLiquidity** (el que estés intentando hacer)
3. Ingresa las direcciones de los tokens de ambos tokens del LP.
4. En **liquidity (uint256),** ingresa el número uint256 que obtuviste de "balanceOf" arriba.
5. Establece un **amountAMin** o **amountBMin** bajo: prueba con 1 para ambos.
6. Agrega la dirección de tu billetera en **to (address)**.
7. El plazo debe ser un tiempo epoch mayor que el tiempo de ejecución de la transacción.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
Esto puede causar un deslizamiento muy alto y puede hacer que el usuario pierda algunos fondos si es víctima de frontrunning
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> La transacción no puede tener éxito debido al error: PancakeRouter: EXPIRED. Probablemente sea un problema con uno de los tokens que estás intercambiando.

Inténtalo de nuevo, pero confirma (firma y emite) la transacción tan pronto como la generes.

Esto ocurrió porque comenzaste a realizar una transacción, pero no la firmaste ni la emitiste hasta que pasó el plazo. Eso significa que no hiciste clic en "Confirmar" lo suficientemente rápido.

### Pancake: K

> La transacción no puede tener éxito debido al error: Pancake: K. Probablemente sea un problema con uno de los tokens que estás intercambiando.

Intenta modificar la cantidad en el campo "A" (destino). Por lo tanto, coloca el símbolo "(estimado)" en "De" (origen). Luego inicia el intercambio de inmediato.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

Esto suele suceder cuando intentas intercambiar un token con su propia comisión.

### Pancake: TRANSFER\_FAILED

> La transacción no puede tener éxito debido al error: execution reverted: Pancake: TRANSFER\_FAILED.

Asegúrate de tener un 30% más de tokens en tu billetera de los que pretendes intercambiar, o intenta intercambiar una cantidad menor. Si quieres vender el máximo posible, prueba con el 70% o el 69% en lugar del 100%.\
Causado por el diseño de tokens Restorative Rebase como tDoge o tBTC.\
[Entiende cómo funcionan los tokens de rebase restaurativos](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Otra posible causa de este problema es que el emisor malicioso del token simplemente suspendió el trading de su token. O hizo posible la acción de venta solo para direcciones de billetera seleccionadas. Siempre haz tu propia investigación para evitar cualquier posible fraude. Si el token que intentas intercambiar pero falló con este código de error proviene de un airdrop, lo más probable es que sea una estafa. Por favor, no realices ninguna aprobación de token ni sigas ningún enlace, tus fondos pueden estar en riesgo si lo haces.

### La transacción no puede tener éxito

Intenta intercambiar una cantidad menor, o aumenta la tolerancia al deslizamiento a través del ícono de configuración e inténtalo de nuevo. Esto es causado por baja liquidez.

### **Impacto en el Precio demasiado Alto**

Intenta intercambiar una cantidad menor, o aumenta la tolerancia al deslizamiento a través del ícono de configuración e inténtalo de nuevo. Esto es causado por baja liquidez.

### estimateGas failed

> Esta transacción fallaría. Por favor, comunícate con soporte

{% tabs %}
{% tab title="Solución" %}
**Si obtienes este error al eliminar liquidez de un par BNB:**

Por favor, selecciona "Receive WBNB" e inténtalo de nuevo.

**Si obtienes este error al intentar intercambiar:**

Por favor, comunícate con el equipo del proyecto del token que intentas intercambiar. \*\*\*\* Este problema debe ser resuelto por el equipo del proyecto.
{% endtab %}

{% tab title="Razón" %}
**Este problema (al intercambiar) es causado por tokens que han codificado de forma fija el router V1 de PancakeSwap en su contrato.**

Si bien esta práctica es desaconsejable en el mejor de los casos, la razón por la que estos proyectos parecen haberlo hecho se debe a su Tokenomics, en el que cada compra envía un % del token a los LPs.

Los proyectos afectados probablemente no funcionarán con el router V2: lo más probable es que necesiten crear nuevas versiones de sus tokens apuntando a nuestra nueva dirección del router y migrar a los titulares de tokens existentes a su nuevo token.

Recomendamos que cualquier proyecto que haya creado tales tokens también haga esfuerzos para evitar que sus usuarios los agreguen al LP de V2.

La dirección actualizada del router es [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

Al intentar intercambiar tokens, la transacción falla y se muestra este mensaje de error. Este error ha sido reportado en dispositivos móviles que usan Trust Wallet.

{% tabs %}
{% tab title="Solución" %}
1. Intenta la transacción nuevamente con un mayor margen de deslizamiento.
2. Si 1. no resuelve tu problema, considera usar otra billetera como SafePal para tu transacción.
{% endtab %}

{% tab title="Razón" %}
**Esto suele suceder cuando se intercambian tokens con margen de deslizamiento insuficiente en Trust Wallet.**

Los detalles exactos del problema aún están siendo investigados.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> La transacción no puede tener éxito debido al error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Al intentar intercambiar tokens, la transacción falla y se muestra este mensaje de error. Este error ha sido reportado en varias plataformas.

{% tabs %}
{% tab title="Solución" %}
1. Verifica que tengas fondos suficientes disponibles.
2. Asegúrate de haber otorgado al contrato el permiso para gastar la cantidad de fondos con los que intentas intercambiar.
{% endtab %}

{% tab title="Razón" %}
Este error ocurre cuando se intercambian tokens con permiso insuficiente, o cuando una billetera tiene fondos insuficientes.\
Si estás intercambiando tokens con Restorative Rebase como los activos tau tDoge o tBTC, asegúrate de entender cómo funcionan primero con esta [guía de tokens Rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

## **Problemas con los Farms**

### Error con 'ds-math-sub-underflow'

Se te ha agotado el permiso de tu LP token para el contrato MasterChef.

**Usa un gestor de aprobación de tokens como unrekt o BscScan para**

## **Problemas con los Syrup Pools**

### BEP20: burn amount exceeds balance

> Error con 'BEP20: burn amount exceeds balance'

No tienes suficiente SYRUP en tu billetera para retirar del pool CAKE-CAKE.

**Obtén al menos tanto SYRUP como la cantidad de CAKE que intentas retirar.**

1. Compra SYRUP en el exchange. Si quieres retirar 100 CAKE, necesitas al menos 100 SYRUP.
2. Intenta retirar de nuevo.

Si eso sigue fallando, puedes realizar un "emergencyWithdraw" directamente desde el contrato para retirar tus tokens apostados.

1. Ve a: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Haz clic en **"Connect to Web3"** y conecta tu billetera. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. En la sección **"4. emergencyWithdraw"**, ingresa "0" y haz clic en "Write".

Esto retirará tus tokens apostados y perderás cualquier rendimiento de CAKE no recolectado.

{% hint style="warning" %}
**Esto perderá cualquier rendimiento que no hayas cosechado todavía.**
{% endhint %}

Para evitar que esto suceda de nuevo, **no vendas tu SYRUP.** Aún lo necesitas para retirar del pool "Stake CAKE Earn CAKE".

Este error ocurrió porque vendiste o transferiste tokens SYRUP. SYRUP se acuña en una proporción 1:1 con CAKE cuando haces Staking en el Syrup Pool CAKE-CAKE. SYRUP debe quemarse en una proporción 1:1 con CAKE al llamar a leaveStaking (retirar tu CAKE del pool), por lo que si no tienes suficiente, no puedes retirarte del pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Error de Sin Gas

> ¡Advertencia! Error encontrado durante la ejecución del contrato \[out of gas]

Has establecido un límite de gas bajo al intentar realizar una transacción.

{% tabs %}
{% tab title="Solución" %}
Intenta aumentar manualmente el **límite de gas** (¡no el precio del gas!) en tu billetera antes de firmar la transacción.

Un límite de 200000 suele ser suficiente.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

El ejemplo anterior es de Metamask; consulta la documentación de tu billetera si no estás seguro/a de cómo ajustar el límite de gas.
{% endtab %}

{% tab title="Razón" %}
Básicamente, tu billetera (Metamask, Trust Wallet, etc.) no puede terminar lo que está intentando hacer.

Tu billetera estima que el límite de gas es demasiado bajo, por lo que la llamada a la función se queda sin gas antes de que termine.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Error con 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Solución" %}
1. Usa Unrekt.net para revocar el permiso para el contrato inteligente con el que estás intentando interactuar
2. Aprueba el contrato nuevamente, sin establecer un límite en el permiso de gasto
3. Intenta interactuar con el contrato nuevamente.
{% endtab %}

{% tab title="Razón" %}
Esto sucede cuando estableces un límite en tu permiso de gasto cuando apruebas el contrato por primera vez, y luego intentas intercambiar más del límite.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Error con 'BEP20: transfer amount exceeds balance'

Probablemente estés intentando retirar de un Syrup Pool con pocas recompensas en él. Solución a continuación.

Si no, puede que estés intentando enviar tokens que no tienes en tu billetera (por ejemplo, intentando enviar un token que ya está asignado a una transacción pendiente). En este caso, simplemente asegúrate de tener los tokens que estás intentando usar.

{% tabs %}
{% tab title="Solución" %}
Primero,[ informa al equipo](../social-accounts.md) de qué pool estás intentando retirar, para que puedan recargar las recompensas. Si tienes prisa por retirar y no te importa perder tu rendimiento pendiente, prueba con un emergencyWithdraw:

Puedes realizar un "emergencyWithdraw" directamente desde el contrato para retirar tus tokens apostados.

1. Encuentra la dirección del contrato del Syrup Pool del que estás intentando retirar. Puedes encontrarla en el registro de transacciones de tu billetera.
2. Ve a [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) y en la barra de búsqueda, ingresa la dirección del contrato.
3. Selecciona **Write Contract.**
4. Haz clic en **"Connect to Web3"** y conecta tu billetera.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. En la sección **"3. emergencyWithdraw",** haz clic en "Write".

Esto retirará tus tokens apostados y perderás cualquier rendimiento no recolectado.

{% hint style="warning" %}
**Esto perderá cualquier rendimiento que no hayas cosechado todavía.**
{% endhint %}
{% endtab %}

{% tab title="Razón" %}
Este error tiende a aparecer cuando intentas retirar de un Syrup Pool antiguo, pero no quedan suficientes recompensas en el pool para que las cosechas al retirar. Esto hace que la transacción falle.
{% endtab %}
{% endtabs %}

## **Problemas con Prediction**

Consulta [Enlace roto](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")

## **Otros problemas**

### Error de Proveedor

> Error de Proveedor\
> No se encontró ningún proveedor

Esto sucede cuando intentas conectarte a través de una extensión de navegador como MetaMask o Binance Chain Wallet, pero no has instalado la extensión.

{% tabs %}
{% tab title="Solución" %}
Instala la extensión oficial del navegador para conectarte, o lee nuestra guía sobre [cómo conectar una billetera a PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide).
{% endtab %}
{% endtabs %}

### ID de Cadena No Soportado

Cambia tu cadena a BNB Smart Chain. Consulta la documentación de tu billetera si necesitas ayuda.

### Already processing eth\_requestAccounts. Please wait.

Asegúrate de haber iniciado sesión en tu aplicación de billetera y de estar conectado/a a BNB Smart Chain.

### Problemas comprando SAFEMOON y tokens similares

Para intercambiar SAFEMOON, debes hacer clic en el ícono de configuración y **establecer tu tolerancia al deslizamiento al 12% o más.**\
Esto se debe a que **SafeMoon cobra una comisión del 10% en cada transacción**:

* 5% de comisión = redistribuida a todos los titulares existentes
* 5% de comisión = utilizada para agregar liquidez

Esta es también la razón por la que es posible que no recibas tanta cantidad del token como esperas al comprarlo.\
Lee más en [Cómo Comprar Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Errores internos JSON-RPC

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Ocurre al intentar eliminar liquidez en algunos tokens a través de Metamask. La causa raíz aún es desconocida. Intenta usar una billetera alternativa.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Por favor, inténtalo de nuevo.

No tienes suficiente BNB para pagar las tarifas de transacción. Necesitas más BNB de la red BEP-20 en tu billetera.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Aumenta el límite de gas para la transacción en tu billetera. Consulta la documentación de tu billetera para aprender a aumentar el límite de gas.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Causa no clara. Prueba estos pasos antes de intentarlo de nuevo:

1. Aumenta el límite de gas
2. Aumenta el deslizamiento
3. Borra la caché

## **Problemas con el Perfil**

### ¡Vaya! No pudimos encontrar ningún Pancake Collectible en tu billetera.

Estamos investigando la lógica detrás de este problema. Mientras tanto, prueba la solución alternativa.

{% tabs %}
{% tab title="Solución alternativa 1" %}
1. Ve a la página "Collectible", luego vuelve a la página de perfil.\
   Si no puedes encontrar el enlace, ve directamente a [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles).
2. Vuelve a intentar crear el perfil.
{% endtab %}

{% tab title="Solución alternativa 2" %}
Cambia el entorno.

* Borra la caché e inténtalo de nuevo.
* Inténtalo de nuevo en un navegador diferente.
* Inténtalo de nuevo en diferentes aplicaciones de billetera.
* Inténtalo de nuevo en una red diferente (cambia entre Wi-Fi y datos móviles)
{% endtab %}
{% endtabs %}

### La verificación del nombre de usuario sigue girando

Hay dos posibles causas.

1. Tienes múltiples billeteras instaladas en el navegador.
2. Problema de red.

{% tabs %}
{% tab title="Solución 1" %}
Causa raíz: Tienes múltiples billeteras instaladas en el navegador.\
\
Puede crear un conflicto entre billeteras. Esto está fuera del control de PancakeSwap y no podemos hacer nada.

1. Tiene solo una billetera instalada en el navegador, elimina las demás.
2. Vuelve a conectar la billetera e intenta configurar el nombre de usuario de nuevo.
{% endtab %}

{% tab title="Solución 2" %}
Causa raíz: La red es inestable.

Tienes que volver a intentarlo.

1. Elimina completamente lo que se haya ingresado en el campo de texto.
2. Vuelve a escribir el nombre de usuario, luego espera unos segundos.
3. Si no funciona, recarga la página e inténtalo de nuevo.
{% endtab %}
{% endtabs %}
