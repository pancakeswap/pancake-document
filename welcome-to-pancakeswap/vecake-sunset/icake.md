---
description: veCAKE 质押与 IFO 配额
hidden: true
---

# iCAKE

### **新版 iCAKE 是什么？**

在过渡到 veCAKE 之后，新版 iCAKE 将基于 veCAKE 余额计算

* 与旧版 iCAKE 一样，它决定了你在 PancakeSwap IFO 公售中可承诺的最大 CAKE 上限。例如，如果你有 200 iCAKE，你就可以在 IFO 公售中承诺 200 CAKE。
* 新版 iCAKE 数值使用每次 IFO 结束时的 veCAKE 余额来计算。因此，每次 IFO 你的 iCAKE 数值都会不同。
* 由于 veCAKE 余额会随着你剩余的锁定时间逐渐减少，因此你在未来 IFO 中的 iCAKE 也会随着你的 veCAKE 余额减少。要维持你的 iCAKE 数值，可向质押中添加更多 CAKE，或续期/延长你的锁定。

**iCAKE 不是一种新的代币，它是 PancakeSwap IFO 系统所使用的一个数值指标。**

### iCAKE 是如何计算的？

你拥有的 iCAKE 数量基于每次 IFO 结束时的 veCAKE 余额，再乘以一个预定义的比率。

veCAKE 是一个根据你锁定的 CAKE 数量以及锁定剩余时间动态计算的数值。要了解更多关于 veCAKE 如何计算的信息，请查看[此处](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef)。

在 veCAKE 余额之上还会应用一个额外的比率，该比率由 Kitchen 针对每次 IFO 进行调整。例如，如果比率为 2 倍，而你在下一次 IFO 结束时有 1 veCAKE，那么你最多可以承诺 2 CAKE。

示例：

* 你锁定了 100 CAKE，为期 2 年。
  * 你的剩余锁定时间为：`2 * 52 * 7 * 24 * 60 * 60 = 62899200`（秒）
  * 最大锁定时间为：`(209 * 7 * 24 * 60 * 60) - 1 = 126403199`（秒）
  * 在当前时刻，你拥有：`100 * (62899200 / 126403199) ~= 49.76` veCAKE
* 即将到来的下一次 IFO 已排定；其结束时间正好在 1 周后，即当前时刻之后 `604800` 秒。
  * 那时，你的剩余锁定时间为：`62899200 - 604800 = 62294400`（秒）
  * 那时，你拥有：`100 * (62294400 / 126403199) ~= 49.28` veCAKE
* 对于本次 IFO，比率设为 `3x`
* 因此，对于本次 IFO，你拥有：`49.28 * 3 = 147.84` iCAKE，这意味着你在公售中最多可承诺 147.84 CAKE。

### 如何查看我拥有的 iCAKE 数量？

<figure><img src="../../.gitbook/assets/image (9).png" alt="" width="375"><figcaption></figcaption></figure>

你可以在 IFO 页面[此处](https://pancakeswap.finance/ifo)查看你拥有的 iCAKE 数量。

请记住，当没有即将到来的 IFO 时，你的 iCAKE 将使用实时 veCAKE 余额计算，该余额会逐秒逐渐减少。

当有即将到来的 IFO 时，你的 iCAKE 将使用快照时间（即 IFO 结束时）的 veCAKE 余额计算。在 IFO 结束之前，你的 iCAKE 不会减少或改变。

### **我如何增加我拥有的 iCAKE 数量？**

你可以随时通过以下方式增加 iCAKE 数量：

* 向你的 veCAKE 质押仓位添加更多 CAKE。
* 延长你的 veCAKE 质押仓位。

操作请前往 [CAKE 质押页面](https://pancakeswap.finance/cake-staking)

### iCAKE 计算中的"Ratio"（比率）是什么？

比率是在计算 iCAKE 时，于 veCAKE 余额之上应用的一个额外控制因子。

例如，如果比率为 2 倍，而你在下一次 IFO 结束时有 1 veCAKE，那么你最多可以承诺 2 CAKE。

在每次 IFO 之间，Kitchen 将根据各项指标优化"Ratio"（比率）。调整将在所有社交渠道公布。

<figure><img src="../../.gitbook/assets/image (10).png" alt="" width="375"><figcaption></figcaption></figure>

你可以前往 [IFO 页面](https://pancakeswap.finance/ifo)查看当前用于 iCAKE 计算的"Ratio"（比率）数值。
