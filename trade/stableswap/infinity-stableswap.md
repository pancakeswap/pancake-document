# Infinity StableSwap

### 概述

Infinity StableSwap 是 [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) 中的一种池类型，专为兑换应以相近价格交易的资产而优化——例如稳定币（如 USDC/USDT）或紧密锚定的资产（如包装代币对、流动性质押代币和流动性再质押代币）。

它由运行在 Infinity 架构上的 StableSwap hook 提供支持，灵感来自 Curve 的 StableSwap NG 设计。它目前在 BNB Chain 上可用，并计划在未来扩展到更多链。

***

### 工作原理

Infinity StableSwap 使用稳定不变量曲线——一种介于恒定总和与恒定乘积之间的混合曲线：

* 接近锚定点 → 曲线表现接近恒定总和，使得在 1:1 附近的交易滑点非常低。
* 远离锚定点 → 曲线逐渐过渡到恒定乘积，这有助于恢复平衡，并在出现大幅失衡或脱锚事件时保护池。

这使得它对于紧密定价和低滑点最为重要的稳定币对尤其有效。

***

### 主要特性

针对近锚定兑换优化：对于预期以大致相同价格交易的资产之间的交易，滑点较低。

简单的流动性提供：流动性提供者 (LP) 按比例存入两种代币，无需选择或管理价格区间——这与 CLAMM 池不同。

ERC-20 LP 代币：你的 LP 头寸以标准 ERC-20 代币表示，使其易于与收益计划、积分活动和其他 DeFi 协议配合使用。

动态手续费：手续费可根据池的平衡状况进行调整，奖励有助于将池恢复至均衡的交易，并抑制加剧失衡的交易。

Infinity 路由支持：当 StableSwap 池能提供最优价格时，交易会自动通过这些池路由——交易者无需任何额外步骤。

可调整的放大系数 (A) 参数：池运营者可以随时间逐步调高或调低 A 参数，以适应不断变化的市场状况，并设有防止突变的安全保障。

***

### 池参数

StableSwap 池的行为由一小组参数控制，这些参数通常在池创建时设定。

#### 放大系数 (A)

A 参数控制池紧贴 1:1 价格锚定点的程度。

| A 值     | 效果                                                                            |
| -------- | ------------------------------------------------------------------------------ |
| 较高的 A | 围绕锚定点的曲线更紧；1:1 附近滑点更低；对失衡更敏感                              |
| 较低的 A | 曲线更宽松；行为更像标准的恒定乘积池                                              |

经验法则：对于具有强劲、可靠锚定的资产（如 USDC/USDT），使用较高的 A。对于锚定较为宽松或波动较大的资产（如某些 LST 对），使用较低的 A。

A 参数可由池运营者在指定的时间段内逐步调高或调低。变更会以渐进方式应用，并设有防止操纵或突然价格变动的安全保障。

#### 脱锚手续费乘数

一个额外的参数，当池偏离均衡时调整有效手续费。它有助于抑制会进一步加剧池失衡的交易，并使池在市场压力或脱锚事件期间更加稳健。

#### 动态手续费

每笔兑换收取的手续费，支付给流动性提供者。Infinity StableSwap 支持动态手续费——这意味着特定交易的有效手续费可能因池的当前状态而异（例如，交易是改善还是恶化平衡）。

***

### Infinity StableSwap 与 Classic StableSwap

如果你之前使用过 PancakeSwap 现有的 StableSwap，以下是变化之处——以及保持不变之处。

| <p><br></p>                 | Classic StableSwap                                        | Infinity StableSwap                                                |
| --------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------ |
| 定价曲线                    | 稳定不变量（混合恒定总和 / 恒定乘积）                      | 相同的稳定不变量曲线，相同的近锚定低滑点                            |
| ERC-20 LP 代币              | ✅ 是                                                     | ✅ 是                                                              |
| 池创建                      | 运营繁重；需要团队手动设置                                 | 无需许可——任何人都可以创建池                                       |
| 兑换手续费                  | 每对固定（例如 USDC/USDT 为 0.01%）                        | 动态手续费——根据交易对池平衡的影响进行调整                          |
| 放大系数 (A) 参数           | 静态——设定一次，无法更改                                   | 可调整——可随时间逐步调高或调低                                      |
| 脱锚手续费乘数              | ❌ 不支持                                                  | ✅ 支持——有助于在脱锚事件期间保护池                                  |
| Gas 效率                    | 标准                                                      | 改进——受益于 Infinity 的 Singleton 和 Flash Accounting             |

