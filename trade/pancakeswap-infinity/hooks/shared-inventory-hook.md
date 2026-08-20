# Shared Inventory Hook

PancakeSwap's official Shared Inventory Hook (SIH) is designed to allow a single pool of capital market-make across every pool that shares its tokens, instead of locking separate liquidity into each one. It give traders deeper quotes and lower price impact, while letting liquidity providers deploy less capital for the same coverage.

Built by the PancakeSwap core team, this hook is tailored for asset issuers and market makers who want to quote multiple pairs on-chain without fragmenting their inventory.

#### 🔍 Why Shared Inventory?

Providing liquidity to multiple pairs the conventional way means locking dedicated capital into separate pools, most of it sitting idle between trades. SIH instead holds one balance per token and injects it as liquidity only when a swap needs it, so the same capital can back every pool that shares that token.

#### 📊 How Is This Different From Other Models?

Conventional concentrated liquidity requires committing the full principal to a single pool. Other cross-pool approaches such as virtual-balance settlement layers typically sit outside the AMM itself, where liquidity might not be visible as on-chain pool depth and routed directly by aggregators.

SIH's liquidity enters and exits PancakeSwap Infinity CLAMM pool by the hook on every swap, so it shows up as genuine pool depth that routers can see and fill against.

#### ⚙️ How It Works

* **Just-in-time (JIT) injection**\
  Before each swap, the hook mints a configured concentrated liquidity position into the pool; after the swap executes, it burns and settles the net result. The position exists only for the duration of one swap, the balance is free to serve the very next pool that needs it.
* **One balance, many pools**\
  Inventory is the hook's own token balance, there is no per-pool deposit. Any token that is to be used in more than one pool is shared across all of them.

{% hint style="success" %}
This decouples the depth a pool quotes from the in-pool capital directly holds: a funded hook can quote deep, tight liquidity across a number of pools that share a token.
{% endhint %}

* **Configurable hook**\
  For every pool it serves, the hook holds an adjustable independent configuration for price range and depth. Moving the band requires just a configuration update, making it simple to recenter the quotes around a moving reference price.

#### 📌 Key Takeaways

* One shared token balance backs every pool that uses that token. Adding a new pool utilises no new principal.
* Fully on-chain and composable: SIH liquidity is real pool depth, routable by PancakeSwap and third-party aggregators alike.
* Traders get deeper quotes and lower price impact on size; operators earn the same trading fees on a fraction of the conventional capital.

