# 智能路由 (V2)

<figure><img src="../../../.gitbook/assets/Smart Router.png" alt=""><figcaption></figcaption></figure>

PancakeSwap 智能路由是一种连接 BNB 链上的 AMM 和稳定币兑换，以及以太链上的 AMM 和做市商的路由算法，其目的是为用户提供更好的流动性和价格。它使用一种智能订单路由算法，在多个资金池中执行交易，为交易者找到最佳价格。想要了解关于 StableSwap 的更多信息，请点击[此处](../wen-ding-bi-dui-huan/)。关于做市商整合的更多信息，请点击[此处](../zuo-shi-shang-zheng-he.md)。&#x20;

厨房将逐步推出更多稳定币交易对，以进一步测试和改进该产品。

## 为什么我应该通过智能路由来经由 AMM 兑换？

* 同样的交易步骤下，能以更低损耗兑换您的稳定币或其他资产价格相近的代币对。&#x20;
* 通过做市商进行兑换，他们有时能够执行比通过正常 PancakeSwap AMM 兑换更划算的交易。
* 通过稳定币兑换功能，交易滑点比普通的 AMM 兑换更低。&#x20;
* 稳定币兑换的交易费用比普通的 AMM 兑换更低。

## 以下更新正在烹饪中&#x20;

* 输出部分的用户界面优化。&#x20;
* 为了更高效的交易拆分交易路线。例如，路由将 50%的交易对发送到不同的路径以节省费用，这取决于交易的规模和流动性情况。&#x20;