# Cómo usar StableSwap

![](<../../.gitbook/assets/0 (2).png>)

### **Operando en el StableSwap** <a href="#_tisnq4dp6n4k" id="_tisnq4dp6n4k"></a>

Operar en el StableSwap es muy similar a usar el PancakeSwap AMM existente. Antes de comenzar, también requiere una billetera compatible con BNB Smart Chain y BNB para fees de la red. Consulte nuestra[ guía de wallets](https://docs.pancakeswap.finance/v/espanol/empezando-en-pancakeswap/creando-una-wallet) para obtener más detalles.

1. Ir a la página de swap[ aquí](https://pancakeswap.finance/swap)
2. Elija el par de tokens que le gustaría intercambiar.
3. ¡Ya está todo listo! El siguiente proceso del intercambio es el mismo de siempre. Si es tu primera vez haciendo un intercambio consulta la siguiente[ guía](https://docs.pancakeswap.finance/v/espanol/productos/pancakeswap-exchange/how-to-trade-on-the-pancakeswap-exchange).

#### **Agregar y remover liquidez** <a href="#_xyjd6tg1slff" id="_xyjd6tg1slff"></a>

Agregar y remover liquidez del StableSwap también es muy importante y similar al PancakeSwap AMM normal. Consulte [esta guía](https://docs.pancakeswap.finance/v/espanol/productos/pancakeswap-exchange/anadir-remover-liquidez) para obtener una explicación más detallada.

Hay algunas diferencias para la liquidez del StableSwap:

1. Cuando selecciona los pares de activos que están habilitados para StableSwap (por ejemplo, HAY-BUSD), la interfaz le indicará que está proporcionando un "Stable LP”

![](<../../.gitbook/assets/1 (1).png>)

2. El aporte de liquidez de los dos activos puede hacerse de forma desigual, y habrá una página de confirmación para mostrar la proporción de su liquidez.

![](<../../.gitbook/assets/2 (1).png>)

1. Recibirás un token Stable-LP como recibo de la provisión de liquidez para cuando quieras retirarla y removerla.

![](../../.gitbook/assets/3.png)

1. Sin embargo, **TENGA EN CUENTA** que cuando retire la liquidez, siempre obtendrá 50%/50% en los activos sin importar la proporción cuando agregó la liquidez. Un ejemplo más sencillo: si suministró 199 HAY y 1 BUSD, cuando retire la liquidez recibirá 100 HAY y 100 BUSD asumiendo 0 deslizamientos y precios estables 1:1.

![](../../.gitbook/assets/4.png)

### **Migre su Farm Staking USDT-BUSD, USDC-BUSD, USDC-USDT** <a href="#_mzfjxp6fs957" id="_mzfjxp6fs957"></a>

Antes del lanzamiento de los pools de StableSwap, los siguientes pares de liquidez y LP Farms ya están disponibles en PancakeSwap en el swap normal del AMM v2:

* **HAY-BUSD**
* **USDT-BUSD**
* **USDC-BUSD**
* **USDC-USDT**

El lanzamiento de estos pares para el intercambio en el StableSwap, resultara con las siguientes ventajas:

* Puedes hacer el swap de manera más eficiente con los mismos pasos.
* Con la función StableSwap, el deslizamiento es más bajo que en el AMM normal.
* Las tarifas (fees) son más bajas en comparación con el AMM normal.

**TENGA EN CUENTA: Si actualmente no está haciendo farming con los LPs mencionados anteriormente, no tiene que realizar ninguna migración.**

**¿Por qué es necesario migrar el Stake del Farm?**

Dado que la mayoría de los intercambios de USDC-BUSD, USDT-BUSD y USDC-USDT se realizarán en StableSwap utilizando Stable LP en el futuro, los incentivos de CAKE deben redirigirse a recompensar a los participantes del Stable LP para alentarlos a proporcionar liquidez. Habrá menos actividad para los LPs originales (con el AMM v2).

### **Cómo migrar el LP** <a href="#_a8baiyezdqzf" id="_a8baiyezdqzf"></a>

Habrá una **ventana de 5 horas** a partir del lanzamiento del Farm StableSwap a las 9:00 UTC el 6 Dic 2022, y antes de que se redirijan los incentivos de CAKE y se lance los nuevos Farms para USDC-BUSD, USDT-BUSD, USDC-USDT Stable LP a las 14:00 UTC el 6 Dic 2022. Esto es lo que debe hacer si actualmente está haciendo staking de algún LP de USDC-BUSD, USDT-BUSD, USDC-USDT en el Farm:

1 - Retire los LP v2 desde la[ página de farms](https://pancakeswap.finance/farms)

![](../../.gitbook/assets/5.png)

2 - Remueva la liquidez de su LP en la[ página de liquidez](https://pancakeswap.finance/liquidity)

3 - Agregue liquidez nuevamente (esta vez deberías ver que estás agregando a LP estable durante el proceso)

![](<../../.gitbook/assets/6 (1).png>)

4 - Deposite su LP estable en la[ página de Farms](https://pancakeswap.finance/farms) - busque el Farm con la etiqueta “Stable LP”.

![](../../.gitbook/assets/7.png)

### **Timeline:** <a href="#_j0bq0daiy2lb" id="_j0bq0daiy2lb"></a>

* Lanzamiento de StableSwap y provisión de liquidez USDC-BUSD, USDT-BUSD, USDC-USDT habilitada: **30 de noviembre de 2022 11:00 UTC**
* Migración de Farm (las recompensas de CAKE se redirigen de USDC-BUSD, USDT-BUSD, USDC-USDT LP Farm a USDC-BUSD, USDT-BUSD, USDC-USDT Stable LP Farm): **06** **de diciembre de 2022 a las 09:00 UTC.**
