# 代币兑换

![](../../.gitbook/assets/swap-trade-header.png)

PancakeSwap 上的[**代币兑换**](https://pancakeswap.finance/swap)是一种简单的方式，可通过 BNB Smart Chain、Ethereum 和 Aptos 上的自动流动性池将一种代币兑换为另一种代币，在 BNB Smart Chain 和 Ethereum 上交易代币时还可通过 Market Maker 进行。

![](<../../.gitbook/assets/image (53).png>)

当您在 [BNB Smart Chain](https://pancakeswap.finance/swap?chain=bsc) 或 [Ethereum](https://pancakeswap.finance/swap?chain=eth) PancakeSwap Exchange 上进行代币兑换（交易）时，您将根据交易路由所经过的流动性池类型支付交易手续费。您可以通过点击 “Route” 部分中的放大镜图标来查看路由详情。

对于 Exchange V3 流动性池，目前有四个不同的费率档位：0.01%、0.05%、0.25% 和 1%。

对于 StableSwap 流动性池，费率取决于各个池的配置。详情请查看 “Fee” 部分。

对于 Exchange V2 流动性池，将收取固定的 0.25% 交易手续费，其分配如下：

* **0.17%** - 以手续费奖励的形式返还给流动性池中的流动性提供者。
* **0.0225%** - 发送至 PancakeSwap 国库。
* **0.0575%** - 用于 CAKE 回购和销毁。

![](<../../.gitbook/assets/image (277).png>)

请注意，在 [Aptos](https://aptos.pancakeswap.finance/swap) 上仅部署了 PancakeSwap Exchange V2，因此 Aptos 上的所有代币兑换都将收取固定的 0.25% 交易手续费，其分配方式与上述相同。
