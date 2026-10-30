# Cómo usar Farms con BscScan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Como requiere varios pasos, usar Farms con PancakeSwap puede parecer intimidante al principio. Esta guía te explica cómo usar el contrato de Farms directamente a través de BscScan.

{% hint style="warning" %}
Ten en cuenta que no se recomienda usar BscScan para interactuar con contratos si eres principiante. Si no te sientes seguro, te sugerimos usar en su lugar la [guía Cómo usar Farms](https://docs.pancakeswap.finance/earn/yield-farming/how-to-use-farms/how-to-use-farms).
{% endhint %}

## Cómo encontrar el identificador de proceso de la Farm

Para interactuar correctamente con el contrato inteligente de farming, necesitarás el identificador de proceso (PID) correspondiente a tu par de LP. Por ahora, la forma más sencilla de localizarlo es consultar GitHub.

1\. Abre el [código de Farms del sitio web de PancakeSwap en GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Pulsa **Control**/**command** + **F** y busca tu par por su ticker (no por el nombre del proyecto). Por ejemplo, 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. Anota o copia el número de PID (en este caso 389) en algún lugar al que puedas acceder fácilmente. Lo necesitarás más adelante.

## Depositar tokens LP a través de BscScan

Depositar tokens LP usando BscScan implica varias cosas. Lo hemos dividido en pasos para que sea más fácil seguirlo.

### Obtener la dirección del Main Staking Contract

La dirección del contrato principal de staking es: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Pero si quieres confirmarlo, visita la [página de BscScan de PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Verás la dirección en la parte superior izquierda. Haz clic en el **icono de páginas** para copiarla al portapapeles. La necesitarás enseguida.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### Abrir el contrato de tu token LP

Necesitarás aprobar el contrato inteligente del token LP que quieras destinar a una farm antes de poder gastarlo.

### Desde el código fuente

1\. Primero, abre [farms.ts en GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. Pulsa **Control**/**command** + **F** y busca tu par por su ticker (no por el nombre del proyecto). Por ejemplo, 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Cuando tengas abierto el código del par de LP que buscas, encuentra la dirección que aparece después de "56:". Esa será la dirección de tu contrato.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### Desde la interfaz

1\. Primero, visita la [página de Farms de PancakeSwap](https://pancakeswap.finance/farms) y busca el par elegido con el campo "SEARCH" en la parte superior derecha. En este ejemplo usamos CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Haz clic en **Details** para expandir la fila y mostrar más información.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Haz clic en **View Contract** para abrir el contrato inteligente en BscScan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### Dar permiso al contrato del token LP

Ahora que tienes abierto en BscScan el contrato de tu token LP, vas a aprobar el gasto de tus tokens LP en la Farm.

1\. En la página del contrato del token LP, ve a **Contract** y luego a **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Haz clic en **Connect to Web3** para conectar MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Confirma la conexión.

3\. En la función 1, “approve”, verás “spender:address”. Pega la dirección del Main Staking Contract que copiaste antes al portapapeles.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. También tendrás que aprobar la cantidad de tokens LP que el contrato puede gastar. En el campo de valor, debes introducir la cantidad en Wei. Puedes usar el [BscScan Unit Converter](https://www.bscscan.com/unitconverter) para convertir fácilmente tu cantidad a Wei. Aquí usaremos 5 tokens LP de CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
También puedes usar `-1` como valor para dar aprobación de gasto ilimitada. Esto no significa que vayas a gastarlo todo por defecto, sino únicamente que tu billetera permitirá una transacción de cualquier tamaño que use este contrato.
{% endhint %}

6\. Haz clic en **Write** y acepta la acción en tu billetera MetaMask. Ya puedes destinar tokens LP a la Farm hasta la cantidad que hayas aprobado.

### Depositar tokens LP con el contrato inteligente Main Staking Contract

Con el Main Staking Contract ya autorizado para gastar tus tokens LP, es hora de hacer un depósito.

1\. De vuelta en la [página de BscScan de PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), ve a **Contract** y luego a **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Haz clic en **Connect to Web3** para conectar MetaMask.

3\. Desplázate hasta la función 2, "deposit", y escribe tu PID en el campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

Si no copiaste tu PID antes, puedes aprender a obtenerlo en la sección **Cómo encontrar el identificador de proceso de la Farm** más arriba en esta página.

4\. Debajo de \_pid verás "\_amount". Introduce la cantidad de LP que el contrato podrá gastar, la que aprobaste antes.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Revisa la información y haz clic en **Write**. Confirma la acción en MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Puedes confirmar que tu depósito funcionó haciendo clic en **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Retirar de un Pool

Retirar tus tokens LP de un Pool es muy similar a hacer un depósito. La diferencia está en la función con la que interactúas.

1\. De vuelta en la [página de BscScan de PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), ve a **Contract** y luego a **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Haz clic en **Connect to Web3** para conectar MetaMask.

3\. Desplázate hasta el final, a la función 15, "withdraw", y escribe tu PID en el campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

Si no copiaste tu PID antes, puedes aprender a obtenerlo en la sección **Cómo encontrar el identificador de proceso de la Farm** más arriba en esta página.

4\. Debajo de \_pid verás "\_amount". Introduce la cantidad de LP que quieres retirar del Pool.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Revisa la información y haz clic en **Write**. Confirma la acción en MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Puedes confirmar que tu retiro funcionó haciendo clic en **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Hacer un retiro de emergencia**

‌Usar la función de retiro de emergencia te permite sacar todos tus fondos de un pool cuando ninguna otra vía funciona.

{% hint style="danger" %}
**¡Usar la función de retiro de emergencia hará que pierdas tus recompensas de CAKE!**

El equipo de PancakeSwap recomienda encarecidamente evitar esta función, salvo que el equipo de PancakeSwap te lo indique oficialmente o que te sientas muy cómodo interactuando con contratos inteligentes y entiendas el código subyacente.
{% endhint %}

‌1. En la [página de BscScan de PancakeSwap: Main Staking Contract](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), ve a **Contract** y luego a **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Haz clic en **Connect to Web3** para conectar MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Desplázate hasta la función 4, "emergencyWithdraw", y escribe tu PID en el campo "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

Si no copiaste tu PID antes, puedes aprender a obtenerlo en la sección **Cómo encontrar el identificador de proceso de la Farm** más arriba en esta página.

5\. Revisa la información y haz clic en **Write**. Confirma la acción en MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Puedes confirmar que tu retiro funcionó haciendo clic en **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
