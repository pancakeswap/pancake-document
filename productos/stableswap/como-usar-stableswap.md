# Cómo usar StableSwap

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

## **Operando con StableSwap**

Operar en StableSwap es muy similar a usar el PancakeSwap AMM existente. Antes de comenzar, también requiere una billetera compatible con BNB Smart Chain y BNB para fees de la red. Consulte nuestra [guía de wallets ](https://docs.pancakeswap.finance/v/espanol/empezando-en-pancakeswap/creando-una-wallet)para obtener más detalles.

1 - Ir a la página de swap [aquí](https://pancakeswap.finance/swap#/swap)

2 - Haga clic en la pestaña "StableSwap"

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

3 - Elija los pares de tokens que le gustaría intercambiar. En el lanzamiento, solo se agregará un par (HAY-BUSD). Gradualmente se agregarán más pares de estables.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

4 - A partir de este paso, el proceso de intercambio es el mismo que el PancakeSwap normal. Consulte la guía [aquí](https://docs.pancakeswap.finance/v/espanol/productos/pancakeswap-exchange/how-to-trade-on-the-pancakeswap-exchange) desde el paso 4 en adelante.

## **Agregar y remover liquidez**

Agregar y remover liquidez para StableSwap también es muy importante y similar al PancakeSwap AMM normal. Consulte la guía [aquí](https://docs.pancakeswap.finance/v/espanol/productos/pancakeswap-exchange/anadir-remover-liquidez) para obtener una explicación más detallada.

Hay algunas diferencias para la liquidez de StableSwap:

&#x20;1 - Cuando selecciona los pares de activos que están habilitados para StableSwap (por ejemplo, HAY-BUSD), la interfaz le indicará que está proporcionando un "LP estable"

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

2 - La aporte de liquidez de los dos activos puede hacerse de forma desigual, y habrá una página de confirmación para mostrar la proporción de su liquidez.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

3 - Recibirás un token Stable-LP como recibo de la provisión de liquidez para cuando quieras retirar tu liquidez.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

4 - Sin embargo, TENGA EN CUENTA que cuando retire la liquidez, siempre obtendrá 50%/50% en los activos sin importar la proporción cuando agregó la liquidez. Como ejemplo simplificado: si suministró 199 HAY y 1 BUSD, cuando retire la liquidez recibirá 100 HAY y 100 BUSD asumiendo 0 deslizamientos y precios estables de 1:1.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

## **Migre su Farm Staking HAY-BUSD**

Antes del lanzamiento de StableSwap, la liquidez de HAY-BUSD y el Farm de LP ya estaban disponibles en PancakeSwap en su intercambio AMM v2 normal. Sin embargo, dado que estamos lanzando HAY-BUSD como el primer par de liquidez en nuestro StableSwap, es probable que la mayoría de ustedes que deseen operar con este par eventualmente se cambien a StableSwap en lugar de continuar usando el intercambio v2 AMM, porque:

* Puedes hacer el swap de manera más eficiente con los mismos pasos.
* Con la función StableSwap, el deslizamiento es más bajo que en el AMM normal que solo usa la fórmula de producto constante
* Las tarifas (fees) son más bajas en comparación con el AMM normal

**TENGA EN CUENTA: si actualmente no está haciendo Farming con HAY-BUSD LP, no tiene que realizar ninguna migración.**

**¿Por qué es necesario migrar el Stake del Farm,?**

Dado que la mayoría de las trades de HAY-BUSD se realizarán en StableSwap utilizando Stable LP en el futuro, los incentivos CAKE deben redirigirse a recompensar a los participantes de Stable LP para alentarlos a proporcionar liquidez. Habrá menos actividad para el LP HAY-BUSD original (con el AMM v2).

## **Cómo migrar el LP**

Habrá una ventana de 24 horas a partir del lanzamiento de StableSwap, y antes de que se redirijan los incentivos CAKE y se lance el nuevo Farm para HAY-BUSD Stable LP. Esto es lo que debe hacer si actualmente está apostando LP de HAY-BUSD en el Farm:

1 - Retire los HAY-BUSD LP desde la [página de farms](https://pancakeswap.finance/farms)

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

2 - Remueva la liquidez de su HAY-BUSD LP en la [página de liquidez](https://pancakeswap.finance/liquidity)

3 - Agregue liquidez nuevamente para HAY-BUSD (esta vez deberías ver que estás agregando a LP estable durante el proceso)

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

4 - Deposite su LP estable HAY-BUSD en la [página de Farms](https://pancakeswap.finance/farms) cuando se lance el 23 de septiembre: busque el Farm con la etiqueta LP estable

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## **Timeline:**

* Lanzamiento de StableSwap y provisión de liquidez HAY-BUSD habilitada: **22 de septiembre de 2022 11:00 UTC**
* Migración de Farm (las recompensas de CAKE se redirigen de HAY-BUSD LP Farm a HAY-BUSD Stable LP Farm): **23 de septiembre de 2022 a las 11:00 UTC.**
