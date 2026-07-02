# Infinity StableSwap

### Overview

Infinity StableSwap is a pool type within[ PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) optimized for swapping assets that should trade near the same price — such as stablecoins (e.g., USDC/USDT) or tightly-pegged assets (e.g., wrapped token pairs, liquid staking tokens, and liquid restaking tokens).

It is powered by a StableSwap hook running on the Infinity architecture, inspired by Curve's StableSwap NG design. It is currently available on BNB Chain, with plans to expand to additional chains in the future.

***

### How It Works

Infinity StableSwap uses a stable invariant curve — a hybrid between constant-sum and constant-product:

* Near the peg → the curve behaves close to constant-sum, resulting in very low slippage for trades around 1:1.
* Away from the peg → the curve gradually transitions toward constant-product, which helps restore balance and protects the pool during large imbalances or depeg events.

This makes it especially effective for stable pairs where tight pricing and low slippage matter most.

***

### Key Features

Optimized for near-peg swaps: Low slippage for trades between assets that are expected to trade at roughly the same price.

Simple liquidity provisioning: Liquidity providers (LPs) deposit both tokens proportionally without needing to select or manage price ranges — unlike CLAMM pools.

ERC-20 LP tokens: Your LP position is represented as a standard ERC-20 token, making it easy to use with yield programs, points campaigns, and other DeFi protocols.

Dynamic fees: Fees can adjust based on pool balance conditions, rewarding trades that help restore the pool toward equilibrium and discouraging those that worsen imbalance.

Infinity routing support: Trades route automatically through StableSwap pools when they offer the best price — no extra steps required for traders.

Adjustable Amplification (A) parameter: Pool operators can ramp the A parameter up or down over time to adapt to changing market conditions, with safeguards to prevent abrupt changes.

***

### Pool Parameters

StableSwap pool behavior is governed by a small set of parameters, typically set at pool creation time.

#### Amplification Coefficient (A)

The A parameter controls how tightly the pool hugs the 1:1 price peg.

| A value  | Effect                                                                         |
| -------- | ------------------------------------------------------------------------------ |
| Higher A | Tighter curve around peg; lower slippage near 1:1; more sensitive to imbalance |
| Lower A  | Looser curve; behaves more like a standard constant-product pool               |

Rule of thumb: Use a higher A for assets with a strong, reliable peg (e.g., USDC/USDT). Use a lower A for assets with looser or more volatile pegs (e.g., some LST pairs).

The A parameter can be gradually ramped up or down by the pool operator over a defined period of time. Changes are applied gradually with safeguards to prevent manipulation or sudden pricing shifts.

#### Off-Peg Fee Multiplier

An additional parameter that adjusts effective fees when the pool moves away from equilibrium. It helps discourage trades that would further imbalance the pool and makes the pool more robust during market stress or depeg events.

#### Dynamic Fees

A fee charged on each swap, paid to liquidity providers. Infinity StableSwap supports dynamic fees — meaning the effective fee on a given trade can vary depending on the current state of the pool (e.g., whether the trade improves or worsens balance).

***

### Infinity StableSwap vs. Classic StableSwap

If you've used PancakeSwap's existing StableSwap before, here's what changes — and what stays the same.

| <p><br></p>                 | Classic StableSwap                                        | Infinity StableSwap                                                |
| --------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------ |
| Pricing curve               | Stable invariant (hybrid constant-sum / constant-product) | Same stable invariant curve, same low slippage near peg            |
| ERC-20 LP tokens            | ✅ Yes                                                     | ✅ Yes                                                              |
| Pool creation               | Ops-heavy; requires manual setup by the team              | Permissionless — anyone can create a pool                          |
| Swap fees                   | Fixed per pair (e.g. 0.01% for USDC/USDT)                 | Dynamic fees — adjusts based on how the trade affects pool balance |
| Amplification (A) parameter | Static — set once, cannot be changed                      | Adjustable — can be ramped up or down gradually over time          |
| Off-peg fee multiplier      | ❌ Not supported                                           | ✅ Supported — helps protect the pool during depeg events           |
| Gas efficiency              | Standard                                                  | Improved — benefits from Infinity's Singleton and Flash Accounting |

