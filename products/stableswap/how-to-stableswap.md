# How to StableSwap

<figure><img src="../../.gitbook/assets/how-to-stableswap.png" alt=""><figcaption></figcaption></figure>

## **Trading on the StableSwap**

Trading on the StableSwap is very similar to using the existing PancakeSwap AMM. Before we start, it also requires a BNB Smart Chain-compatible wallet and BNB for gas fees. Please check our [wallet guide](https://docs.pancakeswap.finance/get-started/wallet-guide) for more details.

1 - Go to the swap page [here](https://pancakeswap.finance/swap#/swap)

2 - Click on the “StableSwap” tab

![](https://lh6.googleusercontent.com/CnSjYP6R3vS8IXCZkZLfhTtRIDvdIO9ylB8VwV6l80UN0gYB6pBQC1m-aMmzP3ukQQXWLU4F7OLX2cgZ\_9jIctZHvdYiCTDNLAD2mnyD3E1xWopXF0qckLTnxOPQG4Sc3Vx5QLUmdKcEOtxOgmfOGU6wPYP9GhCiS9Wy6nQn-r0tIuUkgf4ePn2qwA)

3 - Choose the token pairs you would like to trade. At launch, only one pair (HAY-BUSD) will be added, more stable pairs will be added gradually

![](<../../.gitbook/assets/Screenshot 2022-09-22 at 7.13.54 PM.png>)

4 - From this step on, the swap process is the same as the normal PancakeSwap! Please check the guide [here](https://docs.pancakeswap.finance/products/pancakeswap-exchange/trade-guide) from step 4 onwards

## **Adding & Removing Liquidity**

Adding and removing liquidity for the StableSwap is also very important and similar to the normal PancakeSwap AMM. Please refer to the guide [here](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) for a more detailed explanation.

There are a few differences for StableSwap liquidity:

1 - When you select the asset pairs that are enabled for StableSwap (e.g. HAY-BUSD), the frontend will prompt that you’re supply “Stable LP”&#x20;

![](https://lh3.googleusercontent.com/MVFsZoVNleguG24mNK4DHEsmAx1vwZT5FEyZUHIwgdrGyfuz5v0XNJbjzqSv26o7VWagi7Vq\_7jZMzpHc93wdPonm0V1OrzMgLYHDYTosoqcZSwQAn8gvIXjjNHJdOwRTJw2TuouiI1wpeJKJ8AFdqAkANp2jfCXo3nRxXdLyPWn90h2oPI\_Zpq7Gw)

2 - The supply of the two assets can be imbalanced at the stage of supplying, and there will be a confirmation page to show the ratio of your supply.

![](<../../.gitbook/assets/Screenshot 2022-09-22 at 7.15.56 PM.png>)

3 - You would receive a Stable-LP token as the receipt of the liquidity provision, for future withdrawal and removal.

![](https://lh3.googleusercontent.com/N4LAjYELBWGQPVWe9mP7nsNBoCAXOhoMQaaQ0K-WZTPM14-K9Ng6qBI29K-DJHrRT2AfJCiRmrKt1uudr7wZxFJv3purL6OFFpqGHArM2\_6QWu3LPA4Uzz\_uXaUV1w8YR1FC7fUoSE5VVHehOjr5NLiZGn588\_85m10ATXMhsT14kEMyPiz6Ss5VQg)

4 - However, PLEASE NOTE that when you remove the liquidity, you will always get 50%/50% in the assets no matter the ratio when you added the supply. As a simplified example, if you supplied 199 HAY and 1 BUSD, when you remove the liquidity you will receive 100 HAY and 100 BUSD assuming 0 slippage and stable 1:1 prices.

![](<../../.gitbook/assets/Screenshot 2022-09-22 at 7.16.55 PM.png>)

## **Migrate your HAY-BUSD Farm Staking**

Before the StableSwap is launched, HAY-BUSD liquidity and LP farm is already available on PancakeSwap in its normal v2 AMM swap. However, since we are launching HAY-BUSD as the first trading pair on our StableSwap, it is likely that most of you who would like to trade this pair will eventually move to the StableSwap instead of continue using the v2 AMM swap, because:

* You can swap more efficiently with the same trade steps
* With the StableSwap function, the trading slippage is lower than normal AMM which just uses the constant product formula
* The trading fees are lower compared to the normal AMM

**PLEASE NOTE: If you’re currently not farming with HAY-BUSD LP, you don’t have to do any migration.**

**Why does the farm staking need to be migrated?**&#x20;

Since most trading activities of HAY-BUSD will be on the StableSwap using the Stable LP going forward, CAKE incentives should be directed to reward the Stable LP stakers for encouraging them to provide the liquidity. There would be less activity for the original HAY-BUSD LP (with the v2 AMM).

## How to Migrate LP

There will be a 24-hour window starting from StableSwap launch, and before the CAKE incentives are redirected and the new farm for HAY-BUSD Stable LP is launched. Here’s what you should do if you are currently staking HAY-BUSD LP in the farm:

1 - Unstake HAY-BUSD LP from the [farms page](https://pancakeswap.finance/farms)&#x20;

<figure><img src="https://lh6.googleusercontent.com/7d4gCf4tKDt45xtcC3-0HJWdi3SO-1-vTf0dZzzTg75taCWNhHpye1OQOEeMd8LM2UuKAWgmY6wRuG1Iw7vaH80nkK9j91L0_xI3u1AD1LAosAW2mEsxilvl49EowEBy9mjWH3BGgFzLsMqWxUYzuRtOPbkBhI9epVYXlLaoRCNRPEoCSTfTTzQqfw" alt=""><figcaption></figcaption></figure>

2 - Remove liquidity of your HAY-BUSD LP at the [liquidity page](https://pancakeswap.finance/liquidity)

3 - Add liquidity again for HAY-BUSD (this time you should see that you’re adding to Stable LP during the process)

![](https://lh5.googleusercontent.com/cB4cqAFzpEhnBDCrecAc\_oks\_2xu7gBc\_6BuRupnDNvrOe9MrW\_WF11NGRzu490KZ\_R26ZPRwwmAyRGr2Q14nLORFxzBVV4w98dC1jJvv7I-yfMdsxpNHF9uHxAGwOtFAz6GsyYlJUG2CdxK5\_7BfnhWDnO9U7IfR0b3i0Hfke33sOqQ5axWdHxscQ)

4 - Stake your HAY-BUSD Stable LP in the [farms page](https://pancakeswap.finance/farms) when it's launched on Sep 23 – look for the card with the Stable LP label

![](https://lh6.googleusercontent.com/wWGXLFRQFMesilP4pMEUieR-qezbiCdTVhT7geBJuDwIIcC4hqwzgOjEIvRkViBVj-j4hmc9K5fB6vhuHJk8ZyrQfYBRqK1e2yGkiJZhlH5J4PDJu-xT6us-x9dVbodhAW5mm8qZ5yb8HkRrZy1bRz4SKc26jm1lMpTiV3S6tT1WyDtHL8Yj13rp8w)

## Timeline:

* StableSwap launch and HAY-BUSD liquidity provision enabled: **Sep 22 2022 11:00 UTC**
* Farm migration (CAKE rewards redirect to from HAY-BUSD LP Farm to HAY-BUSD Stable LP Farm)**: Sep 23 2022 11:00 UTC**
