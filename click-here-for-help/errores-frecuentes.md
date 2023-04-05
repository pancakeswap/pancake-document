---
description: >-
  Mensajes de error comunes. Use la barra lateral➡️ para saltar al error que
  necesita ver.
---

# Errores Frecuentes

![](../.gitbook/assets/problemas-frecuentes.png)

A veces estamos frente a un problema que no parece tener una solución clara. Esperamos que estos tips frente a problemas frecuentes puedan ayudarte a solucionarlo.

## **Problemas en el Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**&#x20;

> The transaction cannot succeed due to error:  PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.&#x20;

> La transacción no pudo realizarse debido al error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. (Probablemente sea un problema con uno de los tokens que está intercambiando)

Está intentando intercambiar tokens, pero su tolerancia al deslizamiento (Slippage) es demasiado baja o la liquidez es demasiado poca.

{% tabs %}
{% tab title="Solución" %}
1. Actualice la página e intente de nuevo más tarde.
2. Pruebe intercambiando montos más pequeños de a una vez.
3. Aumente su tolerancia al deslizamiento (Slippage):
   1. Toque el icono de configuración en la página de liquidez.
   2. Aumente un poco su deslizamiento (Slippage) e intente de nuevo.\
      ![](<../.gitbook/assets/image (9) (4) (2) (4).png>)
4. Por último, intente ingresar una cantidad con menos valores decimales.
{% endtab %}

{% tab title="Razón" %}
**Esto pasa usualmente cuando estás intentando intercambiar tokens con baja liquidez.**

Esto significa que no hay suficiente cantidad de uno de los tokens que estás intentando intercambiando en el Pool de liquidez: es probablemente un token de baja capitalización que pocas personas están intercambiando.

Sin embargo, también existe la posibilidad que estés intentando intercambiar un token malicioso que no puede venderse. En este caso, PancakeSwap no puede bloquear un token ni devolver los fondos.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**&#x20;

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Estás tratando de agregar / remover liquidez de un Pool de Liquidez (LP), pero no hay suficiente de uno de los dos tokens en el par.

{% tabs %}
{% tab title="Solución" %}
**Actualice la página e intente de nuevo, o intente de nuevo más tarde.**

Aún no funciona?

1. Toque el icono de configuración en la página de liquidez.
2. Aumente un poco su deslizamiento (Slippage) e intente de nuevo.

![](<../.gitbook/assets/image (9) (4) (2) (4).png>)
{% endtab %}

{% tab title="Razón" %}
Este error es causado al tratar de agregar o remover liquidez de un Pool de Liquidez (LP) con una cantidad insuficiente del token A o el token B (uno de los tokens del par).

Puede darse el caso de que los precios se actualicen demasiado rápido y su tolerancia al deslizamiento (Slippage) sea demasiado baja.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs\_pxdobz\_kY\_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)



