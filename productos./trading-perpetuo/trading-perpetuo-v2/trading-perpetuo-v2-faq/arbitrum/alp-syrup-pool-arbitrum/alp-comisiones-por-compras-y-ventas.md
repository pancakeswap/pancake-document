# ALP Comisiones por compras y ventas

## Fee de compra:

Basic Rate Parameter 1: FeeBasisPoints，USDT is currently set at 0.25%

Basic Rate Parameter 2: TaxBasisPoints，USDT is currently set at 0.05%

The current asset value: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

The current asset value after minting: AfterMinValue=InitialValue+MinValue

Calculate the Asset value according to the target weight: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Target weight，Total Value=sum(InitialValue)



The current Asset value and the target value (absolute value): InitialDiff=InitialValue-TargetValue

After Minting, the asset value and target mechanism (absolute value): AfterDiff=AfterMintValue-TargetValue

* if AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* if AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Fee de venta:

Basic Rate Parameter 1: FeeBasisPoints，USDT is currently set at 0.25%

Max Base Rate Parameter 2: TaxBasisPoints，USDT is currently set at 0.05%

The current asset value: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

The current asset value after Burn: AfterMaxValue=InitialValue-MinValue

Calculating the Asset value according to the target weight: TargetValue=Total Value\*Target weight



The current asset value and target value (absolute value): InitialDiff=InitialValue-TargetValue



After Burn, the asset value and target mechanism (absolute value): AfterMaxDiff=AfterBurnValue-TargetValue

* if AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* if AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue\


Por ejemplo:

If the value of the ALP pool is $10,000,000, the unrealized PnL is $+10,000, the value of BTC in the liquidity pool is $1,000;

The BTC target weight is 2%, and the current weight is 0.01%. The base rate parameter 1 of BTC is 0.25%, and the base rate parameter 2 is 0.45%.

According to the calculation, the rate of buying ALP with 1 BTC at this time is 0% = 0 BTC. The transaction fee for selling ALP to get 1 BTC is 0.7% = 0.007BTC
