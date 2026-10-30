# ALP 구매 및 판매 수수료

## 구매 수수료:

기본 수수료율 매개변수 1: FeeBasisPoints，USDT는 현재 0.25%로 설정되어 있습니다.

기본 수수료율 매개변수 2: TaxBasisPoints，USDT는 현재 0.05%로 설정되어 있습니다.

현재 자산 가치: InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

발행 후 현재 자산 가치: AfterMinValue=InitialValue+MinValue

목표 비중에 따른 자산 가치 계산: TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Target weight，Total Value=sum(InitialValue)



현재 자산 가치와 목표 가치의 차이(절댓값): InitialDiff=InitialValue-TargetValue

발행 후 자산 가치와 목표 가치의 차이(절댓값): AfterDiff=AfterMintValue-TargetValue

* AfterDiff\<InitialDiffValue 인 경우&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* AfterDiff>=InitialDiff 인 경우&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## 판매 수수료:

기본 수수료율 매개변수 1: FeeBasisPoints，USDT는 현재 0.25%로 설정되어 있습니다.

최대 기본 수수료율 매개변수 2: TaxBasisPoints，USDT는 현재 0.05%로 설정되어 있습니다.

현재 자산 가치: InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

소각(Burn) 후 현재 자산 가치: AfterMaxValue=InitialValue-MinValue

목표 비중에 따른 자산 가치 계산: TargetValue=Total Value\*Target weight



현재 자산 가치와 목표 가치의 차이(절댓값): InitialDiff=InitialValue-TargetValue



소각 후 자산 가치와 목표 가치의 차이(절댓값): AfterMaxDiff=AfterBurnValue-TargetValue

* AfterDiff\<InitialDiffValue 인 경우

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* AfterDiff>=InitialDiff 인 경우&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

예시:

ALP 풀의 가치가 $10,000,000이고, 미실현 손익이 $+10,000이며, 유동성 풀 내 BTC의 가치가 $1,000라고 가정합니다.

BTC의 목표 비중은 2%이고 현재 비중은 0.01%입니다. BTC의 기본 수수료율 매개변수 1은 0.25%, 매개변수 2는 0.45%입니다.

계산에 따르면 이 시점에 1 BTC로 ALP를 구매할 때의 수수료율은 0% = 0 BTC입니다. ALP를 판매하여 1 BTC를 받을 때의 거래 수수료는 0.7% = 0.007BTC입니다.
