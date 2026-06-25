# Infinity CLAMM & LBAMM

#### 🔷 CLAMM（Concentrated Liquidity AMM）

CLAMM 使流动性提供者能够在**特定价格区间**内配置其资本。这带来：

* **更高的资本效率**：在活跃交易价格处提供更多流动性。
* **更深的流动性**：为交易者提供更好的执行。
* **主动的 LP 管理**：LP 需要随着价格变动调整头寸。
* 对于超出区间的头寸，**更高的无常损失**潜在风险。

{% hint style="info" %}
CLAMM 基于恒定乘积公式（X \* Y = K）运作。每个流动性头寸都是非同质化的，并以 NFT 形式表示。
{% endhint %}

#### 🔷 LBAMM（Liquidity Book AMM 或 "Bin Pool"）

LBAMM 实现了**离散的价格 bin**，每个 bin 在特定价格水平上持有流动性。LBAMM 遵循**恒定总和公式（X + Y = K）。**



**关键特征：**

* 在一个 bin 内交易**零价格影响**。
* **同质化流动性**（每个 bin 内的流动性是一个 ERC-20 代币）。
* 调整 LP 头寸时的**更低 gas 成本**。
* **支持不同的流动性形态**（如偏斜、均匀）。
* 由于每个 bin 的平缓定价曲线，更适合**低波动性**交易对。

> 🥞 **PancakeSwap 是首个提供带 hooks 的 LBAMM 资金池的协议。**

{% hint style="success" %}
CLAMM 和 LBAMM 资金池均支持 **hooks**，让开发者能够定制资金池行为。资金池类型可通过新的 Pool Managers 进行扩展，且无需重新部署协议即可添加。
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>特性</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>定价曲线</strong></td><td>恒定乘积（X * Y = K）</td><td>恒定总和（X + Y = K）</td></tr><tr><td><strong>流动性代币</strong></td><td>非同质化（NFT）</td><td>同质化（每个 bin 一个 ERC-20）</td></tr><tr><td><strong>最适合</strong></td><td>高/低波动性交易对皆可</td><td>低波动性交易对</td></tr><tr><td><strong>优势</strong></td><td><ol><li>资本效率</li><li>在宽/全区间内省 gas</li><li>广泛采用</li></ol></td><td><ol><li>bin 内零价格影响</li><li>更便宜的 LP 管理</li><li>灵活的流动性形态</li></ol></td></tr><tr><td><strong>Hook 支持</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 费用

PancakeSwap Infinity 通过静态和动态费用设置支持灵活且可扩展的费用系统。这种设置为资金池创建者和 LP 提供了强大的工具，以针对不同的交易策略和风险偏好进行优化。

#### 🔁 动态费用

* 动态费用通过 hook 合约实时确定。
* 这些费用可以基于波动性、交易量、用户状态（如 CAKE 持有量）或任何编码进 hook 的自定义逻辑等外部因素而波动。
* 采用动态费用的资金池必须在资金池创建时启用该设置，并附加一个能够通过 `beforeSwap` 修改费用的 hook。
* 资金池一经初始化，费用类型（动态或静态）即不可更改。

动态费用提供最大的灵活性，并根据市场状况为 LP 和兑换者优化费用结构。

#### 📌 静态费用

* 静态费用资金池在创建时设定一个固定费用。
* 这些费用在资金池初始化后无法更改。
* 适合更简单的用例，或费用结构的可预测性至关重要的场景。<br>

**🔒 最高费用上限：**

* CLAMM 资金池：最高可达 100%（主要用于专门或实验性用例）
* LBAMM 资金池：上限为 10%<br>

**🏛 协议费用（针对静态费用资金池）：**

* PancakeSwap 对 Infinity 资金池收取协议费用
* LP 费用的 33%，上限为 0.4%

| **LP 费用**       | **协议费用** |
| ---------------- | ---------------- |
| 1%               | 0.33%            |
| 2%               | 0.4%（上限）    |
| 动态费用资金池 | 0%               |

#### 🛠️ 资金池创建者设置说明

* 通过 PoolManager 初始化资金池时，创建者必须选择：
  * 资金池使用静态费用还是动态费用
  * 是否附加 hook 合约（动态费用必需）

这些设置是永久性的，并定义了资金池在其整个生命周期内的行为方式。
