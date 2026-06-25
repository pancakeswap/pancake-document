---
description: 使用你的 veCAKE 投票，决定 CAKE 排放如何分配
hidden: true
---

# Gauges 投票

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

#### 什么是 gauge？

要理解 gauges 投票，你可以把任何需要 CAKE 排放的产品看作一系列 gauges。这包括农场（farms）、CAKE 每周奖励池、持仓管理器金库（position manager vaults）等。

veCAKE 持有者现在可以使用其 veCAKE 作为投票，来决定多少百分比的 CAKE 流向哪个产品。一个 gauge 通过 Gauges 投票累积的 veCAKE 越多，分配给其底层流动性池/持仓管理器金库的 CAKE 排放就越多。

{% hint style="info" %}
每个 epoch（E-0）中的投票决定下一个 epoch（E+1）的 CAKE 排放，且这些变更仅在当前 epoch 结束后生效。
{% endhint %}

#### Gauge 类型

gauges 有两种类型——"核心（core）"和"非核心（non-core）"。前者的 CAKE 排放由 Kitchen 控制，而社区通过用 veCAKE 投票来影响"非核心"池的排放。

1. "核心" gauges 包括含主流代币和稳定币（WBTC、ETH、BNB、USDC、USDT 等）的交易对——Kitchen 将确保这些交易对获得足够的 CAKE 奖励，因为它们对协议的收入贡献显著
2. "非核心" gauges 代表所有未被归类为"核心" gauges 的其他 gauges

## 如何投票？

### 1 - 了解投票时间表

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

Gauges 权重投票每两周进行一次。一个 epoch 的开始与收入分享一样，是在每个偶数周的星期四 UTC 时间 00:00。

在上述示例中：

* Epoch 1 从第 1 周星期四（1 日）UTC 时间 00:00 开始。
* Epoch 1 在 2 周后，即第 3 周星期四（15 日）UTC 时间 00:00 结束。
* 用户可在 1 日至 14 日 UTC 时间 00:00 期间投票。
* 在 14 日至 15 日 UTC 时间 00:00 期间**不能**投票，因为此时正在调整和统计票数。
* 投票结果将在 15 日 UTC 时间 00:00 进行快照，即 Epoch 1 结束之时。
* 投票结果将在一个 epoch 关闭后的 72 小时内应用。

### 2 - 获得资格

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

由于 veCAKE 会根据剩余锁定时间逐渐减少，投票结果将在每个 epoch 结束时通过快照获取。这包括 veCAKE 总量，以及每个用户拥有的 veCAKE。

在上述示例中：

* Epoch 1 的结果将基于 15 日 UTC 时间 00:00 的 veCAKE 余额。
* veCAKE 仓位在 15 日或之前解锁的用户，在快照时间的 veCAKE 余额将为 0。因此他们在 Epoch 1 中没有投票权。

因此，要获得资格，你必须拥有一个有效的 veCAKE 仓位，且其解锁时间**晚于**当前 epoch 的结束/快照时间。

在上述示例中：

* 如果你想在 epoch 1 中投票，你必须拥有一个在 21 日或晚于 21 日（即第 3 周星期四）解锁的 veCAKE 仓位。

### 3 - 查看当前投票结果

前往"CAKE staking"，向下滚动找到"Gauges Voting"部分，然后点击"Check Gauges"。

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

在左上角部分，你可以看到：

* 你的 veCAKE。
* 当前 epoch 的快照时间和投票结束时间。
* 下一个 epoch 将根据当前 epoch 的投票结果分配的 CAKE 奖励总数。
* 已投出的 veCAKE 票数总量。

在右上角，你可以看到一个饼状图，表示每个 gauge 所获得的百分比。

在底部，有一份完整的所有投票 gauges 列表，包含它们获得的票数以及在当前 epoch 中获得的预期百分比权重。其中还有"boost"（加成）和"caps"（上限）字段，详细说明了两个重要的 gauge 特性。继续阅读以了解更多详情。

