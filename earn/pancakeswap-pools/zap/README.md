---
description: 一键添加流动性
---

# Zap

### 什么是 Zap <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap 是一项让您轻松添加流动性的功能。借助 Zap，无论资金池中所需的代币是什么，您都可以使用任何您持有余额的代币来提供流动性。只需设置价格区间，选择要提供的金额，然后执行即可。您的代币将以最高效的方式自动进行平衡以构成流动性头寸，同时以最低的价格影响和滑点进行交易。

### 支持的链

* v3 - BNB Chain 上的所有资金池，Ethereum 和 Arbitrum 网络上的精选资金池
* Infinity - BNB Chain 上的所有 CLAMM 资金池（无 hook）

### 如何使用 <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

目前，Zap 支持：

* 🆕 任何代币！
* 使用单一代币
* 🆕 使用两种代币
* 🆕 或者……使用多种代币（是的，它可以像灰尘收集器一样使用）

#### 开始 <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="../../../.gitbook/assets/image (3) (2).png" alt=""><figcaption></figcaption></figure>

要使用 Zap，只需前往添加流动性页面，选择您想要提供流动性的交易对、手续费等级以及价格区间。

然后选择您想要提供流动性的代币数量。

当一种或多种代币余额不足时，Zap 选项将自动出现。

点击该链接以调出 Zap 弹窗。

#### 发起 Zap <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

在新的“Zap in”弹窗中，您可以找到以下字段：

1. 您正在 Zap（提供流动性）的交易对。
2. 存入的代币及存入金额。您可以自由地为 Zap 添加或移除任何代币。
3. 新头寸的价格区间。您也可以点击箭头在不同的价格显示之间切换。
4. Zap 功能将如何处理您的存入代币的详细明细。
5. 统计数据摘要，包括：
   1. 新流动性头寸的预估美元价值。
   2. 新流动性头寸中的预估代币数量。
   3. Zap 后剩余资金的预估美元价值。在大多数情况下应为 0。如果流动性资金池或代币的流动性非常少，此数值可能会增加。
   4. Zap 过程中代币兑换和再平衡的价格影响。
   5. 添加流动性和构建头寸的价格影响。
   6. Zap 手续费。根据流动性对的不同，手续费率可能有所不同。

{% hint style="warning" %}
请注意，您可能需要根据您的可用余额重新配置要 Zap 的金额。如果您没有其中一种代币的余额，请移除它们。
{% endhint %}

{% hint style="info" %}
您可能会注意到，“Add V3 Liquidity”（添加 V3 流动性）中的设置会自动带入 Zap 弹窗，包括存入金额和价格区间设置。
{% endhint %}

#### 开始 Zap <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="../../../.gitbook/assets/image (2) (2).png" alt="" width="375"><figcaption></figcaption></figure>

最后点击“Approve”（批准），并在钱包弹窗中确认代币授权额度。

然后，点击“Preview”（预览）以调出最终确认弹窗。在继续之前，请仔细查看最终确认弹窗中显示的所有统计数据和预估值，尤其是影响数值和最大滑点。

最后，点击“Add Liquidity”（添加流动性）并在您的钱包弹窗中确认。

交易确认后，您应能在“My Position”（我的头寸）页面看到您崭新的头寸。

<figure><img src="../../../.gitbook/assets/image (3) (2) (1).png" alt="" width="375"><figcaption></figcaption></figure>

#### 更多设置 <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="../../../.gitbook/assets/image (4).png" alt="" width="375"><figcaption></figcaption></figure>

如果您想进一步自定义您的 Zap 体验，只需点击右上角的齿轮图标。在设置中，您可以配置：

* Zap 过程中的最大滑点。
* 交易截止时间的时限。
* 是否使用 KyberSwap 的聚合流动性来执行代币再平衡。如果您只想在 PancakeSwap Pools 中交易，请关闭此选项。
* Degen 模式可用于执行超高滑点的 Zap。不建议在正常使用场景中使用，使用风险自负。

{% hint style="warning" %}
请注意，滑点和截止时间设置独立于兑换（Swap）和流动性页面。
{% endhint %}

#### 使用两种代币 Zap in

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1).png" alt="" width="375"><figcaption></figcaption></figure>

现在您可以使用两种代币 Zap in 您的流动性。当您的可用余额与价格设置以及所需的代币数量和比例不匹配时，这非常有用。只需 Zap，比例将自动重新平衡。

#### 使用多种代币 Zap in

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt="" width="375"><figcaption></figcaption></figure>

是的，它的运作方式就像一个灰尘代币收集器。它适合清理您钱包中的小额余额，并将它们投入一个头寸中，开始从交易手续费中赚取收益。&#x20;
