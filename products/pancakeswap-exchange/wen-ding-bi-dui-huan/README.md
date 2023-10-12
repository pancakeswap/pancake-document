# 🔄 稳定币兑换

<figure><img src="../../../.gitbook/assets/docs masthead (1) (1).png" alt=""><figcaption></figcaption></figure>

PancakeSwap 上的 StableSwap 是一项基于不变曲线滑点函数，具有较低滑点的稳定币对交易的功能。 它设计用于交换特定资产的代币对，该代币对存在某些机制使两种资产的价格相当接近——例如美元稳定币（例如 HAY、BUSD 和 USDT）或流动权益质押的质押凭证（liquid staking tokens）（例如 stkBNB 和 aBNBc）。&#x20;

稳定币兑换是 Curve Finance 的 AMM 在 PancakeSwap 上的实现。 它在恒定乘积公式 (x\*y=k) 之上添加线性不变常数和曲线 (x+y=k)，以在流动性池不是极度不平衡的情况下保持价格更加均等。 因此，由于 StableSwaps 仅限于价格逼近的资产，因此无常损失并不那么令人担忧（在极端价格脱锚情况下除外），并且滑点低于仅使用恒定乘积公式的普通 AMM。&#x20;

当您在 StableSwap 上进行代币兑换（交易）时，您将支付比普通 PancakeSwap AMM 上通常的 0.25%更低的交易手续费。费用细分如下：

* 50% 属于 LP 份额作为交易手续费收益&#x20;
* 40% 用于 CAKE 回购和销毁&#x20;
* 10% 分配给 PancakeSwap 团队金库&#x20;

## 稳定币交易费用

下表中列出了对应稳定币代币对的费用细分：

<table><thead><tr><th width="168">稳定币对</th><th width="120">交易手续费</th><th width="135.33333333333331">LP 手续费收益</th><th width="109">CAKE 回购</th><th>PancakeSwap 团队金库</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-BUSD</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>USDC-USDT</td><td>0.01%</td><td>0.005%</td><td>0.004%</td><td>0.001%</td></tr><tr><td>HAY-BUSD</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>HAY-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>axlUSDC-USDT</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>BNBx-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr><tr><td>stkBNB-WBNB</td><td>0.04%</td><td>0.02%</td><td>0.016%</td><td>0.004%</td></tr></tbody></table>

厨房将逐步推出更多的稳定币交易对，并修改费用明细，以进一步测试和改进产品。

## 为什么我应该使用稳定币兑换而不是一般的自动化做市商（AMM）兑换？&#x20;

* 相同的交易步骤下，兑换您的稳定币或其他价格相似的资产将更高效！
* 使用稳定币兑换功能，交易滑点低于仅使用恒定乘积公式的普通 AMM 。
* 与普通的 AMM 相比，交易费用也更低。

## 厨房目前仍在修复和烹饪那些功能？&#x20;

* StableSwap 和 Stable LP 的用户界面指南优化
* StableSwap 信息页面&#x20;
* 添加更多的稳定交易对，以及现有 LP 的迁移

