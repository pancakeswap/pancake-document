# bCAKE FAQ

<figure><img src="../../../.gitbook/assets/how-bCAKE-FAQ.png" alt=""><figcaption></figcaption></figure>

### bCAKE 对农场的助推倍数如何计算？

您可能注意到了，在不同农场质押时，获得的 bCAKE 助推倍数不同。

&#x20;这是因为 bCAKE - 农场助推器倍数是使用以下指标计算的，当指标激活或更新到最新时：&#x20;

* 用户 LP 质押量（`userLpBalanceInFarm`）：您在此农场中质押的流动性数额。
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* 农场 LP 质押总量（`totalLpBalanceInFarm`）：质押在农场的流动性的总量，或 V3 LP 池中当前有效流动性资金量，bCAKE 在计算时将在这两者中选择较小的数字。
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* 用户 veCAKE 持仓量（`veCAKE.balanceOf(user)`） : 您当下持有的 veCAKE 数值。
* veCAKE 总量（`veCAKE.totalSupply`）: 当下 veCAKE 总量。

加成倍数计算公式：&#x20;

1. `结果A = 常数A * 用户 LP 质押量`&#x20;
2. `结果B = (农场 LP 质押总量 * 用户锁仓量 * 用户锁仓时长 / 常数B) / (锁仓总量 * 锁仓平均时间)`&#x20;
3. `助推倍数 = min(用户 LP 质押量, (结果A + 结果B)) / 结果A`&#x20;

`常数A` 和 `常数B` 由厨房设定，未来会根据社区反馈和市场情况进行调整。

因不同代币对的 LP 价值不同，不同的农场将适用不同的 `常数B`，以弭平这些差异。

`常数A` 及 `常数B` 自以下代码获取：

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

一言以蔽之：

{% hint style="info" %}
**简单来说：**

您想助推的 LP （流动性）量越多；

您将需要锁仓更多 CAKE ，并锁仓更长的时间。
{% endhint %}

### 为什么我的助推倍数在激活之后也会发生改变？

请注意，**在农场质押的流动性仓位，或 CAKE staking 池进行的任何操作，**都会影响农场及 CAKE staking池的最新数据和统计方式**，**从而**自动更新您的助推倍数**，包括但不限于以下：

* 将流动性从农场质押/解押
* 从农场收割 CAKE 奖励&#x20;
* 延长您的 CAKE 锁仓时间&#x20;
* 将更多的 CAKE 添加到您的锁仓仓位中&#x20;
* 将您的 CAKE 锁仓质押转换为灵活质押

{% hint style="warning" %}
请注意：

为了确保公平，防止潜在的滥用及使用过时数据进行的作弊行为，农场助推器被设计为无需许可和社区治理。因此，**任何人**都可以在 MasterChef V3 合约上调用 `updateLiquidity(address _tokenId)`函数，使用最新数据刷新任何人的助推器倍数。&#x20;

在此基础上，厨房还将监看所有启用 bCAKE 的农场仓位，并将刷新带有过时助推倍数的仓位。
{% endhint %}

### 为什么我无法助推某个农场？

1. 农场助推器仅适用于特定的农场。未来将支持更多农场。现在请在界面上查找 APR 旁边带有绿色火箭图标的的农场。

<figure><img src="../../../.gitbook/assets/bCAKE-boost-tag.png" alt=""><figcaption></figcaption></figure>

2\. 由于涉及多个合约，一些合约交互需要稍微多一点的 gas 代币（BNB）。所以请确保钱包里有足够的 BNB。如果错误仍然存在，请尝试手动增加的 gas 限额。

### 最大 bCAKE 助推倍数是多少？

目前，农场助推器最大之助推倍数为 2.5 倍。仅能提高基准 APR 最高至 2.5 倍。

请注意，您可以获得的最大提升倍数因您尝试质押的流动性仓位类型而异：

* V3: 最大 2x&#x20;
* V2, StableSwap: 最大 2.5x&#x20;
* 仓位管理工具: 最大 2.5x

### 如何增加我的 bCAKE 助推倍数？

* 在 veCAKE 锁仓中添加更多 CAKE
* 将 veCAKE 质押仓位 延长锁仓时间或更新锁仓时长

简单的说： **锁仓质押更多 CAKE，质押更长的时间。**

[bCAKE 助推倍数如何计算](chang-jian-wen-ti-jie-da.md#bcake-dui-nong-chang-de-zhu-tui-bei-shu-ru-he-ji-suan)

### 助推器额外加成的 CAKE 奖励从何而来？

**请别担心，bCAKE 设计上并没有使用到额外的 CAKE 产出及分配。**

类似于 veCAKE 锁仓质押。bCAKE 提高了个人用户相对于其他用户的份额。

即使在部署 bCAKE 后基准 APR 可能会下降。大厨们认为这是一个很好的权衡，因为它不仅通过提高农场产量使忠实的 CAKE 爱好者受益，而且还创造了对 CAKE 的更多需求场景，并成为 CAKE 锁仓质押的巨大动力。&#x20;

### 为什么我的助推倍数很低？

bCAKE - 农场助推器通过评估您的 veCAKE 锁仓的仓位、质押时长和您的流动性 LP 数量来运作。简单来说：

如果用户想在农场中获得更高的助推倍数，他们将需要在 veCAKE 锁仓中锁定更多的 CAKE 、延长锁仓持续时间或两者均提高。

这种设计不仅对大户有利，而且同样有利于任何与农场持仓相较来说拥有相当大 CAKE 锁仓持仓的用户。

&#x20;在[此处了解有](ru-he-shi-yong-bcake.md)关如何计算倍数的更多信息。

### 为什么现在能使用助推器的农场只有 X 个？

&#x20;由于 bCAKE 涉及更新 PancakeSwap 的核心产品之一，即流动性农场。大厨们希望采取更慢、更稳定的方式来发布。&#x20;

因此，在最初的产品发布阶段，许多参数非常保守。包括可以助推的农场数量，哪些农场用户可以助推，以及获得助推倍数的难度参数。&#x20;

大厨们将根据社区反馈调整参数。

### bCAKE V3 是否经过审计？&#x20;

bCAKE 已经过内部和外部审计机构的审计。&#x20;

在此处查看审计报告：[https://docs.pancakeswap.finance/v/chinese/master/shen-ji-bao-gao](https://docs.pancakeswap.finance/v/chinese/master/shen-ji-bao-gao)
