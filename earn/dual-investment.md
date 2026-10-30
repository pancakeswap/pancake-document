# 🍩 Dual Investment

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201%20%282%29.png" alt=""><figcaption></figcaption></figure>

Dual Investment 让你以目标价格投入资金并赚取固定奖励，无论市场最终如何结算。选择一种资产，选择你想要 **Buy Low** 还是 **Sell High**，再选择目标价格和结算日期。结算时，你会收到本金加奖励，具体以你存入的资产或按目标价格转换后的资产形式发放。

Dual Investment 已在 BNB 链上线，支持 **BTCB** 和 **BNB**，与 **USDT** 配对。

{% hint style="info" %}
Dual Investment 不是储蓄产品。根据结算价格不同，你的资金可能会按目标价格被转换为另一种资产，而该资产的价值可能低于你存入的金额。
{% endhint %}

***

## 什么是 Dual Investment？

#### **两种结果，一份固定奖励**

每个 Dual Investment 产品都有目标价格和结算日期。认购时，你的奖励会按所显示的 APR 锁定。结算时，由市场价格决定你会得到两种结果中的哪一种：

* **价格未达到你的目标。** 你取回原始资产加奖励。
* **价格达到你的目标。** 你的本金和奖励会按目标价格转换为另一种资产。

两种情况下你都能获得奖励。唯一变化的是你收到的是哪种资产。

#### **Buy Low**

如果你乐于以低于当前价格的价格买入 BTCB 或 BNB，可以使用 Buy Low。你存入 **USDT**，并选择一个低于当前价格的目标价格。

| 结算价格        | 你将收到                                                     |
| ----------------------- | --------------------------------------------------------------- |
| 等于或高于你的目标 | USDT（本金 + 奖励）                                       |
| 低于你的目标       | 按你的目标价格买入的 BTCB 或 BNB，以及你的奖励 |

#### **Sell High**

如果你乐于以高于当前价格的价格卖出 BTCB 或 BNB，可以使用 Sell High。你存入 **BTCB 或 BNB**，并选择一个高于当前价格的目标价格。

| 结算价格        | 你将收到                                            |
| ----------------------- | ------------------------------------------------------ |
| 等于或低于你的目标 | BTCB 或 BNB（本金 + 奖励）                       |
| 高于你的目标       | 按你的目标价格卖出得到的 USDT，以及你的奖励 |

#### **APR 如何运作**

APR 取决于目标价格与当前价格的接近程度以及产品的运行时长。越接近当前价格的目标，APR 越高，因为转换的可能性更大。越远的目标 APR 越低，但更有可能退还你的原始资产。

你的奖励计算公式为：

`Reward = Subscription amount × APR × (Days to settlement ÷ 365)`

#### **示例：Buy Low**

BTCB 当前价格为 $83,467。你向一个 1 天期、目标价 $82,000、APR 为 14.68% 的 Buy Low 产品认购 1,000 USDT。你的奖励约为 0.40 USDT。

| 结算价格 | 你将收到                           |
| ---------------- | ------------------------------------- |
| $82,000 或以上 | 1,000.40 USDT                         |
| 低于 $82,000    | 0.0122 BTCB（1,000.40 USDT ÷ $82,000） |

如果 BTCB 以 $78,000 结算，你仍然按 $82,000 买入。你将持有 0.0122 BTCB，价值约 951.60 USDT，低于你存入的金额。

#### **示例：Sell High**

BTCB 当前价格为 $83,467。你向一个 1 天期、目标价 $84,500、APR 为 89.28% 的 Sell High 产品认购 0.01 BTCB。你的奖励约为 0.0000245 BTCB。

| 结算价格 | 你将收到                            |
| ---------------- | -------------------------------------- |
| $84,500 或以下 | 0.0100245 BTCB                         |
| 高于 $84,500    | 847.07 USDT（0.0100245 BTCB × $84,500） |

如果 BTCB 以 $88,000 结算，你仍然按 $84,500 卖出。你将收到 847.07 USDT，而这些 BTCB 本来价值约 882 USDT。

