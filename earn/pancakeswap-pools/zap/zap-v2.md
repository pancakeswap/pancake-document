---
description: Provisión de liquidez simple con solo un clic
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### ¿Qué es Zap? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap permite la provisión de liquidez simple. Agrega liquidez con solo un token y un solo clic, sin intercambios manuales ni equilibrado de tokens.

* Agrega liquidez con solo un token: Puedes agregar liquidez usando solo un token del par de trading. Zap realizará automáticamente intercambios usando el único token que proporcionas y equilibrará automáticamente el par de trading a una división 50/50 antes de agregar liquidez.
* Agrega liquidez con una cantidad desequilibrada de tokens en el par de trading: Puedes agregar liquidez incluso si la cantidad de tokens que proporcionas en el par de trading no está perfectamente equilibrada con el pool actual. Por ejemplo, 30:70, que difiere del peso predeterminado del pool de 50:50. Zap reequilibrará automáticamente los tokens en una división 50/50 antes de agregar liquidez.
* Elimina liquidez y elige qué token(s) quieres recibir: Al eliminar liquidez, Zap te permite recibir solo un token del par de trading. Zap realizará automáticamente intercambios antes de devolverte tus tokens.

### Habilitar Zap <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

De forma predeterminada, la función Zap está activada para todos los usuarios. Si no ves la nueva interfaz de Zap al agregar o eliminar liquidez, por favor habilítala en el panel de configuración. Puedes abrir el panel de configuración haciendo clic en el icono de engranaje.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
Nota: Actualmente, la función Zap está en beta. Ten en cuenta que no admite algunos tokens, como tokens con comisiones en transferencias. Si experimentas algún problema al agregar o eliminar liquidez, por favor desactívala en el panel de configuración.
{% endhint %}

### Zap In (Agregar Liquidez) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

Visita la [página de Liquidez](https://pancakeswap.finance/liquidity) y elige "Agregar Liquidez".

Elige el par de trading al que deseas proporcionar liquidez seleccionando dos tokens de entrada; consulta la [guía de Liquidez](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) para obtener más información.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

Haz clic en el botón "Agregar Liquidez" para continuar.

Si el token en el par de trading al que estás agregando liquidez tiene un saldo en tu billetera, la casilla de verificación para ese token se marcará automáticamente. Si ambos tokens tienen saldo en tu billetera, ambas casillas se marcarán.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### Zap usando un token <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

Puedes agregar liquidez usando solo un token del par de trading. Simplemente marca solo una casilla para el token que deseas usar. Zap intercambiará automáticamente la mitad de los tokens marcados por otro token en el par de trading antes de agregar liquidez. Verás un mensaje de advertencia indicando qué token se convertirá.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
Si el impacto de precio es demasiado alto, Zap te protegerá con deslizamiento. Haz clic en "Reducir TOKEN" para reducirlo al límite preferido.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### Zap usando dos tokens con cantidades desequilibradas <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Si ambos tokens están marcados, las cantidades de los tokens de entrada no coinciden con una división 50/50. Se introducirá el equilibrado de Zap. Verás un mensaje que dice "Una parte de tu Token A se convertirá en Token B".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
Si no quieres que Zap equilibre el número de tokens antes de agregar liquidez, simplemente haz clic en "No Convertir". En este caso, Zap ajustará el número de tokens de entrada para que coincidan con una división 50/50 en lugar de intentar intercambiar y reequilibrar.
{% endhint %}

### Proceder con Zap <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

Cuando hagas clic en "Suministrar", se mostrarán los detalles del Zap y esperará tu confirmación.

Verás:

1. Cuántos tokens LP recibirás.
2. Cuáles son los tokens de entrada y el número de tokens que estás comprometiendo.
3. Cómo se intercambian los tokens de entrada para que coincidan con una división 50/50.
4. La tolerancia al deslizamiento que estás usando.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap out (Eliminar Liquidez) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap también te permite recibir un solo token del par de trading al eliminar liquidez.

1. Visita la [página de Liquidez](https://pancakeswap.finance/swap#/pool).
2. Haz clic en el par del que deseas eliminar liquidez bajo "Tu Liquidez".
3. Haz clic en "Eliminar". Aparecerá una nueva ventana emergente.

En la sección "Recibirás", puedes desmarcar el token que no deseas recibir. Zap intercambiará y convertirá automáticamente el 100% de los retornos en el token marcado al eliminar liquidez.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
