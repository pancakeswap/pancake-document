# 如何使用锁仓质押糖浆池

1.跳转到糖浆池页面，点击[此处](https://pancakeswap.finance/pools)。

2.单击**连接钱包**按钮（右上角）连接到您的 BNB 智能链兼容钱包。

<figure><img src="../../../.gitbook/assets/2.png" alt=""><figcaption></figcaption></figure>

3.选择您相应的钱包并连接。

<figure><img src="../../../.gitbook/assets/3 (3).png" alt=""><figcaption></figcaption></figure>

4.选择 CAKE 糖浆池并单击**启用**按钮。 您的钱包会要求您确认操作。

<figure><img src="../../../.gitbook/assets/启用 (2).png" alt=""><figcaption></figcaption></figure>

5.**启用**按钮现在应该替换为**灵活**和**锁定**。单击按钮以调出质押菜单。

<figure><img src="../../../.gitbook/assets/Stake - before enable.png" alt=""><figcaption></figcaption></figure>

6.对于锁仓质押，只需按下 **Locked（已锁定）**，这将显示一个新窗口，输入您想要质押的 CAKE 数量以及您想要锁定 CAKE 多长时间。

在此下方，您将找到您的质押细节，包括收益率、锁定持续时间以及解锁日期和时间。 仔细检查以确保您对锁定持续时间和质押金额没有问题，单击**确认**并确认您钱包中的交易。

<figure><img src="../../../.gitbook/assets/first time lock.png" alt=""><figcaption></figcaption></figure>

请注意，我们仍在完善我们的前端显示界面，包括解锁时间的精确度细化，如有需要可能会考虑添加倒计时设计。

## 延长锁仓质押时间

在锁仓质押期间改变了主意？没问题。您可以随时通过单击 “**延长 (Extend)**” 来延长锁定 CAKE 的时间，然后选择要在初始锁仓持续时间之上延长多少时间。锁仓的时间越长，收益就会越高。锁仓期最长 365 天。

用户延长时间后新的锁仓时长 = 初始锁仓时长 + 新增时长&#x20;

每次延长需要由钱包中存入 0.0001 CAKE，这些 CAKE 将进入您的锁仓持仓中，并不是由平台收取。

如果钱包中没有足额的 CAKE，前端将显示如左图，点击图中之 “启用” 按钮，将协助您将钱包中的 BNB 兑换为 0.0001 CAKE。

如果钱包中已经有足够的 CAKE，页面将显示如右图，您可以点击 “确认” 并于钱包中确认操作，待讯息提交上链，即可更新您的锁仓持仓及剩余时间。

延長時，點擊 “最大” 将自动将目前的锁仓剩余时间，延长至最大值 365天，加成倍数（yield boost）加到最大值 21.00 倍。

<figure><img src="../../../.gitbook/assets/progress when extend lock duration-big.jpg" alt=""><figcaption><p>新版界面，每次延长锁仓收取 0.0001 CAKE<br>左图：钱包中无足额 CAKE；右图：钱包中已有足额 CAKE</p></figcaption></figure>

#### 举例说明：

&#x20;一位用户在 2022 年 5 月 7 日用 10 CAKE 质押在锁仓质押糖浆池，初始锁仓持续时间为 1 周。 2022 年 5月 8日（ 1 天后，距离解锁还剩 6 天），用户决定要增加 5 周锁仓持续时间。

1. 前往 CAKE 糖浆池，单击**延长**。

请注意，您新的锁仓持续时间 6 周将等于 1 周的初始锁仓持续时间，加上增加的 5 周新锁仓时间。也就是，您现在锁仓到期时间为 2022 年 6 月 12 日。

<figure><img src="../../../.gitbook/assets/延长1 (1).png" alt=""><figcaption></figcaption></figure>

2\.  选择您要增加的持续时长（本例中为 5 周）。

<figure><img src="../../../.gitbook/assets/延长2APR.jpg" alt=""><figcaption></figcaption></figure>

3\. 仔细检查，确保您对延长的锁仓持续时间没有问题，然后单击**确认**。

{% hint style="info" %}
请注意，您不能缩短锁仓时间，也不能提前取回您的 CAKE。
{% endhint %}



## 往锁仓仓位中添加更多 CAKE&#x20;

只需单击 “添加 CAKE (Add CAKE)” 并选择您要存入多少 CAKE。&#x20;

注意，往现有锁仓添加更多 CAKE ，会根据剩余锁仓持续时间重置您的质押期限，本质上是 “更新” 您的锁仓质押头寸。这会导致收益加成倍数 (boost 倍数) 较原先缩小，并进而影响您的收益提升倍数，因为您新添加的那部分 CAKE，锁仓剩余持续时间低于您的初始锁定持续时间。&#x20;

#### 举例说明：

&#x20;一位用户在 2022 年 5 月 7 日用 10 CAKE 质押在锁仓质押糖浆池，初始锁仓持续时间为 1 周。

2022年5月8日（1 天后，到用户的 CAKE 解锁还剩6 天），用户决定新添加 10 个 CAKE 到锁仓余额。

1. 前往 CAKE 糖浆池，单击 **添加 CAKE（Add CAKE)**。

<figure><img src="../../../.gitbook/assets/延长1.png" alt=""><figcaption></figcaption></figure>

2\.   选择添加数量（在本例中，我们添加 10 CAKE）。请注意，您的收益提升倍数（boost 倍数）低于初始收益提升倍数，因为它是使用 6 天锁仓持续时间而不是初始 1 周锁仓持续时间计算的。&#x20;

<figure><img src="../../../.gitbook/assets/添加锁定CAKE.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/添加锁定CAKE APR.jpg" alt=""><figcaption></figcaption></figure>

2.1.   或者，用户可以勾选 “更新并延长您的锁仓以保留类似收益率” 。为了保持类似的收益提升倍数，将锁仓持续时间设置为 “等于” 初始锁仓持续时间（在本例中为 1 周）。

<figure><img src="../../../.gitbook/assets/增加并延长.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/增加并延长APR.jpg" alt=""><figcaption></figcaption></figure>

3\.   仔细检查以确保您增加的 CAKE 数量和锁仓持续时间没有问题，然后单击**确认**。
