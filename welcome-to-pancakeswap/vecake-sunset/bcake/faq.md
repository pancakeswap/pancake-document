# 常见问题解答

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### bCAKE 倍数是如何计算的？

你可能会注意到，在不同农场质押时所获得的 bCAKE 加成倍数各不相同。

这是因为 bCAKE - 农场加成器的倍数会在激活或刷新时，使用以下指标进行计算：

* `userLpBalanceInFarm` ：你在农场中质押的流动性数量。&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` ：农场中质押的流动性总量，或 V3 LP 池中当前活跃的流动性数量。bCAKE 会取两者中较小的数值。
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` ：你拥有的 veCAKE 实时数量
* `veCAKE.totalSupply` ：veCAKE 的实时总供应量

倍数使用以下方法计算：

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` 和 `constantB` 由厨房设定，并将根据社区反馈和市场情况在未来进行调整。`constantB` 在不同农场之间有所不同，以补偿 LP 价格的差异。

`constantA` 和 `constantB` 可通过以下方式获取：

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

但是：

{% hint style="info" %}
**太长不看版（TL;DR）**

你想要加成的 LP（流动性）越多

你需要锁定的 CAKE 就越多、锁定时间也越长
{% endhint %}

### 为什么我的倍数在激活后还会变化？

请注意，**任何对农场仓位或 CAKE 质押池的用户操作都会根据农场和 CAKE 质押池的最新数据和统计信息自动更新你的加成倍数**，包括但不限于：

* 在农场中质押/取消质押仓位
* 从农场收获 CAKE 奖励
* 延长你的 CAKE 质押时长
* 向你的固定期限质押仓位中添加更多 CAKE
* 将你的 CAKE 质押仓位转换为灵活质押

{% hint style="warning" %}
请注意：&#x20;

为确保公平并防止利用过时数据进行潜在的滥用和作弊。农场加成器被设计为无需许可且由社区治理。因此，**任何人**都可以调用 MasterChef V3 合约上的 `updateLiquidity(address _tokenId)` 函数，使用最新数据刷新任何人的加成倍数。

除此之外，厨房还会监控所有启用了 bCAKE 的农场仓位，并刷新任何倍数过时的仓位。
{% endhint %}

### 为什么我无法为某个仓位加成

1. 农场加成器仅适用于选定的农场。未来将开放更多农场。目前，**请寻找带有绿色火箭图标的绿色 APR 数字。**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. 由于涉及多个合约，某些合约交互需要稍多一些的 gas 代币（BNB）。所以请确保你的钱包中有足够的 BNB。如果错误仍然存在，请尝试手动提高交易的 gas 上限。

### 我能获得的最大 bCAKE 加成倍数是多少？

目前，用户在农场加成器上能获得的最大加成为 2.5 倍，这为他们提供了原始 APR 的 2.5 倍。

请注意，你能获得的最大加成会因你尝试质押的流动性类型而有所不同：

* V3：最高 2 倍
* V2、StableSwap：最高 2.5 倍
* 仓位管理器：最高 2.5 倍

### 我该如何提高我的 bCAKE 加成倍数？

* 向 veCAKE 质押仓位中添加更多 CAKE
* 延长或续期你的 veCAKE 质押仓位时长

简而言之：

**质押更多 CAKE，质押更长时间**

[了解更多关于 bCAKE 加成倍数如何计算的信息](faq.md#how-are-the-bcake-multipliers-calculated)。

### 额外加成的 CAKE 奖励来自哪里？

**放心，为了实现 bCAKE，没有分配任何额外的代币释放。**

与 veCAKE 的 CAKE 质押类似。bCAKE 提升的是个人用户相对于其他人的份额。

尽管在 bCAKE 部署后基础 APR 可能会下降。厨师们相信这是一个不错的权衡，因为它通过加成忠实 CAKE 爱好者的农场收益使他们受益，为 CAKE 创造了更多需求，并成为 CAKE 质押的一大激励。

### 为什么我收到的倍数偏低？&#x20;

bCAKE - 农场加成器的工作方式是，将你的 veCAKE 质押仓位和你的流动性农场仓位与其他用户进行综合评估。简而言之：

> 如果用户想在农场中加成更多流动性，他们必须在池中锁定更多 CAKE、锁定更长时间。

这种设计确保了好处不仅提供给大额持有者，也提供给任何与农场仓位相比拥有相当规模 CAKE 质押仓位的用户。

在[此处](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated)了解更多关于倍数如何计算的信息。

### 为什么只有 x 个农场可以使用加成器？

由于 bCAKE 涉及对 PancakeSwap 核心产品之一（即流动性农场）的更新。厨师们希望以更缓慢、更稳健的方式进行推出。

因此，在产品的初始发布阶段。许多参数都非常保守。包括用户可加成的农场数量、用户可加成哪些农场，以及获得加成倍数的难度参数。

**厨师们将根据社区反馈调整参数。**

### **bCAKE V3 经过审计了吗？** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE 已通过内部和外部审计师的审计。

在此查看审计报告：[https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
