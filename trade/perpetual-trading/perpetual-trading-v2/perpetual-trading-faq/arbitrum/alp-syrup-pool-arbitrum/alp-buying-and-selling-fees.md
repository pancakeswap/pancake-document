# Frais d'Achat et de Vente d'ALP

## Frais d'achat :

Paramètre de taux de base 1 : FeeBasisPoints, actuellement fixé à 0,25% pour l'USDT

Paramètre de taux de base 2 : TaxBasisPoints, actuellement fixé à 0,05% pour l'USDT

La valeur actuelle de l'actif : InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

La valeur actuelle de l'actif après le minting : AfterMinValue=InitialValue+MinValue

Calcul de la valeur de l'actif selon le poids cible : TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Poids cible, Total Value=sum(InitialValue)



La valeur actuelle de l'actif et la valeur cible (valeur absolue) : InitialDiff=InitialValue-TargetValue

Après le Minting, la valeur de l'actif et le mécanisme cible (valeur absolue) : AfterDiff=AfterMintValue-TargetValue

* if AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* if AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Frais de vente :

Paramètre de taux de base 1 : FeeBasisPoints, actuellement fixé à 0,25% pour l'USDT

Paramètre de taux maximum 2 : TaxBasisPoints, actuellement fixé à 0,05% pour l'USDT

La valeur actuelle de l'actif : InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

La valeur actuelle de l'actif après le Burn : AfterMaxValue=InitialValue-MinValue

Calcul de la valeur de l'actif selon le poids cible : TargetValue=Total Value\*Poids cible



La valeur actuelle de l'actif et la valeur cible (valeur absolue) : InitialDiff=InitialValue-TargetValue



Après le Burn, la valeur de l'actif et le mécanisme cible (valeur absolue) : AfterMaxDiff=AfterBurnValue-TargetValue

* if AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* if AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Par exemple :

Si la valeur du pool ALP est de 10 000 000 $, le PnL non réalisé est de +10 000 $, et la valeur du BTC dans le pool de Liquidité est de 1 000 $ ;

Le poids cible du BTC est de 2%, et le poids actuel est de 0,01%. Le paramètre de taux de base 1 du BTC est de 0,25%, et le paramètre de taux de base 2 est de 0,45%.

D'après le calcul, le taux d'achat d'ALP avec 1 BTC est de 0% = 0 BTC. Les frais de transaction pour vendre des ALP et obtenir 1 BTC sont de 0,7% = 0,007 BTC.
