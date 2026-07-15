# ALP खरीदने और बेचने के शुल्क

## खरीदने का शुल्क:

Basic Rate Parameter 1: FeeBasisPoints, USDT वर्तमान में 0.25% पर सेट है

Basic Rate Parameter 2: TaxBasisPoints, USDT वर्तमान में 0.05% पर सेट है

वर्तमान एसेट मूल्य: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

मिंटिंग के बाद वर्तमान एसेट मूल्य: AfterMinValue=InitialValue+MinValue

लक्ष्य वजन के अनुसार एसेट मूल्य की गणना करें: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Target weight, Total Value=sum(InitialValue)



वर्तमान एसेट मूल्य और लक्ष्य मूल्य (निरपेक्ष मूल्य): InitialDiff=InitialValue-TargetValue

मिंटिंग के बाद, एसेट मूल्य और लक्ष्य तंत्र (निरपेक्ष मूल्य): AfterDiff=AfterMintValue-TargetValue

* यदि AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* यदि AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## बेचने का शुल्क:

Basic Rate Parameter 1: FeeBasisPoints, USDT वर्तमान में 0.25% पर सेट है

Max Base Rate Parameter 2: TaxBasisPoints, USDT वर्तमान में 0.05% पर सेट है

वर्तमान एसेट मूल्य: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

Burn के बाद वर्तमान एसेट मूल्य: AfterMaxValue=InitialValue-MinValue

लक्ष्य वजन के अनुसार एसेट मूल्य की गणना करना: TargetValue=Total Value\*Target weight



वर्तमान एसेट मूल्य और लक्ष्य मूल्य (निरपेक्ष मूल्य): InitialDiff=InitialValue-TargetValue



Burn के बाद, एसेट मूल्य और लक्ष्य तंत्र (निरपेक्ष मूल्य): AfterMaxDiff=AfterBurnValue-TargetValue

* यदि AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* यदि AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

उदाहरण के लिए:

यदि ALP pool का मूल्य $10,000,000 है, unrealized PnL $+10,000 है, तरलता पूल में BTC का मूल्य $1,000 है;

BTC का लक्ष्य वजन 2% है, और वर्तमान वजन 0.01% है। BTC का base rate parameter 1 0.25% है, और base rate parameter 2 0.45% है।

गणना के अनुसार, इस समय 1 BTC के साथ ALP खरीदने की दर 0% = 0 BTC है। ALP बेचकर 1 BTC प्राप्त करने का transaction fee 0.7% = 0.007BTC है।
