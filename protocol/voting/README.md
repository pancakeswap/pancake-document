# 📔 治理

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
作为 [Tokenomics 3.0 升级](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3) 的一部分，本页面已于 2025 年 5 月 15 日更新
{% endhint %}

投票赋予 PancakeSwap 社区发声的权利，让社区能够对 PancakeSwap 未来的发展方向发表意见。

请查看 [PancakeSwap 的原生投票门户](https://pancakeswap.finance/voting) 和我们的 [论坛](https://forum.pancakeswap.finance/) 页面。

## 投票机制

:notebook\_with\_decorative\_cover:摘要 - 变更内容（在 [Tokenomics 3.0 更新](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3) 之后）

<table><thead><tr><th width="200.6015625">治理组成部分</th><th width="218.01953125">Tokenomics 3.0 之前</th><th width="205.1796875">Tokenomics 3.0 之后</th><th>状态<select><option value="q1dVFsCri7zA" label="✅ 已变更" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 未变更" color="blue"></option></select></th></tr></thead><tbody><tr><td>投票权</td><td>1 veCAKE = 1 投票权</td><td>1 CAKE = 1 投票权</td><td><span data-option="q1dVFsCri7zA">✅ 已变更</span></td></tr><tr><td>委托</td><td>允许（通过 veCAKE 机制）</td><td>不允许委托</td><td><span data-option="q1dVFsCri7zA">✅ 已变更</span></td></tr><tr><td>提案提交门槛</td><td>Snapshot 需要 100K veCAKE</td><td>Snapshot 需要 100K CAKE</td><td><span data-option="q1dVFsCri7zA">✅ 已变更</span></td></tr><tr><td>核心提案 vs 社区提案</td><td>为每种提案类型定义了角色和目的</td><td>无变更</td><td><span data-option="4AGl26rwjYcI">🔁 未变更</span></td></tr><tr><td>投票周期</td><td>社区：固定<br>核心：可变</td><td>无变更</td><td><span data-option="4AGl26rwjYcI">🔁 未变更</span></td></tr><tr><td>Snapshot 时间</td><td>在提案发布的区块</td><td>无变更</td><td><span data-option="4AGl26rwjYcI">🔁 未变更</span></td></tr><tr><td>法定人数</td><td>无最低法定人数</td><td>无变更</td><td><span data-option="4AGl26rwjYcI">🔁 未变更</span></td></tr></tbody></table>

### 1. **投票权（已变更）**

* **所有 CAKE 持有者均拥有直接投票权。**
* **投票权直接对应于快照时钱包地址中持有的 CAKE 数量**
  * **1 CAKE = 1 投票权**
  * **质押在 Syrup Pools 中的 CAKE 不计入** 你的投票权，因为在快照时它不属于你的钱包余额
  * 快照余额 = 提案发布的同一区块
* **不再支持委托。** 每位 CAKE 持有者都必须单独投票。

### 2. **提案提交（未变更）**

* **如何提交提案**
  * 在 [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create) 提交
  * 必须包含：
    * 标题
    * 内容
    * 描述
    * 链上操作（如有需要）
    * 投票时长
* 提案类型
  1.  核心提案

      * 只能由 **PancakeSwap 核心团队**提出。
      * 需要 CAKE 持有者投票。
      * 如果通过，将由 PancakeSwap 团队实施。

      示例

      1. 协议调整（产品变更、手续费变更）
      2. 此前提案未涵盖的、对生态系统增长资金的重大使用
  2. 社区提案
     * **社区**提案由 PancakeSwap 社区发布。这些提案用于提出想法并表达社区的观点。它们是来自社区的**非约束性建议**。
     * 任何持有 **100,000 CAKE（快照余额）**的人都可以提交。
     * PancakeSwap 团队可能会将优秀的提案采纳进未来的核心提案
     * 社区成员还可以利用我们的 [论坛](https://forum.pancakeswap.finance/) 提供反馈并向协议提出建议。

### **3. 投票时长（未变更）**

* 所有 CAKE 持有者均可在每项提案的**投票窗口期内**投票。
  * 社区提案：固定为 3 天
  * 核心提案：可变，由 PancakeSwap 设定
* 你的投票权由**提案发布时区块的 CAKE 余额快照**决定。
* **在提案发布后增加更多 CAKE 不会提高你在该特定投票中的投票权。**

如需完整详情，请参阅 [投票指南](https://docs.pancakeswap.finance/protocol/voting/voting-guide)。

### **4. 投票结果（未变更）**

* 结果基于**投出的总票数**（用于投票的 CAKE 总量）
* **目前提案通过没有最低法定人数要求。**

## 注意：否决权

为保护协议，**PancakeSwap 核心团队保留在关键情况下进行干预的权利**——例如安全威胁或影响平台稳定运行的问题——**无需社区投票或 Snapshot 投票**。

在任何采取否决行动的情况下，核心团队都将**公开分享对该决定的清晰解释**。

**可能的否决行动包括：**

1. **临时暂停智能合约**以修复紧急错误或漏洞。
