# Infinity CLAMM & LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

CLAMM enables liquidity providers to allocate their capital within **specific price ranges**. This leads to:

* **Higher capital efficiency**: More liquidity at active trading prices.
* **Deeper liquidity**: Better execution for traders.
* **Active LP management**: LPs need to adjust positions as prices move.
* **Higher impermanent loss** potential for out-of-range positions.

{% hint style="info" %}
CLAMM operates on the constant product formula (X \* Y = K). Each liquidity position is non-fungible and represented as an NFT.
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM or “Bin Pool”)

LBAMM implements **discrete price bins**, each holding liquidity at a specific price level. LBAMM follows the **constant sum formula (X + Y = K).**



**Key characteristics:**

* **0 price impact** trades within a bin.
* **Fungible liquidity** (liquidity within each bin is an ERC-20 token).
* **Lower gas costs** for adjusting LP positions.
* **Support for different liquidity shapes** (e.g., skewed, uniform).
* More suitable for **low volatility** pairs due to the flat pricing curve per bin.

> 🥞 **PancakeSwap is the first protocol to offer LBAMM pools with hooks.**

{% hint style="success" %}
Both CLAMM and LBAMM pools support **hooks**, which allow developers to customize pool behavior. Pool types are extendable via new Pool Managers, which can be added without protocol redeployment.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Feature</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Pricing Curve</strong></td><td>Constant Product (X * Y = K)</td><td>Constant Sum (X + Y = K)</td></tr><tr><td><strong>Liquidity Token</strong></td><td>Non-fungible (NFT)</td><td>Fungible (ERC-20 per bin)</td></tr><tr><td><strong>Best For</strong></td><td>Both high/low volatility pairs</td><td>Low volatility pairs</td></tr><tr><td><strong>Advantages</strong></td><td><ol><li>Capital efficiency</li><li>Gas efficient in wide/full range</li><li>Widely adopted</li></ol></td><td><ol><li>0 price impact within bin</li><li>Cheaper LP management</li><li>Flexible liquidity shapes</li></ol></td></tr><tr><td><strong>Hook Support</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Fees

PancakeSwap Infinity supports a flexible and extensible fee system through Static and Dynamic fee settings. This setup gives both pool creators and LPs powerful tools to optimize for different trading strategies and risk profiles.

#### 🔁 Dynamic Fees

* Dynamic Fees are determined in real-time via hook contracts.
* These fees can fluctuate based on external factors such as volatility, trading volume, user status (e.g., CAKE holdings), or any custom logic coded into the hook.
* Pools with dynamic fees must enable the setting at the time of pool creation and attach a hook capable of modifying fees via `beforeSwap`.
* Once a pool is initialized, the fee type (dynamic or static) is immutable.

Dynamic fees offer maximum flexibility and optimize fee structures for both LPs and swappers based on market conditions.

#### 📌 Static Fees

* Static Fee pools have a fixed fee set during pool creation.
* These fees cannot be changed after the pool is initialized.
* Suitable for simpler use cases or where predictability of fee structure is important.<br>

**🔒 Max Fee Caps:**

* CLAMM Pools: Up to 100% (mostly for specialized or experimental use cases)
* LBAMM Pools: Capped at 10%<br>

**🏛 Protocol Fee (for static fee pools):**

* PancakeSwap applies a protocol fee on Infinity pools
* 33% of LP fee, capped at 0.4%

| **LP Fee**       | **Protocol Fee** |
| ---------------- | ---------------- |
| 1%               | 0.33%            |
| 2%               | 0.4% (capped)    |
| Dynamic Fee Pool | 0%               |

#### 🛠️ Setup Notes for Pool Creators

* When initializing a pool via PoolManager, the creator must choose:
  * Whether the pool uses a static or dynamic fee
  * Whether a hook contract is attached (required for dynamic fees)

These settings are permanent and define how the pool behaves throughout its lifetime.
