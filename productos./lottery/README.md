# 🎟 Lotería v2

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/loteria-v2.png)

​¡Jugar a la Lotería PancakeSwap te da la oportunidad de ganar enormes premios CAKE! Es fácil, justo, y puedes entrar tantas veces como quieras siempre y cuando tengas CAKE para comprar un boleto. [Ver el smart contract](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)​

## **Especificaciones:** <a href="#specifics" id="specifics"></a>

* Costo de un boleto de lotería \~$5 USD en CAKE.
* Límite de participación en la Lotería de usuarios individuales: No hay límite general, pero solo se pueden comprar 100 boletos a la vez.
* Pagar por un boleto dará a los usuarios una combinación aleatoria de 6 dígitos con cada dígito entre 0-9, por ejemplo, "1-9-3-2-0-4". Coincide con los números ganadores empezando desde la izquierda para ganar premios: cuantos más números coincidan, mayor será el premio acumulado que compartirás.
* Lotería V2 utiliza la implementación de VRF de Chainlink para una aleatoriedad verdadera y segura.

## Costo del Ticket y descuento por compra en cantidad <a href="#ticket-costs-and-bulk-purchase-discount" id="ticket-costs-and-bulk-purchase-discount"></a>

Los precios de los boletos de lotería se establecen al comienzo de la nueva ronda de lotería, y el objetivo es de $5 USD (puede variar ligeramente con las fluctuaciones repentinas de los precios).

Comprar varios boletos de lotería a la vez da un descuento a su compra. Puede comprar hasta 100 boletos en una compra, con un descuento pequeño comenzando en 2 boletos, y escalando hasta 4.95% en 100 boletos.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MdoMyKjuabNBbt1PxoP%2F-MdoPP07JEa9GDmnE5bu%2Fimage.png?alt=media\&token=192155fd-53df-483f-aac1-faa5780c9605)

## **Cómo ganar** <a href="#how-to-win" id="how-to-win"></a>

Coincide con los números, **desde el lado izquierdo de tu boleto**, con los números ganadores sorteados al final de una ronda de Lotería.

* Igualar incluso el primer número le hará ganar un pequeño premio.
* Iguala más números y gana una parte de un premio acumulado más grande.
* ¡Iguala los 6 números exactamente y gana una parte del 40% del total de premios recaudados!

## **‌**Elegibilidad para el premio <a href="#prize-eligibility" id="prize-eligibility"></a>

Hay un total de seis bolas de lotería, de 0 a 9, en cada boleto. Para ganar, sus números deben coincidir con los números sorteados en el mismo orden que las bolas de lotería, comenzando desde la izquierda del boleto. por ejemplo:

Números Sorteados![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MdpMa-EHc7hyY29e6dr%2F-MdpOY\_cQRE7q\_pphjsc%2Fimage.png?alt=media\&token=108a4565-4494-4a5f-a047-8acff540afc7)Números Sorteados

&#x20;Números de Ticket![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MdpMa-EHc7hyY29e6dr%2F-MdpOU\_vVcWmXuUGvtYV%2Fimage.png?alt=media\&token=d699a43b-dd0a-4ff9-b4ac-5ef48013ee4c)Tu Ticket A

En el ejemplo anterior, el Ticket A, cinco de los números del ticket coinciden con los mismos números sorteados, en el mismo orden exacto: todos excepto el cuarto.

Sin embargo, puesto que el cuarto dígito no coincide con el número sorteado, sólo los tres primeros dígitos cuentan como coincidentes en orden. Esto ganaría un premio de "Match first 3".

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MdpMa-EHc7hyY29e6dr%2F-MdpPAGJFJvx\_3KJA8Z2%2Fimage.png?alt=media\&token=60133967-ee4d-4560-9222-907f12aff88a)Tu Ticket B

Ejemplo ticket B. Aquí hay mala suerte. A pesar de que los últimos cinco dígitos coinciden, el primer dígito no coincide, por lo que este boleto no gana nada en absoluto.

Solo compartirás los premios del grupo de premios más alto para el que seas elegible. Un boleto que coincida con los tres primeros números solo será elegible para premios del grupo de tres coincidencias, y no para las distribuciones de ganadores con uno o dos números coincidentes.

**Recuerda: Los dígitos deben coincidir en orden, empezando de izquierda a derecha.**

## Reparto de premios entre los grupos de premios <a href="#prize-sharing-across-prize-brackets" id="prize-sharing-across-prize-brackets"></a>

Después de que se sortea una ronda y se determinan los boletos con números coincidentes, se otorgan los premios. La cantidad ganada por cada boleto dependerá de cuántos otros boletos ganaron en el mismo rango de premios.

Por ejemplo, si tiene el único boleto coincidió con tres números en orden, y la parte predeterminada de la bolsa de premios para su grupo fue 2000 CAKE, recibirá los 2000 CAKE completos.

Sin embargo, si usted y otras tres personas coinciden con tres números en orden, los 2000 CAKE se dividirían entre los cuatro boletos ganadores, lo que significa que recibiría 500 CAKE.

Vea la imagen de abajo para un desglose de los premios en cada grupo.[\
](https://docs.pancakeswap.finance/products/syrup-pool/syrup-pool-faq)

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MduQ2RtStF7WobF1e2A%2F-MduUqhz46Gaf5m0kXLP%2Fimage.png?alt=media\&token=feb3e737-0fc4-42b6-85f5-d47c37fd01b9)
