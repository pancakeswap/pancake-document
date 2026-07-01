# Comisiones y Rutas

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

En Exchange V3, por defecto, el Smart Router de PancakeSwap utiliza liquidez de V3, V2, StableSwap (BNB Chain), y el AMM y los market makers (BNB Chain y Ethereum), para ejecutar trades y encontrar el mejor precio para los traders.

Sin embargo, los usuarios siempre pueden personalizar su trade eligiendo qué fuentes de liquidez utilizará el router, y activar o desactivar los saltos múltiples y el enrutamiento dividido.

### **Comprobar la tasa de comisión y el monto de comisión aplicado actualmente**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

Para comprobar cuánto se cobrará por tu intercambio actual, consulta la sección "Comisión" en los detalles del intercambio.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

Para comprobar qué tipo de pool y nivel de comisión tiene tu trade actualmente enrutado, consulta la sección "Ruta".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

Para ver más detalles, haz clic en el icono de lupa para mostrar la visualización completa de la ruta de trading.



### **Personalizar fuentes de liquidez**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

En la parte superior de la interfaz "Personalizar Enrutamiento", puedes elegir qué fuente de liquidez usará la ruta al enrutar tu trade. Para abrir esta interfaz, puedes:

* Hacer clic en "Personalizar Enrutamiento" en la parte inferior de la visualización de la ruta de trading.
* Hacer clic en el icono de engranaje en la interfaz de intercambio y luego en "Personalizar Enrutamiento" en la parte inferior.

Por defecto, todas las fuentes de liquidez están activadas y el Smart Router aprovechará al máximo toda la liquidez disponible en PancakeSwap.

Ten en cuenta que el router NO enrutará trades entre los pools de liquidez AMM y los market makers. Cuando tu trade sea ejecutado por market makers, no pasará por ningún pool de liquidez AMM.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

Puedes hacer clic en el botón "Restablecer" en la esquina superior derecha para restablecer las configuraciones a los valores predeterminados.



### **Personalizar preferencias de enrutamiento**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

En la parte inferior de la interfaz "Personalizar Enrutamiento", puedes personalizar tus preferencias de enrutamiento activando o desactivando los saltos múltiples y el enrutamiento dividido.

Los saltos múltiples permiten que los tokens se intercambien a través de múltiples saltos entre varios pools de liquidez para conseguir el mejor precio. Desactivarlo restringirá los trades a intercambios directos, lo que puede provocar mayor deslizamiento o incluso pérdida de fondos.

El enrutamiento dividido permite que los intercambios de tokens se dividan en múltiples rutas para conseguir el mejor precio. Desactivarlo restringirá los trades a una única ruta, lo que puede resultar en menor eficiencia o mayor deslizamiento.

{% hint style="warning" %}
Cuando tu trade no pueda ejecutarse debido a una configuración de trading personalizada, aparecerá una advertencia. Puedes hacer clic en "Revisar tu configuración" para abrir rápidamente la interfaz "Personalizar Enrutamiento", o elegir "Restablecer valores predeterminados" para restablecer tu configuración.
{% endhint %}
