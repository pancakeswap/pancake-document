# 🔄 StableSwap

<figure><img src="../../.gitbook/assets/docs masthead.png" alt=""><figcaption></figcaption></figure>

StableSwap on PancakeSwap is a feature to trade stable pairs with a lower slippage based on an invariant curve slippage function. It is designed to swap specific assets that are priced closely – such as USD stablecoins (e.g. HAY, BUSD and USDT) or liquid staking tokens (e.g. stkBNB and aBNBc).

The StableSwap is an implementation of Curve Finance’s AMM on PancakeSwap. It adds linear invariant constant sum curve (x+y=k) on top of the constant product formula (x\*y=k) to keep prices more equal as long as the liquidity pool is not extremely unbalanced. As a result, since StableSwaps are restricted to similarly priced assets, impermanent loss is not as much of a concern (except in extreme depeg cases) and the slippage is lower than normal AMM which just uses the constant product formula.

When you make a token swap (trade) on the StableSwap you will pay a fee of 0.04% trading fees, which is lower than the usual 0.25% on normal PancakeSwap AMM. The fee attribution is broken down as follows

* 0.02% to the LP as rewards (50%)
* 0.016% to CAKE buyback and burn (40%)
* 0.004% to the PancakeSwap Treasury (10%)

At launch, the Kitchen will be rolling out StableSwap pairs gradually to test and improve the product further. The first pair to be launched will be **HAY-BUSD**.

[**HAY**](https://helio.money/) **** from Helio Protocol is a fully decentralized, BNB overcollateralized [destablecoin](https://docs.helio.money/). The reasons the HAY-BUSD pair is selected as the first are:

* Be one of the first major trading venues for HAY to absorb volume overtime
* As HAY only recently launched (mid-Aug 2022) compared to other stablecoins, the volume and operational impact from liquidity transfer is more manageable to launch on the StableSwap product
* Based on progress of this pair and community feedback, the Kitchen can gradually add other stable pairs

## **Why should I use the StableSwap instead of the normal AMM swap?**

* Swap your stablecoins or other pairs of similarly priced assets more efficiently with the same trade steps!
* With the StableSwap function, the trading slippage is lower than normal AMM which just uses the constant product formula
* The trading fees are lower compared to the normal AMM as well.

## What are some of the features that the Kitchen is still fixing and cooking?

* Better guides on UI regarding StableSwap and stable LPs&#x20;
* StableSwap information page&#x20;
* Adding more stable trading pairs, and the migration process of existing LPs

## Timeline:

* StableSwap launch and HAY-BUSD liquidity provision enabled: **Sep 22 2022 11:00 UTC**
* Farm migration (CAKE rewards redirect to from HAY-BUSD LP Farm to HAY-BUSD Stable LP Farm)**: Sep 23 2022 11:00 UTC**
