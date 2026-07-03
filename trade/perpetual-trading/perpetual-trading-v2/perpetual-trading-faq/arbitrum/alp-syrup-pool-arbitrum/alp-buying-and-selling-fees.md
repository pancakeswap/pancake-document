# ALP 購入・売却手数料

## 購入手数料：

基本レートパラメーター1：FeeBasisPoints、USDTは現在0.25%に設定されています。

基本レートパラメーター2：TaxBasisPoints、USDTは現在0.05%に設定されています。

現在のアセット価値：InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

ミント後の現在のアセット価値：AfterMinValue=InitialValue+MinValue

目標ウェイトに基づくアセット価値の計算：TargetValue=（Total Value\_usd+totalUnrealizedpnl\_Usd）× 目標ウェイト、Total Value=sum(InitialValue)



現在のアセット価値と目標価値（絶対値）：InitialDiff=InitialValue-TargetValue

ミント後のアセット価値と目標機構（絶対値）：AfterDiff=AfterMintValue-TargetValue

* AfterDiff\<InitialDiffValueの場合&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue、0)

* AfterDiff>=InitialDiffの場合&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## 売却手数料：

基本レートパラメーター1：FeeBasisPoints、USDTは現在0.25%に設定されています。

最大基本レートパラメーター2：TaxBasisPoints、USDTは現在0.05%に設定されています。

現在のアセット価値：InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

バーン後の現在のアセット価値：AfterMaxValue=InitialValue-MinValue

目標ウェイトに基づくアセット価値の計算：TargetValue=Total Value × 目標ウェイト



現在のアセット価値と目標価値（絶対値）：InitialDiff=InitialValue-TargetValue



バーン後のアセット価値と目標機構（絶対値）：AfterMaxDiff=AfterBurnValue-TargetValue

* AfterDiff\<InitialDiffValueの場合

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue、0)

* AfterDiff>=InitialDiffの場合&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

例：

ALPプールの価値が$10,000,000、未実現PnLが$+10,000、流動性プール内のBTCの価値が$1,000の場合；

BTCの目標ウェイトは2%、現在のウェイトは0.01%です。BTCの基本レートパラメーター1は0.25%、基本レートパラメーター2は0.45%です。

計算によると、この時点で1 BTCを使用してALPを購入する手数料率は0% = 0 BTCとなります。ALPを売却して1 BTCを得るためのトランザクション手数料は0.7% = 0.007 BTCとなります。
