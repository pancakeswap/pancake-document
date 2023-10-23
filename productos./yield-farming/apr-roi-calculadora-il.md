# APR/ROI/Calculadora IL ()

En Liquidez y Farm V3, con la nueva función de rango de precios personalizable para los LP no fungibles, cada posición tiene su propio fee de LP y APR de CAKE del farming.

Para hacerlo más fácil y menos desafiante a la hora de aportar liquidez, el nuevo APR automático se presenta con una flamante calculadora de ROI disponible al momento de aportar liquidez o depositar en el Farm.

## Indicador y cálculo automático de APR <a href="#12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Cuando aportas liquidez, el indicador automático de APR responde a tus cambios en la configuración y calcula el APR basado en la misma.

Por ejemplo, en la mayoría de los casos, si achicas tu rango de precios, el APR subirá.

Tenga en cuenta para los APRs de los fee de LP:

* La cantidad estimada de recompensas de fee de LP varía basada en el tier de fee seleccionado, el reclamo y reinversión de las recompensas de fee deben hacerse manualmente.
* Las cifras de APR son calculadas usando el volumen de trading histórico, el cual depende de Subgraph y puede verse afectado por demoras en la actualización.

Para los APRs de farming:

* La cantidad estimada de recompensas en CAKE se basa en las emisiones actuales de CAKE para los farms. Están sujetas a cambios, basados en futuros ajustes en las emisiones.

{% hint style="info" %}
Todos los valores son calculados según las tasas y condiciones del pool actuales y están sujetas a cambios debidos a varias variables externas. Son estimaciones brindadas solamente como ayuda, y de ninguna manera garantizan retornos específicos.
{% endhint %}

Puedes encontrar este indicador de APR en las siguientes secciones:

* La página de “Add Liquidity” - mostrando el APR de fee de LP
* Página de detalles de cada posición de liquidez existente - mostrando el APR de fee de LP\
  ![](<../../.gitbook/assets/image (6) (1).png>)
* Página de Farm, dentro de la posición debajo de cada farm - mostrando el APR combinado de los fee de LP y las recompensas en CAKE\
  ![](<../../.gitbook/assets/image (9) (4).png>)\


## Calculadora de ROI mejorada <a href="#6f06dc46-ff61-4022-a29d-3ebe67a50607" id="6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="../../.gitbook/assets/image (7) (6).png" alt=""><figcaption></figcaption></figure>

Siempre que vea las pantallas de APR automática, puede hacer clic y abrir la nueva calculadora de ROI. La nueva calculadora de ROI ha sido rediseñada con funciones adicionales de servicio para satisfacer las necesidades de aporte de liquidez concentrada y farming V3.&#x20;

Repasemos juntos cada una de las secciones:

### Monto de depósito, “Staked For” y “Compounding Every” <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Estos son los tres datos principales a ingresar, los cuales también fueron presentados en la calculadora anterior. Sirven para definir:

1. Cuánto es lo que está aportado en la posición, en USD.
2. Por cuánto tiempo estará  depositado en la posición.
3. Con qué frecuencia harás la reinversión de las recompensas.



⓵ **Monto de depósito**

<figure><img src="../../.gitbook/assets/deposit-amount.gif" alt=""><figcaption></figcaption></figure>

Puedes ingresar la cantidad en USD manualmente, o usar los botones para autocompletar directamente $100, $1000 o la cantidad máxima permitida, según la cantidad disponible en tu wallet.



⓶ **Duración del depósito**

<figure><img src="../../.gitbook/assets/stake-durations.gif" alt=""><figcaption></figcaption></figure>

Puedes elegir por cuánto tiempo tus activos estarán depositados en la posición, eligiendo entre: 1 dia, 7 dias, 30 dias, 1 año, and 5 años.

La cantidad de retorno se calculará en base a esa duración.



⓷ **Compounding (Reinversión)**

<figure><img src="../../.gitbook/assets/compounding.gif" alt=""><figcaption></figcaption></figure>

Puedes seleccionar con qué frecuencia estarás recogiendo las recompensas generadas por la posición, y reinvirtiéndolas en ella. puedes elegir entre: 12 horas, 1 dia, 7 dias, and 30 dias.

La cantidad de retorno y el APY serán calculados en base a tu elección. Si no tienes pensado reinvertir tus recompensas, desmarca la casilla de la izquierda.

{% hint style="info" %}
En V3, los fees ganados por el LP y los CAKE de recompensa, deben ser recogidos y reinvertidos manualmente.
{% endhint %}

### &#x20;⓸ Histórico del Precio <a href="#19cd815c-ef3d-496a-8469-fb0164f3946b" id="19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Esta es sólo una sección informativa para ver los movimientos históricos del precio del par seleccionado.

Puedes ver el histórico en diferentes escalas de tiempo, como, por ejemplo, cuánto suele fluctuar el precio y luego establecer una configuración de rango de precios adecuada para equilibrar entre una APR más alta y un menor riesgo de impermanent loss.

* MIN - precio mínimo
* MAX - precio máximo
* AVG - precio promedio
* CURRENT - precio actual

{% hint style="info" %}
The price chart is only using data from the actual V3 pair. Therefore price data before V3 deployment is not available. The four price metrics represent the currently selected timeframe and will change based on the selection.
{% endhint %}

### ⓹ Price Range <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](broken-reference)

Using this section, you may check how much liquidity has been deposited to different price ranges, and come up with and set the price range you are providing liquidity to.

You may find the distribution chart below the title. The larger the amount of liquidity, the higher the chart will be.

You can change your price range settings by:

* Dragging the two handles on the chart to increase or describes the minimum and maximum price limit.
* Using the space between two handles to shift the selected range.
* Clicking the + and - button on the min and max price fields.
* Clicking the numbers in the price fields and entering them manually.

If you want to navigate the distribution chart:

1. Use the plus and minus magnifier buttons to zoom in and out
2. Drag the X (bottom) axis to shift left and right

If you want to provide liquidity to the entire price range, click “Full Range”

### ⓺ Flip the price direction to view prices with different base <a href="#5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](broken-reference)

For some token pairs, it is easier and more intuitive to view prices with certain base tokens. For example, for BNB/USDT pair, most people will prefer to view prices in “how many USDT per BNB” instead of the other way around.

You can easily flip the price displays. Simply click the button following the “View prices in:” to switch the base between two tokens in the pair.

### ⓻ Import and export (apply) your settings <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](broken-reference)

When you open the ROI calculator in the “Add Liquidity” window, or by viewing an existing position, the following settings will be automatically imported so you don’t need to set them again:

1. The amount of assets you are depositing
2. The price range
3. The selected fee tier

When you finish configuring in the ROI calculator, you can click “Apply Settings” to quickly apply the settings from the calculator back to the “Add Liquidity” window so you don’t need to match them manually.

### ⓼ Calculate farming rewards and APR <a href="#584c385b-5f76-42e5-8751-8344d6bd4749" id="584c385b-5f76-42e5-8751-8344d6bd4749"></a>

Farming rewards will be included in the calculations if you bring up the ROI calculator under the “Farm” page.

You can expand the detail sections to see the rewards breakdown
