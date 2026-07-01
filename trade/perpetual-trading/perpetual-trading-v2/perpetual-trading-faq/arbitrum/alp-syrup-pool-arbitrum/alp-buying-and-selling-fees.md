# Comisiones de Compra y Venta de ALP

## Comisión de compra:

Parámetro de Tasa Base 1: FeeBasisPoints, USDT está configurado actualmente al 0,25%

Parámetro de Tasa Base 2: TaxBasisPoints, USDT está configurado actualmente al 0,05%

El valor actual del activo: ValorInicial=ValorActivoEnPool+PnlNoRealizadoActivo_usd

El valor actual del activo después de la acuñación: ValorDespuésDeMin=ValorInicial+ValorMin

Calcula el valor del Activo según el peso objetivo: ValorObjetivo=(Valor Total_usd+PnlNoRealizadoTotal_Usd)\*Peso objetivo, Valor Total=suma(ValorInicial)



La diferencia actual del valor del Activo y el valor objetivo (valor absoluto): DiferenciaInicial=ValorInicial-ValorObjetivo

Después de la Acuñación, la diferencia del valor del activo y el mecanismo objetivo (valor absoluto): DiferenciaDespués=ValorDespuésDeAcuñación-ValorObjetivo

* si DiferenciaDespués\<DiferenciaInicialValor&#x20;

ComisiónAcuñación=Máx(FeeBasisPoints-TaxBasisPoints\*DiferenciaInicial/ValorObjetivo，0)

* si DiferenciaDespués>=DiferenciaInicial&#x20;

ComisiónAcuñación=FeeBasisPoints+TaxBasisPoints\*Mín((DiferenciaInicial+DiferenciaDespués)/2,ValorObjetivo)/ValorObjetivo

## Comisión de venta:

Parámetro de Tasa Base 1: FeeBasisPoints, USDT está configurado actualmente al 0,25%

Parámetro de Tasa Base Máxima 2: TaxBasisPoints, USDT está configurado actualmente al 0,05%

El valor actual del activo: ValorInicial=ValorActivoEnPool+PnlNoRealizadoActivo_usd

El valor actual del activo después de la quema: ValorDespuésDeMáx=ValorInicial-ValorMin

Cálculo del valor del Activo según el peso objetivo: ValorObjetivo=Valor Total\*Peso objetivo



La diferencia del valor actual del activo y el valor objetivo (valor absoluto): DiferenciaInicial=ValorInicial-ValorObjetivo



Después de la Quema, la diferencia del valor del activo y el mecanismo objetivo (valor absoluto): DiferenciaDespuésDeMáx=ValorDespuésDeQuema-ValorObjetivo

* si DiferenciaDespués\<DiferenciaInicialValor

ComisiónQuema=Máx(FeeBasisPoints-MTaxBasisPoints\*DiferenciaInicial/ValorObjetivo，0)

* si DiferenciaDespués>=DiferenciaInicial&#x20;

ComisiónQuema=FeeBasisPoints+TaxBasisPoints\*Mín((DiferenciaInicial+DiferenciaDespués)/2,ValorObjetivo)/ValorObjetivo<br>

Por ejemplo:

Si el valor del pool ALP es $10.000.000, el PnL no realizado es $+10.000, el valor de BTC en el pool de liquidez es $1.000;

El peso objetivo de BTC es 2%, y el peso actual es 0,01%. El parámetro de tasa base 1 de BTC es 0,25%, y el parámetro de tasa base 2 es 0,45%.

Según el cálculo, la tasa de comprar ALP con 1 BTC en este momento es 0% = 0 BTC. La comisión de transacción por vender ALP para obtener 1 BTC es 0,7% = 0,007BTC.
