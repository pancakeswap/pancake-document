# 🔄 稳定币兑换

<figure><img src="../../.gitbook/assets/docs masthead (1) (1).png" alt=""><figcaption></figcaption></figure>

PancakeSwap 上的 StableSwap 是一项基于不变曲线滑点函数，具有较低滑点的稳定币对交易的功能。 它旨在交换价格接近的特定资产——例如美元稳定币（例如 HAY、BUSD 和 USDT）或流动质押代币（liquid staking tokens）（例如 stkBNB 和 aBNBc）。&#x20;

稳定币兑换是 Curve Finance 的 AMM 在 PancakeSwap 上的实现。 它在恒定乘积公式 (x\*y=k) 之上添加线性不变常数和曲线 (x+y=k)，以在流动性池不是极度不平衡的情况下保持价格更加均等。 因此，由于 StableSwaps 仅限于价格逼近的资产，因此无常损失并不那么令人担忧（在极端价格脱锚情况下除外），并且滑点低于仅使用恒定乘积公式的普通 AMM。&#x20;

当您在 StableSwap 上进行代币兑换（交易）时，您将支付 0.04% 的交易费用，低于普通 PancakeSwap AMM 上通常的 0.25%。 费用细分如下：

* 0.02% 分配给 LP 作为奖励 (50%)&#x20;
* 0.016% 用于 CAKE 回购和销毁 (40%)&#x20;
* 0.004% 分配给PancakeSwap 团队金库 (10%)

产品发布同时，厨房将逐步推出 StableSwap 交易对，以进一步测试和改进产品。 首批推出的将是**HAY-BUSD**。

Helio Protocol 的 HAY 是一种完全去中心化的 BNB 超额抵押[destablecoin](https://docs.helio.money/v/chinese/) (分布式代币）。 选择 HAY-BUSD 对作为第一个交易对的原因是：&#x20;

* 希望HAY交易量成长，同时成为HAY首批主要交易场域之一
* 由于与其他稳定币相比，HAY最近才推出（2022年8月中旬），进行流动性迁移对运营、体量影响更易分析，较适合稳定币兑换初上线时的流动性交易对
* 根据这一交易对的使用情况和社区反馈，厨房可以逐步添加其他稳定交易对

## 为什么我应该使用 StableSwap 而不是普通的 AMM 兑换？&#x20;

* 相同的交易步骤下，更有效率效地交换交换您的稳定币或其他价格相似的资产！
* 使用 StableSwap 功能，交易滑点低于仅使用恒定乘积公式的普通 AMM 。
* 与普通的 AMM 相比，交易费用也更低。

## 厨房目前仍在修复和烹饪那些功能？&#x20;

* StableSwap和Stable LP的用户界面指南优化
* StableSwap 信息页面&#x20;
* 添加更多的稳定交易对，以及现有LP的迁移

## 时间线：&#x20;

* StableSwap 启动和 HAY-BUSD 流动性供应启用：**2022 年 9 月 22 日 11:00 UTC**&#x20;
* 农场迁移（CAKE 奖励从 HAY-BUSD LP 农场 重新定向到 HAY-BUSD stable LP 农场）：**2022 年 9 月 23 日 11:00 UTC**
