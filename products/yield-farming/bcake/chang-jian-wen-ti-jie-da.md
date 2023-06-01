# 常见问题解答

<figure><img src="../../../.gitbook/assets/how-bCAKE-FAQ.png" alt=""><figcaption></figcaption></figure>

### bCAKE 对农场的助推倍数如何计算？

您可能注意到了，在不同农场质押时，获得的bCAKE助推倍数不同。

&#x20;这是因为 bCAKE - 农场助推器倍数是在激活或刷新时使用以下指标计算的：&#x20;

* 用户 LP 质押数量 ：您在此农场中质押的 LP 代币数量&#x20;
* 农场 LP 质押总数：此农场中质押的 LP 代币总数&#x20;
* 用户锁仓数量 : 您在 CAKE 锁仓质押糖浆池中锁仓的 CAKE 数量
* 用户锁仓时长 : 您的 CAKE 锁仓仓位的总质押时长&#x20;
* 锁仓总量 :  所有用户在 CAKE 锁仓质押糖浆池中锁定的 CAKE 总数&#x20;
* 锁仓平均时间 : 所有用户锁仓在 CAKE 锁仓池的平均锁仓时长

加成倍数计算公式：&#x20;

1. 结果A = 常量A \* 用户 LP 质押数量&#x20;
2. 结果B = (农场 LP 质押总数 \* 用户锁仓数量 \* 用户锁仓时长 / 常量B) / (锁仓总量 \* 锁仓平均时间)&#x20;
3. 助推倍数 = min(用户 LP 质押数量, (结果A + 结果B)) / 结果A&#x20;

常量A 和 常量B 由厨房设定，未来会根据社区反馈和市场情况进行调整。以下是一些计算示例：

| 计算因子        | 数值    |
| ----------- | ----- |
| 农场 LP 质押总数  | 10000 |
| 锁仓总量 (CAKE) | 10000 |
| 锁仓平均时间      | 35    |
| 常量A         | 0.5   |
| 常量B         | 5     |

<table><thead><tr><th>用户</th><th width="109">LP 质押数</th><th width="131">CAKE 锁仓数</th><th width="104">锁仓时间</th><th width="78">结果A</th><th width="78">结果B</th><th>bCAKE 倍数</th></tr></thead><tbody><tr><td>用户1</td><td>1000</td><td>1000</td><td>28</td><td>500</td><td>160</td><td>1.32</td></tr><tr><td>用户2</td><td>1000</td><td>1000</td><td>10</td><td>500</td><td>57</td><td>1.11</td></tr><tr><td>用户3</td><td>1000</td><td>1000</td><td>52</td><td>500</td><td>297</td><td>1.59</td></tr><tr><td>用户4</td><td>5000</td><td>1000</td><td>35</td><td>2500</td><td>200</td><td>1.08</td></tr><tr><td>用户5</td><td>1000</td><td>5000</td><td>35</td><td>500</td><td>1000</td><td>2.00</td></tr></tbody></table>

{% hint style="info" %}
您想提升农场收益的 LP 数量越多；

您将需要锁仓更多 CAKE ，并锁仓更长的时间。
{% endhint %}

### 为什么我的助推倍数在激活之后也会发生改变？

请注意，任何用户针对农场或 CAKE 锁仓质押池的操作都会影响农场及 CAKE 锁仓质押池的最新数据和统计方式从而自动更新您的助推倍数，包括但不限于。

* 将 LP 代币从农场质押/解压&#x20;
* 从农场收割 CAKE 奖励&#x20;
* 延长您的 CAKE 锁仓时间&#x20;
* 将更多的 CAKE 添加到您的锁仓仓位中&#x20;
* 将您的 CAKE 锁仓质押转换为灵活质押

{% hint style="warning" %}
请注意：

