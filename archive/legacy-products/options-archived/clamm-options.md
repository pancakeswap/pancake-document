# CLAMM Options

{% hint style="danger" %}
\[ARCHIVED] Options – As of March 11, 2025\
If you still have liquidity to withdraw, please do so immediately by visiting https://www.stryke.xyz/en/trade.
{% endhint %}

<figure><img src="../../../.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options presents a novel approach to on-chain options trading, offering liquidity providers a platform to capitalize on v3 liquidity on Labswap. This enables them to utilize liquidity for both the v3 liquidity pools and to sell options, earning standard AMM trading fees, options premiums, and additional rewards, while traders can utilize this liquidity to buy American-style options on various tokens.

Crafted by the Stryke (formerly Dopex) team, the CLAMM options protocol introduces an efficient dual liquidity provision system for options traders (buyers) and Labswap v3 pools.

Here's a structured breakdown of how CLAMM Options operates:

1. LPs adding liquidity to CLAMM options simultaneously contribute to the designated Labswap v3 pool within their chosen price range.
2. When an options trader (buyer) initiates a position, liquidity is extracted from the v3 pool to facilitate options selling. The respective LP thereby becomes an options seller and receives a premium.
3. Liquidity unutilized by options buyers resides in the Labswap v3 pool, potentially earning trading fees.
4. The payoff from selling options and providing liquidity in a v3 pool mirrors the same impermanent loss, ensuring users face no increased risk compared to the conventional method of adding liquidity to v3 pools.
5. LPs face some risks, as liquidity might remain unutilized due to lower options buying demand. Additionally, since liquidity is added to the pool in an inactive range, it might not earn any fees.

Labswap’s American-style CLAMM options will debut on the Arbitrum chain, offering flexibility with diverse expiry durations ranging from 1 hour to 24 hours.

| **Markets**          | ARB/USDC, ETH/USDC, and wBTC/USDC |
| -------------------- | --------------------------------- |
| **Options Types**    | Call & Put                        |
| **Strike Prices**    | Based on v3 pool ticks            |
| **Expiry Durations** | 1H, 2H, 6H, 12H, and 24H          |

**Exercise Conditions:** Users can exercise positions before closure to avoid in-the-money options expiring worthless. Auto-exercise can be enabled to realize profits automatically at expiry, skipping further actions.

### Step-by-step guide

Here’s the step-by-step guide on how to use Labswap CLAMM Options.

**For Traders:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**For LPs:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
