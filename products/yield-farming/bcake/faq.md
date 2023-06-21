# FAQ

![](../../../.gitbook/assets/how-bCAKE-FAQ.png)

### How are the bCAKE multipliers calculated?

You may notice that you get different bCAKE boost multipliers when staking in different farms.

That's because bCAKE - Farm Boosters multipliers are calculated using the following metrics upon activation or refresh:

* `userLpStakedAmount` : The amount of liquidity you are staking in the farm
* `totalLpStakedAmount` : The total amount of liquidity staking in the farm or the current active amount of liquidity in the V3 LP pool. bCAKE V3 will choose the smaller number between the two
* `userLockedAmount` : The number of CAKE you are staking in the fixed-term staking CAKE pool
* `userLockedDuration` : The staking duration of your fixed-term staking position
* `totalLockedAmount` : The total number of locked CAKE in the fixed-term staking CAKE pool
* `averageLockedDuration` : The average staking duration of the fixed-term staking CAKE pool

The multiplier is calculated using the following method:

1. `resultA = constantA * userLpStakedAmount`
2. `resultB = (totalLpStakedAmount * userLockedAmount * userLockedDuration / constantB) / (totalLockedAmount * averageLockedDuration)`
3. `boostMultiplier = min(userLpStakedAmount, (resultA + resultB)) / resultA`

`constantA` and `constantB` are set by the kitchen and subject to future adjustments based on community feedback and market condition. `constantB` varies between different farms to compensate for the LP price differences.

But:

{% hint style="info" %}
**TL;DR**

The more LP (liquidity) you want to boost

The more CAKE you need to lock for longer durations
{% endhint %}

### Why do my multipliers change even after activation?

Please note that **any user actions to the farming position or CAKE staking pool will automatically update your boost multiplier** based on the latest data and statistics from farms and the CAKE staking pool, including but not limited to:

* Stake/Unstake position to/from the farm
* Harvest CAKE rewards from farm
* Extend your CAKE staking duration
* Add more CAKE into your fixed-term staking position
* Convert your CAKE staking position to flexible

{% hint style="warning" %}
Please note:&#x20;

To ensure fairness and prevent potential abuse and cheating using out-of-date data. Farm booster is designed to be permissionless and community governance. Therefore, **anyone** can call `updateLiquidity(address _tokenId)` function on the MasterChef V3 contract to refresh anyone's boost multipliers using the latest data.

On top of that, the kitchen will also monitor all bCAKE-enabled farming positions and will refresh any position with an out-of-date multiplier.
{% endhint %}

### Where are my CAKE rewards after activating or unsetting the booster?

In bCAKE V3, CAKE rewards are automatically harvested to your wallet when activating or unsetting a booster.

### Why I'm not able to boost a position

1. Farm booster is only available for selected farms. More farms will be made available in the future. For now, **look for the "Boosted" tag on the UI.**\
   ![](<../../../.gitbook/assets/bCAKE-boost-tag (1).png>)
2.  There is a **limit to the number of positions** you can boost simultaneously. To check the number of remaining boosters, refer to the panel on top.

    \
    ![](<../../../.gitbook/assets/bCAKE-farm-number-limit (1).png>)\
    You will need to unset an active booster in order to activate boosters on other farms.
3. Due to multiple contracts' involvement, some contract interactions require slightly more gas tokens (BNB). So please make sure you have enough BNB in your wallet.

### What is the maximum bCAKE Boost Multiplier I can get?

Currently, the maximum boost a user can get for a farm booster is 2x, which offers them double the original APRs.

### How can I increase my bCAKE Boost Multipliers?

* Add more CAKE into the fixed-term staking position
* Extend the duration of your fixed-term staking position

Simply put:

**Stake more CAKE, stake for longer**

[Learn more about how the bCAKE boost multipliers are calculated](faq.md#how-are-the-bcake-multipliers-calculated).

### Where are the extra boosted CAKE rewards coming from?

**Relax, no extra emissions are allocated in order to make bCAKE possible.**

Similar to fixed-term CAKE staking. bCAKE boosts individual users' share against others.

Even though the baseline APR may drop after the deployment of bCAKE. Chefs believe it is a good tradeoff as it benefits loyal CAKE lovers by boosting their farming yield, creates more demand for CAKE, and serves as a great incentive for CAKE staking.

### Why the multiplier I receive is low?&#x20;

bCAKE - farm booster works in a way by evaluating both your fixed-term CAKE staking position and your liquidity farming position against other users. Simply put:

> If users want to boost more liquidity in the farm, they must lock more CAKE for longer durations in the pool.

This design ensures the benefits are not only offered to large holders, but to any user who has a sizable CAKE staking position when compared to the farming position.

Learn more about how the multiplier is calculated [here](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated).

### Why are there only x number of farms that are booster-available?

Since bCAKE involves updating one of PancakeSwap's core products, which is liquidity farming. Chefs want to take a slower and more steady approach to the launch.

Therefore, in the initial product release phase. Many of the parameters are very conservative. Including the number of farms users can boost, which farm users can boost, as well as the difficulty parameter in receiving the boost multiplier.

After the initial release phase, **Chefs will adjust the parameters based on the community feedback.**

### **Is bCAKE V3 audited?** <a href="#68559543-51e4-438c-9a0a-1e6ece7d2133" id="68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE has been audited by both internal and external auditors.

Check out audit reports here: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)

