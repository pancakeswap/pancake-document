# Lotería: FAQ

## Qué pasa si no hay ganadores?

Si no hay premios ganados en una ronda no se tiran a la basura! Los premios pasan directamente a la siguiente ronda.&#x20;

## Mi Ticket coincide con varios números, pero no puedo reclamar ningún premio

Los boletos solo son elegibles para premios si coinciden los con números de izquierda a derecha. Consulte la documentación de Lotería v2 para obtener una explicación detallada.

## En qué se diferencia la Lotería v2 de la Lotería v1?

Lotería v2 distribuye más ampliamente los premios que Lotería v1. Le da a cada ticket una oportunidad de 1 en 10 de igualar el primer número, lo que significa que más tickets ganarán al menos un pequeño premio. También tiene 6 (frente a 4) números que deben coincidir secuencialmente para ganar el premio más grande.

En general, esto significa que más boletos pueden ganar un premio, pero el premio mayor se ganará con menos frecuencia, ¡lo que hace que haya grandes premios acumulados!

**La Lotería v2 introduce:**

* Tickets más baratos (\~$5 USD en CAKE por ticket) que no oscilan con el precio de CAKE
* Descuento por compras en cantidad
* 6-tiered prize pool brackets with increasing prize pools as more numbers are matched Horquillas de premios acumulados de 6 niveles con un aumento de los premios acumulados a medida que se emparejan más números
* Selección manual de números (opcional), así que los usuarios pueden utilizar sus números afortunados.
* [Implementación de VRF por parte de Chainlink](https://docs.chain.link/docs/chainlink-vrf/) para una aleatoriedad verdadera y segura
* Tarifas más bajas (consulte más abajo en esta página para obtener más información)

Más información sobre las características, el modo de juego y los premios de Lottery v2

## Cómo se dividen los premios entre categorías??

El total de premios de cada categoría es una parte del CAKE total en cada ronda de la Lotería.

* | Categoría | Cantidad Total de CAKE |
  | --------- | ---------------------- |
  | 1 número  | 1%                     |
  | 2 números | 3%                     |
  | 3 números | 6%                     |
  | 4 números | 10%                    |
  | 5 números | 20%                    |
  | 6 números | 40%                    |
  | Quema     | 20%                    |

## Puedo cambiar mis boletos de vuelta a CAKE??

No, una vez comprado no podrás volver a convertir tu boleto a CAKE.

## Si gano, ¿necesito reclamar manualmente el premio?

Sí, deberá hacer clic en el botón **Check Now** en "Are you a winner?" en la página de la Lotería.

![](<../../.gitbook/assets/image (86).png>)

## Cada cuánto se juega la Lotería?

Cada sesión completa de Lotería durará 12 horas.

## Qué tarifa de transacción pagaré por comprar Tickets?

Cada compra de tickets que realices será una transacción. Comprar un solo boleto en una compra de la Lotería costará la cantidad normal de tarifas para una transacción.

Sin embargo, comprar más boletos en esa compra aumentará la tarifa. Comprar 100 boletos en lugar de 1 no multiplicará la tarifa por 100, pero puede aumentar el monto de la tarifa unas 5-6 veces (aunque esto varía).

## Cómo funciona el descuento por comprar varios tickets?

El descuento en cantidad recompensa la compra de mayores cantidades de boletos con un descuento de escala. Si solo compra 2 boletos, el descuento es insignificante, pero se sumará rápidamente a medida que aumente el número de tickets para comprar en una transacción.

El descuento solo se aplica a cada transacción de hasta 100 boletos. El descuento no se traslada a la siguiente transacción o ronda siguiente.

## Por qué solo puedo comprar 100 tickets?

Usted puede comprar más de 100 tickets, pero sólo de a 100 en cada compra. No hay nada que le impida comprar más boletos después de sus primeros 100.

## Si creo manualmente dos o más boletos con los mismos números y ganan, ¿soy elegible para premios por cada boleto?

Sí, cada boleto se trata como una entrada distinta a la Lotería. Sin embargo, tenga en cuenta que los premios no serán de 1:1, ya que cada boleto ganador que tenga diluye cada parte de los premios totales del grupo.

