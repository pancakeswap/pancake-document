---
description: 使用您的 veCAKE 投票来决定 CAKE 激励该如何分发
---

# Gauges Voting

<figure><img src="../../../.gitbook/assets/image (239).png" alt=""><figcaption></figcaption></figure>

#### 什么是 gauge？&#x20;

要理解 Gauge Voting 是什么，大致上为，所有需要使用到 CAKE 激励的产品，都可视为 Gauge 系列的产品中的一个 Gauge。这些产品包括农场、每周 CAKE 池的奖励（CAKE weekly reward pool）、仓位管理工具管理的资金库（vaults）等。

veCAKE 持有者现在可以使用他们的 veCAKE 作为选票，来决定哪个产品将可以获得多少百分比的 CAKE 产率。当一个 Gauge 透过 Gauges Voting 投票机制获投的 veCAKE 票数越多，其代表的流动池／仓位管理资金库所获得的 CAKE 激励配额就越多。

{% hint style="info" %}
每轮投票（第 n 轮）时，每个 Gauge 的得票数，将决定下一轮投票（第 n+1 轮）时，CAKE 激励将如何分配，这些变动在当前这轮投票结束后才会生效。
{% endhint %}

#### Gauge 的类型

Gauge 有两种类型—— "核心（core）" 和 "非核心（non-core）"。前者厨房将会保证其获得一定量的 CAKE 激励。后者社区可以通過 veCAKE 投票來影響 "非核心" 池能获得多少的 CAKE 激励配额。

1. "核心" Gauges，包括主流币和稳定币（WBTC、ETH、BNB、USDC、USDT 等）的代币对——厨房将确保这些代币对获得足够的 CAKE 奖励，因为它们对协议的收入贡献巨大。&#x20;
2. "非核心" Gauges，即为未被归类为 "核心" Gauges 的所有其他 Gauges。

## 如何投票？

### 1- 了解投票时间表

<figure><img src="../../../.gitbook/assets/image (250).png" alt=""><figcaption></figcaption></figure>

Gauge 加权投票（Gauges weight voting）每两周进行一次。每一轮之开始时间，跟每一回收入分成开始时间一样，在每两周的周四 00:00 UTC。

\
在上图的范例中：

* 第一轮投票开始时间：当月 1 日，第 1 周，星期四 00:00 UTC。
* 第一轮投票结束时间：当月 15 日，第 3 周，星期四 00:00 UTC 时，即两周后。&#x20;
* 用户可以在 1 日 00:00 UTC 到 14 日 00:00 UTC 之间的这段时间进行投票。&#x20;
* 14 日 00:00 UTC 到 15 日 00:00 UTC 期间，为统计票数以及厨房配票的时间，期间**不能**进行投票。
* 第一轮投票结束：最终投票结果将在 15 日 00:00 UTC 进行快照。此时第一轮投票结束。&#x20;
* 投票结果将在结束后 72 小时内实施。

## 2- 取得资格

<figure><img src="../../../.gitbook/assets/image (251).png" alt=""><figcaption></figcaption></figure>

由于 veCAKE 数值会根据剩余锁仓时间的减少而逐渐减少，投票结果将在每轮投票结束时通过快照获取，这包括总 veCAKE 数量，以及每个用户持有的 veCAKE 数值。\
\
在上图的范例中：

* 第一轮的投票结果，将根据 15 日 00：00（UTC）时 veCAKE 数值来计算。&#x20;
* 如果用户的 veCAKE 仓位在 15 日之前或 15 日当天解锁，则因其在快照时间时的 veCAKE 数值为 0，所以他们在第一轮投票没有投票权。

因此，要获得投票资格，您需要保有一个有效的 veCAKE 仓位，并且仓位解锁时间在当前投票结束/快照时间**之后**。\
\
在上图的范例中：

* 如果您想在第一轮投票中进行投票，您需要拥有一个有效的 veCAKE 仓位，此仓位的解锁时间需于 21 日或之后，或晚于第三周的周四。

## 3- 查看当前投票结果

前往 CAKE Staking 页面，向下滚动并找到 Gauges Voting 部分，然后点击 "查看 Gauges"。

<figure><img src="../../../.gitbook/assets/image (252).png" alt=""><figcaption></figcaption></figure>

在左上角部分。您可以看到：&#x20;

* 您持有的 veCAKE 票数。&#x20;
* 当前轮次的快照时间和投票结束时间。&#x20;
* 根据当前轮次投票结果，下一轮将会分发出去的 CAKE 奖励总数。
* &#x20;投出的 veCAKE 总数。

在右上方，您会发现一个圆饼图，代表每个 gauge 得到的票数百分比。

底下有一个完整的 Gauges Voting 列表。其中有目前轮次中，每个 Gauge 的得票数，及预计得票率百分比（% weight）。此外，还有一个 "加权（boost）" 和 "上限（caps）" 栏位，他们显示并说明了 Gauge 的两个重要特性。继续阅读，以了解更多详情。

