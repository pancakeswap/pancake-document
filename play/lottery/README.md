# 🎟️ Lotería

Jugar la Lotería de PancakeSwap te da la oportunidad de ganar enormes premios en CAKE. ¡Es fácil, justa y puedes participar tantas veces como quieras siempre que tengas CAKE para comprar un boleto!

[Ver contrato inteligente](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)

## **Detalles:**

* Costo del boleto de Lotería por 1 boleto: \~$5 USD en CAKE.
* Límite de participación individual en la Lotería: Sin límite total, pero solo se pueden comprar 100 boletos a la vez.
* Al pagar por un boleto, se les dará a los usuarios una combinación aleatoria de 6 dígitos, siendo cada dígito un número entre 0 y 9, por ejemplo "1-9-3-2-0-4". Haz coincidir los números de izquierda a derecha para ganar premios: cuantos más números coincidan, mayor será el pozo de premios que compartirás.
* La Lotería usa la implementación de VRF de Chainlink para una aleatoriedad verdadera y segura.

## Costos de boletos y descuento por compra al por mayor

Los precios de los boletos de Lotería se establecen al inicio de la nueva ronda de lotería, con un objetivo de $5 USD (puede variar ligeramente con fluctuaciones de precio repentinas).

Comprar varios boletos de Lotería a la vez ofrece un descuento por volumen en tu compra. Puedes comprar hasta 100 boletos en una sola compra, con el descuento comenzando de forma pequeña con 2 boletos y escalando hasta un 10% con 100 boletos.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-08-22%20at%209.59.52%20PM.png)

## **Cómo ganar**

Haz coincidir los números, **desde el lado izquierdo de tu boleto**, con los números ganadores sorteados al final de una ronda de Lotería.

* Hacer coincidir incluso solo el primer número te dará un pequeño premio.&#x20;
* Haz coincidir más números para ganar una parte de un pozo de premios mayor.

## **‌**Elegibilidad de premios

‌Hay un total de seis bolas de lotería, del 0 al 9, en cada boleto. Para ganar, tus números deben coincidir con los números sorteados en el mismo orden que las bolas de lotería, comenzando desde la izquierda del boleto. Por ejemplo:

Números sorteados

![Números sorteados](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28285%29.png)

Los números de tu boleto

![Tu Boleto A](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2895%29%20%281%29.png)

En el ejemplo anterior, el Boleto A, cinco de los números del boleto coinciden con los mismos números sorteados, en el mismo orden exacto: todos excepto el cuarto.

Sin embargo, dado que el cuarto dígito **no** coincide con el número sorteado, solo los primeros tres dígitos cuentan como coincidentes en orden. Esto ganaría un premio de "Coincide los primeros 3".

![Tu Boleto B](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28205%29.png)

Boleto B de ejemplo. Este no tiene suerte. Aunque los últimos cinco dígitos coinciden, el primer dígito no coincide, por lo que este boleto no gana absolutamente nada.

Solo compartirás los premios del nivel de premio más alto para el que seas elegible. Un boleto que coincida con los primeros tres números solo será elegible para los premios del nivel de coincidencia de tres, y no para los niveles de coincidencia de uno o dos.

**Recuerda: Los dígitos deben coincidir en orden, de izquierda a derecha.**

## Distribución de premios entre los niveles

‌Después de que se realice el sorteo de una ronda y se determinen los boletos con números coincidentes, se otorgan los premios. El monto ganado por cada boleto dependerá de cuántos otros boletos hayan ganado en el mismo nivel de premio.

‌Por ejemplo, si tienes el único boleto que coincidió con tres números en orden, y la parte predeterminada del pozo de premios para tu nivel era 2000 CAKE, recibirás los 2000 CAKE completos.

‌Sin embargo, si tú y otras tres personas coinciden con tres números en orden, los 2000 CAKE se dividirían entre los cuatro boletos ganadores, lo que significa que recibirías 500 CAKE.

Consulta las [FAQ de la Lotería para ver el desglose de premios](lottery-faq.md#how-are-prizes-broken-down-between-brackets) en cada nivel.