#### 保持不变之处

* 核心定价曲线和近锚定低滑点行为保持不变。

#### 新增和改进之处

* 无需许可的池创建：池可以无需许可地创建，无需团队手动设置。
* 动态手续费保护 LP：手续费不再是单一固定值，而是可以根据交易是有助于还是损害池平衡而逐笔调整——使池在波动状况下更具韧性。
* 可适应的 A 参数：放大系数可以随市场状况变化而随时间调整，而不是在部署时永久锁定。

***

### 常见问题解答

哪些资产适合 Infinity StableSwap？

预期以相近价格交易的资产：稳定币（USDC、USDT、BUSD 等）、同一资产的包装等价物（如 WBTC/cbBTC），以及锚定波动较低的精选流动性质押代币 / 流动性再质押代币 (LST/LRT) 对。

<br>

Infinity StableSwap 与旧版 PancakeSwap StableSwap 有何不同？

Infinity StableSwap 作为 PancakeSwap Infinity 上的一个 hook 实现，这意味着它继承了 Infinity 的所有基础设施优势，包括通过 Singleton 和 Flash Accounting 实现更低的 gas 成本，以及更灵活的手续费系统。它还支持旧版 StableSwap 未提供的新功能，例如动态手续费和可调整的放大系数。

<br>

我需要随时间管理我的头寸吗？

不需要。与 CLAMM 不同，你无需设置或调整价格区间。你的流动性始终在整条曲线上处于活跃状态，因此不存在头寸"超出区间"的风险。

<br>

我可以只用一种代币提供流动性吗？

可以，支持单代币存入。

<br>

动态手续费如何运作？

在 Infinity StableSwap 中，兑换手续费可根据交易对池平衡的影响而逐笔变化。有助于将池恢复至均衡的交易可能支付较低的有效手续费，而加剧失衡的交易可能支付较高的手续费。这旨在保护 LP 并维持更健康的池状况。



***



## 创建 Infinity StableSwap 池



Infinity StableSwap 池是无需许可的——任何人都可以创建，无需 PancakeSwap 团队批准。

<br>

### 分步操作

1\. 前往 Farm/流动性页面并点击 Create Pool。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. 从池类型选项中选择 StableSwap Pool。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. 为你的池选择代币对（例如 USDC / USDT）。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. 池参数

| 参数                  | 作用                                                                                                            |
| --------------------- | --------------------------------------------------------------------------------------------------------------- |
| 兑换手续费            | 每笔兑换收取的手续费，支付给 LP。紧密稳定币对的默认值为 0.01%。                                                   |
| A（放大系数）         | 控制曲线紧贴锚定点的程度。越高 = 1:1 附近滑点越低，但对失衡越敏感。                                               |
| 脱锚手续费乘数        | 当池偏离平衡时放大手续费，抑制加剧失衡的交易。                                                                   |
| 移动平均时间          | 用于计算移动平均价格以进行动态手续费调整的时间窗口。                                                             |

⚠️ 请谨慎设置参数。错误的参数——尤其是对锚定较为宽松的资产设置非常高的 A——可能会增加 LP 的风险。如果不确定，请使用适合你资产类型的预设，并避免更改高级设置。

<br>

选择一个池参数预设——这将自动为你的资产类型设置推荐参数。你仍可以通过高级 (Advanced) 开关手动调整它们。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| 预设                              | A    | 脱锚手续费乘数        | 移动平均时间（秒）            |
| --------------------------------- | ---- | --------------------- | ----------------------------- |
| 法币可赎回稳定币                  | 1000 | 10                    | 600                           |
| 加密抵押稳定币                    | 100  | 12.5                  | 600                           |
| 流动性再质押代币                  | 500  | 10                    | 600                           |

<br>

&#x20; 不确定该选哪个？&#x20;

* 对于像 USDC/USDT 这样的交易对，使用法币可赎回稳定币
* 对于算法或加密支持的稳定币，使用加密抵押稳定币
* 对于像 stkBNB/WBNB 这样的 LRT 对，使用流动性再质押代币。

<br>

5\. 输入存款金额以注入初始流动性。两种代币的金额必须相等（例如 1 USDC 和 1 USDT）。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. 点击 Preview Pool，查看你的设置，勾选确认框，然后点击 Create Pool。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>

