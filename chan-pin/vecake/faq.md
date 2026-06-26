# veCAKE FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28338%29.png" alt=""><figcaption></figcaption></figure>

### 锁仓的 CAKE 和 veCAKE 有什么区别？&#x20;

veCAKE 是锁仓质押 CAKE 的新版本，可以为 CAKE 锁仓用户提供更多好处和权力。包括 Gauge 投票（gauge weight voting）、额外的激励（投票奖励）、农场收益助推等。&#x20;

### 部署新的 veCAKE 后，CAKE 糖浆池奖励会发生什么变化？&#x20;

CAKE 糖浆池的奖励发放，将根据 veCAKE 持有者个人的 veCAKE 数值，与 veCAKE 总量之比，来进行分配。&#x20;

CAKE 奖励和每周收入分成奖励现在可以在每周四进行领取。&#x20;

请注意，要继续获取奖励，用户需要将原来的 CAKE 糖浆池锁仓仓位进行迁移，以取得 veCAKE。

### 锁仓 CAKE 的最长期限是多长？&#x20;

可以选择的锁仓 CAKE 的最长期限现已延长至 4 年。&#x20;

### veCAKE 是新的代币吗？可以转让吗？&#x20;

veCAKE 是根据锁定的 CAKE 数量和剩余锁仓时长，实时生成的数字。它不是标准代币（通证），不能转让。&#x20;

### 为什么我的 veCAKE 数值发生了变化？此数值如何计算的？&#x20;

veCAKE 数值将会根据剩余锁仓时长，线性递减至 0。因此，当越接近解锁时间，您的持有数值就会减少。veCAKE 数值的计算方法如下：

```javascript
您的锁仓数量 // 锁仓的 CAKE 的数量
现在的时间 // 现在的时间
锁仓到期时间 // 解锁时间
最大锁仓时间 = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // 最大锁仓时间 (4 年)

剩余锁仓时长 = 锁仓到期时间 - 现在的时间
veCAKE = 您的锁仓数量 * (剩余锁仓时长 / 最大锁仓时间)
```

### 如何增加我的 veCAKE 数字？&#x20;

只要您拥有有效的 veCAKE 仓位，您就可以添加更多 CAKE 或延长锁仓时长，以提高您的 veCAKE 数值。&#x20;

### 锁仓仓位解锁后会发生什么？我可以立即续期吗？&#x20;

当 veCAKE 仓位解锁时，您可以提取所有质押的 CAKE。&#x20;

想要继续锁仓，您需要提取所有的 CAKE，并通过选择锁仓数量和锁仓时长来建立新的锁仓仓位。&#x20;

### 我锁仓了 1 周，为什么剩余锁仓时间少于 1 周？&#x20;

当您在 veCAKE 页面创建新的锁仓仓位时，解锁时间会向前追溯到与其最接近的 UTC 时间的星期四 。例如，当您在星期二锁定 1 周时，您的实际解锁时间将是下一个星期四，也就是 2 天后。&#x20;

您可以在底部预览实际解锁时间。

### 我可以在 CAKE 糖浆池中锁定更多的 CAKE 吗？&#x20;

不可以。&#x20;

一旦部署了 veCAKE，CAKE 糖浆池将被废弃，不再接受任何 CAKE 存入或者延期。&#x20;

要锁仓 CAKE 并享受其好处，请前往 veCAKE 页面进行锁仓。&#x20;

### 为什么我不能操作迁移？&#x20;

从 CAKE 糖浆池迁移到 veCAKE 需要您有一个有效的锁仓仓位。如果您的 CAKE 糖浆池锁仓仓位已经解锁，只需提取这些 CAKE 并转到 veCAKE 页面创建一个新的锁仓仓位即可。&#x20;

在某些情况下，如果您的 CAKE 糖浆池池剩余锁仓时长少于 7 天，则无法执行迁移。在这种情况下，只需等待解锁，提取这些 CAKE 并转到 veCAKE 页面创建一个新的锁仓仓位。

### 我可以提前提取锁仓的 CAKE 吗？

&#x20;不可以。&#x20;

一旦锁定，CAKE 将被存放在 veCAKE 合约中，直到解锁时间到才可被提取。&#x20;

### 我可以选择部分迁移我的 CAKE 锁仓仓位吗？&#x20;

不能。&#x20;

您只能一次性迁移整个 CAKE 糖浆池锁仓仓位。

### iCAKE、bCAKE、vCAKE 和 rCAKE 会发生什么变化？

**iCAKE 产品：**&#x20;

IFO iCAKE 现已升级至支持 veCAKE。查看此文档：

