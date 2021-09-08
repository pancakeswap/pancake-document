# 🚜 流动性挖矿

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-McQraJG25bEh9ufOHLT%2F-McS-Rk4u3IqogZhr2N2%2Fdocs%20masthead%20%281%29.png?alt=media&token=0124644e-2c34-492d-bd66-2710c4dd8869)

流动性挖矿让用户们通过质押 LP 代币（流动性凭证）来支持 PancakeSwap 并赚取 CAKE 代币。

查看 [如何使用农场指南](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) 立刻开始流动性挖矿。

请同时查阅 [如何找到农场智能合约](https://docs.pancakeswap.finance/products/yield-farming)

{% hint style="warning" %}
流动性挖矿与糖浆池相比，会给予更高的奖励，但同时它们拥有**无常损失**带来的风险。它并没有听起来那么可怕，但在开始挖矿前，适当的去了解它是值得的。

查看这一篇来自币安的， [关于无常损失的文章](https://academy.binance.com/en/articles/impermanent-loss-explained) 来了解更多。
{% endhint %}

## 奖励计算

流动性挖矿的年化利率包括两大部分：提供流动性得到的奖励，以及将 LP 代币（流动性凭证）质押到农场获得的奖励。

在此之前，提供流动性，从交易手续费中获得的奖励，并没有计算在农场年化利率上。

以下是一个使用 [pancakeswap.info](https://pancakeswap.info) 计算年化利率的例子。

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

上图中展示的是 WBNB/BUSD 交易对，其中我们看到以下信息：

**流动性：**$387.42M  
**交易量 24H:** $96.97M  
**交易量 7D:** 709.73M

若要计算年化利率，我们先使用 24 小时内交易量，即 $96,970,000 ，结合 0.17% 的费率，计算出给予流动性提供者的手续费分成：  
\[**$96,970,000\*0.17/100 = $164,849\]**

下一步，我们用上述 24 小时数据，估算出全年的手续费收入：   
\[**$164,849\*365 = $60,169,885**\]

现在，我们可以使用全年手续费收入，除以流动性总额，来计算手续费这一部分的年化利率：  
\[\(**$60,169,885/$387,420,000\)\*100 = 15.53%**\]

得到这个年化利率后，我们即可将其 \(15.53%\) 与农场质押年化利率 \(20.08%\) 来得到最终的年化利率：  
\[**15.53%+20.08% = 35.61%**\]

##  <a id="reward-calculations"></a>