#### Gauge 加成（Boost）和排放上限（Emission Caps）

为确保 CAKE 奖励流向效率最高的 gauges，每个 gauge 都可以应用一个加成和/或一个排放上限。这两种特性可以同时存在。

Gauge 加成是应用于一个 gauge 所获票数的乘数，范围从 1 倍到 2.5 倍（V3 池的 gauges 上限为 2 倍）。这是为了鼓励对重要交易对的投票和流动性。

排放上限是对一个 gauge 可获得的百分比权重的最大上限，范围从 2% 到 20%。这是为了促进分配的公平性并防止 gauge 系统被滥用。

例如：

* 一个 gauge 有 10 票、2 倍加成和 15% 上限。总票数为 100。
* 应用加成后，该 gauge 将有 20 票，占总数（100）的 20% 权重。
* 然而，由于它有 15% 的上限，该 gauge 在下一个 epoch 中实际获得的 CAKE 奖励百分比将被调整为 15%。

#### Gauge 加成和排放上限是如何确定的？

在 gauge 申请过程中，我们会要求申请人提议他们希望为该 gauge 分配的加成乘数值和排放上限百分比。这些必须连同整个 gauge 申请一起，由 veCAKE 持有者投票表决。

所有 gauges 的默认选项为 1.00 倍乘数和 5% 排放上限。它们可以通过未来的提案进行更改。

{% hint style="info" %}
请注意，投票结果每周更新。数值基于即将到来的星期四 UTC 时间 00:00 的 veCAKE 余额计算。
{% endhint %}

### 4 - 添加要投票的 gauges

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

要为某个 gauge 投票，请向下滚动找到"My Votes"部分。点击"Add Gauge"。

在弹出窗口中，你可以通过点击蓝色的"+"图标将 gauges 添加到你的投票列表中。你可以在列表中找到当前的投票结果，以及加成和上限。

要快速定位某个 gauge，你可以使用筛选功能按区块链、费率层级和流动性类型筛选 gauges。或者在搜索框中输入代币代码。

### 5 - 选择对每个 gauge 投入多少百分比的 veCAKE

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

添加 gauges 后，你可以选择将你的 veCAKE 的多少百分比投给每个 gauge。

这是因为：

* veCAKE 会随着剩余锁定时间逐渐减少。估算和计算要投出多少确切的 veCAKE 并不现实。
* 在每个即将到来的 epoch 中重新投票很麻烦。因此，gauges 投票被设计为在你投出新一轮投票之前，将你的投票决定延续到所有即将到来的 epoch。

在上述示例中：

* 目前，我有 2.62 veCAKE。
* 我决定将 80% 分配给 CAKE-BNB，目前相当于 2.10 veCAKE。
* 20% 分配给 USDC-ETH，目前同样相当于 0.52 veCAKE。
* 我的 veCAKE 总量将随着剩余锁定时间逐渐减少。在快照时间，我的 veCAKE 可能会更少，但我 80% - 20% 的分配决定仍将应用于最终结果。
* 此外，这个 80% - 20% 的决定将应用于每一个即将到来的 epoch，直到我通过投出新的投票请求来更新它，或直到我的 veCAKE 因解锁而归零。

确认你的决定后，点击"Submit vote"并在你的钱包中确认。

### 6 - 更新你的投票

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

投票提交后，你可能会看到你的投票被更新为"Current Votes"，剩余的 veCAKE 也会更新。

请注意，每个 gauge 的投票决定只能每 10 天更新一次。一旦你提交投票请求，所有已投票的 gauges 在你能够提交另一个更新请求之前，都将应用 10 天的冷却期。

要更新你的投票决定，请更改百分比并再次提交。

{% hint style="info" %}
请注意，在通过添加 CAKE 或延长锁定时间获得更多 veCAKE 后，你需要通过重新提交投票请求来手动更新每一个 gauge。

无论你是否更改了百分比决定，10 天的冷却期仍然适用。
{% endhint %}
