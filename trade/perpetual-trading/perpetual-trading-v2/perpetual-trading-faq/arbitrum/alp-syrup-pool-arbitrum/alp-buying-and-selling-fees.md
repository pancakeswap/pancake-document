# ALP Kauf- und Verkaufsgebühren

## Kaufgebühr:

Basisratenparameter 1: FeeBasisPoints, USDT derzeit auf 0,25 % festgelegt

Basisratenparameter 2: TaxBasisPoints, USDT derzeit auf 0,05 % festgelegt

Der aktuelle Asset-Wert: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

Der aktuelle Asset-Wert nach dem Prägen: AfterMinValue=InitialValue+MinValue

Berechnung des Asset-Werts gemäß Zielgewichtung: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Target weight，Total Value=sum(InitialValue)



Die aktuelle Differenz zwischen Asset-Wert und Zielwert (Absolutwert): InitialDiff=InitialValue-TargetValue

Nach dem Prägen, Differenz zwischen Asset-Wert und Zielmechanismus (Absolutwert): AfterDiff=AfterMintValue-TargetValue

* if AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* if AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Verkaufsgebühr:

Basisratenparameter 1: FeeBasisPoints, USDT derzeit auf 0,25 % festgelegt

Maximaler Basisratenparameter 2: TaxBasisPoints, USDT derzeit auf 0,05 % festgelegt

Der aktuelle Asset-Wert: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

Der aktuelle Asset-Wert nach dem Burn: AfterMaxValue=InitialValue-MinValue

Berechnung des Asset-Werts gemäß Zielgewichtung: TargetValue=Total Value\*Target weight



Die aktuelle Differenz zwischen Asset-Wert und Zielwert (Absolutwert): InitialDiff=InitialValue-TargetValue



Nach dem Burn, Differenz zwischen Asset-Wert und Zielmechanismus (Absolutwert): AfterMaxDiff=AfterBurnValue-TargetValue

* if AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* if AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Beispiel:

Wenn der Wert des ALP-Pools 10.000.000 $ beträgt, der nicht realisierte PnL +10.000 $ und der Wert von BTC im Liquiditätspool 1.000 $ ist;

Die BTC-Zielgewichtung beträgt 2 % und die aktuelle Gewichtung 0,01 %. Der Basisratenparameter 1 von BTC beträgt 0,25 % und der Basisratenparameter 2 beträgt 0,45 %.

Gemäß der Berechnung beträgt die Rate für den Kauf von ALP mit 1 BTC zu diesem Zeitpunkt 0 % = 0 BTC. Die Transaktionsgebühr für den Verkauf von ALP gegen 1 BTC beträgt 0,7 % = 0,007 BTC.
