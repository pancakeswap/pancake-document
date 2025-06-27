# 🔁 Swap Scenarios

There are 4 scenarios for Crosschain transactions.

#### 1️⃣ Bridge Only

* Example: **Bridge ETH on Base to ETH on Arbitrum**
* Only supported tokens (USDC, USDT, WETH, etc) can be bridged directly

**Tokens supported for bridging by Across**

| Chains      | USDC | USDT | WETH | ETH | CAKE | DAI | BAL | POOL | WBTC |
| ----------- | :--: | :--: | :--: | :-: | :--: | :-: | :-: | :--: | :--: |
| ARB <> BNB  |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ❌  |  ❌  |   ❌  |   ❌  |
| BASE <> BNB |   ✅  |   ✅  |   ✅  |  ✅  |   ❌  |  ❌  |  ❌  |   ❌  |   ❌  |
| ARB <> BASE |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ❌  |
| ETH <> BNB  |   ✅  |   ✅  |   ✅  |  ✅  |   ✅  |   ❌ |   ❌ |   ❌  |   ❌  |
| ETH <> BASE |   ✅  |   ✅  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ❌  |
| ETH <> ARB  |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ✅  |

#### 2️⃣ Swap → Bridge

* Example: **Swap BNB on BNB Chain to USDC on Arbitrum**
* Swap BNB to a supported bridge token (e.g. USDC) using PancakeSwap pools on BNB chain
* Bridge USDC via Across to Arbitrum

#### 3️⃣ Bridge → Swap

* Example: **Swap USDC on BNB Chain to ARB on Arbitrum**
* Bridge USDC via Across
* Swap USDC to ARB using PancakeSwap pools on Arbitrum

#### 4️⃣ Swap → Bridge → Swap

* Example: **Swap BNB on BNB Chain to ARB on Arbitrum**
* Swap BNB to a bridge token (maximizing user output)
* Bridge via Across
* Swap bridged token to ARB on Arbitrum using PancakeSwap pools

***

### ⚠️ Fail Cases

| Scenario                              | Outcome                                                                                                  |
| ------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **Swap/Tx Failure on Source Chain**   | User instantly receives the original token on source chain                                               |
| **Bridge Tx Failure**                 | Across processes a refund within 90 mins to 2 hours, and user receives the bridged asset on source chain |
| **Swap Failure on Destination Chain** | User receives the bridged asset on the destination chain                                                 |

