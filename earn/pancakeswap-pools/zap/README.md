---
description: Agregar liquidez con un solo clic
---

# Zap

### ¿Qué es Zap? <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap es una función que te permite agregar liquidez con facilidad. Con Zap, puedes proporcionar liquidez con cualquier token que tengas en tu saldo sin importar los tokens requeridos en el pool. Simplemente establece el rango de precios, elige la cantidad a proporcionar y ejecuta. Tus tokens se equilibrarán automáticamente para formar la posición de liquidez mientras se intercambian de la manera más eficiente, con el menor impacto de precio y deslizamiento.

### Cadenas Admitidas

* v3 - Todos los pools en BNB Chain, pools seleccionados en redes Ethereum y Arbitrum
* Infinity - Todos los pools CLAMM (sin hook) en BNB Chain

### Cómo Usar <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

Por ahora, Zap admite:

* 🆕 ¡Cualquier token!
* Usando un solo token
* 🆕 Usando dos tokens
* 🆕 O... usando múltiples tokens (sí, puede usarse como recolector de polvo)

#### Iniciar <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Para usar Zap, simplemente ve a la página de Agregar Liquidez, selecciona el par de trading al que deseas proporcionar liquidez, el nivel de comisión y el rango de precios.

Luego selecciona la cantidad de tokens que deseas proporcionar como liquidez.

La opción de Zap aparecerá automáticamente cuando uno o más tokens tengan poco saldo.

Haz clic en el enlace para abrir el modal de Zap.

#### Iniciar Zap <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

Dentro del nuevo modal "Zap in", puedes encontrar los siguientes campos:

1. El par de trading al que estás haciendo Zap (proporcionando liquidez).
2. El/los token(s) de depósito y la(s) cantidad(es) a depositar. Puedes agregar o eliminar libremente cualquier token para el Zap.
3. El rango de precios de la nueva posición. También puedes hacer clic en las flechas para alternar entre diferentes visualizaciones de precios.
4. Un desglose detallado de cómo la función Zap manejará tus tokens de depósito.
5. Un resumen de las estadísticas que incluye:
   1. Valor estimado en USD para la nueva posición de liquidez.
   2. Cantidad estimada de tokens en la nueva posición de liquidez.
   3. Fondos sobrantes estimados en USD después del Zap. En la mayoría de los casos debería ser 0. Si el pool de liquidez o los tokens tienen muy poca liquidez, este valor puede aumentar.
   4. El impacto de precio para los intercambios de tokens y reequilibrios mientras se hace Zap.
   5. El impacto de precio para agregar liquidez y construir la posición.
   6. Tarifa de Zap. Dependiendo del par de liquidez, la tasa de tarifa puede variar.

{% hint style="warning" %}
Ten en cuenta que es posible que necesites reconfigurar la cantidad a hacer Zap según tu saldo disponible. Si no tienes saldo en uno de los tokens, por favor elimínalos.
{% endhint %}

{% hint style="info" %}
Es posible que notes que la configuración de "Agregar Liquidez V3" se traslada automáticamente al modal de Zap. Incluyendo el monto de depósito y la configuración del rango de precios.
{% endhint %}

#### Comenzar a hacer Zap <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

Finalmente, haz clic en "Aprobar" y confirma en el popup de la billetera para el permiso del token.

Luego, haz clic en "Vista Previa" para abrir el modal de confirmación final. Antes de continuar, por favor revisa todas las estadísticas y estimaciones mostradas en el modal de confirmación final. Especialmente las cifras de impacto y el deslizamiento máximo.

Finalmente, haz clic en "Agregar Liquidez" y confirma en el popup de tu billetera.

Después de que la transacción sea confirmada, verás tu nueva y brillante posición en la página "Mi Posición".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### Más Configuraciones <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Si deseas personalizar aún más tu experiencia de Zap, simplemente haz clic en el icono de engranaje en la esquina superior derecha. En la configuración, puedes configurar:

* El deslizamiento máximo mientras se hace Zap.
* El tiempo límite de la transacción.
* Si usar la liquidez agregada de KyberSwap para realizar el reequilibrio de tokens. Desactiva esto si solo quieres intercambiar en los Pools de PancakeSwap.
* El modo Degen puede usarse para realizar Zaps con deslizamiento muy alto. No se recomienda para casos de uso normales, úsalo bajo tu propio riesgo.

{% hint style="warning" %}
Ten en cuenta que la configuración de Deslizamiento y Plazo son independientes a la página de Intercambio y Liquidez.
{% endhint %}

#### Hacer Zap usando dos tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Ahora puedes hacer Zap de tu liquidez con dos tokens. Esto es útil cuando tu saldo disponible no coincide con la configuración de precios y la cantidad de tokens requerida y la proporción que está solicitando. Simplemente haz Zap y la proporción se reequilibrará automáticamente.

#### Hacer Zap usando muchos tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Sí, funciona igual que un recolector de tokens polvo. Es adecuado para limpiar pequeños saldos en tu billetera y ponerlos en una posición para comenzar a ganar comisiones de trading.
