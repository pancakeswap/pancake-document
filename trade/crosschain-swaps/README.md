# 🔀 Crosschain Swaps

跨链兑换让用户能够在各条链之间无缝地兑换代币——全部都在一笔单一、流畅的交易中完成。

跨链兑换支持在以下各链之间进行：

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**交易极速——通常在几秒到一分钟内完成。**
{% endhint %}

***

### 🔍 工作原理

1. 用户选择源链/目标链（From / To chain）以及源代币/目标代币（From / To token）
2. PancakeSwap 路由计算出最高效的路由
3. 在源链和目标链上使用 PancakeSwap 的流动性池（v2、v3、Infinity、StableSwap）执行兑换
4. 桥接通过我们的合作伙伴协议处理：[Across](https://across.to/)（用于 EVM <> EVM）、[Relay](https://relay.link/bridge)（用于 SOL <> EVM）

{% hint style="success" %}
**对于在源链和目标链上都具有足够流动性的任何代币，均可进行跨链兑换。**
{% endhint %}

***

### 💸 费用

* **PancakeSwap 不对跨链交易收取任何费用。**
* 费用由以下部分构成：
  1. **交易费（Trading Fee）：** 在源链和目标链的流动性池内进行兑换时产生
  2. **桥接费（Bridge Fee）：** 支付给中继者（relayer）以桥接资产

***

### 🎯 什么是意图（Intents）？

意图（Intents）让用户能够定义其期望的结果，而无需担心如何实现。

意图示例：

* “在 Base 上将 1 ETH 兑换为 Arbitrum 上至少 3000 USDC”

如果没有意图，用户将需要手动：

* 将 ETH 桥接到 Arbitrum
* 找到一个具有最优 ETH → USDC 价格的 DEX

{% hint style="success" %}
**有了意图——系统会自动处理这一切。**
{% endhint %}

**基于意图的设计的好处：**

* 无缝的用户体验
* 更快的交易时间
* 一键、单笔交易

***

### 🔐 审计

我们已与跨链安全领域备受尊敬的机构进行了多轮审计：

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
