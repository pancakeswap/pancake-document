# 🔀 Crosschain Swaps

Crosschain Swaps allow users to seamlessly swap tokens between chains — all within a single, streamlined transaction.

Crosschain swaps are supported between:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**Transactions are lightning-fast — typically completing within seconds to under a minute.**
{% endhint %}

***

### 🔍 How It Works

1. User selects From / To chain and From / To token
2. The PancakeSwap router computes the most efficient route
3. Swaps are executed using PancakeSwap’s liquidity pools (v2, v3, Infinity, StableSwaps) on source and destination chains
4. Bridging is handled via our partner protocols: [Across](https://across.to/) (for EVM <> EVM), [Relay](https://relay.link/bridge) (for SOL <> EVM)

{% hint style="success" %}
**Crosschain swaps are available for any token with adequate liquidity on both the source and destination chains.**
{% endhint %}

***

### 💸 Fees

* **PancakeSwap does not charge any fee for Crosschain transactions.**
* Fees are comprised of:
  1. **Trading Fee:** Incurred for swaps within liquidity pools on the source and destination chains
  2. **Bridge Fee:** Paid to relayers for bridging assets

***

### 🎯 What Are Intents?

Intents let users define their desired outcome without worrying about how it’s achieved.

Example Intents:

* “Swap 1 ETH on Base for at least 3000 USDC on Arbitrum”

Without intents, a user would need to manually:

* Bridge ETH to Arbitrum
* Find a DEX with the best ETH → USDC price

{% hint style="success" %}
**With intents — the system handles it all automatically.**
{% endhint %}

**Benefits of intent-based design:**

* Seamless UX
* Faster transaction times
* One-click, single transactions

***

### 🔐 Audits

We’ve conducted multiple audit rounds with respected names in the cross-chain security space:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
