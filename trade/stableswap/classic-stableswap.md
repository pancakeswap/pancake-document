# Classic StableSwap

Classic StableSwap 是 Curve Finance 的 AMM 在 PancakeSwap 上的一种实现。它在恒定乘积公式 (x\*y=k) 之上加入了线性不变量恒定总和曲线 (x+y=k)，以便在流动性池没有极度失衡的情况下保持价格更趋一致。因此，由于 StableSwap 仅限于价格相近的资产，无常损失就不那么令人担忧（除极端脱锚情况外），并且滑点低于仅使用恒定乘积公式的普通 AMM。

当您在 StableSwap 上进行兑换（交易）时，您将支付比普通 PancakeSwap AMM 通常的 0.25% 更低的交易手续费。手续费的分配明细如下：

* 50% 作为奖励给 LP&#x20;
* 40% 用于 CAKE 回购和销毁&#x20;
* 10% 给 PancakeSwap 国库

## Stableswap 手续费

各交易对的手续费明细见下表：

<table><thead><tr><th width="150">稳定币对</th><th width="132">交易手续费</th><th width="118.33333333333331">LP 奖励</th><th width="124">CAKE 回购</th><th>PancakeSwap 国库</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-USDT</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>HAY-BUSD</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>HAY-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>axlUSDC-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>BNBx-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>stkBNB-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr></tbody></table>

Kitchen 将逐步推出 StableSwap 交易对并修订手续费，以进一步测试和改进该产品。

## 我为什么应该使用 StableSwap 而不是普通 AMM 兑换？

* 以相同的交易步骤更高效地兑换您的稳定币或其他资产价格相近的交易对&#x20;
* 使用 StableSwap 功能，交易滑点低于普通 AMM&#x20;
* 与普通 AMM 相比，StableSwap 的交易手续费更低
