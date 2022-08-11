# FAQ

![](../../../.gitbook/assets/how-bCAKE-FAQ.png)

### How are the bCAKE multipliers calculated?

You may notice that you get different bCAKE boost multipliers when staking in different farms.

That's because bCAKE - Farm Boosters multipliers are calculated using the following metrics upon activation or refresh:

* `userLpStakedAmount` : The number of LP tokens you are staking in the farm
* `totalLpStakedAmount` : The total number of LP tokens in the farm
* `userLockedAmount` : The number of CAKE you are staking in the fixed-term staking CAKE pool
* `userLockedDuration` : The staking duration of your fixed-term staking position
* `totalLockedAmount` : The total number of locked CAKE in the fixed-term staking CAKE pool
* `averageLockedDuration` : The average staking duration of the fixed-term staking CAKE pool

The multiplier is calculated using the following method:

1. `resultA = constantA * userLpStakedAmount`
2. `resultB = (totalLpStakedAmount * userLockedAmount * userLockedDuration / constantB) / (totalLockedAmount * averageLockedDuration)`
3. `boostMultiplier = min(userLpStakedAmount, (resultA + resultB)) / resultA`

`constantA` and `constantB` are set by the kitchen and subject to future adjustments based on community feedback and market condition.

Here are some examples of the calculation:

![](../../../.gitbook/assets/bCAKE-params.png)

![](../../../.gitbook/assets/bCAKE-cal.png)

{% hint style="info" %}
**TL;DR**

The more LP you want to boost

The more CAKE you need to lock for longer durations
{% endhint %}

### Why do my multipliers change even after activation?

Please note that any user actions to the farms or CAKE staking pool will automatically update your boost multiplier based on the latest data and statistics from farms and the CAKE staking pool, including but not limited to:

* Stake/Unstake LP tokens to/from Farm
* Harvest CAKE rewards from Farm
* Extend your CAKE staking duration
* Add more CAKE into your fixed-term staking position
* Convert your CAKE staking position to flexible

{% hint style="warning" %}
Please note:&#x20;

In order to ensure fairness and prevent potential abuse and cheating using out-of-date data. Farm booster is designed to be community governance. Therefore, anyone can call `refresh(address _user, uint256 _pid)` function on the farm booster contract (link) to refresh anyone's boost multipliers using the latest data.
{% endhint %}

### Where are my CAKE rewards after activating or unsetting the booster?

![](../../../.gitbook/assets/bCAKE-has-pending-balance.png)

While farming with bCAKE - Farm Boosters, some of your harvested CAKE rewards may be temporally stored in the farm booster contract. Whenever this happens, you will see a dotted line under your "CAKE EARNED", indicating that apart from the number shown, you have more CAKE rewards in the farm booster contract.

**This part of the CAKE rewards will be automatically sent to your wallet upon the next harvest, deposit or withdrawal.**

To harvest them right now, simply click the "Harvest" button.

![](../../../.gitbook/assets/bCAKE-has-pending-balance-tooltip.png)

To check the number of extra rewards in the farm booster contract, hover or long-press the number with the dotted line.