#### Gauges 的加权和配额上限&#x20;

为确保作为奖励的 CAKE 会流向贡献最大的 Gauge 们。每一个 Gauge 都有一个加权（boost）以及 激励上限（cap）。两个特性可以同时生效。

Gauge Boost 是一个乘数，此数字会应用在单一个 Gauge 所获得的票数上，范围从 1x 到 2.5x 不等（v3 农场 Gauge 的上限则为 2x）。目的是为了鼓励用户向重要的代币对投票以及提供流动性。

激励额度上限（emission cap）等同每一个 Gauge 得票百分比（% weight）上限，此上限可以为 2% 到 20% 不等。这是为了分配能更加公平，并防止 Gauge 系统被滥用。\
（原文：Emission cap is a maximum cap on the % weight a gauge can receive, ranging from 2% to 20%.）

举例说明：

* 一个 Gauge 获得了 10 票，它有 2 倍的加权和 15% 的上限。总票数为 100。
* 经过加权后，该 Gauge 将有 20 票，占总票数（100）的 20%。&#x20;
* 但由于它有 15% 的得票上限，该 Gauge 在下一轮投票期间，获得的 CAKE 奖励的百分比将最终调整为 15%。

#### Gauge 的加权乘数和激励上限怎么决定的？

在申请 Gauges 的过程中，我们会要求申请人提出他们希望分配给该 Gauge 的加权乘数和激励上限 % 数。这些必须由 veCAKE 持有者投票决定。这在整个 Gauge 申请中全部一块进行。

所有 Gauges 的默认选项为 1.00 倍乘数和 5% 额度激励上限。这些都可以在未来提出新的提案并进行更改。

{% hint style="info" %}
请注意，投票结果每周更新一次。数字根据下周四 00:00 UTC 时的 veCAKE 数值计算。
{% endhint %}

### 4 - 选择 Gauges 以进行投票

<figure><img src="../../../.gitbook/assets/image (253).png" alt=""><figcaption></figcaption></figure>

要对特定的 Gauge 进行投票，请向下滚动并查找 "我的持票（My Votes）"。点击 "Add Gauges (选择 gauges)"。&#x20;

在弹出的视窗中，您可以透过点击蓝色 "+" 图标将该 gauge 添加到您的投票清单中。您可以在清单中看到目前的投票结果，以及加权乘数和得票率上限。

要快速找到 Gauges，您可以使用过滤功能，按照区块链、费用级别和流动性类型过滤 Gauges。或在搜寻栏中输入代币查找。

## 5 - 输入我要投给各 Gauges 的 veCAKE 票数百分比

<figure><img src="../../../.gitbook/assets/image (254).png" alt=""><figcaption></figcaption></figure>

添加好 Gauges 后，您可以选择要分配多少百分比的 veCAKE 给各个 Gauges。

这是因为：

* veCAKE 会随着剩余锁仓时间的减少而逐渐减少。估算和计算要投多少确切的 veCAKE 数量是不切实际的。&#x20;
* 每一轮都需要重新投票会很麻烦。因此，Gauges Voting 系统会将您的投票决定，连贯所有即将到来的每一轮投票，直到您手动更改您的投票为止。

在图片中的范例中：&#x20;

* 目前，我拥有 2.62 veCAKE。&#x20;
* 我决定将其中 80% 分配给 CAKE-BNB，目前是 2.10 veCAKE。&#x20;
* 20% 分配给 USDC-ETH，目前是 0.52 veCAKE。&#x20;
* 我的总 veCAKE 数值会随着剩余锁仓时间的减少逐渐减少。
* 在快照时间，我的 veCAKE 可能会减少，但我的 80% - 20% 的分配决定仍将适用于最终结果。&#x20;
* 此外，这个 80% - 20% 的投票决定还将在接下来的每一轮投票中保留，直到我通过提交新的投票请求来更新它。或者直到我的 veCAKE 因解锁而变为 0。

确认您的投票分配后，点击 "提交投票（Submit vote）" 并在钱包中确认。

## 6- 更改您的投票

<figure><img src="../../../.gitbook/assets/image (255).png" alt=""><figcaption></figcaption></figure>

提交投票后，您会看到您的投票状态显示在 "当前投票（CURRENT VOTES）" 列。剩余可用于投票的 veCAKE （remaining veCAKE）数值也会更新。

请注意，由于每个 Gauge 的投票决定只能每 10 天更改一次。一旦您提交了投票请求，所有已投票的 Gauges 都将有 10 天的冷却期， 10 天后您才能再次提交更改请求。&#x20;

要要变更投票决定，请更改 % 百分比并提交。

{% hint style="info" %}
请注意，通过添加 CAKE 或延长锁仓时间获得更多 veCAKE 后。您需要通过重新提交投票请求 的操作来手动更改/更新每个 Gauges 的得票数。&#x20;

在以上情况下，无论您是否更改了每个 gauge 的百分比，依然会有 10 天的投票更改冷却期。
{% endhint %}
