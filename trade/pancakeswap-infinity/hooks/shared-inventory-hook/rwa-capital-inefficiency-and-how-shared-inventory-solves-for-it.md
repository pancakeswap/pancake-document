---
description: '2026-09-04'
---

# RWA 资金效率低下，以及共享库存如何解决

PancakeSwap 案例研究实验（第 1 部分：背景设定）

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

这是两部分案例研究的第一部分。在这一部分中，我们将阐述 RWA 资产发行方面临的真实资金效率问题，介绍 PancakeSwap 的 Shared Inventory Hook（SIH）旨在如何解决这一问题，并介绍一项使用链上数据对其进行检验的实时案例研究实验。

在接下来的几周内，我们将发布第 2 部分：实验结果。

***

### 🧩 什么是资金效率问题？

RWA 行业钟爱一个数字：**已经代币化了多少。** 几乎每份报告都以它作为头条——一个新的资产类别到来，发行了数十亿美元，增长达数百个百分点。

不过还有第二个数字被埋没了，它可能是更重要的信号：**其中到底有多少可以真正被交易？**

这两个数字之间的差距，才是问题的关键。在权威追踪平台 [rwa.xyz](http://rwa.xyz) 上，链上_所代表_的价值远远超过任意时刻可供_成交_的价值——数据显示，锁定、参考和分发的价值比可交易订单簿中的价值**高出一个数量级以上。**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_来源：app.rwa.xyz/stocks_

对 RWA 发行方来说，这就是陷阱所在。将股票、ETF 或国债代币化很容易——难的是让它们以紧密且可靠的价差交易，而资金效率的成败正取决于此。最终目标是让交易者能够轻松、低成本地_真正交易_这些代币化资产——成交量和手续费归根结底都来源于此。

这也正是它特别属于_资金效率_问题，而不仅仅是流动性问题的原因。

#### 每个报价的资金池都需要自己专属的一笔 USDT

要让一个 RWA 交易对在传统集中流动性（CLAMM）资金池中可交易，发行方需要有专门的计价资产——USDT——放在那里，供买家卖出时对接。上线十个交易对，CLAMM 模式就需要**十笔独立的 USDT 资金**，每个交易对一笔，彼此无法互相支持。于是计价资金被切碎成一个个专属的孤岛。

我们在自己的账面上做了测算。我们选取了 **PancakeSwap 上线的 7 个代币化股票资金池**（每个都运行传统的 V3 CLAMM 资金池），并提取了其中的专属 USDT。

快照时间：**2026 年 9 月 2 日。**

<table data-search="false"><thead><tr><th>交易对</th><th>资金池中的专属 USDT</th><th>资金池 TVL</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>总计</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

也就是说，**约 $745k 的 USDT 被专属占用。**

而这还只是有订单簿的那些代币。

SNXXB、KORUB、SOXSB 和 DJTB 根本没有 CLAMM USDT 订单簿——已经代币化，却难以交易。

***

### 🎯 发行方应该优化什么？

抛开具体机制，RWA 发行方的核心必须解决三件事：

1. **让自己的资产真正且高效地可交易** —— 每一种资产都有紧密的报价，而不仅仅是旗舰代币。
2. **为此占用尽可能少的资金** —— 计价资产成本高昂；专属地为十笔 USDT 提供资金并不高效。
3. **不必运营交易台 —** 发行资产，而无需每天运营流动性基础设施。

所以问题在于，流动性能否以不同的方式来构建——这正是 PancakeSwap 的 Shared Inventory Hook 的设计目标。

***

### 🥞 Shared Inventory Hook（SIH）

**SIH 是一个 PancakeSwap Infinity 的 Hook，让 RWA 发行方可以用一个共享的 USDT 资金池为多个交易对提供支持，而不是每个交易对各用一笔专属资金。**

SIH 通过即时（just-in-time）提供流动性来做到这一点，从而实现：

* 交易对报价更深
* 价格影响更低，尤其是在大额交易中
* 为 RWA 发行方释放资金，因为用更少的资金就能为更多交易对报价

让我们看看这些说法在实践中的表现。

截至同一个 **2026 年 9 月 2 日**快照，SIH 在单个 Hook 中持有 **$635,028** 的库存，用 **$180,467** 的共享 USDT 为 **11 个交易对**报价，利用率达 **87.7%**。借此，SIH 已处理 **17,299 笔交易，共计 $3.56M。**

也就是说，**一份约 $700k 的共享 USDT 余额为约 11 个交易对报价，而约 $745k 却只能为 7 个交易对报价**。

同样的工作，只是设计上不再重复占用资金。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

对照发行方所关心的方面：

* 传统上需要 N 笔专属 USDT 余额 → ✅ SIH 只需一个共享资金池
* 已发行但无法交易 → ✅ 可交易\
  共享库存围绕实时价格即时注入，意味着没有 V3 USDT 订单簿的代币也能获得报价，而不仅仅是被铸造出来。
* 运营交易台 → ✅ 一个获授权的运营方\
  发行方提供库存；Hook 及其运营方负责报价。

***

### 🔬 试用共享库存模拟器

通过我们的交互式对比工具，直观了解 SIH 的运作方式 **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

这是 SIH 与传统 CLAMM 订单簿之间的**高层次、标准化对比**——双方保持多项现实因素不变，以便清晰地分离出资金效率机制。它是用于理解的模型，而不是损益表。

共有三个标签页：

* **Simulator 标签页** - 调整库存、区间宽度和交易流量，查看在不同条件下 SIH _将会_如何相对于可比的 CLAMM 资金池表现。
* **Comparison 标签页** - 将 SIH 与同一批资金池上的 **PancakeSwap V3 CLAMM** 订单簿直接对比，让你并排看到共享 USDT 池与专属 USDT 在投入资金和覆盖范围上的差异。
* **Live data 标签页** — 衡量 SIH 当前_实际_的表现，数据来自支撑本研究的链上查询。

该模拟器旨在帮助展示 Shared Inventory Hook 的运作方式。先试一试，然后对照我们在接下来几周发布的真实结果进行衡量。

***

### 🧪 实验

在**接下来的几周**里，我们将实时运行 SIH，并使用链上数据来检验上述资金效率的说法。每周我们都会发布有关 SIH 表现及其架构的新资讯。

**研究中的实时 RWA 交易对：** CRCLB、MUB、GMEB、SNDKB、SPYB、SOXLB、SOXSB、DRAMB、SNXXB、KORUB、DJTB。

_注：SNXXB、KORUB、SOXSB 和 DJTB 完全没有传统的 CLAMM 订单簿。_

**我们将在接下来的几周内于 PancakeSwap 的** [**Twitter**](https://x.com/PancakeSwap) **上发布结果。**

发布的结果将涵盖：

* **完整的表现数据集 -** 未来几周内的全部 SIH 数据，整合成一幅完整的图景。
* **资金配置问题 -** SIH 实际为 RWA 发行方节省了多少资金。
* **达标 / 未达标 -** SIH 在哪些方面超出预期，又在哪些方面仍需改进。
* **结论 -** 对 SIH 在 RWA 资金效率方面究竟有多有效作出的有据结论。

_关于数据的说明：此处的数字来自实时链上查询和公开的交易对数据，并已在行文中注明出处。部分对比使用了不同的时间窗口，我们已作标注——本研究旨在做同口径的对比，而这篇介绍只能提出问题。_

***

### 想在你的资产上启用 SIH 吗？

如果你是 RWA 发行方，并且厌倦了为每个报价的资金池单独提供一笔 USDT，那么这就是为你准备的。

我们正在接纳 RWA 发行方。请填写这份 Google 表单，我们会带你了解如何让你的资产在 SIH 上获得报价 - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

感谢阅读！关注我们的 [X](https://x.com/PancakeSwap) 获取最新动态，并加入 [Telegram](https://t.me/PancakeSwap) 和 [Discord](https://discord.gg/pancakeswap) 的讨论。

让我们一起构建，\
The Chefs 🥞

***

_免责声明：本内容仅供一般信息和教育目的，不应被视为财务、法律或其他专业建议。数字资产价格可能波动。你的投资价值可能下降，也可能上升。_
