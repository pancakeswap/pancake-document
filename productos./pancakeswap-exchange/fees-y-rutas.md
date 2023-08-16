# Fees y Rutas()

<figure><img src="https://1397868517-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FbltfShICv3qXjBDvXs4D%2Fimage.png?alt=media&#x26;token=150bc744-9677-4cb3-9715-962129da90c9" alt=""><figcaption></figcaption></figure>

En el Exchange V3, por defecto, el Smart Router de PancakeSwap usará la liquidez de V3, V2, StableSwap (BNB Chain), y el AMM y market makers (BNB Chain & Ethereum), para ejecutar los trades y encontrar el mejor precio para el usuario.

No obstante, los usuarios pueden personalizar su trade, eligiendo qué fuentes de liquidez utilizará el router, y habilitar o deshabilitar los saltos múltiples (multihops) y la partición del ruteo.

#### **Compruebe el porcentaje y monto del fee que será aplicado** <a href="#check-the-fee-rate-and-fee-amount-that-is-currently-applied" id="check-the-fee-rate-and-fee-amount-that-is-currently-applied"></a>

**​**![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2Fnqy8uYAg8BQgxS59DX5Z%2Fimage.png?alt=media\&token=d40a135f-5aba-4a3b-96be-7f8c1acc6998)**​**

Para chequear el fee que se cargará a su swap, chequee la secciín "Fee" en la sección de detalles del swap.

​![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F3nrML91JusId7aqIdEVP%2Fimage.png?alt=media\&token=b9aa3a03-727e-445b-bda8-01201992943d)​

Para comprobar qué tipo de pool y el tier de fee al que se está ruteando su trade, chequee la sección "Route".

​![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F58t91ixuBC7aCiKXghwD%2Fimage.png?alt=media\&token=5170c00e-52e5-45af-aa35-3f78b225e4d7)​

Para ver más detalles, haga clic en el ícono de lupa para que se muestre la ruta completa del trade.​

#### **Personalice las fuentes de liquidez** <a href="#customize-liquidity-sources" id="customize-liquidity-sources"></a>

**​**![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FXApQi3HsYCgZ7An6iNNC%2Fimage.png?alt=media\&token=81d58274-199a-41e5-bd66-5aefb04532a9)**​**

En la parte superior de la interfaz “Customize Routing”, puede elegir qué fuente/s de liquidez usará el router mientras ejecuta el trade. Para acceder a esta interfaz, podrá:

* Clic “Customize Routing” en la parte inferior del detalle del ruteo del trade.
* Clic en el ícono de engranaje en la interfaz del swap, y luego clic en "Customize Routing” en la parte inferior.

Por defecto, todas las fuentes de liquidez están habilitadas y el Smart Router aprovechará toda la liquidez disponible dentro de PancakeSwap. Por favor tenga en cuenta que el router NO ruteará trades entre pools de liquidez de AMM y MM market makers. Cuando su trade sea ejecutado por MM market makers, no será a través de ningún pool de liquidez de AMM.

​![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2F2Nrn5dKnU9tyhmnPD5hv%2Fimage.png?alt=media\&token=1946be90-28b8-4cb9-8132-61fa9013f1d6)​

Siempre podrá resetear la configuración como se presenta por defecto, haciendo clic en el botón “Reset” en la esquina superior derecha.​

#### **Personalice las preferencias de ruteo** <a href="#customize-routing-preferences" id="customize-routing-preferences"></a>

**​**![](https://1397868517-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MHREX7DHcljbY5IkjgJ-1972196547%2Fuploads%2FqJtYFWta26LHBtl6FZWC%2Fimage.png?alt=media\&token=46594c8d-586e-4e29-904c-f5f73a77c901)**​**

L pie de la interfaz “Customize Routing”, puede personalizar sus preferencias de ruteo habilitando o deshabilitando multihops y la partición del ruteo.

Multihops permite que se intercambien tokens en varios pasos (saltos) entre varios pools de liquidez para obtener el mejor resultado. Deshabilitarlo restringirá el trade a swaps directos, lo que puede causar un slippage muy alto o incluso la pérdida de fondos.

Particionar el ruteo permite que los swaps se dividan en múltiples rutas para obtener el mejor resultado. Deshabilitarlo restringirá el trade a ser ejecutado mediante una única ruta, lo que puede resultar en una baja eficiencia o alto slippage.

{% hint style="info" %}
Cuando no sea posible ejecutar su trade debido a la configuración personalizada, aparecerá una advertencia, y usted podrá hacer clic en  “Check your settings” para acceder rápidamente a la interfaz de “Customize Routing”. O elegir “Reset to default” para directamente volver a la configuración por defecto.
{% endhint %}
