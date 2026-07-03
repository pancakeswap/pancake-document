# Commissioni di Acquisto e Vendita ALP

## Commissione di Acquisto:

Parametro Tasso Base 1: FeeBasisPoints, USDT è attualmente impostato allo 0,25%

Parametro Tasso Base 2: TaxBasisPoints, USDT è attualmente impostato allo 0,05%

Il valore dell'asset corrente: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

Il valore dell'asset corrente dopo il conio: AfterMinValue=InitialValue+MinValue

Calcola il valore dell'Asset in base al peso target: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Peso Target, Total Value=sum(InitialValue)



La differenza tra il valore dell'Asset corrente e il valore target (valore assoluto): InitialDiff=InitialValue-TargetValue

Dopo il Conio, la differenza tra il valore dell'asset e il meccanismo target (valore assoluto): AfterDiff=AfterMintValue-TargetValue

* se AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* se AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Commissione di Vendita:

Parametro Tasso Base 1: FeeBasisPoints, USDT è attualmente impostato allo 0,25%

Parametro Tasso Base Massimo 2: TaxBasisPoints, USDT è attualmente impostato allo 0,05%

Il valore dell'asset corrente: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

Il valore dell'asset corrente dopo la Bruciatura: AfterMaxValue=InitialValue-MinValue

Calcolo del valore dell'Asset in base al peso target: TargetValue=Total Value\*Peso Target



La differenza tra il valore dell'asset corrente e il valore target (valore assoluto): InitialDiff=InitialValue-TargetValue



Dopo la Bruciatura, la differenza tra il valore dell'asset e il meccanismo target (valore assoluto): AfterMaxDiff=AfterBurnValue-TargetValue

* se AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* se AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Ad esempio:

Se il valore del pool ALP è $10.000.000, il PnL non realizzato è $+10.000, il valore di BTC nel pool di Liquidità è $1.000;

Il peso target di BTC è del 2%, e il peso corrente è dello 0,01%. Il parametro tasso base 1 di BTC è dello 0,25%, e il parametro tasso base 2 è dello 0,45%.

Secondo il calcolo, il tasso di acquisto di ALP con 1 BTC in questo momento è 0% = 0 BTC. La commissione di transazione per la vendita di ALP per ottenere 1 BTC è dello 0,7% = 0,007 BTC.
