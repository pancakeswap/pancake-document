---
description: >-
  Mensajes de error comunes. Use la barra lateral➡️ para saltar al error que
  necesita ver.
---

# Errores Frecuentes

![](../.gitbook/assets/image%20%2879%29.png)

A veces estamos frente a un problema que no parece tener una solución clara. Esperamos que estos tips frente a problemas frecuentes puedan ayudarte a solucionarlo.

## **Problemas en el Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT** 

> The transaction cannot succeed due to error:  PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.

> La transacción no pudo realizarse debido al error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. \(Probablemente sea un problema con uno de los tokens que está intercambiando\)

Está intentando intercambiar tokens, pero su tolerancia al deslizamiento \(Slippage\) es demasiado baja o la liquidez es demasiado poca.

{% tabs %}
{% tab title="Solución" %}
1. Actualice la página e intente de nuevo más tarde.
2. Pruebe intercambiando montos más pequeños de a una vez.
3. Aumente su tolerancia al deslizamiento \(Slippage\):
   1. Toque el icono de configuración en la página de liquidez.
   2. Aumente un poco su deslizamiento \(Slippage\) e intente de nuevo. ![](../.gitbook/assets/image%20%289%29%20%284%29%20%284%29.png)
4. Por último, intente ingresar una cantidad con menos valores decimales.
{% endtab %}

{% tab title="Razón" %}
**Esto pasa usualmente cuando estás intentando intercambiar tokens con baja liquidez.**

Esto significa que no hay suficiente cantidad de uno de los tokens que estás intentando intercambiando en el Pool de liquidez: es probablemente un token de baja capitalización que pocas personas están intercambiando.

Sin embargo, también existe la posibilidad que estés intentando intercambiar un token malicioso que no puede venderse. En este caso, PancakeSwap no puede bloquear un token ni devolver los fondos.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT** 

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'  
> or  
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Estás tratando de agregar / remover liquidez de un Pool de Liquidez \(LP\), pero no hay suficiente de uno de los dos tokens en el par.

{% tabs %}
{% tab title="Solución" %}
**Actualice la página e intente de nuevo, o intente de nuevo más tarde.**

Aún no funciona?

1. Toque el icono de configuración en la página de liquidez.
2. Aumente un poco su deslizamiento \(Slippage\) e intente de nuevo.

![](../.gitbook/assets/image%20%289%29%20%284%29%20%284%29.png)
{% endtab %}

{% tab title="Razón" %}
Este error es causado al tratar de agregar o remover liquidez de un Pool de Liquidez \(LP\) con una cantidad insuficiente del token A o el token B \(uno de los tokens del par\).

Puede darse el caso de que los precios se actualicen demasiado rápido y su tolerancia al deslizamiento \(Slippage\) sea demasiado baja.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)



![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solución para nerds" %}
OK, estás realmente decidido a resolver esto. No recomendamos realmente hacer esto a menos que sepas lo que estás haciendo. 

Actualmente, no existe una forma sencilla de resolver este problema desde el sitio web de PancakeSwap: vas a necesitar interactuar directamente con el contrato. Puedes agregar liquidez directamente a través del contrato del Router, mientras estableces en "amountAMin" una pequeña cantidad, entonces podrás retirar toda la liquidez.

### **Aprobar el contrato LP**

Dirígete al contrato del token LP que estás intentando aprobar. Por ejemplo, de ejemplo está el par ETH / WBNB: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Selecciona **Write Contract**, luego **Connect to Web3** y conecta tu wallet ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. En **la sección"1. approve",** aprueba el LP token del Router ingresando:
   1. spender \(address\): ingrese la dirección del contrato del token LP con el que está tratando de interactuar.
   2. value \(uint256\): -1

### Consulta "balanceOf"

1. Cambia a **Read Contract.**
2. En la sección **5. balanceOf**, ingresa tu dirección de la wallet y presiona **Query**.
3. Anota el número que se exporta. Este muestra tu saldo dentro del LP en formato uint256, que necesitarás en el siguiente paso. 

![](../.gitbook/assets/image%20%2832%29.png)

### Agregar o Remover Liquidez

Dirígete al contrato del Router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f\#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Selecciona **Write Contract** y **Connect to Web3** como antes.
2. Encuentra **addLiquidity** o **removeLiquidity** \(lo que sea que estés tratando de hacer\)
3. Ingresa las direcciones de contrato de ambos tokens del LP.
4. En **liquidity \(uint256\),** ingresa el número en formato uint256 que obtuviste de "balanceOf" anteriormente.
5. Establece un bajo **amountAMin** o **amountBMin**: prueba 1 para ambos.
6. Agrega la dirección de tu billetera en **to \(address\)**.
7. Deadline debe ser un tiempo de epoch mayor que el tiempo en que se ejecuta el transacción. 

![](../.gitbook/assets/image%20%2819%29.png)

{% hint style="warning" %}
Esto puede causar un muy alto deslizamiento \(Slippage\), y causar que el usuario pierda algunos fondos si realiza Frontrun. 
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED 

> The transaction cannot succeed due to error:  PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.

Intente de nuevo, pero confirme \(firma y emisión\) la transacción al momento que esta se genera.

Esto sucedió porque comenzó a realizar una transacción, pero no la firmó ni la emitió hasta que pasó la fecha límite. Eso significa que no presionó "Confirmar" lo suficientemente rápido.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Actualice la página e intente de nuevo, o aumente el deslizamiento \(Slippage\) a través del icono de configuración y vuelva a intentarlo.

Esto probablemente sucedió porque está tratando de comprar o vender tokens durante un gran movimiento de precios. El frontend está obteniendo información desactualizada \(e.g. outAmount\) de los smart contracts, causando que el swap falle.



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
Si sigue fallando, puedes intentar un  “emergencyWithdraw”  \(Retiro de emergencia\) directamente desde el contrato donde estaban stakeados los tokens.

1. Ir a: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E\#writeContract ](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract%20)
2. Click en **“Connect to Web3”** y conecta tu wallet. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. En la sección **“4. emergencyWithdraw”**, ingresa "0" y haz click en “Write”.

Esto retirará tus tokens en stake pero se perderá cualquier CAKE que no se haya cosechado.

{% hint style="warning" %}
**Esto perderá cualquier recompensa que aún no haya cosechado.**
{% endhint %}
{% endtab %}

{% tab title="Razón" %}
Para que esto no vuelva a pasar, **no vendas tus SYRUP.** Los vas a retirar para retirar los CAKE del “Stake CAKE Earn CAKE” pool.

Este error ha aparecido porque has vendido o transferido los SYRUP tokens. Los SYRUP son creados en un ratio 1:1 ratio con CAKE cuando los depositas en el CAKE-CAKE Syrup Pool. Los SYRUP deben ser quemados al mismo ratio 1:1 ratio con CAKE cuando llamamos a la función leaveStaking \(retirar nuestras CAKE del Pool\), entonces si no tienes suficientes, no podrás hacer Unstake del pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}



