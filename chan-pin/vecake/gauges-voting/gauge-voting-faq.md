# Gauge Voting FAQ

### 我持有 veCAKE 仓位，为什么不能投票？

请确认持仓仓位的解锁时间，它需要大于或等于 "本轮投票期的快照时间再往后加上 1 周" 的时间。

如果您的仓位在快照时间当时解锁，表示您在快照时间时持有的 veCAKE 为 0。此时您无法投票。



### 创建 veCAKE 仓位后可以立即投票吗？

可以。&#x20;

仓位设置完成后，您可以立即使用 veCAKE 进行投票。&#x20;

但是：&#x20;

* 每轮投票期的最后 24 小时内，不能投票。&#x20;
* 两次投票更改时间间隔不能小于 10 天。
* 您仓位的解锁时间晚于或等于快照时间。



### 如何获得更多 veCAKE （或选票）？&#x20;

可以，只需锁仓更多 CAKE 或延长锁仓时间即可。&#x20;

请注意，通过添加 CAKE 或延长锁仓时间获得更多 veCAKE 后，您需要手动重新提交投票，您投向每个 Gauge 的票数才会更新。



### 为什么投票结果在计票期结束后发生了变化？

在统计票数期间，PancakeSwap 厨房将依据每个 Gauge 的多重数据结果来投出厨房的持票。

这样做的目的是：

* 确保核心流动性池能给予 LP 流动性资金有竞争力的回报。
* 在现有糖浆池合作伙伴完全迁移到 veCAKE gauge 投票系统之前，确保与现有糖浆池合作伙伴的合约得到履行。
* 确保在 veCAKE 推出后，未获得任何票数的任何小型农场，在最初推出时至少获得一些激励分配，\
  并以其当前获配的激励水平为上限。\
  （原文：Ensuring that any of the smaller farms which did not receive any votes after the launch of veCAKE will receive at least some allocation in the initial rollout, capped at their current emission levels.）

更多详情于此提案中：[https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c](https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c)



### 为什么我的票数在减少？&#x20;

因为当我们向 Gauges 投出持票时，使用的是我们持有的 veCAKE。而 veCAKE 数值会随着剩余锁仓时间的减少而逐渐减少。&#x20;

随着您的 veCAKE 锁仓渐渐到期，您持有的票数会慢慢减少至最终为 0。

若要提高持票数，可在锁仓仓位中添加更多 CAKE 或延长锁仓时间，来获得更多 veCAKE 选票。



### 我获得了一些 veCAKE，为什么我不能向其他 Gauges 投票？

在将票投给 Gauges 时，我们的计算方式是 % 数而非票数，您从持有的选票中将一定 % 数的票分配给复数个 Gauges。

因此，在您获得了更多 veCAKE 之后，如果您在上一次投票中将持有的 100% veCAKE 全数投出，并且仍处在 10 天冷却期之内，此时您将无法对投票决定做出更改，需等到 10 天冷却期结束。



### 投票结果已经统计完毕，为什么 CAKE 激励的分配没有变化？&#x20;

PancakeSwap 上有众多使用到新产出的 CAKE 的产品，将投票结果套用到他们身上需要大约 72 小时。

大厨们将继续努力使这一过程自动化，以缩短时间差并提高准确度。



### 为什么我投票支持的 Gauge 在下一轮投票期间没有分配到任何 CAKE？

白名单上的 Gauges 需要得到至少相当于每天 1 CAKE 产能配额的票数，才能开始获得 CAKE。
