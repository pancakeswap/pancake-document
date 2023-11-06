# Arbitrum

&#x20;2023 年 8 月 31 日，PancakeSwap 永续合约 V2 将在 Arbitrum 链上推出交易奖励计划。在 Arbitrum 上的 [CAKE 糖浆池质押 ALP](https://pancakeswap.finance/pools?chain=arb) 的用户可享有额外收益（CAKE 奖励<mark style="color:purple;">）。</mark>此外，在此计划中获得的奖励不受代币解锁机制限制，用户可随时领取他们的 USDC 奖励。详情如下：

开始时间： 2023 年 8 月 31 日 08:00（UTC）&#x20;

活动时间（每轮）： UTC 时间每周四 08:00:00 至下周四 07:59:59 ，每轮持续 1 周。

奖励发放时间：每轮为每日 00:00（UTC）至 23:59（UTC）。奖励在每周四  08:00 （UTC）左右发放。用户等级更新后，将计算和发放奖励。用户必须在奖励发放后 30 天内领取奖励。逾期未领取视同放弃奖励，平台将收回奖金。

奖励金额： 前 5 周为平台交易手续费的 25%（以 USDC 形式）。5 周之后，奖金将按用户等级进行分配。&#x20;

活动规则： 在 Arbitrum 上进行 PancakeSwap 永续合约 V2 交易的用户将有资格获得奖金。

### 等级明细&#x20;

每周四 08:00:00 UTC，我们会计算从上周四 08:00:00 UTC 到本周四 07:59:59 的交易数据，然后根据等级划分规则更新用户的等级。等级划分标准如下：

<table><thead><tr><th width="161">等级</th><th width="269.3333333333333">标准</th><th>权重</th></tr></thead><tbody><tr><td>钻石</td><td>该轮活动内交易额 >=1M USD</td><td>5</td></tr><tr><td>黄金</td><td>该轮活动内交易额 >=500K USD</td><td>3</td></tr><tr><td>白银</td><td>该轮活动内交易额 >=250K USD</td><td>1</td></tr></tbody></table>

#### 注意：等级标准和权重可能会根据平台资金池内的流动性和整体交易活动发生变化。

同一等级的用户将平均分配奖金。

## 交易奖励计算公式

每轮交易奖励活动结束时，将计算用户在该轮次内的有效交易量，以计算出 USDC 奖金的权重和金额。

&#x20;具体奖金数量的计算公式为：R = min{R \* W/Sum(Wi), R \* 20%\}，参数如下：\
The formula for the number of specific rewards is: r = min{R \* W/Sum(Wi), R \* 20%\}, the parameters are as follows:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>本轮次内用户所能获得的 USDC 奖励的数额</td></tr><tr><td>R</td><td>本轮次的奖金 R=（以 USDC 计的 ETH 的交易手续费 + 以 USDC 计的 DAI 的交易手续费 + 以 USDC 计的 BTC 的交易手续费+ USDC 的交易手续费）*0.25，其中 1% 兑换手续费需要在结算时扣除，例如：当 ETH 本轮次的交易手续费为 1，ETH 价格为 2,000 时，以 USDC 计的 ETH 交易费用 = 1 * 2000 * 0.99</td></tr><tr><td>W</td><td>与用户所处等级相对应的权重</td></tr><tr><td>Sum(Wi)</td><td>所有用户的总权重得分。Wi 代表任意用户的权重，sum(Wi) 代表所有用户的权重得分总和。</td></tr></tbody></table>

* 单一用户可获得的奖金上限为本计划保留收入的 20%。&#x20;

条款和条件&#x20;

* 由于 V2 上每个交易对的交易手续费不同，即使用户的有效交易量相同，他们获得的奖励也可能不同。&#x20;
* 每轮分配的奖励将存储在以下合约地址中：0xbbE8f9E6dE5245A12C2b9dC7B84c8334b4C8Be1f
* PancakeSwap/ApolloX 保留对本活动的最终解释权。



风险提示：加密货币合约交易有很大的风险，所有的交易活动都由用户自己决定和承担风险。这里的信息不应被视为 PancakeSwap 或 ApolloX 的金融或投资建议。PancakeSwap 和 ApolloX 不会对您操作永续合约可能造成的任何损失负责。
