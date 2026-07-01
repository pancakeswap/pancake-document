# Cómo usar las Órdenes Límite

Las órdenes límite con generación de comisiones en PancakeSwap funcionan de manera diferente a las órdenes límite tradicionales. Cuando un usuario coloca una orden límite, está proporcionando efectivamente **liquidez unilateral** a un pool de PancakeSwap Infinity.

A medida que el precio de mercado se mueve, los intercambios en el pool pueden utilizar la liquidez del usuario. Cuando esto ocurre, los tokens depositados se convierten completamente en los tokens de salida, y el usuario recibe:

* Los tokens de salida, y
* Las comisiones de trading ganadas por los intercambios ejecutados contra su liquidez.

***

**Ejemplo: Vender BNB por USDT**

* **Precio actual en el pool BNB/USDT:** 600 USDT por BNB
* **Precio objetivo/límite del usuario:** 700 USDT por BNB

Proceso:

1. El usuario establece una orden límite para vender BNB a 700 USDT.
2. Sus BNB se depositan en el tick más cercano al precio de 700 USDT por BNB en el pool.
3. Cuando el precio del mercado externo alcanza 700 USDT, el precio del pool se ajusta para coincidir (debido a oportunidades de arbitraje / mejor precio).
4. En ese momento, los BNB del usuario se intercambian por USDT.
5. Durante este proceso, el usuario gana comisiones por cada intercambio que consume su liquidez.
6. Una vez que la liquidez se consume completamente, el USDT convertido (más comisiones) se retira automáticamente y se envía a la billetera del usuario.

***

### Guía paso a paso

Elige un par de tokens (p. ej., BNB/CAKE) y la cantidad que deseas vender/comprar

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Establece tu precio objetivo/límite

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Coloca la orden límite y haz clic en "Confirmar". La liquidez se deposita en tu nombre en el tick más cercano al precio límite

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Una vez que el precio del pool alcance tu objetivo, tu orden se ejecuta. Los tokens de salida deseados más las comisiones se retiran automáticamente y se envían a tu billetera.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Estado de la orden

Puedes ver el estado de tu orden haciendo clic aquí

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Tu orden puede encontrarse en uno de los siguientes estados:**

| Estado             | Descripción                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------- |
| Pendiente          | Esperando que el precio alcance tu objetivo                                                              |
| Completada         | Orden ejecutada y fondos enviados a tu billetera                                                         |
| Parcialmente completada | Solo parte de tu orden fue ejecutada. Tendrás ambos tokens (p. ej., parte BNB, parte USDT)         |
| Cancelada          | Cancelaste la orden. Todos tus fondos te son devueltos                                                   |

### FAQ

**P: ¿Necesito pagar comisiones para colocar una orden límite?**

R: No. En cambio, ganas un 0,1% en comisiones de trading cuando tu orden se ejecuta.

**P: ¿Puedo colocar órdenes para cualquier par?**

R: En el lanzamiento, solo se admiten pares seleccionados. Se agregarán más pares más adelante.

**P: ¿Cuál es el tamaño mínimo de orden?**

R: $50. Esto evita órdenes pequeñas que podrían resultar en gas excesivo.&#x20;

**P: ¿Qué ocurre si solo se completa parte de mi orden?**

R: Tendrás ambos tokens. Puedes cancelar en cualquier momento y retirar ambos tokens más las comisiones ganadas.

**P: Mi orden está completada pero aún no he recibido los fondos en mi billetera.**

R: En escenarios muy raros esto podría ocurrir, pero tus fondos siempre están seguros. Simplemente usa el botón "Retirar" en la interfaz de detalles de la orden para reclamar los fondos manualmente.
