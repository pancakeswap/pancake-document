# 🔄 稳定币兑换

<figure><img src="../../.gitbook/assets/docs masthead (1).png" alt=""><figcaption></figcaption></figure>

PancakeSwap 上的 StableSwap 是一项基于不变曲线滑点函数具有较低滑点的稳定币对交易的功能。 它旨在交换价格接近的特定资产——例如美元稳定币（例如 HAY、BUSD 和 USDT）或流动性质押代币（例如 stkBNB 和 aBNBc）。&#x20;

StableSwap 是 Curve Finance 的 AMM 在 PancakeSwap 上的实现。 它在恒定乘积公式 (x\*y=k) 之上添加线性不变常数和曲线 (x+y=k)，以在流动性池不是极度不平衡的情况下保持价格更加平等。 因此，由于 StableSwaps 仅限于价格相似的资产，因此无常损失并不那么令人担忧（在极端价格脱锚情况下除外），并且滑点低于仅使用恒定乘积公式的普通 AMM。&#x20;

当您在 StableSwap 上进行代币兑换（交易）时，您将支付 0.04% 的交易费用，低于普通 PancakeSwap AMM 上通常的 0.25%。 费用归属细分如下：

* 0.02% 分配给 LP 作为奖励 (50%)&#x20;
* 0.016% 用于 CAKE 回购和销毁 (40%)&#x20;
* 0.004% 分配给PancakeSwap 团队金库 (10%)

在产品发布时，厨房将逐步推出 StableSwap 交易对，以进一步测试和改进产品。 推出的第一个稳定币交易对将是 HAY-BUSD。&#x20;

Helio Protocol 的 HAY 是一种完全去中心化的 BNB 超额抵押[destablecoin](https://docs.helio.money/v/chinese/) (分布式代币）。 选择 HAY-BUSD 对作为第一个交易对的原因是：&#x20;

* Stablesawp希望成为 HAY 交易量成长的首批主要交易场所之一&#x20;
* 由于 HAY 最近才推出（2022 年 8 月中旬），与其他稳定币相比，流动性转移的数量和运营影响较小，更易于在 StableSwap 产品上推出&#x20;
* 根据这一交易对的进展和社区反馈，厨房可以逐步添加其他稳定交易对

## 为什么我应该使用 StableSwap 而不是正常的 AMM 兑换？&#x20;

* 使用相同的交易步骤更有效地交换您的稳定币或其他价格相似的资产对！
* 使用 StableSwap 功能，交易滑点低于仅使用恒定乘积公式的普通 AMM 。
* 与正常的 AMM 相比，交易费用也较低。

## 厨房目前仍在修复和烹饪的一些功能是什么？&#x20;

* 关于 StableSwap 和stable LP 的更好的 UI 指南&#x20;
* StableSwap 信息页面&#x20;
* 添加更多的稳定交易对，以及现有LP的迁移过程

## 时间线：&#x20;

* StableSwap 启动和 HAY-BUSD 流动性供应启用：**2022 年 9 月 22 日 11:00 UTC**&#x20;
* 农场迁移（CAKE 奖励从 HAY-BUSD LP 农场 重新定向到 HAY-BUSD stable LP 农场）：**2022 年 9 月 23 日 11:00 UTC**