#### What stays the same

* The core pricing curve and the near-peg low slippage behavior is unchanged.

#### What's new and better

* Permissionless Pool Creation: Pools can be created permissionlessly without requiring manual team setup.
* Dynamic fees protect LPs: Instead of a single fixed fee, the fee can adjust per trade based on whether the trade helps or hurts pool balance — making the pool more resilient during volatile conditions.
* Adaptable A parameter: The amplification coefficient can be tuned over time as market conditions change, rather than being locked in at deployment forever.

***

### Frequently Asked Questions

What assets are suitable for Infinity StableSwap?

Assets that are expected to trade near the same price: stablecoins (USDC, USDT, BUSD, etc.), wrapped equivalents of the same asset (e.g., WBTC/cbBTC), and select liquid staking tokens / liquid restaking tokens (LST/LRT) pairs where peg volatility is low.

<br>

How is Infinity StableSwap different from the old PancakeSwap StableSwap?

Infinity StableSwap is implemented as a hook on PancakeSwap Infinity, which means it inherits all of Infinity's infrastructure benefits, including lower gas costs via Singleton and Flash Accounting, and a more flexible fee system. It also supports new capabilities like dynamic fees and adjustable amplification that the legacy StableSwap did not offer.

<br>

Do I need to manage my position over time?

No. Unlike CLAMM, you don't need to set or adjust price ranges. Your liquidity is always active across the full curve, so there's no risk of your position going "out of range."

<br>

Can I provide liquidity with just one token?

Yes, single-token deposits are supported.

<br>

How do dynamic fees work?

In Infinity StableSwap, the swap fee can vary per trade based on how the trade affects the pool's balance. Trades that help bring the pool back toward equilibrium may pay lower effective fees, while trades that worsen imbalance may pay higher fees. This is designed to protect LPs and maintain healthier pool conditions.



***



## Creating an Infinity StableSwap Pool



Infinity StableSwap pools are permissionless — anyone can create one without needing approval from the PancakeSwap team.

<br>

### Step-by-step

1\. Go to the Farm/Liquidity page and click Create Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Select StableSwap Pool from the pool type options.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Select the token pair for your pool (e.g. USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Pool Parameters

| Parameter             | What it does                                                                                                    |
| --------------------- | --------------------------------------------------------------------------------------------------------------- |
| Swap Fee              | Fee charged on each swap, paid to LPs. Default is 0.01% for tight stable pairs.                                 |
| A (Amplification)     | Controls how tightly the curve hugs the peg. Higher = lower slippage near 1:1, but more sensitive to imbalance. |
| Offpeg Fee Multiplier | Scales up fees when the pool moves away from balance, discouraging trades that worsen imbalance.                |
| Moving Average Time   | Time window used to calculate the moving average price for dynamic fee adjustments.                             |

⚠️ Set parameters carefully. Incorrect parameters — especially a very high A on a loosely-pegged asset — can increase risk for LPs. If unsure, use the preset for your asset type and avoid changing Advanced settings.

<br>

Choose a Pool Parameter Preset — this automatically sets the recommended parameters for your asset type. You can still manually adjust them via the Advanced toggle.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Preset                            | A    | Offpeg Fee Multiplier | Moving Average Time (seconds) |
| --------------------------------- | ---- | --------------------- | ----------------------------- |
| Fiat Redeemable Stablecoins       | 1000 | 10                    | 600                           |
| Crypto Collateralized Stablecoins | 100  | 12.5                  | 600                           |
| Liquid Restaking Tokens           | 500  | 10                    | 600                           |

<br>

&#x20; Not sure which to pick?&#x20;

* Use Fiat Redeemable Stablecoins for pairs like USDC/USDT
* Use Crypto Collateralized Stablecoins for algo or crypto-backed stablecoins
* Use Liquid Restaking Tokens for LRT pairs like stkBNB/WBNB.

<br>

5\. Enter the deposit amount to seed initial liquidity. Both token amounts must be equal (e.g. 1 USDC and 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Click Preview Pool, review your settings, check the confirmation box, then click Create Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>

