# Arbitrum

2023 年 8 月 31 日，PancakeSwap 永续合约将在 Arbitrum 上推出 V2 交易奖励计划。在 Arbitrum 上 [在 CAKE 糖浆池中质押 ALP](https://pancakeswap.finance/pools?chain=arb) 的用户可以享受提升倍数。此外，本计划赚取的奖励没有锁仓期。用户可以随时领取他们的 USDC 奖励。详情如下：

开始时间：2023 年 8 月 31 日 08:00 (UTC)

活动（Epoch）周期：每周四 08:00:00 UTC 至下周四 07:59:59，持续 1 周

奖励分配时间：每个周期为每日 00:00 (UTC) 至 23:59 (UTC)。奖励在每周四约 08:00 (UTC) 发放。用户等级更新后，将计算并分配奖励。用户必须在奖励发放后 30 天内领取奖励。如未领取，平台将撤销奖励。&#x20;

奖励金额：前 5 周为交易费用的 25%（以 USDC 计）。该奖池随后将根据等级进行分配。

活动规则：在 Arbitrum 上交易 PancakeSwap 永续合约 V2 的用户将有资格参与该奖池

### 等级细分

每周四 08:00:00 UTC，我们会计算从上周四 08:00:00 UTC 到本周四 07:59:59 的交易数据，然后根据等级规则更新用户的等级。等级规则如下（支持配置）：

<table><thead><tr><th width="161">等级</th><th width="249.33333333333331">描述</th><th>权重</th></tr></thead><tbody><tr><td>钻石</td><td>Epoch 交易金额 >=1M USD</td><td>5</td></tr><tr><td>黄金</td><td>Epoch 交易金额 >=500K USD</td><td>3</td></tr><tr><td>白银</td><td>Epoch 交易金额 >=250K USD</td><td>1</td></tr></tbody></table>

**注意：等级标准和权重可能会根据池流动性和平台上的整体交易活动而变化**

奖励将在符合特定等级资格的所有用户之间平均分配

### 交易奖励计算公式：&#x20;

在每个交易奖励周期结束时，将计算用户在该周期内的有效交易量，以确定 USDC 奖励的权重和金额。

具体奖励数量的公式为：r = min{R \* W/Sum(Wi), R \* 20%\}，参数如下：

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>用户在当前 epoch 可挖取的 USDC 奖励金额</td></tr><tr><td>R</td><td>当前 epoch 的奖励 R=(ETH 费用的 USDC 价值 + DAI 费用的 USDC 价值 + BTC 费用的 USDC 价值 + USDC 费用)*0.25，其中在结算时需扣除 1% 的 Swap 费用，例如：当每周 ETH 费用为 1 且 ETH 价格为 2,000 时，USDC 价值的 ETH 费用 = 1 * 2000 * 0.99</td></tr><tr><td>W</td><td>与用户等级级别对应的权重</td></tr><tr><td>Sum(Wi)</td><td>所有用户的总权重得分。Wi 表示任一用户的权重，sum(Wi) 表示所有用户的权重得分之和。</td></tr></tbody></table>

* 每位用户的最大收入分成上限为为该计划预留收入的 20%

条款与条件

* 由于 V2 上每个交易对的交易费用不同，即使用户的有效交易量相同，他们获得的奖励也可能有所不同。
* 每个周期要分配的奖励将存储在以下合约地址中：&#x20;
* PancakeSwap/ApolloX 保留对本活动的最终解释权。



风险警告：加密货币期货交易具有重大风险。所有交易活动均由你自行决定并自担风险。此处的信息不应被视为来自 PancakeSwap/ApolloX 的财务或投资建议。PancakeSwap/ApolloX 对你使用 PancakeSwap/ApolloX 可能产生的任何损失概不负责。

<br>
