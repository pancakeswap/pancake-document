# FAQ de la Lotería

## ¿Qué pasa si no hay ganadores?

Si el CAKE del pozo de premios no es ganado, ¡no se desperdicia! El CAKE no reclamado pasa a la siguiente ronda de la Lotería.

## Mi boleto coincide con varios números pero no puedo reclamar un premio

Los boletos solo son elegibles para premios si los números coinciden de izquierda a derecha. Consulta la [documentación de Lottery v2](./) para una explicación detallada.

## ¿En qué se diferencia Lottery v2 de Lottery v1?

Lottery v2 distribuye premios de manera más amplia que Lottery v1. Le da a cada boleto 1 posibilidad entre 10 de coincidir con el primer número, lo que significa que más boletos ganarán al menos un pequeño premio. También tiene 6 números (en lugar de 4) que deben coincidir secuencialmente para ganar el mayor premio.

En general, esto significa que más boletos pueden ganar un premio, pero el jackpot más grande se ganará con menos frecuencia, ¡lo que da lugar a enormes pozos de premios para el primer lugar!

**Lottery v2 introduce:**

* precios de boletos más económicos (\~$5 USD en CAKE por boleto) que no fluctúan drásticamente con el precio de CAKE
* descuentos por compra de boletos al por mayor
* 6 niveles de premios con pozos de premios crecientes a medida que se coinciden más números
* selección manual de números (opcional), para que los usuarios puedan usar sus números de la suerte
* [implementación de VRF de Chainlink](https://docs.chain.link/docs/chainlink-vrf/) para una aleatoriedad verdadera y segura
* tarifas generales más bajas (ver [más abajo en esta página](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets) para más información)

[Aprende más sobre las características, el juego y los premios de Lottery v2](./)

## ¿Cómo se distribuyen los premios entre los niveles?

El pozo de premios de cada nivel es una parte del total de CAKE en cada ronda de Lotería.

* | Nivel (números coincidentes en orden) | Asignación de CAKE |
  | ------------------------------------- | ------------------ |
  | Primer 1 número                       | 2%                 |
  | Primeros 2 números                    | 3%                 |
  | Primeros 3 números                    | 5%                 |
  | Primeros 4 números                    | 10%                |
  | Primeros 5 números                    | 20%                |
  | Primeros 6 números                    | 40%                |
  | Quema                                 | 20%                |

## ¿Puedo intercambiar mis boletos de vuelta a CAKE?

No, una vez comprados no podrás convertir tus boletos de vuelta a CAKE.

## Si gano, ¿necesito reclamar el premio manualmente?

Sí, deberás hacer clic en el botón **Verificar ahora** debajo de "¿Eres un ganador?" en la página de la Lotería.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2868%29.png)

## ¿Con qué frecuencia se realiza la lotería?

El sorteo de la lotería ocurre cada 12 o 36 horas. Un sorteo de lotería ocurre cada día alternando entre las 0 AM UTC y las 12 PM UTC; las próximas rondas después de las rondas de las 0 AM UTC serán después de 36 horas, y las próximas rondas después de las rondas de las 12 PM UTC serán después de 12 horas.

![Calendario de inyección de la Lotería](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Lottery%20Schedule%20Update%20Feb%204.png)

## ¿Qué tarifa de transacción pagaré por comprar boletos?

Cada compra de boletos que realices será una transacción. Comprar un solo boleto en una compra de Lotería costará la cantidad normal de tarifas por una transacción.

Sin embargo, comprar más boletos en esa compra aumentará la tarifa. Comprar 100 boletos en lugar de 1 no multiplicará la tarifa por 100, pero puede aumentar el monto de la tarifa entre 5 y 6 veces (aunque esto varía).

## ¿Cómo funciona el descuento por volumen?

El descuento por volumen recompensa la compra de mayores cantidades de boletos con un descuento escalonado. Si solo compras 2 boletos, el descuento es insignificante, pero se acumulará rápidamente a medida que aumentes el número de boletos a comprar en una transacción.

El descuento solo se aplica a cada transacción de hasta 100 boletos. El descuento no se traslada a la siguiente transacción ni a la siguiente ronda.

## ¿Por qué solo puedo comprar 100 boletos?

Solo puedes comprar un máximo de 100 boletos en una sola compra, pero puedes hacer varias compras. Nada te impide comprar más boletos después de tus primeros 100.

## Si creo manualmente dos o más boletos con los mismos números y ganan, ¿soy elegible para recibir premios por cada boleto?

Sí, cada boleto se trata como una participación separada en la Lotería. Sin embargo, ten en cuenta que los premios no serán 1:1, ya que cada boleto ganador que tengas diluye cada parte de los premios totales del nivel.

## Calendario de inyección: ¿Cuándo se agrega CAKE a la lotería?

Cuando las personas compran boletos, el CAKE que gastan se agrega al pozo de la lotería. Además, se agregan (inyectan) 8,000 CAKE al pozo de la lotería cada dos rondas en un calendario regular durante el transcurso de siete rondas por semana, como se muestra arriba en la figura del calendario de lotería.