为了确保公平，防止潜在的滥用以及使用过时的数据进行欺骗。农场助推器被设计为由社区治理。因此，任何人都可以在[农场助推器合约](https://bscscan.com/address/0xe4faa3ef5a9708c894435b0f39c2b440936a3a52)上调用 refresh(address \_user, uint256 \_pid)函数，使用最新数据刷新任何人的助推倍数。
{% endhint %}

### 激活或停止助推器后，我的 CAKE 奖励在哪里？

<div align="center">

<figure><img src="../../../.gitbook/assets/bCAKE-has-pending-balance.png" alt=""><figcaption></figcaption></figure>

</div>

在使用 bCAKE - 农场助推器进行耕种时，您收获的一些 CAKE 奖励会暂时存储在农场助推器合约中。当发生这种情况时，您会在 “CAKE EARNED (CAKE 已赚取）” 下方看到一条虚线，表示除了显示的数字之外，您在农场助推器合约中还有更多的 CAKE 奖励。

**这部分 CAKE 奖励将在下次收割、存款或取款时自动发送到您的钱包**。

要立即收割它们，只需单击“Harvest 收割”按钮。

<figure><img src="../../../.gitbook/assets/bCAKE-has-pending-balance-tooltip.png" alt=""><figcaption><p>.</p></figcaption></figure>

要查看农场助推器合约中的额外奖励数量，请悬停或长按带有虚线的数字。

### 为什么我无法助推农场？

1. 农场助推器仅适用于特定的农场。未来将支援更多农场。现在请在界面上查找标有 “助推（Boosted） ” 标签的农场。

<figure><img src="../../../.gitbook/assets/bCAKE-boost-tag.png" alt=""><figcaption></figcaption></figure>

2\. 能够同时提升的农场有数量限制。要查看可用助推器数量，请参阅顶部的面板。

<figure><img src="../../../.gitbook/assets/bCAKE-farm-number-limit (1).png" alt=""><figcaption></figcaption></figure>

若助推器使用数量达到上限，您需要取消已经激活的助推器才能激活其他农场的助推器。&#x20;

3\. 确保您已完成一次性设置 (one-time setup)。&#x20;

4\. 由于涉及多个合约，一些合约交互需要稍微多一点的 gas 代币（BNB）。所以请确保钱包里有足够的 BNB。

### 最大 bCAKE 助推倍数是多少？

目前，农场助推器最大之助推倍数为 2 倍。

仅能提高基准 APR (仅 CAKE 收益），最高至 2 倍。 bCAKE 不能提高交易手续费收益（LP 手续费）。

### 如何增加我的 bCAKE 助推倍数？

* 在锁仓质押糖浆池中添加更多 CAKE&#x20;
* 延长您的 CAKE 锁仓质押的持续时间&#x20;

简单的说： 锁仓质押更多 CAKE，质押更长的时间。

[详细了解如何计算 bCAKE 助推倍数](ru-he-shi-yong-bcake.md)。

### 额外提升的 CAKE 奖励从何而来？

**请别担心，bCAKE 设计上并没有使用到额外的 CAKE 产出及分配。**

类似于锁仓 CAKE 质押。bCAKE 提高了个人用户相对于其他用户的份额。

即使在部署 bCAKE 后基准 APR 可能会下降。大厨们认为这是一个很好的权衡，因为它不仅通过提高农场产量使忠实的 CAKE 爱好者受益，而且还创造了对 CAKE 的更多需求场景，并成为 CAKE 锁仓质押的巨大动力。&#x20;

### 为什么第一次启用农场助推器时 gas 费用很高？

要启用 bCAKE - 农场助推器，用户必须设置代理钱包地址，这需要部署新合约。这个过程是需要消耗比较多的 gas 费。（根据 BNB 价格和区块链状况，约 2\~5 美元） 但是，每个钱包地址的设置过程都是一次性的，您只需执行一次即可。

### 为什么我的助推倍数很低？

bCAKE - 农场助推器通过评估您的锁仓 CAKE 的仓位、质押时长和您的流动性 LP 数量来运作。简单来说：

如果用户想在农场中获得更高的助推倍数，他们将需要在锁仓质押糖浆池中锁定更多的 CAKE 、延长锁仓持续时间或两者均提高。

这种设计不仅对大量持仓者有利，而且同样有利于任何与农场持仓相较来说拥有相当大 CAKE 锁仓持仓的用户。

&#x20;在[此处了解有](ru-he-shi-yong-bcake.md)关如何计算倍数的更多信息。

### 为什么现在能使用助推器的农场只有三个？

&#x20;由于 bCAKE 涉及更新 PancakeSwap 的核心产品之一，即流动性农场。大厨们希望采取更慢、更稳定的方式来发布。&#x20;

因此，在最初的产品发布阶段，许多参数非常保守。包括可以助推的农场数量，哪些农场用户可以助推，以及获得助推倍数的难度参数。&#x20;

在初始发布阶段之后，大厨们将根据社区反馈调整参数。

### bCAKE 是否经过审计？&#x20;

bCAKE 已经过内部和外部审计机构的审计。&#x20;

在此处查看 [PeckSheild 的审计报告](https://github.com/peckshield/publications/blob/master/audit\_reports/PeckShield-Audit-Report-PancakeSwap-FarmBooster-v1.0.pdf)。
