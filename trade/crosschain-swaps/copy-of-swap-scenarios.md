---
hidden: true
---

# 🔁 Copy of Swap Scenarios

跨链交易有 4 种情形。

#### 1️⃣ 仅桥接（Bridge Only）

* 示例：**将 Base 上的 ETH 桥接到 Arbitrum 上的 ETH**
* 只有受支持的代币（USDC、USDT、WETH 等）才能直接桥接。这些代币因源链和目标链而异。

**Across 支持桥接的代币**

| 链      | USDC | USDT | WETH | ETH | CAKE | DAI | BAL | POOL | WBTC |
| ----------- | :--: | :--: | :--: | :-: | :--: | :-: | :-: | :--: | :--: |
| ARB <> BNB  |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ❌  |  ❌  |   ❌  |   ❌  |
| BASE <> BNB |   ✅  |   ✅  |   ✅  |  ✅  |   ❌  |  ❌  |  ❌  |   ❌  |   ❌  |
| ARB <> BASE |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ❌  |
| ETH <> BNB  |   ✅  |   ✅  |   ✅  |  ✅  |   ✅  |   ❌ |   ❌ |   ❌  |   ❌  |
| ETH <> BASE |   ✅  |   ✅  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ❌  |
| ETH <> ARB  |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ✅  |

#### 2️⃣ 兑换 → 桥接（Swap → Bridge）

* 示例：**将 BNB Chain 上的 BNB 兑换为 Arbitrum 上的 USDC**
* 使用 BNB chain 上的 PancakeSwap 池将 BNB 兑换为受支持的桥接代币（例如 USDC）
* 通过 Across 将 USDC 桥接到 Arbitrum

#### 3️⃣ 桥接 → 兑换（Bridge → Swap）

* 示例：**将 BNB Chain 上的 USDC 兑换为 Arbitrum 上的 ARB**
* 通过 Across 桥接 USDC
* 使用 Arbitrum 上的 PancakeSwap 池将 USDC 兑换为 ARB

#### 4️⃣ 兑换 → 桥接 → 兑换（Swap → Bridge → Swap）

* 示例：**将 BNB Chain 上的 BNB 兑换为 Arbitrum 上的 ARB**
* 将 BNB 兑换为桥接代币（使用户产出最大化）
* 通过 Across 桥接
* 使用 Arbitrum 上的 PancakeSwap 池将桥接后的代币兑换为 ARB

***

### ⚠️ 失败情形

| 情形                              | 结果                                                                                                                                                                                         |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **源链上的兑换/交易失败**   | 用户立即在源链上收到原始代币                                                                                                                      |
| **桥接交易失败**                 | Across 会在 90 分钟到 2 小时内处理退款，用户在源链上收到桥接资产。而在 SOL <> EVM 之间的此类情形下，Relay 会在一分钟内处理退款。 |
| **目标链上的兑换失败** | 用户在目标链上收到桥接资产                                                                                                                        |

