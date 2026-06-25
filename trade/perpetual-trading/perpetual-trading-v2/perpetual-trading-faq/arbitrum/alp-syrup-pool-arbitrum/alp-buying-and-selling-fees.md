# ALP 买入和卖出费用

## 买入费用：

基础费率参数 1：FeeBasisPoints，USDT 目前设置为 0.25%

基础费率参数 2：TaxBasisPoints，USDT 目前设置为 0.05%

当前资产价值：InitialValue=AssetValueInPool+AssetUnrealizedpnl\_usd

铸造后的当前资产价值：AfterMinValue=InitialValue+MinValue

根据目标权重计算资产价值：TargetValue=(Total Value\_usd+totalUnrealizedpnl\_Usd)\*Target weight，Total Value=sum(InitialValue)



当前资产价值与目标价值（绝对值）：InitialDiff=InitialValue-TargetValue

铸造后，资产价值与目标机制（绝对值）：AfterDiff=AfterMintValue-TargetValue

* 如果 AfterDiff\<InitialDiffValue&#x20;

MintFee=Max(FeeBasisPoints-TaxBasisPoints\*InitialDiff/TargetValue，0)

* 如果 AfterDiff>=InitialDiff&#x20;

MintFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue

## 卖出费用：

基础费率参数 1：FeeBasisPoints，USDT 目前设置为 0.25%

最大基础费率参数 2：TaxBasisPoints，USDT 目前设置为 0.05%

当前资产价值：InitialValue=AssetValueInPool+AssetUnreliazedpnl\_usd

销毁后的当前资产价值：AfterMaxValue=InitialValue-MinValue

根据目标权重计算资产价值：TargetValue=Total Value\*Target weight



当前资产价值与目标价值（绝对值）：InitialDiff=InitialValue-TargetValue



销毁后，资产价值与目标机制（绝对值）：AfterMaxDiff=AfterBurnValue-TargetValue

* 如果 AfterDiff\<InitialDiffValue

BurnFee=Max(FeeBasisPoints-MTaxBasisPoints\*InitialDiff/TargetValue，0)

* 如果 AfterDiff>=InitialDiff&#x20;

BurnFee=FeeBasisPoints+TaxBasisPoints\*Min((InitialDiff+AfterDiff)/2,TargetValue)/TargetValue<br>

例如：

如果 ALP 池的价值为 $10,000,000，未实现 PnL 为 $+10,000，流动性池中 BTC 的价值为 $1,000；

BTC 目标权重为 2%，当前权重为 0.01%。BTC 的基础费率参数 1 为 0.25%，基础费率参数 2 为 0.45%。

根据计算，此时用 1 BTC 购买 ALP 的费率为 0% = 0 BTC。出售 ALP 以获得 1 BTC 的交易费用为 0.7% = 0.007BTC。