![](https://lh4.googleusercontent.com/KchAcnM6cpX2BotEGppAxPAnY4Xbona6yI6ZWg9FlUUBfPi_YO9ulM1s6htXJVXMzEwl0Uxcvdk8o4yhI7ar5g0TRpLVFjkS4YLKL7FS8Z4uFqeC37sw-TIkrPr7BCZQVpuD-5jO)
{% endtab %}
{% endtabs %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas\]
>
> ¡Advertencia! Error encontrado durante la ejecución del contrato \[sin gas\]

El problema es que se estableció un límite de gas bajo al intentar realizar una transacción.

{% tabs %}
{% tab title="Solución" %}
Intenta aumentar manualmente el **gas limit** \(no el gas price!\) en tu wallet, antes de firmar la transacción.

Un límite de gas \(Gas Limit\) en 200000 usualmente es suficiente

![](../.gitbook/assets/image%20%28169%29.png)

El ejemplo de arriba es en Metamask; echa un vistazo a los docs de tu wallet si no estás seguro cómo ajustar el gas limit.
{% endtab %}

{% tab title="Razón" %}
Básicamente, tu wallet \(Metamask, Trust Wallet, etc.\) no pudo finalizar lo que intentó hacer. 

Su billetera estima que el límite de gas es demasiado bajo, por lo que la llamada a la función se queda sin gas antes de que finalice la misma.  
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'
>
> Error: "BEP20: el monto de la transferencia excede el saldo"

Estás tratando de hacer Unstake de un Pool que tiene pocas rewards en él.

{% tabs %}
{% tab title="Solución" %}
Puedes intentar un “emergencyWithdraw” \(Retiro de emergencia\) directamente desde el contrato donde estaban stakeados los tokens.

1. Encuentre la dirección del contrato del Syrup Pool del que está tratando de hacer Unstake. Puede encontrarlo en el registro de transacciones de su billetera.
2. Vaya a [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract%20) y en la barra de búsqueda, ingrese la dirección del contrato.
3. Seleccione **Write Contract.**
4. Haga Click en **“Connect to Web3”** y conecte la wallet![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
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

## **Otros Errores**

### Provider Error: No provider was found // "No se encuentra el Proveedor"

* Limpia el cache y las cookies
* Conecta y desconecta la wallet
* Reinicia tu dispositivo

### Unsupported Chain ID / Chain ID No Soportada

Cambie su red a Binance Smart Chain. Consulte la documentación de su billetera para obtener una guía si necesita ayuda.

### Problemas tratando de comprar SAFEMOON y tokens similares

Para tradear SAFEMOON, debes hacer clic en el icono de configuración y **establecer su tolerancia de deslizamiento \(slippage\) en 12% o más.**

  
****Esto es porque **SafeMoon cobra un 10% de fee en cada transacción**:

* 5% de fee = redistribuidos a todos los holders
* 5% de fee = usados para agregar liquidez

Esta es también la razón por la que es posible que no reciba tantos tokens como espera cuando realice la compra.  
Puede leer más en  [Cómo comprar Safemoon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742) \(en inglés\)

