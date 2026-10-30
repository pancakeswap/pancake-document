---
description: '2026-08-21'
---

# Shared Inventory Hook 介绍

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

为五个交易对报价,不该花五倍的资金。但在链上,每个资产发行方面对的却是这样的局面:流动性与每个交易对绑定,因此每新增一个交易对,就要再投入一大笔资金——其中大部分只是闲置着,直到恰好该交易对在恰好的价格区间内成交才能赚取收益。每当你想为新的交易对报价,就得向其中注入新的流动性——这些资金随后被锁定在这一个交易对上,无法用于其他任何地方。

Shared Inventory Hook(SIH)打破了这种绑定。它是 PancakeSwap Infinity 上最新的 Hook,也是首个专为资金效率而构建的 Hook。

_💡 回顾:Hook 是一种智能合约(类似附加组件),接入 Infinity 资金池,并在兑换过程中运行自定义逻辑——无需另建新的交易场所。_

那么它是如何运作的?

RWA 资产发行方无需在每个资金池中各锁定一份资金,只需注入**一份共享库存**,Shared Inventory Hook 便会从中向任何正在交易的交易对提供深度报价——即时(just-in-time),恰好在兑换发生的那一刻。可以把它想象成一个库房供应厨房里的每一道菜,而不是每道菜各配一个库房。一份余额,发挥多份余额的作用。

正是这一转变让 SIH 具备了资金效率,具体体现在三个方面:

* **资金保持活跃、持续运转。** Hook 库存中的流动性在兑换时即时注入,因此始终在运转并为你赚取手续费,而不是闲置不动。
* **一份余额,在多个交易对中获得手续费收益。** 一份库存可在其服务的所有交易对中赚取收益,因此你只需投入少得多的资金,就能捕获手续费流量。
* **更低的价格影响。** 由于兑换时提供报价的流动性更深,只要 SIH 提供最优价格,大额交易的价格影响就会更低。
* **更高的资金效率。** 一次注入资金,同一份资金即可为每个启用 SIH 的交易对提供深度。此外,你无需追加资金,就能为新的交易对启用 SIH。

> \*\*已经心动了?以资金高效的方式把你的资产带上链——填写此表单 → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**链上数据为证**

SIH 于今年 8 月随 bStocks 上线,最重要的指标是这些资金的运转效率有多高。根据最新的 Hook 快照(2026 年 8 月 21 日),共享库存的 75% 已在三个交易对中被实际部署(Hook 库存约 $297K,活跃约 $224K)。在 CRCLB 和 MUB 这两个成熟的交易对上,利用率约为 99%(98.96% / 98.95%)。在传统 V3 CLAMM 资金池中会闲置的资金,在这里都处于区间内并持续报价。

在上线最初的几周(截至 8 月 21 日),这三个交易对共成交约 $710K,共 5,713 笔兑换——由约 $297K 的共享库存提供服务,并以 0.25% 费率档位赚取 LP 手续费。

_**数据来源:** 内部 Dune 看板_ **在线资金池:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**未来走向**

这一模式为规模化而设计——更多交易对,一份共享余额覆盖数千个全天候(24/7)交易的市场。这是我们见过的、将一个代币的全部交易对阵容搬上链,同时又不必成倍增加背后资金的最快路径。

在线的 SIH 资金池位于 [PancakeSwap Earn 页面](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001)——打开 **Infinity**,在资金池特性下查找 **Shared Inventory**。SIH 目前已在 CRCLB / USDT、MUB / USDT 和 GMEB / USDT 上启用。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_注意:散户 LP 已经可以通过 Earn 向这些资金池添加流动性——该存款将成为资金池的常驻流动性,与共享库存分开持有。_

_**重要提示:**_

_由于库存仅在兑换发生的瞬间投入使用,SIH 相比标准 LP 头寸受价格漂移的影响更小,但并非没有风险。运营方仍持有随市场波动的库存。与任何链上策略一样,结果取决于交易量、库存、对冲和市场状况。_

准备好最大化资金效率了吗?立即让你的代币交易对启用 SIH → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, The Chefs 🥞

***

_免责声明:本内容仅供一般信息和教育用途,不应被视为财务、法律或其他专业建议。数字资产价格可能波动。你的投资价值可能下跌,也可能上涨。_
