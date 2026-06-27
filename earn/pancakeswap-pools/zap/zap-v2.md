---
description: 只需一键即可简单地提供流动性
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### 什么是 Zap？ <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap 让提供流动性变得简单。只需一种代币、轻轻一点即可添加流动性，无需手动兑换或平衡代币。

* 仅用一种代币添加流动性：您可以仅使用交易对中的一种代币来添加流动性。Zap 将自动使用您提供的这一种代币执行兑换，并在添加流动性之前自动将交易对平衡为 50/50 的比例。
* 以不平衡数量的交易对代币添加流动性：即使您在交易对中提供的代币数量与当前资金池并不完全平衡，您也可以添加流动性。例如 30:70，这与默认的资金池权重 50:50 不同。Zap 将在添加流动性之前自动将代币重新平衡为 50/50 的比例。
* 移除流动性并选择您想要收到的代币：移除流动性时，Zap 允许您仅收到交易对中的一种代币。Zap 将在返还您的代币之前自动执行兑换。

### 启用 Zap <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

默认情况下，Zap 功能对每位用户都是开启的。如果您在添加或移除流动性时没有看到新的 Zap 界面，请在设置面板中启用它。您可以通过点击齿轮图标来调出设置面板。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
注意：目前，Zap 功能处于测试阶段（beta）。请注意，它不支持某些代币，例如带有转账手续费的代币。如果您在添加或移除流动性时遇到任何问题，请在设置面板中禁用它。
{% endhint %}

### Zap In（添加流动性） <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

访问[流动性页面](https://pancakeswap.finance/liquidity)，然后选择“Add Liquidity”（添加流动性）。

通过选择两个输入代币来挑选您想要提供流动性的交易对，查看[流动性指南](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide)了解更多。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

点击“Add Liquidity”（添加流动性）按钮以继续。

如果您正在添加流动性的交易对中的代币在您的钱包中有余额，该代币的复选框将被自动勾选。如果您的钱包中两种代币都有余额，则两个复选框都将被勾选。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### 使用一种代币 Zap <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

您可以仅使用交易对中的一种代币来添加流动性。只需勾选您希望使用的代币的那一个复选框。Zap 将在添加流动性之前自动将所勾选代币的一半兑换为交易对中的另一种代币。您将看到一条警告消息，指明哪种代币将被转换。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
如果价格影响过高，Zap 将通过滑点来保护您。点击“Reduce TOKEN”（减少 TOKEN）将其降低至首选限度。
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### 使用两种数量不平衡的代币进行 Zap <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

如果两种代币都被勾选，而输入代币的数量不符合 50/50 的比例，则将引入 Zap 平衡。您将看到一条消息“Some of your Token A will be converted to Token B”（您的部分 Token A 将被转换为 Token B）。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
如果您不希望 Zap 在添加流动性之前平衡代币数量，只需点击“Don’t Convert”（不转换）。在这种情况下，Zap 将调整输入代币的数量以符合 50/50 的比例，而不是尝试兑换和重新平衡。
{% endhint %}

### 继续进行 Zap <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

当您点击“Supply”（提供）时，Zap 的详情将会显示，并等待您确认。

您将看到：

1. 您将收到多少 LP 代币。
2. 输入代币是什么，以及您投入的代币数量。
3. 输入代币如何被交易以符合 50/50 的比例。
4. 您正在使用的滑点容差。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap out（移除流动性） <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap 还让您在移除流动性时能够收到交易对中的单一代币。

1. 访问[ ](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442758\&usg=AOvVaw2ZJPj_97-YuUMQjQbYbfN4)[流动性页面](https://pancakeswap.finance/swap#/pool)。
2. 在“Your Liquidity”（您的流动性）下点击您想要移除流动性的交易对。
3. 点击“Remove”（移除）。将出现一个新的弹窗。

在“You Will Receive”（您将收到）部分，您可以取消勾选您不想收到的代币。Zap 将在移除流动性时自动兑换并将 100% 的收益转换为所勾选的代币。

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
