# 🚜 农场

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-McQraJG25bEh9ufOHLT%2F-McS-Rk4u3IqogZhr2N2%2Fdocs%20masthead%20\(1\).png?alt=media\&token=0124644e-2c34-492d-bd66-2710c4dd8869)

PancakeSwap农场让用户们通过质押 LP 代币（流动性凭证）来支持 PancakeSwap 并赚取 CAKE 代币。

查看 [如何使用农场指南 ](yield-farming/ru-he-shi-yong-nong-chang.md)立刻开始流动性挖矿。

附加资讯：[如何找到农场智能合约](https://docs.pancakeswap.finance/products/yield-farming)

{% hint style="warning" %}
农场与糖浆池相比，农场拥有更高的收益，但同时它们有**无常损失**带来的风险。别担心，它并没有听起来那么可怕，但是在开始进行流动性挖矿前，值得您花些时间适当地了解它。

查看这一篇来自币安的 [关于无常损失的文章](https://academy.binance.com/en/articles/impermanent-loss-explained) 以了解更多。
{% endhint %}

## 奖励计算

农场的年化利率（APR）由 2 部分组成：

* 提供流动性得到的奖励（从交易手续费中获得的奖励）
* 将 LP 代币（流动性凭证）质押到农场获得的 CAKE 奖励。

为什么有 2 部分？ 因为当您在农场中质押您的 LP 代币以赚取 CAKE 时，您仍在为流动性池提供流动性，因此您也可以同时获得 LP 手续费奖励！

<figure><img src="../.gitbook/assets/APR解释 (1).png" alt=""><figcaption><p>年化利率=基准年华利率+LP 奖励利率</p></figcaption></figure>

### 农场基准年化利率 APR

农场**基准年化利率 APR** ，是根据该农场的 CAKE 权重（multiplier，又翻译成倍数），和目前质押于农场中的流动性总金额，两者一起计算得出。

此处 APR 单指分配给这个农场的 CAKE 奖励，不含流动性提供者的LP 奖励。

{% hint style="info" %}
CAKE 权重：决定有多少比重的 CAKE 分配给此农场。少用，一般看 APR 即可。

一旦农场 CAKE 权重为 0x，农场将下架进入 “finished（已完成）" 区 ，期间您仍然可以领取交易手续费奖励。

农场 CAKE 权重修改均需经由社区投票同意后才会实施变更。
{% endhint %}

### LP 奖励 APR

除此以外，流动性提供者因提供流动性而获得 LP 奖励。 以下是计算 LP 奖励的示例：

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1\_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq\_cfiBriKcl)

上图中展示的是 WBNB/BUSD 交易对，其中我们看到以下信息：

**流动性：**$387.42M\
**24小时交易量:** $96.97M\
**7天交易量:** 709.73M

若要计算年化利率，我们先使用 24 小时交易量，即 $96,970,000 ，结合 0.17% 的费率，计算出给予流动性提供者的手续费分成：\
\[**$96,970,000\*0.17/100 = $164,849]**

下一步，我们用上述 24 小时数据，估算出全年的手续费收入： \
\[**$164,849\*365 = $60,169,885**]

现在，我们可以使用全年手续费收入，除以流动性总额，来计算手续费这一部分的年化利率：\
\[(**$60,169,885/$387,420,000)\*100 = 15.53%**]
