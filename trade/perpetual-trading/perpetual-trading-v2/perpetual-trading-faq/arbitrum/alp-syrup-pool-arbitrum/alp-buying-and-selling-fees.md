# ALP Alım ve Satım Ücretleri

## Alım ücreti:

Temel Oran Parametresi 1: FeeBasisPoints, USDT için şu anda %0,25 olarak belirlenmiştir

Temel Oran Parametresi 2: TaxBasisPoints, USDT için şu anda %0,05 olarak belirlenmiştir

Mevcut varlık değeri: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

Mint'lemeden sonraki mevcut varlık değeri: AfterMinValue=InitialValue+MinValue

Hedef ağırlığa göre varlık değerini hesapla: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Hedef ağırlık, Total Value=sum(InitialValue)



Mevcut varlık değeri ile hedef değer arasındaki fark (mutlak değer): InitialDiff=InitialValue-TargetValue

Mint'lemeden sonra varlık değeri ile hedef mekanizma arasındaki fark (mutlak değer): AfterDiff=AfterMintValue-TargetValue

* AfterDiff\<InitialDiffValue ise&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* AfterDiff>=InitialDiff ise&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Satım ücreti:

Temel Oran Parametresi 1: FeeBasisPoints, USDT için şu anda %0,25 olarak belirlenmiştir

Maksimum Temel Oran Parametresi 2: TaxBasisPoints, USDT için şu anda %0,05 olarak belirlenmiştir

Mevcut varlık değeri: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

Yakma sonrası mevcut varlık değeri: AfterMaxValue=InitialValue-MinValue

Hedef ağırlığa göre varlık değerini hesapla: TargetValue=Total Value\*Hedef ağırlık



Mevcut varlık değeri ile hedef değer arasındaki fark (mutlak değer): InitialDiff=InitialValue-TargetValue



Yakma sonrası varlık değeri ile hedef mekanizma arasındaki fark (mutlak değer): AfterMaxDiff=AfterBurnValue-TargetValue

* AfterDiff\<InitialDiffValue ise

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* AfterDiff>=InitialDiff ise&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Örneğin:

ALP havuzunun değeri 10.000.000 $, gerçekleşmemiş K&Z +10.000 $, likidite havuzundaki BTC değeri 1.000 $ ise;

BTC hedef ağırlığı %2, mevcut ağırlık %0,01'dir. BTC'nin temel oran parametresi 1 %0,25 ve temel oran parametresi 2 %0,45'tir.

Hesaplamaya göre bu durumda 1 BTC ile ALP satın alma oranı %0 = 0 BTC'dir. ALP satarak 1 BTC elde etme işlem ücreti ise %0,7 = 0,007 BTC'dir.
