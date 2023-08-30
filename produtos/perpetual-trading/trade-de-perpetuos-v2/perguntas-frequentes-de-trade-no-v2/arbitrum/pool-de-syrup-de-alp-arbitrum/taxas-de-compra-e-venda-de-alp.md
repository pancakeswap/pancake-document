# Taxas de Compra e Venda de ALP

## Taxa de compra:&#x20;

Parâmetro de taxa básica 1: FeeBasisPoints，USDT está atualmente definido em 0,25%&#x20;

Parâmetro de taxa básica 2: TaxBasisPoints，USDT está atualmente definido em 0,05%&#x20;

O valor do ativo atual: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd&#x20;

O valor do ativo atual após a cunhagem: AfterMinValue=InitialValue+MinValue&#x20;

Calcule o valor do ativo de acordo com o peso alvo: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Target Weight，Total Value=sum(InitialValue)

O valor do ativo atual e o valor alvo (valor absoluto): InitialDiff=InitialValue-TargetValue&#x20;

Após a cunhagem, o valor do ativo e o mecanismo de destino (valor absoluto):&#x20;

* if AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* if AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Taxa de venda:&#x20;

Parâmetro de taxa básica 1: FeeBasisPointsUSDT está atualmente definido em 0,25%&#x20;

Parâmetro 2 da taxa básica máxima: TaxBasisPoints, USDT está atualmente definido em 0,05%&#x20;

O valor do ativo atual: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd&#x20;

O valor atual do ativo após Burn: AfterMaxValue=InitialValue-MinValue&#x20;

Cálculo do valor do Ativo de acordo com o peso alvo: TargetValue=Total Value\*Target weight

O valor do ativo atual e o valor alvo (valor absoluto): InitialDiff=InitialValue-TargetValue

AfterBurn, o valor do ativo e o mecanismo de destino (valor absoluto): AfterMaxDiff=AfterBurnValue-TargetValue&#x20;

* if AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* if AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

Por exemplo: Se o valor da pool de ALP for $ 10.000.000, o PnL não realizado for $+10.000, o valor do BTC na pool de liquidez será $1.000; O peso alvo do BTC é de 2% e o peso atual é de 0,01%. O parâmetro de taxa básica 1 do BTC é 0,25% e o parâmetro de taxa básica 2 é 0,45%. De acordo com o cálculo, a taxa de compra de ALP com 1 BTC neste momento é de 0% = 0 BTC. A taxa de transação para vender ALP para obter 1 BTC é de 0,7% = 0,007 BTC.
