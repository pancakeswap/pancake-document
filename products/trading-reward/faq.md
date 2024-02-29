---
description: Trading Reward FAQ
---

# FAQ

<figure><img src="../../.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## Generic

#### Why my traded volume was not tracked?

* Volume numbers take time to update and are subject to SubGraph delays. Please check back in a later time
* Your trade must be routed through the **exact** trading pair being highlighted on the [Trading Reward page](https://pancakeswap.finance/trading-reward#rewards-breakdown), including the fee tier. Check out [this tutorial](https://docs.pancakeswap.finance/products/pancakeswap-exchange/fees-and-routes#check-the-fee-rate-and-fee-amount-that-is-currently-applied) for how to view your trading routes
* Only V3 trading pairs are eligible for this program
* Please use the same wallet address eligible for the trading reward program on both Ethereum and BNB Chain
* If your trading volume within a pair is too small, you may not be eligible to claim any rewards
* Using third-party trading aggregators may result in trades being routed through other liquidity providers and not being tracked

#### Why I traded a lot but only received a very small amount of rewards

The amount of the trading reward is based on the trading fee paid in those trades.

If your trades are routed through pairs with a low fee tier, for example, 0.01%, you are paying a very small fee for your trade. Therefore the number of rewards will become lower accordingly.



## Top Traders Campaign

#### Do I need to stay within the required ranking for the whole time to win the campaign?

No, you only need to be ranked higher than the required ranking **at the end of the campaign**. But it is recommended to rank higher and maintain the rank. And make sure to check back often to ensure you are not falling out of the required ranking.

#### What number the ranking is based on?

The ranking is based on the number of rewards each user accumulates by trading. The reward amount equals a fixed % of the trading they pay in the trades.



## CAKE Stakers Campaign

#### My address was eligible for the previous campaign. Why is it not eligible for the latest one?

Each campaign has its own eligibility requirements, like the minimum threshold for veCAKE amount at snapshot time.

Also, snapshot time is set to be each campaign's end time. With veCAKE decreasing with time, your veCAKE balance may drop below threshold for future campaigns.

You may need to increase your veCAKE. Simply follow the instructions on the page.

#### Why is it telling me I have additional rewards that can not be claimed?

![](<../../.gitbook/assets/image (69).png>)

The amount of veCAKE at snapshot time will determine the maximum amount of rewards you can earn from the campaign. Check out the footnote from the “Max Reward Cap” section.

While a campaign is active, you can increase your veCAKE and raise this cap at any time.

#### What is “veCAKE at snapshot time”

veCAKE is gradually decreasing with time as the remaining lock time decreases. Therefore, similar to IFO iCAKE, a snapshot veCAKE balance - the veCAKE balance at a specific time, which is static, is better suited to be utilised as a qualification metric.

In Trading Reward, snapshot time refers to the end of each campaign. Therefore, your “veCAKE balance at snapshot time” means “your veCAKE balance at the campaign end time”.

#### How is “veCAKE at snapshot time” related to the campaign

* Your number of veCAKE balance at snapshot time is higher than the required threshold
* The maximum amount of rewards you can earn is linked to y % of your veCAKE balance at snapshot time

For example:

1. Alice locked 300 CAKE for 2 years (104 weeks) on day 1. On day 1, Alice will have a veCAKE balance of `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149` .
2. A trading reward campaign is launched on day 1, with a threshold veCAKE of 100, and a 1% reward cap. The campaign is ending in 30 days.
3. After 30 days, Alice’s position will have a remaining lock time of roughly 99.71 weeks, therefore a veCAKE balance of `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143`.
4. Therefore, for this campaign, Alice will have `143` veCAKE at snapshot time.
5. 143 is larger than 100 so Alice is eligible for the campaign, she may start trading eligible pairs to earn trading rewards.
6. With 1% reward cap, the maximum amount of CAKE Alice may earn from this campaign is `143 * 1% = 1.43` CAKE.
7. Alice may increase her veCAKE any time before the campaign ends, either by locking more CAKE, or extending her position.

#### How can I check my veCAKE at snapshot time during the campaign?

You may check on the Trading Reward page.

The page will alert you when your veCAKE at snapshot time is lower than the threshold or your rewards are currently being capped by it.

In those cases, you may click the “Increase veCAKE” button to increase your veCAKE without leaving the page.

#### Can I increase my veCAKE during the campaign?

Yes, you may increase your veCAKE any time before the campaign ends. Your “veCAKE at snapshot time” will get updated accordingly.
