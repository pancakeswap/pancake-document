# CAKE 代币经济 v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **释放速率** <a href="#emission-rate" id="emission-rate"></a>

### **每区块**

| **指标**                                                                   | **释放量/区块（CAKE）** | **释放量/天（CAKE）** |
| ---------------------------------------------------------------------------- | ------------------------: | ----------------------: |
| 释放量                                                                     |                        40 |               1,152,000 |
| 每周销毁 [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |                    -25.75 |                -787,600 |
| **有效释放量**                                                        |              **<14.25\*** |           **364,400\*** |

\*有效释放量实际上略低于此数值：每天还会从分配给彩票的数量中额外划出 45,000 CAKE 并销毁（PID 137 - 详情见下文）。

除上述之外，还会按 9.09% 的比例[向 Dev 地址铸造](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns)动态数量的 CAKE。这意味着，如果收获了 100 CAKE，则会额外铸造 9.09 CAKE 并发送至 Dev 地址。

{% hint style="info" %}
所有铸造到 Dev 地址的 CAKE 都会在每周销毁中被销毁，不会进入流通。&#x20;

因此，我们没有将其计入上述释放速率。
{% endhint %}

## 分配 <a href="#distribution" id="distribution"></a>

| 分配对象                | 奖励/区块（占释放量的 %） | 奖励/区块（CAKE 总量） |           奖励/天 |
| ----------------------------- | ---------------------------: | ------------------------: | -------------------: |
| 农场和彩票             |                       10.62% |                      4.25 |     122,400（约） |
| 其中被划出并销毁  |                              |                           |              -46,000 |
| 糖浆池                   |                          25% |                        10 |     288,000（约） |
| **每日 CAKE 总释放量** |                              |                           | **364,400（约）** |

## **其他通缩机制** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
目前销毁流程为手动操作。[在此查看销毁交易](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead)。
{% endhint %}

除上述之外，CAKE 还通过以下方式被销毁：

* PancakeSwap V2 上每笔交易的 **0.05%**
* 发送至 Dev 地址的 CAKE 的 **100%**
* IFO 中 CAKE 绩效费用的 **100%**
* 用于创建个人资料和铸造 NFT 的 CAKE 的 **100%**
* 农场拍卖期间竞拍所用 CAKE 的 **100%**
* 用于购买彩票门票的 CAKE 的 **20%**
* 每天 **45,000** CAKE（历史上分配给彩票）（_这部分 CAKE 由一个农场产生 - PID 137）_
* 预测市场每一轮的 **3%** 用于购买 CAKE 并销毁
* Auto CAKE Pool 中每次收益收获的 **2%**
* NFT 市场中每笔 NFT 销售额的 **2%** 用于购买 CAKE 并销毁

## 为什么 CAKE 销毁是手动的？

为了快速启动，PancakeSwap 以 MVP（最小可行产品）形式上线，MasterChef 合约每区块释放 40 CAKE。因此，早期团队没有添加诸如自定义 CAKE 铸造逻辑之类的额外功能。由于迁移到新的 MasterChef 需要耗费大量时间和精力，团队选择通过创建两个资金池，以手动销毁的方式来减少 CAKE 释放量：

* 旧彩票池（PID - 137）- 销毁来自彩票的 CAKE
* 销毁池（PID - 138）- 销毁每区块的 CAKE

这些资金池的运作方式与农场类似，主厨们可以在每次 CAKE 释放量削减投票之后，调整分配给它们的每区块 40 CAKE 的比例。

{% hint style="warning" %}
在销毁当天，主页上显示的供应量可能会突然增加数百万 CAKE。&#x20;

别担心——**这些 CAKE 实际上从未进入流通：**
{% endhint %}

这种明显的跳升只是因为分配给销毁的所有 CAKE 在一周内的存放方式所致。&#x20;

发送至 PID-137 和 PID-138 两个资金池的 CAKE 会在完成每周代币销毁之前被收获，这会使网站上显示的总供应量跳升约 600 万。这是因为待领取的 CAKE 在销毁日被收获之前不会计入总供应量。代币销毁交易完成后，这约 600 万会显示在“已销毁总量”中。&#x20;

## 如何自行确认 CAKE 供应量

要确认 PancakeSwap 主页上显示的 CAKE 流通供应量是否正确，&#x20;

1. 前往 BscScan 上的 CAKE 代币合约，[查看销毁地址持有多少 CAKE。](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances)这就是已被销毁的 CAKE 总量（永久退出流通，且永远无法取回）。
2. 然后，从 BscScan 显示的“Total Supply”中减去这个已销毁数量。
3. 得到的就是实际的 CAKE 供应量。



#### **请在下一页阅读更多关于 CAKE 通缩机制的内容。** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
