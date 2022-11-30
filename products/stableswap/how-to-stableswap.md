# How to StableSwap

<figure><img src="../../.gitbook/assets/how-to-stableswap.png" alt=""><figcaption></figcaption></figure>

## **Trading on the StableSwap**

Trading on the StableSwap is very similar to using the existing PancakeSwap AMM. Before we start, it also requires a BNB Smart Chain-compatible wallet and BNB for gas fees. Please check our [wallet guide](https://docs.pancakeswap.finance/get-started/wallet-guide) for more details.

1 - Go to the Swap page here

2 - Choose the token pairs you would like to trade.&#x20;

3 - Check the “Use Stableswap for Lower Fees” box. Our [Smart Router](../pancakeswap-exchange/smart-router/) will generate the best possible fees for the Swap.&#x20;

4 - Your all set! The following Swap process is the same as usual! If it’s your first time trading please check the guide [here.](../pancakeswap-exchange/trade-guide.md)

**Adding & Removing Liquidity**

Adding and removing liquidity for the StableSwap is also very important and similar to the normal PancakeSwap AMM. Please refer to the guide [here](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) for a more detailed explanation.

There are a few differences for StableSwap liquidity:

1 - When you select the asset pairs that are enabled for StableSwap (e.g. HAY-BUSD), the frontend will prompt that you’re supplying “Stable LP”

![](https://lh3.googleusercontent.com/MVFsZoVNleguG24mNK4DHEsmAx1vwZT5FEyZUHIwgdrGyfuz5v0XNJbjzqSv26o7VWagi7Vq\_7jZMzpHc93wdPonm0V1OrzMgLYHDYTosoqcZSwQAn8gvIXjjNHJdOwRTJw2TuouiI1wpeJKJ8AFdqAkANp2jfCXo3nRxXdLyPWn90h2oPI\_Zpq7Gw)

2 - The supply of the two assets can be imbalanced at this stage, and there will be a confirmation page to show the ratio of your supply.

![](<../../.gitbook/assets/Screenshot 2022-09-22 at 7.15.56 PM.png>)

3 - You will receive a Stable-LP token as the receipt for liquidity provision, which you can later withdraw and remove.

![](https://lh3.googleusercontent.com/N4LAjYELBWGQPVWe9mP7nsNBoCAXOhoMQaaQ0K-WZTPM14-K9Ng6qBI29K-DJHrRT2AfJCiRmrKt1uudr7wZxFJv3purL6OFFpqGHArM2\_6QWu3LPA4Uzz\_uXaUV1w8YR1FC7fUoSE5VVHehOjr5NLiZGn588\_85m10ATXMhsT14kEMyPiz6Ss5VQg)

4 - **PLEASE NOTE** that when you remove the liquidity, you will always get 50%/50% in the assets no matter the ratio when you added the supply. As a simplified example, if you supplied 199 HAY and 1 BUSD, when you remove the liquidity you will receive 100 HAY and 100 BUSD assuming 0 slippage and stable 1:1 price.

![](<../../.gitbook/assets/Screenshot 2022-09-22 at 7.16.55 PM.png>)

## **Migrate your** USDT-BUSD, USDC-BUSD, USDC-USDT **Farm Staking**

Before the launch of StableSwap pools, the following liquidity pairs and LP Farms are already available on PancakeSwap in normal V2 AMM swap:

* HAY-BUSD&#x20;
* USDT-BUSD&#x20;
* USDC-BUSD&#x20;
* USDC-USDT

The launch of trading pairs on StableSwap, will likely result in:

* More efficient swaps&#x20;
* With the StableSwap function, the trading slippage is lower than normal AMM
* The trading fees are lower compared to the normal AMM

**PLEASE NOTE: If you are currently not farming with the above-listed LPs, no migration is required.**

**Why does the farm staking need to be migrated?**&#x20;

Since most trading activities of USDC-BUSD, USDT-BUSD, USDC-USDT & HAY-BUSD will be on StableSwap using the Stable LP going forward, CAKE incentives should be directed to reward the Stable LP stakers for encouraging them to provide liquidity. There would be less activity for the original LPs (with the v2 AMM).

## How to Migrate LP

There will be a **24-hour window** starting from StableSwap pool launch, and before the CAKE incentives are redirected and the new farm for USDC-BUSD, USDT-BUSD, USDC-USDT Stable LP is launched. If you are currently staking USDC-BUSD, USDT-BUSD, USDC-USDT LP in the farm you should:

1 - Unstake V2 LP from the [Farms Page.](https://pancakeswap.finance/farms)

<figure><img src="https://lh6.googleusercontent.com/7d4gCf4tKDt45xtcC3-0HJWdi3SO-1-vTf0dZzzTg75taCWNhHpye1OQOEeMd8LM2UuKAWgmY6wRuG1Iw7vaH80nkK9j91L0_xI3u1AD1LAosAW2mEsxilvl49EowEBy9mjWH3BGgFzLsMqWxUYzuRtOPbkBhI9epVYXlLaoRCNRPEoCSTfTTzQqfw" alt=""><figcaption></figcaption></figure>

2 - Remove liquidity of your LP at the [liquidity page](https://pancakeswap.finance/liquidity)

3 - Add liquidity again (this time you should see that you’re adding to Stable LP during the process)

![](https://lh5.googleusercontent.com/cB4cqAFzpEhnBDCrecAc\_oks\_2xu7gBc\_6BuRupnDNvrOe9MrW\_WF11NGRzu490KZ\_R26ZPRwwmAyRGr2Q14nLORFxzBVV4w98dC1jJvv7I-yfMdsxpNHF9uHxAGwOtFAz6GsyYlJUG2CdxK5\_7BfnhWDnO9U7IfR0b3i0Hfke33sOqQ5axWdHxscQ)

4 - Stake your Stable LP in the [farms page](https://pancakeswap.finance/farms) – look for the card with the Stable LP label

![](https://lh6.googleusercontent.com/wWGXLFRQFMesilP4pMEUieR-qezbiCdTVhT7geBJuDwIIcC4hqwzgOjEIvRkViBVj-j4hmc9K5fB6vhuHJk8ZyrQfYBRqK1e2yGkiJZhlH5J4PDJu-xT6us-x9dVbodhAW5mm8qZ5yb8HkRrZy1bRz4SKc26jm1lMpTiV3S6tT1WyDtHL8Yj13rp8w)

## Timeline:

* USDC-BUSD, USDT-BUSD, USDC-USDT liquidity provision enabled: **Nov 30 2022 11:00 UTC**
* Farm migration (CAKE rewards redirect from USDC-BUSD, USDT-BUSD, USDC-USDT LP Farm to USDC-BUSD, USDT-BUSD, USDC-USDT Stable LP Farm): **Dec 1 2022 11:00 UTC**
