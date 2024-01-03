---
description: CAKE定期质押和IFO分配
---

# iCAKE

### 什么是新的 iCAKE？

过渡到 veCAKE 后，新的 iCAKE 将根据 veCAKE 数值来计算

* 和旧的 iCAKE 一样，它将决定每场 PancakeSwap IFO 公开销售中的最大 CAKE 投入限额。例如，如果您有 200 个 iCAKE，您就可以在 IFO 公开销售中最高投入 200 个 CAKE。&#x20;
* 新的 iCAKE 数量使用每场 IFO 结束时间时的 veCAKE 数值计算得出。因此，每场 IFO 您拥有的 iCAKE 数量都不同。&#x20;
* 由于 veCAKE  数值会随着您的剩余锁仓时间的减少而逐渐减少。因此，您在未来场次的 IFO 中持有的 iCAKE 会随着 veCAKE 数值的减少而减少。要保持住您持有的 iCAKE 数量，请向锁仓仓位添加更多 CAKE，或更新/延长您的锁仓仓位。

**iCAKE 不是一个新的代币，他是 PancakeSwap IFO 系统中使用的一个数值度量。**

### iCAKE 怎么计算？

您拥有的 iCAKE 数量，是根据每场 IFO 结束时持有的 veCAKE 数值，乘以一个预先设定的比率。&#x20;

veCAKE 是根据您锁定的 CAKE 数量和锁仓剩余时间动态计算得出的值。要进一步了解 veCAKE 的计算方法，请点击[此处](../../chan-pin/vecake/vecake-faq.md)。&#x20;

在 veCAKE 数值的基础上，还应用了一个额外的比率，该比率每场 IFO 时厨房将进行调整。例如，如果比率是 2x，在下一场  IFO 结束时您有 1 veCAKE，则您最多可以投入 2 CAKE。

举例说明：&#x20;

* 您锁定 100 个 CAKE 2 年
  * 剩余锁仓时间为：`2 * 52 * 7 * 24 * 60 * 60 = 62899200`（秒）
  * 最大锁仓时间为：`(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (秒)
  * 目前，您有`100 * (62899200 / 126403199) ~= 49.76` veCAKE
* 下一场 IFO 公布时间；其结束时间正好是 1 周后，也就是当前时刻往后数 `604800` 秒。
  * 此时，您的剩余锁仓时间为：`62899200 - 604800 = 62294400`（秒）
  * 此时，您有`100 * (62294400 / 126403199) ~= 49.28` veCAKE
* 当本场 IFO，比率设置为`3x`&#x20;
* 因此在本场 IFO，您拥有`49.28 * 3 = 147.84` iCAKE，代表您最多可在公开销售中投入 147.84 CAKE。

### 如何查看我拥有多少个 iCAKE ?

<figure><img src="../../.gitbook/assets/image.png" alt="" width="375"><figcaption></figcaption></figure>

您可以在 [IFO界面](https://pancakeswap.finance/ifo) 看到您的 iCAKE 数量。

请注意，在尚未安排下一场 IFO 时，您的 iCAKE 将使用实时的 veCAKE 数值计算，该数值会逐秒减少。&#x20;

当 IFO 即将开始时，您的 iCAKE 将使用快照时间（即 IFO 结束时）的 veCAKE 数值作为基准来进行计算。因此在 IFO 结束之前，您的 iCAKE 数量不会减少或变化。

### 如何增加我拥有的 iCAKE 数量?

您可以增加 iCAKE 数量的途径有：

* 在 veCAKE 锁仓仓位中，增加您锁仓的 CAKE 数量
* 延长您的 veCAKE 锁仓时间

需要在 [Cake Staking 页面](https://pancakeswap.finance/cake-staking) 上操作。

### 在计算 iCAKE 过程中 "比率" 是什么？

比率是在计算 iCAKE 数量时，在 veCAKE 数值基础上应用的一个额外的控制系数。&#x20;

例如，如果比率为 2x，而您在下一场 IFO 结束时有 1 veCAKE，您最多可以投入 2 CAKE。

在两场 IFO 之间，厨房将根据各种指标优化 "比率"。调整结果将公布在所有社媒渠道上。

<figure><img src="../../.gitbook/assets/image (2).png" alt="" width="375"><figcaption></figcaption></figure>

您可以前往 [IFO 页面](https://pancakeswap.finance/ifo)，查看用于计算 iCAKE 数量的当前 "比率" 数值。
