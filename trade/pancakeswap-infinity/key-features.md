# Key Features

### 1️⃣ Singleton

In PancakeSwap v3, every liquidity pool had its own contract, which made creating pools and swapping across multiple pools more expensive.

Infinity fixes this by implementing the Singleton model. Now, all pools live inside a single contract called the PoolManager. This change cuts pool creation gas costs by up to 99% and makes multi-hop swaps (swaps that go through multiple pools) much cheaper by avoiding unnecessary token transfers.

#### ⚙️ **How it works:**

* Each pool’s data is stored in a shared contract using a unique pool ID.
* Creating a new pool is now just a state update, not a full contract deployment.
* Swapping across pools is faster and uses less gas.\


This Singleton approach, along with other optimizations like Flash Accounting and ERC-6909, helps make PancakeSwap Infinity one of the most gas-efficient DEX platforms available today.

***

### ⚡️ Flash Accounting

Flash Accounting is a powerful optimization in PancakeSwap Infinity that helps reduce gas fees during complex transactions like multi-hop swaps and liquidity changes.

In older versions (like v3), tokens were moved in and out of each pool during every step of a transaction. This led to high gas costs, especially for multi-hop swaps.

With Flash Accounting, that’s no longer necessary. Instead of moving tokens after each step, PancakeSwap Infinity keeps track of all token movements internally and only makes one final transfer at the end of the whole transaction. This saves a lot of gas.

#### ⚙️ **How It Works:**

* When you interact with Infinity (e.g., swapping or adding liquidity), the system calculates the net balance of tokens you owe or receive.
* These net token balances are stored temporarily using Transient Storage, a new feature introduced with Ethereum’s Cancun upgrade (EIP-1153).
* Transient Storage is cheaper than traditional storage because it only lasts for the duration of the transaction — no permanent writing or reading is needed.

***

### 🪙 Native Token Support

With the introduction of Singleton architecture and Flash Accounting, PancakeSwap Infinity now supports native gas tokens (e.g., BNB, ETH) directly in liquidity pools — no more wrapping and unwrapping required.

#### ✅ Key Highlights

* **Direct Native Token Pools:** You can now create pools like ETH/USDC, BNB/CAKE without needing WETH or WBNB.
* **Gas Efficient:** Native token transfers are \~50% cheaper than ERC-20 token transfers, leading to lower gas costs for swaps and liquidity actions.\


**Previously Removed, Now Re-enabled:** Native token support was absent in earlier versions due to implementation complexity and liquidity fragmentation.

***

### 📈 Custom Pricing Curves

PancakeSwap Infinity gives developers the power to create custom pricing models for pools — moving beyond the traditional model used in most AMMs.

{% hint style="success" %}
#### Developers can build entirely new swap behaviors and liquidity models tailored to specific asset types or trading strategies.
{% endhint %}

#### 🔧 What Are Custom Pricing Curves?

Custom pricing curves allow developers to:

* Bypass the native pool manager logic, creating pools with custom-defined swap behaviors.
* Alter how token amounts are calculated for swaps or liquidity modifications.
* Incorporate custom fee mechanics, such as:
  * Liquidity withdrawal fees
  * Rebates or penalties based on strategy

All of this is made possible through before / after swap hook callbacks, which can intercept and modify swap parameters dynamically.

#### 🛠 Example Use Cases

* **StableSwap Curves:** Design flatter curves around a 1:1 price ratio, reducing price impact between assets like USDC and USDT.
* **RWAs:** Create custom behaviors for different asset types with dynamic supply.
* **Hook-Level Fees:** Charge unique fees that differ from pool-level fees, such as developer fees.
* **Custom Risk Models:** Adjust pricing to reflect volatility, oracle data, or external metrics.

{% hint style="info" %}
In previous AMM versions (e.g., PancakeSwap v2/v3), pricing logic was hardcoded and rigid. PancakeSwap Infinity’s architecture unlocks the ability to build more capital-efficient and tailored pools.
{% endhint %}

#### 🔍 Developer Flexibility

* Developers can deploy custom hook contracts to override the pricing logic.
* Hook callbacks such as beforeSwap and afterSwap allow full control over how token deltas are calculated and applied.

***

### 🧮 ERC-6909: Efficient Multi-Token Accounting

PancakeSwap Infinity adopts[ ERC-6909](https://eips.ethereum.org/EIPS/eip-6909), a lightweight and gas-efficient token standard designed for internal accounting of multiple tokens within a single contract. It replaces many traditional ERC-20 operations with mint and burn primitives—leading to significant gas savings and simplified transaction flows.

#### ⚙️ How It Works

Rather than moving tokens in and out of the protocol with each interaction, ERC-6909 tokens represent internal balances:

* Mint: When users deposit tokens or perform a trade, they can choose to receive ERC-6909 tokens as claims.
* Burn: Later, instead of transferring ERC-20 tokens again, users can simply burn these ERC-6909 tokens to settle balances or fund new operations.

This model drastically reduces the need for external token transfers, which typically incur higher gas costs and interact with third-party logic (e.g., USDC's blacklisting checks).

#### 🪙 Benefits of ERC-6909

<table><thead><tr><th width="262.9921875">Feature</th><th width="497.7421875">Benefit</th></tr></thead><tbody><tr><td>✅ Internal Balance Claims</td><td>No need to transfer tokens repeatedly between user and contract</td></tr><tr><td>✅ Gas-Efficient Mint/Burn</td><td>Constant overhead regardless of token, no external contract calls</td></tr><tr><td>✅ Simpler Than ERC-1155</td><td>Smaller code size, no callbacks, no batched transfer requirements</td></tr><tr><td>✅ Multi-Token Support</td><td>A single contract can track multiple token types with isolated balances</td></tr><tr><td>✅ Seamless with PoolManager</td><td>Eliminates redundant ERC-20 approvals and transfers</td></tr></tbody></table>

#### 🚀 Use Cases

* **High-frequency traders:** Avoid gas-heavy transfers and interact directly using internal balances.
* **Liquidity managers:** Open and close positions more efficiently without excessive token movements.

#### 💡 Key Notes

* Users opt-in to ERC-6909 flow when they don’t need to immediately settle token transfers.
* Internal balances can be consolidated and net-settled later, giving power users greater control and flexibility.

***

### 💸 Donate Method

The `donate()` method allows users to directly incentivize in-range liquidity providers within a pool by donating tokens. This method relies on the pool's fee accounting system to facilitate the payments, ensuring that only pool tokens are supported.

#### 🔹 Key Features:

* **Direct Payments to LPs:** Donations are made directly to liquidity providers, rewarding those who maintain liquidity within the active range of the pool.
* **Supports Pool Tokens Only:** The `donate()` method only supports donations in the pool's tokens, as it leverages the fee accounting system to ensure proper distribution.
* **Open to All Users:** Any user can call the `donate()` method, enabling anyone to incentivize active liquidity provision.



While the `donate()` method is a powerful tool to incentivize LPs, donors should be aware that their donations may be front run by other users. This can occur when a user quickly adds liquidity to the pool right before a donation is made, receiving a portion of the donated funds.

To prevent front-running, donors may need to consider additional strategies when designing their donation mechanisms, such as:

* Ensuring that donations occur in a way that minimizes the ability for opportunistic front-running.
* Adding time delays or specific conditions (using before / after donate hook callbacks) that ensure the donations are not being exploited in this way.
