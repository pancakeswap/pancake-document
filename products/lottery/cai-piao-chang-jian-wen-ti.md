# 彩票常见问题

## 如果没有中奖者？&#x20;

若无人中奖，该奖池中的 CAKE 将被添加进下一轮彩票奖池中。

## 我的彩票匹配了多个数字，但我却无法领奖?

&#x20;您的彩票上的数字需要与开奖数字 “由左到右” 开始完全吻合。详细说明请参阅[彩票v2 文档](../lottery.md)。

## 彩票 v2 与彩票 v1 有何不同？

彩票 v2 比彩票 v1 中奖率高一些。彩票 v2 普奖的中奖率提高了，每张彩票第一个数字有 1/10 的中奖率，而头奖需要 6 个号码按序跟开奖数字匹配（ v1 为 4 个数字）。彩票普遍中奖率提高，但头的中奖几率降低，进而形成巨大、甚至顶级的总奖池！

彩票 v2 介绍：

* 较便宜的票价（每张彩票约 5 美元的 CAKE），票价不受 CAKE 价格影响而大幅波动&#x20;
* 批量购彩折扣&#x20;
* 6 个分级奖池：匹配的号码越多，奖池越大&#x20;
* 手动选择彩票号码（可选），因此用户可以使用他们的幸运数字&#x20;
* 使用 [Chainlink VRF （随机数生成器）](https://docs.chain.link/docs/vrf/v2/introduction/)确保开奖数字为安全可信的随机数字。
* 降低了总费用（有关更多信息，请参阅[本页下方](cai-piao-chang-jian-wen-ti.md#gou-mai-cai-piao-xu-yao-zhi-fu-shen-me-jiao-yi-fei-ma)）&#x20;

了解有关[彩票 v2 功能、玩法和奖金的更多信息](../lottery.md)

## 每个奖项对应的分级奖池有多大？&#x20;

每个分级奖池的奖金来自每回合总奖池总 CAKE 奖金分配得来。

| 分级奖池(根据匹配号码数量排序） | CAKE 分配 |
| ---------------- | ------- |
| 第一个数字匹配          | 2%      |
| 前两个数字匹配          | 3%      |
| 前三个数字匹配          | 5%      |
| 前四个数字匹配          | 10%     |
| 前五个数字匹配          | 20%     |
| 六个数字全部匹配         | 40%     |
| 销毁部分             | 20%     |

## 我可以把我的彩票换回 CAKE 吗？&#x20;

不能，一旦购买成功，您将无法将您的彩票兑换回 CAKE。

## 如果我中奖了，我需要手动领取我的奖金吗？

是的，您需要在彩票页面上单击 “我中奖了吗” 字段下的 “**立即检查”** 按钮。&#x20;

## 彩票多久开一次奖？&#x20;

每 12 或 36 小时进行一次开奖。每天上午 0 点（UTC）和下午 12 点（UTC）之间交替进行一次开奖，UTC 时间上午 0 点之后的下一轮将在 36 小时之后进行，UTC 时间下午 12 点之后的下一轮将在 12 小时之后进行。

<figure><img src="../../.gitbook/assets/彩票轮次变化.png" alt=""><figcaption><p>彩票开奖轮次以及额外奖金注入时间表</p></figcaption></figure>

## 购买彩票需要支付上链费吗？&#x20;

每一次彩票购买操作都是一次链上操作，购买单张彩票将花费与一般链上转帐差不多的上链费用。

但是，购买多张彩票会增加上链费用。购买 100 张彩票的上链费用并不是单纯的购买 1 张彩票的费用乘以 100，上链费可能会增加至 5-6 倍（每回操作可能不同）。

## 批量购彩优惠是如何运作的？&#x20;

批量购彩优惠用于奖励一次性购买大量彩票的用户，而且折扣是随着购买数量递增的。如果您只购买 2 张彩票，则折扣可以忽略不计，但随着您在一次上链中增加要购买的彩票数量，折扣力度会迅速增加。

购彩优惠仅适用于单笔上链操作，单笔上链最多 100 张彩票。折扣无法累计至下一笔链上交易或下一轮彩票。

## 为什么我只能买100张彩票？

&#x20;一次购买最多只能购买 100 张彩票，但您可以多次购买。没有什么可以阻止您在购买 100 张彩票之后购买更多彩票。

## 如果我手动编辑两张或多张相同号码的彩票并且它们中奖了，我是否有资格获得每张彩票的奖金？

是的，每张彩票都被视为独立的。请注意，奖金不会是 1:1，因每张中奖彩票将均分对应分级奖池中的奖金。&#x20;

## 注入时间表：CAKE 什么时候注入彩票池？&#x20;

当人们购买彩票时，他们花费的 CAKE 将被添加到彩票总奖池中。另外，彩票每周七轮，每间隔一轮，就会有额外的 10000 CAKE 注入彩票总奖池中，如前面额外奖金注入时间表所示。

该注入计划从第 440 轮开始。