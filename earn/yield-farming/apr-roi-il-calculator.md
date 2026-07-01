# Calculadora APR/ROI/IL

En la Liquidez y las Granjas V3, con la nueva liquidez no fungible y la capacidad de rango de precios personalizable, cada posición LP tendrá su propio APR de comisión LP y APR de farming de CAKE.

Para hacer la provisión de liquidez más fluida y menos desafiante, los nuevos displays automáticos de APR con una calculadora de ROI completamente nueva están disponibles para usar cada vez que proporcionas liquidez o haces farming.

## Cálculo y displays automáticos de APR <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

Cuando proporcionas liquidez, el display automático de APR reacciona a los cambios en tu configuración y calcula el APR basándose en tus ajustes.

Por ejemplo, en la mayoría de los casos, si ajustas la configuración del rango de precios, el APR sube.

Ten en cuenta para los APRs de comisión LP:

* La cantidad estimada de recompensas de comisión LP varía según el nivel de comisión seleccionado; las recompensas de comisiones requieren reclamación y composición manual.
* Las cifras de APR se calculan usando el volumen de trading histórico, que depende del Subgraph y puede estar sujeto a retrasos de indexación.

Para los APRs de farming:

* La cantidad estimada de recompensas de CAKE se basa en las emisiones de CAKE en vivo a las granjas. Están sujetas a cambios basados en ajustes de emisión futuros.

{% hint style="info" %}
Los números se calculan con las tasas actuales y las condiciones del pool, y están sujetos a cambios basados en diversas variables externas. Son estimaciones proporcionadas para tu conveniencia únicamente y de ninguna manera representan rendimientos garantizados.
{% endhint %}

Puedes encontrar este display de APR en:

* Página de "Agregar Liquidez" - mostrando el APR de comisión LP
* Página de detalle de cada posición de liquidez existente - mostrando el APR de comisión LP\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* Página de Granja, dentro de la posición en cada granja - mostrando el APR combinado con comisión LP y recompensas de CAKE\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## Calculadora ROI mejorada <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

Siempre que veas los displays automáticos de APR, puedes hacer clic y abrir la nueva calculadora de ROI. La nueva calculadora de ROI ha sido rediseñada con varias características añadidas para adaptarse a las necesidades de la provisión de liquidez concentrada y el farming en V3.

Repasemos juntos cada una de las secciones:

### Monto de Depósito, "En Staking Por" y "Componiendo Cada" <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Estos tres son las entradas básicas, que también están presentes en la calculadora de ROI anterior. Están ahí para definir:

1. Cuántos activos se proporcionan a la posición de liquidez, en USD.
2. Por cuánto tiempo esos activos estarán en staking en la posición.
3. Con qué frecuencia compondrás las recompensas de vuelta a la posición.



⓵ **Monto de Depósito**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

Puedes ingresar manualmente el monto en USD, o usar los botones de acción rápida para ingresar rápidamente $100, $1000 o el monto máximo permitido según el saldo del token en tu billetera.



⓶ **Duración del Staking**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

Puedes seleccionar por cuánto tiempo los activos están en staking en la posición de liquidez eligiendo entre: 1 día, 7 días, 30 días, 1 año y 5 años.

El número de retorno se calculará según tu duración de staking.



⓷ **Composición**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

Puedes seleccionar con qué frecuencia cosecharás las recompensas generadas por la posición y las compondrás de vuelta a la posición. Puedes elegir un número entre: 12 horas, 1 día, 7 días y 30 días.

El número de retornos y el APY se calcularán según tu elección. Si no planeas componer tu posición, desmarca la casilla de verificación a la izquierda.

{% hint style="info" %}
En V3, las comisiones LP y el CAKE ganado deben cosecharse y componerse manualmente.
{% endhint %}

### &#x20;⓸ Precio Histórico <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

Esta es una sección de solo vista para referenciar el movimiento histórico de precios del par seleccionado.

Puedes referenciar los movimientos históricos de precios en diferentes marcos de tiempo, como cuánto fluctúa usualmente el precio y luego idear una configuración de rango de precios adecuada para equilibrar entre un APR más alto y un menor riesgo de pérdida impermanente.

* MIN - precio mínimo
* MAX - precio máximo
* AVG - precio promedio
* CURRENT - precio actual

{% hint style="info" %}
El gráfico de precios solo usa datos del par V3 real. Por lo tanto, los datos de precios antes del despliegue de V3 no están disponibles. Las cuatro métricas de precios representan el marco de tiempo actualmente seleccionado y cambiarán según la selección.
{% endhint %}

### ⓹ Rango de Precios <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

Usando esta sección, puedes verificar cuánta liquidez se ha depositado a diferentes rangos de precios y idear y establecer el rango de precios al que estás proporcionando liquidez.

Puedes encontrar el gráfico de distribución debajo del título. Cuanto mayor sea la cantidad de liquidez, más alto será el gráfico.

Puedes cambiar tu configuración de rango de precios:

* Arrastrando los dos controles del gráfico para aumentar o disminuir el límite de precio mínimo y máximo.
* Usando el espacio entre dos controles para desplazar el rango seleccionado.
* Haciendo clic en los botones + y - en los campos de precio mínimo y máximo.
* Haciendo clic en los números en los campos de precio e ingresándolos manualmente.

Si deseas navegar por el gráfico de distribución:

1. Usa los botones de lupa más y menos para acercar y alejar
2. Arrastra el eje X (inferior) para desplazarte a la izquierda y a la derecha

Si deseas proporcionar liquidez en todo el rango de precios, haz clic en "Rango Completo".

### ⓺ Cambiar la dirección del precio para ver precios con diferente base <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

Para algunos pares de tokens, es más fácil e intuitivo ver los precios con ciertos tokens base. Por ejemplo, para el par BNB/USDT, la mayoría de las personas preferirá ver los precios en "cuántos USDT por BNB" en lugar de al revés.

Puedes cambiar fácilmente los displays de precio. Simplemente haz clic en el botón que sigue a "Ver precios en:" para cambiar la base entre los dos tokens del par.

### ⓻ Importar y exportar (aplicar) tu configuración <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

Cuando abres la calculadora de ROI en la ventana de "Agregar Liquidez", o al ver una posición existente, la siguiente configuración se importará automáticamente para que no necesites configurarla de nuevo:

1. La cantidad de activos que estás depositando
2. El rango de precios
3. El nivel de comisión seleccionado

Cuando termines de configurar en la calculadora de ROI, puedes hacer clic en "Aplicar Configuración" para aplicar rápidamente los ajustes de la calculadora de vuelta a la ventana de "Agregar Liquidez" para que no necesites coincidirlos manualmente.

### ⓼ Calcular recompensas de farming y APR <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

Las recompensas de farming se incluirán en los cálculos si abres la calculadora de ROI en la página de "Granja".

Puedes expandir las secciones de detalle para ver el desglose de recompensas.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
