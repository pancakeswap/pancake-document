# Hooks

{% hint style="info" %}
如果你是开发者或正在寻找有关开发 hook 的详细技术文档，请访问[此处](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook)。
{% endhint %}

Hooks 是强大的附加组件，让开发者能够扩展和定制 PancakeSwap Infinity 中流动性资金池的行为。可以将它们视为为流动性资金池添加新功能的 "插件" 或 "小工具"。

#### 🔍 什么是 Hooks？

* Hooks 是由任何人——开发者、协议或社区成员——创建的外部智能合约，并附加到流动性资金池上以增强或修改其行为。
* 每个资金池只能附加一个 hook，但单个 hook 可以服务于多个资金池。
* Hooks 可以在关键操作前后运行自定义代码，例如：
  * 初始化资金池
  * 兑换
  * 添加/移除流动性
  * 捐赠<br>

**⛓️ Hooks 的工作方式：**

* Hook 在资金池创建时选定，之后无法更改。
* Hook 合约在特定操作（兑换、添加流动性等）时触发，并按合约内定义在这些操作前后执行逻辑。
* 例如，一个 hook 可以：
  * 为 CAKE 持有者提供兑换费用折扣
  * 收取自定义费用并分发奖励
  * 启用诸如 stableswap 或 TWAMM 式订单等新的兑换逻辑<br>

#### ⚙️ Hook 回调

Hooks 可以在十个特定时刻被触发。开发者可以选择他们想要实现哪些：

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

这些使得通过 hooks 实现高度可定制和模块化的行为成为可能。

#### 🔧 两种类型的 Hooks

**类型 1：无需授权**

这些 hooks 自动运行，无需用户许可。它们由兑换或流动性变更等操作触发。



示例：

* 动态费用：根据市场波动性调整兑换费用
* 费用回扣：为持有 CAKE 或交易量大的用户提供折扣



示例流程（CAKE 费用折扣）：

1. 用户发起一次兑换。
2. Hook 通过 `beforeSwap` hook 回调检查其 CAKE 余额。
3. 如果用户持有的 CAKE 达到定义的阈值，他们将获得资金池费用的 50% 折扣。
4. 交易的其余部分照常进行。<br>

{% hint style="success" %}
这些 hooks 不需要特殊的 UI 或额外的交互。其好处会自动应用。
{% endhint %}

**类型 2：需要用户授权**

这些 hooks 需要用户直接与之交互、提供授权，并且可能需要转移资金，通常用于创建或管理头寸。



示例：

* 限价单：仅在达到目标价格时执行兑换。
* TWAMM：将大额订单拆分为较小的部分以获得更好的执行。
* 主动流动性管理：自动管理 LP 头寸以获得最佳回报。



示例流程（限价单 Hook）：

1. 用户直接与 hook 合约交互（而非通常的兑换 UI）。
2. 他们输入诸如限价、代币对、数量等详情。
3. Hook 签发一个代表该订单的凭证代币。
4. 之后，当资金池价格达到目标时，hook 使用 afterSwap 执行该订单。
5. 用户可以归还凭证代币以领取已兑换的资产。

{% hint style="info" %}
这些 hooks 通常需要自定义 UI，并且用户必须信任并批准 hook 合约持有他们的资金。
{% endhint %}

#### 🚀 用例与创新

Hooks 解锁了无限可能，包括：

* 自定义 AMM（如稳定币曲线）
* 流动性挖矿奖励
* 自动化交易策略、流动性管理
* 链上限价单及其他订单类型
* 动态定价和费用调整
* 增强收益的 LP 策略<br>

借助 hooks，开发者可以利用 PancakeSwap Infinity 现有的基础设施构建全新的 DeFi 体验——加快开发速度并降低成本。
