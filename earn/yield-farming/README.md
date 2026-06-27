# 🚜 农场

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

农场允许用户通过质押 LP 代币来支持 PancakeSwap，同时赚取 CAKE。

查看我们的[农场使用指南](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms)，开始进行农场挖矿。

了解[如何查找农场智能合约](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
农场挖矿能带来比 Syrup 资金池更高的回报，但同时伴随着**无常损失**的风险。它并不像听起来那么可怕，但在开始之前值得先了解一下这个概念。

查看币安学院的这篇精彩的[无常损失解析文章](https://academy.binance.com/en/articles/impermanent-loss-explained)以了解更多。
{% endhint %}

## 奖励计算

农场 APR 计算包括以下两部分：

* 通过提供流动性赚取的 **LP 奖励 APR**；以及
* 通过在农场中质押 LP 代币赚取的**农场基础奖励 APR**。

为什么？因为当你在农场中质押 LP 代币以赚取 CAKE 时，你仍然在为流动性资金池提供流动性，所以你也会赚取 LP 奖励！

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

那么我们是如何计算这些数字的呢？

### 计算农场基础奖励 APR

**农场基础 APR** 根据农场倍数和农场中流动性的总额计算 —— 这就是分配给该农场的 CAKE 数量。

### 计算 LP 奖励 APR

除此之外，农场挖矿者还会因提供流动性而获得 **LP 奖励**。以下是计算 **LP 奖励**的一个示例：

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

在上面的 WBNB/BUSD 交易对中，我们看到以下数值：

**流动性：** $387.42M\
**24小时交易量：** $96.97M\
**7天交易量：** 709.73M

* 计算年度手续费
  * 使用 24 小时交易量计算资金池中流动性提供者的**手续费份额**（基于 0.17% 的交易手续费结构）：\
    $96,970,000\*0.17/100 = **$164,849**
  * 接下来，使用该**手续费份额**估算资金池预计赚取的**年度手续费**（基于当前 24 小时交易量）：\
    $164,849\*365 = **$60,169,885**
* 现在我们可以使用年度手续费来计算 **LP 奖励 APR：**即**年度手续费**除以**流动性：**\
  ($60,169,885/$387,420,000)\*100 = **15.53% LP 奖励 APR**
