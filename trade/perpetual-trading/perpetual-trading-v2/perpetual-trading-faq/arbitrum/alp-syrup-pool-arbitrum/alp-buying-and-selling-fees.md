# Комиссии за покупку и продажу ALP

## Комиссия за покупку:

Базовый параметр ставки 1: FeeBasisPoints — для USDT текущее значение 0.25%

Базовый параметр ставки 2: TaxBasisPoints — для USDT текущее значение 0.05%

Текущая стоимость актива: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

Текущая стоимость актива после минтинга: AfterMinValue=InitialValue+MinValue

Рассчитать стоимость актива согласно целевому весу: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Целевой вес, Total Value=sum(InitialValue)



Текущая стоимость актива и целевое значение (абсолютное): InitialDiff=InitialValue-TargetValue

Стоимость актива после минтинга и целевой механизм (абсолютное): AfterDiff=AfterMintValue-TargetValue

* если AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* если AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## Комиссия за продажу:

Базовый параметр ставки 1: FeeBasisPoints — для USDT текущее значение 0.25%

Максимальный базовый параметр ставки 2: TaxBasisPoints — для USDT текущее значение 0.05%

Текущая стоимость актива: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

Текущая стоимость актива после сжигания: AfterMaxValue=InitialValue-MinValue

Расчёт стоимости актива согласно целевому весу: TargetValue=Total Value\*Целевой вес



Текущая стоимость актива и целевое значение (абсолютное): InitialDiff=InitialValue-TargetValue



Стоимость актива после сжигания и целевой механизм (абсолютное): AfterMaxDiff=AfterBurnValue-TargetValue

* если AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* если AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

Например:

Если стоимость пула ALP составляет $10,000,000, нереализованный PnL — $+10,000, а стоимость BTC в пуле ликвидности — $1,000;

Целевой вес BTC — 2%, текущий вес — 0.01%. Базовый параметр ставки 1 для BTC — 0.25%, базовый параметр ставки 2 — 0.45%.

По расчётам, ставка покупки ALP за 1 BTC в данный момент составляет 0% = 0 BTC. Комиссия за продажу ALP для получения 1 BTC — 0.7% = 0.007 BTC.
