# Комиссии за покупку и продажу ALP

## Комиссия за покупку:

Базовая ставка Параметр 1: FeeBasisPoints — для USDT текущее значение составляет 0,25%

Базовая ставка Параметр 2: TaxBasisPoints — для USDT текущее значение составляет 0,05%

Текущая стоимость актива: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

Текущая стоимость актива после чеканки: AfterMinValue=InitialValue+MinValue

Рассчитываем стоимость актива в соответствии с целевым весом: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Target weight, Total Value=sum(InitialValue)



Текущая стоимость актива и целевое значение (абсолютное): InitialDiff=InitialValue-TargetValue

После чеканки стоимость актива и целевой механизм (абсолютное): AfterDiff=AfterMintValue-TargetValue

* если AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* если AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Комиссия за продажу:

Базовая ставка Параметр 1: FeeBasisPoints — для USDT текущее значение составляет 0,25%

Максимальная базовая ставка Параметр 2: TaxBasisPoints — для USDT текущее значение составляет 0,05%

Текущая стоимость актива: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

Текущая стоимость актива после сжигания: AfterMaxValue=InitialValue-MinValue

Расчёт стоимости актива в соответствии с целевым весом: TargetValue=Total Value\*Target weight



Текущая стоимость актива и целевое значение (абсолютное): InitialDiff=InitialValue-TargetValue



После сжигания стоимость актива и целевой механизм (абсолютное): AfterMaxDiff=AfterBurnValue-TargetValue

* если AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* если AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Например:

Если стоимость пула ALP составляет $10 000 000, нереализованный PnL — +$10 000, стоимость BTC в пуле ликвидности — $1 000;

Целевой вес BTC составляет 2%, текущий — 0,01%. Базовая ставка параметр 1 для BTC — 0,25%, базовая ставка параметр 2 — 0,45%.

По расчёту, ставка покупки ALP за 1 BTC в данный момент составит 0% = 0 BTC. Комиссия за продажу ALP для получения 1 BTC составляет 0,7% = 0,007 BTC.
