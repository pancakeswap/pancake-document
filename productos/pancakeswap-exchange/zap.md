---
description: Liquidez Simple con un click
---

# ⚡ Zap

### ![](<../../.gitbook/assets/image (182).png>) <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

### Qué es Zap? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap permite una provisión de liquidez de manera muy simple. Agregue liquidez con un solo token y un solo clic, sin hacer un swap manual ni equilibrar los tokens.

* Puedes agregar liquidez usando solamente un token en el par de operaciones. Zap realizará automáticamente swaps usando el token que usted proporcione y equilibrará automáticamente el par de tokens a una proporción de 50/50 antes de agregar liquidez.
* &#x20;Agregar liquidez con un número desequilibrado de tokens en el par: Puedes agregar liquidez incluso si el número de tokens que proporcionas en el par no está perfectamente equilibrado con el pool actual. Por ejemplo, 30:70, que difiere del peso predeterminado de 50:50. Zap reequilibrará automáticamente los tokens en una división de 50/50 antes de añadir liquidez.
* Eliminar liquidez y elegir qué token(s) desea recibir: Al eliminar liquidez, Zap le permite recibir sólo un token si lo desea. Zap realizará cambios automáticamente antes de devolver sus tokens.

### Activar Zap <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

De forma predeterminada, la función Zap está activada para todos los usuarios. Si no ve la nueva interfaz de usuario de Zap al añadir o eliminar liquidez, actívela en el panel de configuración. Puede abrir el panel de ajustes haciendo clic en el icono de engranaje.

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FAeEhY4AjRoNtihOD9KFq%2Fzap-8.png?alt=media\&token=44fd9cf8-fcee-401c-8b27-ddcc70b1f245)



{% hint style="warning" %}
Nota: Actualmente, la función Zap está en versión beta. Tenga en cuenta que no es compatible con algunos tokens, como tokens con tarifas en las transferencias. Si experimenta algún problema al añadir o eliminar liquidez, desactívelo en el panel de configuración.
{% endhint %}

### Zap In (Añadir Liquidez) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

Visita la[ ](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442758\&usg=AOvVaw2ZJPj\_97-YuUMQjQbYbfN4)[Página de Liquidez](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442948\&usg=AOvVaw39k9SD0FIdLv9GzmEv10Xz), y elige “Add Liquidity” (añadir liquidez).

Elija el par al que desea proporcionar liquidez seleccionando dos tokens de entrada, consulte la [guía de liquidez ](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide)para obtener más información.

![](<../../.gitbook/assets/image (185).png>)

Clic en el botón “Add Liquidity” para proceder.

Si el token en el par que está añadiendo liquidez tiene un saldo en su billetera, la casilla de verificación de ese token se marcará automáticamente. Si tienes ambos tokens con un saldo en tu billetera, se marcarán ambas casillas de verificación.

![](<../../.gitbook/assets/image (186).png>)

### Zap usando un solo token <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

Usted puede agregar liquidez usando solamente un token del par. Marque sólo una casilla de verificación para el token que desea utilizar. Zap cambiará automáticamente la mitad de los tokens comprometidos por otro token del par antes de añadir liquidez. Verá un mensaje de advertencia que indica qué token se convertirá.

![](<../../.gitbook/assets/image (187).png>)

{% hint style="info" %}
Si el impacto en el precio es demasiado alto, Zap lo protegerá por deslizamiento (slippage). Haga clic en "Reducir TOKEN" para reducirlo al límite preferido.
{% endhint %}

![](<../../.gitbook/assets/image (189).png>)

### Zap usando dos tokens con balances dispares <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Si se marcan ambos tokens y las cantidades de los mismos no coinciden con una división de 50/50. Zap equilibrará este desequilibrio. Verá un mensaje de "Parte de su Token A se convertirá en Token B" (“Some of your Token A will be converted to Token B”).

![](<../../.gitbook/assets/image (184).png>)



{% hint style="info" %}
Si no desea que Zap equilibre el número de tokens antes de añadir liquidez, simplemente haga clic en “No convertir” ("Don't Convert). En este caso, Zap ajustará el número de tokens de entrada para que coincida con una división de 50/50 en lugar de intentar intercambiar y reequilibrar.
{% endhint %}

### Proceder con Zap <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

Cuando haga clic en "Supply", se mostrarán los detalles del Zap y lo esperará para confirmar.

Verás ahí:

1. Cuántos LP tokens recibirás.
2. Cuáles son los tokens de entrada, y el número de tokens comprometidos.
3. Cómo los tokens serán intercambiados para llegar a una división del 50/50.
4. El slippage (deslizamiento) que estás utilizando

![](<../../.gitbook/assets/image (188).png>)

### Zap out (Remover Liquidez) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap también le permite recibir un solo token en el par LP al eliminar la liquidez. Visita la[ ](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442758\&usg=AOvVaw2ZJPj\_97-YuUMQjQbYbfN4)[Página de Liquidez](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442948\&usg=AOvVaw39k9SD0FIdLv9GzmEv10Xz).

1. Haga clic en el par que desea eliminar la liquidez en "Su liquidez".
2. Click en “Remover”. Aparecerá una nueva ventana emergente.

En la sección “You Will Receive” ("Recibirá"), puedes desmarcar el token que no deseas recibir. Zap intercambiará y convertirá automáticamente el 100% de los rendimientos en el token elegido al eliminar la liquidez.

![](<../../.gitbook/assets/image (183).png>)