![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt\_FAwpEylaIJhff5ZcYlzB\_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solución para nerds" %}
OK, estás realmente decidido a resolver esto. No recomendamos realmente hacer esto a menos que sepas lo que estás haciendo.&#x20;

Actualmente, no existe una forma sencilla de resolver este problema desde el sitio web de PancakeSwap: vas a necesitar interactuar directamente con el contrato. Puedes agregar liquidez directamente a través del contrato del Router, mientras estableces en "amountAMin" una pequeña cantidad, entonces podrás retirar toda la liquidez.

### **Aprobar el contrato LP**

Dirígete al contrato del token LP que estás intentando aprobar. Por ejemplo, de ejemplo está el par ETH / WBNB: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Selecciona **Write Contract**, luego **Connect to Web3** y conecta tu wallet\
   <img src="https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME" alt="" data-size="original">
2. En **la sección"1. approve",** aprueba el LP token del Router ingresando:
   1. spender (address): ingrese la dirección del contrato del token LP con el que está tratando de interactuar.
   2. value (uint256): -1

### Consulta "balanceOf"

1. Cambia a **Read Contract.**
2. En la sección **5. balanceOf**, ingresa tu dirección de la wallet y presiona **Query**.
3. Anota el número que se exporta. Este muestra tu saldo dentro del LP en formato uint256, que necesitarás en el siguiente paso.&#x20;

![](<../.gitbook/assets/image (32).png>)

### Agregar o Remover Liquidez

Dirígete al contrato del Router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Selecciona **Write Contract** y **Connect to Web3** como antes.
2. Encuentra **addLiquidity** o **removeLiquidity** (lo que sea que estés tratando de hacer)
3. Ingresa las direcciones de contrato de ambos tokens del LP.
4. En **liquidity (uint256),** ingresa el número en formato uint256 que obtuviste de "balanceOf" anteriormente.
5. Establece un bajo **amountAMin** o **amountBMin**: prueba 1 para ambos.
6. Agrega la dirección de tu billetera en **to (address)**.
7. Deadline debe ser un tiempo de epoch mayor que el tiempo en que se ejecuta el transacción.&#x20;

![](<../.gitbook/assets/image (19).png>)

{% hint style="warning" %}
Esto puede causar un muy alto deslizamiento (Slippage), y causar que el usuario pierda algunos fondos si realiza Frontrun.&#x20;
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED&#x20;

> The transaction cannot succeed due to error:  PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.&#x20;

Intente de nuevo, pero confirme (firma y emisión) la transacción al momento que esta se genera.

Esto sucedió porque comenzó a realizar una transacción, pero no la firmó ni la emitió hasta que pasó la fecha límite. Eso significa que no presionó "Confirmar" lo suficientemente rápido.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Intente modificar la cantidad en el campo "To". Luego de modificarlo, deberías ver el símbolo "(estimated)" en "From". A continuación, procede hacer el intercambio inmediatamente.

<figure><img src="https://lh4.googleusercontent.com/NO9ktK8MzJ3DGNvYdqJXgsQ3TKXDIYsszlUv50txmQOAaWxLN3m5s1XzvCLMsa0i6BmXFCereM4H7VbSbvffmVjfwCUP8O9xHzceB12KRDZ0Cl4PHo_ZOgjGMbJ6iEin2DdCjRLc6Grnpe_7yXWGXjdhOHlf_aIdg6FrU3lstT4eUbxHwIH6YZKDn4Mmmg" alt=""><figcaption></figcaption></figure>

Esto suele suceder cuando intentas intercambiar un token con un fee interno o propio.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

Asegúrese de tener un 30% más de tokens en su billetera de los que pretende intercambiar, o intente intercambiar una cantidad menor. Si quieres vender el máximo posible, prueba con el 70% o el 69% en lugar del 100%. Esto debido al diseño de los tokens con Rebase Restaurativa como tDoge o tBTC.[ Guia en ingles sobre este tema](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Otra posible causa de este problema es que el emisor del token malicioso acaba de suspender el comercio de su token o hicieron que la acción de venta solo fuera posible para algunas wallets seleccionadas. Por favor, siempre haga su propia investigación para evitar cualquier posible fraude. Si el token que está intentando intercambiar falló con este código de error y proviene de un airdrop, lo más probable es que sea una estafa. Por favor, no realice ninguna aprobación de contrato importante ni siga ningún enlace, sus fondos puede estar en riesgo si intenta hacerlo.

### Transaction cannot succeed

Intente operar una cantidad menor o aumente el slippage a través del icono de configuración e inténtelo de nuevo. Esto es causado por la baja liquidez del token.

### Price Impact muy alto

Intente operar una cantidad menor o aumente el slippage a través del icono de configuración e inténtelo de nuevo. Esto es causado por la baja liquidez del token.

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Solución" %}
Si recibió este error al eliminar la liquidez de un par BNB:

Seleccione "Receive WBNB" y vuelva a intentarlo.

Si recibió este error al intentar hacer un swap:

Ponte en contacto con el equipo del proyecto del token que estás intentando intercambiar.

\*\*\* Este problema debe ser resuelto por el equipo del proyecto.
{% endtab %}

{% tab title="Razón" %}
Este problema (durante el intercambio) es causado por tokens que en su contrato han sido hard-codeados en el router V1 (version antigua) de PancakeSwap.

Si bien esta práctica es desacertada en el mejor de los casos, la razón por la que estos proyectos han hecho esto parece deberse a su tokenomics, en la que cada compra envía un % del token a los LP.

Es probable que los proyectos afectados no funcionen con el router V2: lo más probable es que necesiten crear nuevas versiones de sus tokens que apunten a nuestra nueva dirección del router y migrar cualquier titular de token existente a su nuevo token.

Recomendamos que cualquier proyecto que haya creado dichos tokens también haga esfuerzos para evitar que sus usuarios los agreguen a un LP v2.

La dirección del router actualizada es[ https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}





### “Cannot read property 'toHexString' of undefined”

> "Unknown error: "Cannot read property 'toHexString' of undefined”

Al intentar intercambiar tokens, la transacción falla y se muestra este mensaje de error. Este error se ha informado en dispositivos móviles usando Trust Wallet.

{% tabs %}
{% tab title="Solución" %}
1. Intente la transacción de nuevo pero aumentando el slippage.
2. Si el paso anterior no resuelve su problema, considere usar otra billetera como SafePal.
{% endtab %}

{% tab title="Razón" %}
Esto suele suceder cuando se intercambian tokens con un slippage insuficiente en Trust Wallet.

Los detalles exactos del problema aún se están investigando.
{% endtab %}
{% endtabs %}

### Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Al intentar intercambiar tokens, la transacción falla y se muestra este mensaje de error. Este error se ha notificado en todas las plataformas.

{% tabs %}
{% tab title="Solución" %}
1. Verifique que tenga fondos suficientes.
2. Asegúrese de haber aprobado el contrato del token y haber asignado o permitido una cantidad igual o mayor de fondos de los que está intentando operar.
{% endtab %}

{% tab title="Razón" %}
Este error ocurre cuando se intercambian tokens con una asignación insuficiente cuando se aprueba el contrato, o cuando una billetera no tiene fondos suficientes. Si está intercambiando tokens con [Restorative Rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c) como tDoge o tBTC, asegúrese de comprender cómo funcionan primero con esta[ guía.](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c)
{% endtab %}
{% endtabs %}

## Problemas con los Farms

### Falla con el error 'ds-math-sub-underflow'

Se ha quedado sin asignación o permiso asignado en la aprobación del contrato del token LP del MasterChef.

Utilice el administrador de aprobación de tokens como unrekt o BscScan para modificar la asignación y aumentarla.

## **Problemas con los Syrup Pools**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'
>
> Error con "BEP20: la cantidad quemada excede el saldo"

No tienes suficientes SYRUP en tu wallet para hacer Unstake del CAKE-CAKE pool.

{% tabs %}
{% tab title="Solución 1" %}
**Obtenga tanto SYRUP como la cantidad de CAKE que está intentando retirar.**

1. Puede comprar SYRUP en el exchange. Si quieres retirar 100 CAKE, necesitarás 100 SYRUP.
2. Prueba hacer Unstake otra vez.
{% endtab %}

{% tab title="Solución 2" %}
Si sigue fallando, puedes intentar un  “emergencyWithdraw”  (Retiro de emergencia) directamente desde el contrato donde estaban stakeados los tokens.

1. Ir a: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract ](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Click en **“Connect to Web3”** y conecta tu wallet.\
   <img src="https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME" alt="" data-size="original">
3. En la sección **“4. emergencyWithdraw”**, ingresa "0" y haz click en “Write”.

Esto retirará tus tokens en stake pero se perderá cualquier CAKE que no se haya cosechado.

{% hint style="warning" %}
**Esto perderá cualquier recompensa que aún no haya cosechado.**
{% endhint %}
{% endtab %}

{% tab title="Razón" %}
Para que esto no vuelva a pasar, **no vendas tus SYRUP.** Los vas a retirar para retirar los CAKE del “Stake CAKE Earn CAKE” pool.

Este error ha aparecido porque has vendido o transferido los SYRUP tokens. Los SYRUP son creados en un ratio 1:1 ratio con CAKE cuando los depositas en el CAKE-CAKE Syrup Pool. Los SYRUP deben ser quemados al mismo ratio 1:1 ratio con CAKE cuando llamamos a la función leaveStaking (retirar nuestras CAKE del Pool), entonces si no tienes suficientes, no podrás hacer Unstake del pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}



![](https://lh4.googleusercontent.com/KchAcnM6cpX2BotEGppAxPAnY4Xbona6yI6ZWg9FlUUBfPi\_YO9ulM1s6htXJVXMzEwl0Uxcvdk8o4yhI7ar5g0TRpLVFjkS4YLKL7FS8Z4uFqeC37sw-TIkrPr7BCZQVpuD-5jO)
{% endtab %}
{% endtabs %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas]
>
> ¡Advertencia! Error encontrado durante la ejecución del contrato \[sin gas]

El problema es que se estableció un límite de gas bajo al intentar realizar una transacción.

{% tabs %}
{% tab title="Solución" %}
Intenta aumentar manualmente el **gas limit** (no el gas price!) en tu wallet, antes de firmar la transacción.

Un límite de gas (Gas Limit) en 200000 usualmente es suficiente

![](<../.gitbook/assets/image (169).png>)

El ejemplo de arriba es en Metamask; echa un vistazo a los docs de tu wallet si no estás seguro cómo ajustar el gas limit.
{% endtab %}

{% tab title="Razón" %}
Básicamente, tu wallet (Metamask, Trust Wallet, etc.) no pudo finalizar lo que intentó hacer.&#x20;

Su billetera estima que el límite de gas es demasiado bajo, por lo que la llamada a la función se queda sin gas antes de que finalice la misma.\

{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'
>
> Error: "BEP20: el monto de la transferencia excede el saldo"

Estás tratando de hacer Unstake de un Pool que tiene pocas rewards en él.

{% tabs %}
{% tab title="Solución" %}
Puedes intentar un “emergencyWithdraw” (Retiro de emergencia) directamente desde el contrato donde estaban stakeados los tokens.

1. Encuentre la dirección del contrato del Syrup Pool del que está tratando de hacer Unstake. Puede encontrarlo en el registro de transacciones de su billetera.
2. Vaya a [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) y en la barra de búsqueda, ingrese la dirección del contrato.
3. Seleccione **Write Contract.**
4. Haga Click en **“Connect to Web3”** y conecte la wallet<img src="https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME" alt="" data-size="original">
5. En la sección **“4. emergencyWithdraw”,** ingrese "0" y haga click en “Write”.

Esto retirará tus tokens en stake pero se perderá cualquier recompensa que no se haya cosechado.

{% hint style="warning" %}
**Esto perderá cualquier recompensa que no se haya cosechado.**
{% endhint %}
{% endtab %}

{% tab title="Razón" %}
Este error tiende a aparecer cuando intentas hacer Unstake de un Syrup Pool antiguo, pero no quedan recompensas suficientes en el Pool para que puedas cosechar cuando retires la liquidez. Esto hace que la transacción falle.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance’

{% tabs %}
{% tab title="Solución" %}
1. Usa[ Unrekt.net](http://unrekt.net/) para revocar la aprobación del contrato con el que intentas interactuar.
2. Apruebe el contrato de nuevo, sin configurar un límite de asignación de gasto.
3. Intente interactuar con el contrato de nuevo.
{% endtab %}

{% tab title="Razón" %}
Esto sucede cuando establece un límite en su asignación de gastos cuando aprobó el contrato por primera vez y luego intenta intercambiar más que el límite.
{% endtab %}
{% endtabs %}

## Problemas con Predicción

Revisa [Errores y preguntas frecuentes sobre Predicción](https://docs.pancakeswap.finance/v/espanol/productos/prediccion/errores-y-preguntas-frecuentas).

## **Otros Errores**

### Provider Error: No provider was found // "No se encuentra el Proveedor"

* Limpia el cache y las cookies
* Conecta y desconecta la wallet
* Reinicia tu dispositivo

### Unsupported Chain ID / Chain ID No Soportada

Cambie su red a BNB Smart Chain. Consulte la documentación de su billetera para obtener una guía si necesita ayuda.

### “Already processing eth\_requestAccounts. Please wait”

Asegúrese de haber iniciado sesión en su wallet y de estar conectado a la BNB Smart Chain.

### Problemas tratando de comprar SAFEMOON y tokens similares

Para tradear SAFEMOON, debes hacer clic en el icono de configuración y **establecer su tolerancia de deslizamiento (slippage) en 12% o más.**

\
Esto es porque **SafeMoon cobra un 10% de fee en cada transacción**:

* 5% de fee = redistribuidos a todos los holders
* 5% de fee = usados para agregar liquidez

Esta es también la razón por la que es posible que no reciba tantos tokens como espera cuando realice la compra.\
Puede leer más en  [Cómo comprar Safemoon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742) (en inglés)

### Internal JSON-RPC errors

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit “

Sucede cuando se intenta eliminar la liquidez en algunos tokens a través de Metamask. La causa raíz aún se desconoce. Intente usar una billetera alternativa.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

No tiene suficiente BNB para pagar las tarifas de la transacción. Necesita más BNB BEP-20 en su billetera.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}”

Aumente el límite del gas para la transacción en su billetera. Consulte la documentación de su billetera para obtener información sobre cómo aumentar el límite de gas.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}’

Causa poco clara. Prueba estos pasos antes de volver a intentar:

1. Incremente el gas limit.
2. Incremente el slippage.
3. Borra la memoria cache.

### Problemas con el Perfil

#### Oops! We couldn't find any Pancake Collectibles in your wallet.

Estamos investigando la lógica detrás de este problema. Mientras tanto, pruebe estas soluciones alternativas.

{% tabs %}
{% tab title="Solución 1" %}
1. Vaya a la página "Collectible", luego regrese a la página de perfil. Si no encuentras el enlace, ve a[ https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles) directamente.
2. Vuelva a intentar crear el perfil.
{% endtab %}

{% tab title="Solución 2" %}
Cambia el entorno.

1. Borra la memoria cache y reintenta.
2. Reintenta en otro navegador.
3. Reintenta en otra wallet.
4. Reintenta usando otra red diferente (cambia entre el Wi-Fi y red de datos móvil).
{% endtab %}
{% endtabs %}

#### La comprobación del nombre de usuario sigue girando

Hay dos posibles causas.

1. Tienes varias wallets instaladas en tu navegador.
2. Problemas con tu red, tu conexión a internet.

{% tabs %}
{% tab title="Solución 1" %}
Causa principal: Tienes varias wallets instaladas en tu navegador.

Puede haber un conflicto entre las wallets. Esto está fuera de control de PancakeSwap y no podemos hacer nada.

1. Tengo solo una wallet instalada en el navegador, elimine las demás.
2. Vuelve a conectar la wallet e intente configurar el nombre de usuario de nuevo.
{% endtab %}

{% tab title="Solución 2" %}
Causa principal: conexión a la red inestable.

Tienes que volver a intentarlo.

1. Elimine completamente lo que se haya introducido en el campo de texto.
2. Vuelva a escribir el nombre de usuario, luego espere unos segundos.
3. Si no funciona, vuelva a cargar la página y vuelva a intentarlo.
{% endtab %}
{% endtabs %}