#### **谁是对手方？**

每个产品由做市商报价，由其作为你头寸的对手方。做市商会缴纳保证金来保障你的收益支付。如果做市商违约，你的索赔将由其保证金覆盖。

***

## 如何使用 Dual Investment

#### **前往 Dual Investment 页面**

前往 [pancakeswap.finance/dual-investment](https://pancakeswap.finance/dual-investment?chain=bsc)，或点击 PancakeSwap 主导航栏中的 **Dual Investment**。

#### **1. 选择目标资产**

选择 **BTCB** 或 **BNB**。每张卡片显示当前价格，以及该资产所有产品的 APR 范围。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28407%29.png" alt=""><figcaption></figcaption></figure>

#### **2. 选择方向**

选择 **Buy Low**：存入 USDT，以较低价格买入资产；或选择 **Sell High**：存入资产，以较高价格卖出。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28430%29.png" alt=""><figcaption></figcaption></figure>

#### **3. 选择结算日期和目标价格**

使用期限筛选器（**1 Day**、**< 3 Days**、**< 7 Days** 以及更长）来缩小列表范围。产品按结算日期分组。每一行显示目标价格、与当前价格的距离以及 APR。

每个结算日期旁边的倒计时显示你还剩多少时间可以认购。认购会在结算前关闭。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28475%29.png" alt=""><figcaption></figcaption></figure>

#### **4. 输入认购金额**

点击你想要的目标上的 **Subscribe**，然后输入金额或点击 **MAX**。每个产品对单次认购设有最小和最大限额，并有固定的总额度。一旦某个目标被认购满额，就无法重新开放，因此你需要选择其他目标价格。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28476%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### **5. 检查并确认**

检查方向、目标价格、结算日期以及两种结果。&#x20;

你确认期间，该利率会保持一小段时间。如果它过期或发生变动，页面会获取新的利率，并要求你在继续之前接受。

#### **6. 领取你的收益**

结算后，点击某个头寸上的 **Claim**，或点击 **Claim all** 一次性领取所有已结算的头寸。你的收益会以结算结果所决定的资产形式发送到你的钱包。

***

## Dual Investment 常见问题解答

#### **什么是 Dual Investment？**

Dual Investment 是一种让你以目标价格投入资金并赚取固定奖励的产品。结算时，你会收到本金加奖励，形式为你的原始资产，或按目标价格转换后的另一种资产。

#### **支持哪些资产？**

BNB 链上的 BTCB 和 BNB，与 USDT 配对。

#### **Buy Low 和 Sell High 有什么区别？**

Buy Low 让你存入 USDT，并以低于当前价格的目标价格买入 BTCB 或 BNB。Sell High 让你存入 BTCB 或 BNB，并以高于当前价格的目标价格卖出。

#### **两种结果下我都能获得奖励吗？**

是的。奖励在你认购时即已固定，两种结果下都会支付。它会与你的本金一起，以你在结算时收到的资产形式发放。

#### **我可以在结算日期之前提取吗？**

不可以。一旦认购，你的资金将被锁定到结算，且认购不能取消。

#### **为什么不同产品的 APR 不同？**

越接近当前价格的目标以及越短的结算日期，通常 APR 越高，因为发生转换的概率更高。利率为实时报价，从你打开产品到确认之间可能发生变化。

#### **为什么我认购时利率变了？**

利率由做市商实时报价，且只保持很短的时间。如果利率过期、发生变动，或其他用户先成交了该价格，页面会获取新的利率，并要求你在继续之前接受。

#### **我需要领取我的收益吗？**

需要。结算后，请从 **Your Holdings** 领取你的收益。你可以逐个领取头寸，也可以使用 **Claim all**。

#### **谁是我头寸的对手方？**

做市商为每个产品报价，并作为你头寸的对手方。他们缴纳保证金来保障你的收益支付，如果做市商违约，你的索赔将由该保证金覆盖。

#### **收取哪些费用？**

免费。
