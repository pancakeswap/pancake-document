# Hooks

{% hint style="info" %}
If you're a developer or looking for detailed technical documentation on developing a hook, please visit [here](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook).
{% endhint %}

Hooks are powerful add-ons that let developers extend and customize the behavior of liquidity pools in PancakeSwap Infinity. Think of them as "plugins" or "widgets" that add new features to liquidity pools.

#### 🔍 What Are Hooks?

* Hooks are external smart contracts created by anyone — developers, protocols, or community members — and attached to liquidity pools to enhance or modify their behavior.
* Each pool can have only one hook attached, but a single hook can serve many pools.
* Hooks can run custom code before or after key actions like:
  * Initializing a pool
  * Swapping
  * Adding/removing liquidity
  * Donating<br>

**⛓️ How Hooks Work:**

* A hook is selected during pool creation and can’t be changed later.
* A hook contract triggers on specific actions (swap, add liquidity, etc) and executes logic before or after those actions as defined within the contract.
* For example, a hook could:
  * Offer swap fee discounts to CAKE holders
  * Charge custom fees and distribute rewards
  * Enable new swap logic like stableswaps or TWAMM-style orders<br>

#### ⚙️ Hook Callbacks

Hooks can be triggered during ten specific moments. Developers can choose which ones they want to implement:

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

These allow to implement highly customizable and modular behavior through hooks.

#### 🔧 Two Types of Hooks

**Type 1: No Authorization Needed**

These hooks run automatically and do not require user permission. They are triggered by actions like swaps or liquidity changes.



Examples:

* Dynamic Fees: Adjust swap fees based on market volatility
* Fee Rebates: Give discounts to users holding CAKE or trading high volumes



Example Flow (CAKE Fee Discount):

1. A user initiates a swap.
2. The hook checks their CAKE balance via `beforeSwap` hook callback.
3. If the user holds enough CAKE as per defined thresholds, they get a 50% discount on pool fees.
4. The rest of the transaction proceeds as usual.<br>

{% hint style="success" %}
These hooks don’t need a special UI or additional interaction. The benefits are applied automatically.
{% endhint %}

**Type 2: User Authorization Required**

These hooks need users to interact directly with them, provide authorisation and may require to transfer funds, often to create or manage positions.



Examples:

* Limit Orders: Execute a swap only when target price is reached.
* TWAMM: Break large orders into smaller pieces for better execution.
* Active Liquidity Management: Automatically manage LP positions for optimal returns.



Example Flow (Limit Order Hook):

1. User interacts directly with the hook contract (not the usual swap UI).
2. They enter details like limit price, token pair, amount.
3. The hook issues a receipt token representing the order.
4. Later, when pool price hits the target, the hook executes the order using afterSwap.
5. The user can return the receipt token to claim the swapped assets.

{% hint style="info" %}
These hooks often need a custom UI and users must trust and approve the hook contract to hold their funds.
{% endhint %}

#### 🚀 Use Cases & Innovation

Hooks unlock limitless possibilities, including:

* Custom AMMs (e.g., stablecoin curves)
* Liquidity mining rewards
* Automated trading strategies, liquidity management
* On-chain limit orders, other order types
* Dynamic pricing and fee adjustments
* Yield-enhancing LP strategies<br>

With hooks, developers can build an entirely new DeFi experience using the existing infrastructure of PancakeSwap Infinity — speeding up development and lowering costs.