{% content-ref url="../../products/ifo-initial-farm-offering/icake.md" %}
[icake.md](../../products/ifo-initial-farm-offering/icake.md)
{% endcontent-ref %}

**bCAKE 产品：**&#x20;

农场助推器 bCAKE 现已升级为支持 veCAKE。查看此文档：

{% content-ref url="../../products/yield-farming/bcake/" %}
[bcake](../../products/yield-farming/bcake/)
{% endcontent-ref %}

**vCAKE 产品**：

投票功能 vCAKE 现已升级为支持 veCAKE。查看此文档：

{% content-ref url="../../zhi-li-dai-bi-jing-ji/zhi-li-xin/ru-he-tou-piao/" %}
[ru-he-tou-piao](../../zhi-li-dai-bi-jing-ji/zhi-li-xin/ru-he-tou-piao/)
{% endcontent-ref %}

**rCAKE 产品：**&#x20;

所有 veCAKE 持有者（包括原生或迁移）将自动参与进新的收入分成池。收入分成按照既定时间表进行分配。旧的收入分成池将停止使用，用户可前往 "veCAKE 福利" 部分领取待领奖励。查看此文档：

{% content-ref url="../shou-ru-fen-cheng/" %}
[shou-ru-fen-cheng](../shou-ru-fen-cheng/)
{% endcontent-ref %}

### 多重签名钱包可用于与 veCAKE 合约交互吗？

可以。

不过，veCAKE 质押合约中针对未列入白名单的地址实施了 `noContract` 修改器。要启用质押或从 CAKE 糖浆池迁移。所有基于合约的多重签名钱包都必须执行一次性的自赋白名单操作。

如要加入白名单，请在以下任一页面操作：&#x20;

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

一个提示将会弹出。点击 "白名单"，然后多重签名钱包中继续操作上链交易。&#x20;

之后将向 veCAKE 的所有者发送一个 tx，这是一个具有 "无需许可即可写入" 功能的合约，透过它，任何合约即可执行自赋白名单操作。

如果提示没有弹出，请按照以下指示，在 [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11) 上与合约交互并上链：

```
// call:
VECakeOwner.setWhitelist(bool _status = true)

// VECakeOwner address:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### **为什么我看到了很多个 APR ? 他们代表了什么？**

锁定 CAKE 以获得 veCAKE，可围绕 PancakeSwap 构建的产品套件获得多项巨大优惠。优惠和奖励的形式和来源各不相同。因此，有多种年利率。 您可以同时获得所有优惠和奖励，因此综合年利率将是所有年利率的总和。 请注意，veCAKE 的许多其他好处无法以年度收益率的形式量化，例如农场助推器 bCAKE 或 IFO iCAKE。也请务必查看。&#x20;

锁定 CAKE 后您可以获得 veCAKE 数值。持有 veCAKE 数值可以通过 PancakeSwap 建立的一系列产品，来获得一系列多种巨大的福利。

\
Locking CAKE to get veCAKE provides a number of great benefits around the suite of products built by PancakeSwap. Benefits and incentives come in different forms and from different sources. Therefore, there are multiple APRs.

You can earn all of them concurrently therefore the combined APR will be the sum of all the APRs.

Please note that many other benefits from veCAKE can not be quantified in the format of APRs, such as [Farm Yield Booster bCAKE](https://docs.pancakeswap.finance/products/yield-farming/bcake), or [IFO iCAKE](https://docs.pancakeswap.finance/products/ifo-initial-farm-offering/icake). Be sure to check those out too.

什么是 veCAKE 奖池年利率？\
**What is veCAKE Pool APR?**

这是来自 CAKE 排放的奖励，其比率由 veCAKE Pool 表决器控制。 要增加该仪表的排放量，请查看仪表投票。\
This is the incentive coming from CAKE emissions, with its rate controlled by the veCAKE Pool voting gauge.

To increase the emission to this gauge, check out [Gauge Voting](https://docs.pancakeswap.finance/products/vecake/gauges-voting).

什么是收入共享年利率？\
**What is Revenue Sharing APR?**

这是来自协议收入共享的激励，来自 DEX 产品中收取的交换费。 查看收益分享，了解更多信息。 上一页 激励流动性\
This is the incentive coming from protocol revenue sharing, coming from swap fees collected in DEX products.

Check out [Revenue Sharing](https://docs.pancakeswap.finance/products/revenue-sharing) for more info.

[PreviousIncentivizing Liquidity](https://docs.pancakeswap.finance/products/vecake/incentivizing-liquidity)[\
](https://docs.pancakeswap.finance/products/syrup-pool)

&#x20; &#x20;
