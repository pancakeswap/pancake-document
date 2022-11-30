# 🔄 StableSwap

<figure><img src="../../.gitbook/assets/docs masthead.png" alt=""><figcaption></figcaption></figure>

StableSwap on PancakeSwap is a feature to trade stable pairs with a lower slippage based on an invariant curve slippage function. It is designed to swap specific assets that are priced closely – such as USD stablecoins (e.g. HAY, BUSD and USDT) or liquid staking tokens (e.g. stkBNB and aBNBc).

The StableSwap is an implementation of Curve Finance’s AMM on PancakeSwap. It adds linear invariant constant sum curve (x+y=k) on top of the constant product formula (x\*y=k) to keep prices more equal as long as the liquidity pool is not extremely unbalanced. As a result, since StableSwaps are restricted to similarly priced assets, impermanent loss is not as much of a concern (except in extreme depeg cases) and the slippage is lower than normal AMM which just uses the constant product formula.

When you conduct a Swap (trade) on the StableSwap you will pay lower trading fees, than the usual 0.25% on normal PancakeSwap AMM. The fee attribution is broken down as follows:

* 50% to the LP as rewards&#x20;
* 40% to CAKE buyback and burn&#x20;
* 10% to the PancakeSwap Treasury

Fees for pairs are broken down in the table below:

| Stablepair | Trading Fees | LP Rewards | CAKE Buyback | PancakeSwap Treasury |
| ---------- | ------------ | ---------- | ------------ | -------------------- |
| USDT-BUSD  | 0.15%        | 0.075%     | 0.06%        | 0.015%               |
| USDC-BUSD  | 0.15%        | 0.075%     | 0.06%        | 0.015%               |
| USDC-USDT  | 0.15%        | 0.075%     | 0.06%        | 0.015%               |
| HAY-BUSD   | 0.04%        | 0.02%      | 0.016%       | 0.004%               |

The Kitchen will gradually roll out StableSwap pairs and revise the fees to test and improve the product further.

## Why should I use the StableSwap instead of the normal AMM Swap?

* Swap your stablecoins or other pairs with similar asset prices more efficiently with the same trade steps&#x20;
* With the StableSwap function, the trading slippage is lower than normal AMM&#x20;
* The StableSwap trading fees are lower compared to the normal AMM

## Still Cooking&#x20;

* Better guides on UI regarding StableSwap and stable LPs&#x20;
* StableSwap information page&#x20;
* Adding more stable trading pairs and the migration process of existing LPs

## Timeline:

* USDC-BUSD, USDT-BUSD, USDC-USDT liquidity provision enabled: **Nov 30 2022 11:00 UTC**
* Farm migration (CAKE rewards redirect from USDC-BUSD, USDT-BUSD, USDC-USDT LP Farm to USDC-BUSD, USDT-BUSD, USDC-USDT Stable LP Farm): TBD

## FAQ on Stablepool Launch 30 Nov

What happened to the new Stablepools?

* We have encountered a minor issue with the fee parameter
* This has resulted in an inability to remove liquidity at 50%/50% due to higher admin fees

Key Updates:

* Your funds are safe
* We have reverted the FE and rolled it back to the previous version before the new pools
* Fees will be rebated to every active LP provider in the pool
* In the meantime, the chefs are working on a fix. Once it's deployed, you will be able to manage your stable LP
* Farm migration will be delay until fix is deployed

We will continue to provide updates here as soon as we can.
