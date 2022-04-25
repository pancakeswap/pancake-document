# New CAKE Syrup Pool

## Stake CAKE, earn CAKE!

PancakeSwap now offers one CAKE Syrup Pool with two staking options: flexible staking or fixed-term staking. Note that the Auto CAKE, IFO CAKE, and Manual CAKE pools will be retired upon the launch of the new CAKE Syrup Pool with flexible and fixed-term staking. Keep reading on to learn more!

![\*Note that actual APY values will vary](../../../.gitbook/assets/cake-pool-enabled1.png)

## What’s the difference between “Flexible” and “Fixed-Term” staking?

With both, you can simply stake your CAKE tokens to earn more CAKE tokens with no deposit fees—both staking options auto-compound CAKE rewards for you. Flexible staking allows users to stake CAKE and earn rewards with the ability to unstake whenever they please. Fixed-term staking allows users to maximise their yield and earn even more CAKE by locking their staked CAKE for a period of time they choose, earning a linearly boosted APY compared to flexible staking.

Flexible staking and fixed-term staking are both part of the same pool to allow users easy migration between the two staking options. **Because of this, you can only choose one staking option at a time.** More details about the differences are below.

### Flexible Staking

Stake your CAKE and forget about it! The CAKE you stake in this Syrup Pool will be automatically compounded (reinvested) for you, minus a small fee (same as the old Auto CAKE Syrup Pool).

**If you have CAKE staked in flexible staking**

* ✅ Add more CAKE to flexible staking
* ✅ Harvest rewards any time
* ✅ Withdraw any time (fees apply for the first 72 hours, see below)
* ✅ Convert all staked CAKE in flexible to fixed-term staking
* ❌ Add CAKE to fixed-term staking if you have any CAKE in flexible staking
* ❌ Convert part of the staked CAKE in flexible to fixed-term staking

**Unstaking fee**

* **0.1%  if you unstake (withdraw) within 72 hours.**
* Only applies within 3 days of manually staking.
* After 3 days, you can unstake with **no fee**.
* The 3-day timer resets every time you manually stake more CAKE in the pool.
* This fee only applies to manual unstaking: it does not apply to automatic compounding.

**Performance fee**

* **2%, subtracted automatically from each yield harvest**.
* For example, if the harvest were 1 CAKE, then 0.02 CAKE would be subtracted as the performance fee.

The CAKE collected via the unstaking fee and performance fee is **burned every week** as part of the regular CAKE token burns.

This is a good thing for CAKE holders because it reduces the overall amount of CAKE tokens in existence, which helps reduce inflation.

### Fixed-Term Staking

Stake your CAKE for a fixed amount of time to maximise yields and receive additional benefits! The staked CAKE will be automatically compounded during the entire lock duration.

* No performance fees
* The longer you lock, the higher the boost applied to the yield!
* CAKE rewards are auto-compounded and will unlock, along with your staked CAKE, when your lock duration expires
* Once staked in fixed-term staking, you cannot withdraw until the end of your lock duration.
* IFO CAKE credit (the maximum amount of CAKE they can commit during an IFO) will be determined from the fixed-term staking pool

**If you have CAKE locked in fixed-term staking**

* ✅ Add more CAKE to lock
* ✅ Extend lock period
* ❌ Add CAKE to flexible staking
* ❌ Harvest rewards
* ❌ Withdraw before locked term ends

Chefs are cooking up additional benefits in the kitchen for Q2!

## FAQ

### What lock duration can we choose?

You can choose from 1-52 weeks. What do you prefer?

### Can I harvest the rewards during the locked period?

No. You can harvest the rewards only when the locked duration is ended. This is based on the yield/return we are providing as well as the technical implementations.

### Can I extend the lock duration?

Yes. Extending the lock duration adds more time to your **initial lock duration**. When choosing to extend your lock duration, note:

New extended lock duration = initial lock duration + added duration

### Is the Fixed-Term Staking CAKE pool APY fixed or variable?

The APY is variable, just like the previous CAKE pools. The fixed-term staking CAKE pool APY is fixed and dependent on:

* Total CAKE staked in the CAKE pool (the sum of both Flexible + Fixed-Term Staking)
* A yield boost (similar to a multiplier) calculated from a user's initial lock duration.&#x20;

For example, if you lock your CAKE for 52 weeks, your yield boost will be larger than if you lock your CAKE for 26 weeks. The yield boost increases linearly the longer you lock your CAKE.

### Can I use both the Flexible Staking CAKE pool and the Fixed-Term Staking CAKE pool at the same time?

No. As mentioned above in the "What’s the difference" section, both options are part of the same, single pool. You currently can **never** have CAKE in both fixed-term and flexible staking.

We have multiple solutions coming in the future to allow users to use both flexible staking and fixed-term staking at the same time, but for now, you can choose only one of them.

### What happens at the end of the lock duration? What is "After Burning"?

When your fixed-term staking period ends, and your CAKE unlocks, you have 7 days to complete one of two options:

* Lock your CAKE to begin a new fixed-term staking period\
  or
* Convert your staked CAKE to flexible staking (no 72-hour withdrawal fee).

![](../../../.gitbook/assets/cake-pool-lock-end.png)

During these 7 days, you will still earn CAKE at the same APY as your lock period.

After 7 days, if you have not done one of the two options, your staked CAKE will enter what is called "After Burning". In "After Burning", you will still earn CAKE, but a portion of your rewards will be sent to burn at a linearly decreasing APR over 90 days, where your APR will be 0% after 90 days.

The “After Burning” state will last for 90 days until all the CAKE rewards are burnt. So, to avoid missing out on CAKE rewards, we recommend starting a new fixed-term staking period or converting your CAKE to flexible staking at the end of your lock staking period.

![](../../../.gitbook/assets/cake-pool-lock-burn.png)
