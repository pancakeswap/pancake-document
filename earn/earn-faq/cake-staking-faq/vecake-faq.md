---
hidden: true
---

# veCAKE 常见问题解答

<figure><img src="../../../.gitbook/assets/image (340).png" alt=""><figcaption></figcaption></figure>

#### 锁仓 CAKE 与 veCAKE 有什么区别？ <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE 是固定期限 CAKE 质押的新版本，为锁仓 CAKE 持有者提供更多的好处和权力。包括 gauge 权重投票、额外激励、收益加成等等。

#### 当新的 veCAKE 部署后，CAKE 池奖励会发生什么？ <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

CAKE 池奖励释放将被转用于奖励所有 veCAKE 持有者，奖励依据是他们的 veCAKE 余额占总供应量的比例。

CAKE 奖励和每周收入分成奖励现在可以在每周四领取。

请注意，要继续接收奖励，用户需要迁移到新的 veCAKE 质押。

#### 我可以锁仓 CAKE 的最大时长是多少？ <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

你可以锁仓 CAKE 的最大时长现已延长至 4 年。

#### veCAKE 是一种新代币吗？它可以转移吗？ <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE 是一个根据锁仓的 CAKE 数量和剩余锁仓时间实时生成的数值。它不是标准代币，无法转移。

#### 为什么我的 veCAKE 余额变化了？如何计算其余额？ <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

veCAKE 余额根据剩余锁仓时长线性递减至 0。因此当我们接近解锁时间时，你的余额会减少。

veCAKE 余额可以通过以下方式计算：

```javascript
lockedAmount // amount of CAKE locked
currentTime // current time
lockEndTime // the unlock time
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // max lock time (4 years)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### 如何增加我的 veCAKE？ <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

一旦你拥有一个活跃的 veCAKE 头寸，你可以添加更多 CAKE 或续期/延长你的锁仓时长，以提升你的 veCAKE 余额。

#### 当头寸解锁时会发生什么？我可以立即续期吗？ <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

当 veCAKE 质押头寸解锁后，你可以提取所有质押的 CAKE。

要续期你的头寸，你需要提取所有 CAKE，并通过选择锁仓数量和锁仓时长来设置一个新的质押头寸。

#### 我锁仓了 1 周，为什么剩余锁仓时间少于 1 周？ <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

当你使用新的 veCAKE 锁仓时，解锁时间会向前取整到最近的 UTC 时间星期四。例如，当你在星期二锁仓 1 周时，你的实际解锁时间将是即将到来的星期四，即 2 天后。

你可以在底部预览你的实际解锁时间。

#### 我可以在 CAKE 池中锁仓更多 CAKE 吗？ <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

不可以。

一旦 veCAKE 部署，CAKE 质押池将被弃用，不再接受任何进一步的 CAKE 延期或存入。

要锁仓 CAKE 并享受其好处，请前往 veCAKE 页面。

#### 为什么我无法迁移？ <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

从 CAKE 池迁移到 veCAKE 需要你拥有一个活跃的头寸。如果你的 CAKE 池质押头寸已经解锁，只需提取那些 CAKE 并创建一个原生 veCAKE 质押头寸。

在某些情况下，当你的 CAKE 池剩余锁仓时间少于 7 天时，无法执行迁移。在这种情况下，只需等待解锁，提取那些 CAKE 并创建一个原生 veCAKE 质押头寸。

#### 我可以提前提取我锁仓的 CAKE 吗？ <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

不可以。

一旦锁仓，CAKE 将质押在 veCAKE 合约中直到解锁时间。

#### 我可以部分迁移我的 CAKE 吗？ <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

不可以。

你只能一次性迁移你的整个 CAKE 池头寸。

#### iCAKE、bCAKE、vCAKE 和 rCAKE 会发生什么？ <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**对于 iCAKE：**

IFO iCAKE 现已升级以支持 veCAKE。查看：

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**对于 bCAKE：**

农场加成 bCAKE 现已升级以支持 veCAKE。查看：

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**对于 vCAKE：**

投票 vCAKE 现已升级以支持 veCAKE。查看：

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**对于 rCAKE：**

所有 veCAKE 持有者（无论是原生还是迁移而来）都将自动注册到新的收入分成池。收入份额按照现有时间表分配。旧的收入分成池将停止运行，用户可以通过前往权益卡片领取其待领取的奖励。查看：

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Broken link](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### 多签钱包可以用于与 veCAKE 交互吗？

可以

但是，veCAKE 质押合约中为未列入白名单的地址实施了一个 `noContract` 修饰符。要启用质押或从固定期限 CAKE 质押池迁移，所有基于合约的多签钱包都必须执行一次性的自我加入白名单操作。

要加入白名单，请访问以下任一页面：

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

应该会出现一个提示。点击"Whitelist"并在你的多签钱包中继续执行该交易。

一笔交易将被发送到 veCAKE 的所有者，它是一个具有无需许可的写入函数的合约，允许任何合约执行自我加入白名单。

如果提示没有出现，请按照此说明从 [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11) 执行交易：

```
// call:
VECakeOwner.setWhitelist(bool _status = true)

// VECakeOwner address:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### 为什么会有多个 APR？

锁仓 CAKE 以获得 veCAKE 在 PancakeSwap 构建的产品套件方面提供了许多巨大的好处。好处和激励以不同的形式来自不同的来源。因此，会有多个 APR。

你可以同时赚取所有这些，因此综合 APR 将是所有 APR 的总和。

请注意，veCAKE 的许多其他好处无法以 APR 的形式量化，例如[农场收益加速器 bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/) 或 [IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)。请务必也查看这些内容。

#### 什么是 veCAKE 池 APR？

这是来自 CAKE 释放的激励，其速率由 veCAKE 池投票 gauge 控制。

要增加对此 gauge 的释放，请查看 [Gauge 投票](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/)。

#### 什么是收入分成 APR？

这是来自协议收入分成的激励，来自 DEX 产品中收取的兑换手续费。

查看[收入分成](/broken/pages/wQegezs7c6A2HzQjPEjh)了解更多信息。
