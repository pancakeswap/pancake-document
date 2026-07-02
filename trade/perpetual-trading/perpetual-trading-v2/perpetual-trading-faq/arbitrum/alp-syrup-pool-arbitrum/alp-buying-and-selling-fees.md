# Taxas de Compra e Venda do ALP

## Taxa de Compra:

Parâmetro de Taxa Base 1: FeeBasisPoints, USDT atualmente definido em 0,25%

Parâmetro de Taxa Base 2: TaxBasisPoints, USDT atualmente definido em 0,05%

O valor atual do ativo: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

O valor atual do ativo após a cunhagem: AfterMinValue=InitialValue+MinValue

Calcule o valor do ativo de acordo com o peso alvo: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Peso alvo，Total Value=sum(InitialValue)



A diferença entre o valor atual do ativo e o valor alvo (valor absoluto): InitialDiff=InitialValue-TargetValue

Após a Cunhagem, a diferença entre o valor do ativo e o mecanismo alvo (valor absoluto): AfterDiff=AfterMintValue-TargetValue

* se AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* se AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Taxa de Venda:

Parâmetro de Taxa Base 1: FeeBasisPoints, USDT atualmente definido em 0,25%

Parâmetro de Taxa Base Máxima 2: TaxBasisPoints, USDT atualmente definido em 0,05%

O valor atual do ativo: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

O valor atual do ativo após a Queima: AfterMaxValue=InitialValue-MinValue

Calculando o valor do ativo de acordo com o peso alvo: TargetValue=Total Value\*Peso alvo



A diferença entre o valor atual do ativo e o valor alvo (valor absoluto): InitialDiff=InitialValue-TargetValue



Após a Queima, a diferença entre o valor do ativo e o mecanismo alvo (valor absoluto): AfterMaxDiff=AfterBurnValue-TargetValue

* se AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* se AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Por exemplo:

Se o valor do pool ALP for $10.000.000, o PnL não realizado for $+10.000, e o valor do BTC no pool de liquidez for $1.000;

O peso alvo do BTC é 2%, e o peso atual é 0,01%. O parâmetro de taxa base 1 do BTC é 0,25%, e o parâmetro de taxa base 2 é 0,45%.

De acordo com o cálculo, a taxa de compra de ALP com 1 BTC neste momento é de 0% = 0 BTC. A taxa de transação para vender ALP para obter 1 BTC é de 0,7% = 0,007BTC.
