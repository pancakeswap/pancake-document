# FLASK Syrup Pool FAQ

## FAQ

### What lock duration can we choose?

You can choose from 1-52 weeks. What do you prefer?

### What variables affect the new FLASK Syrup Pool yield %s (Flexible and Fixed-Term Staking options)?

Since flexible staking and fixed-term staking options are part of the same pool, the following variables affect the yield% (APR/APY) of both:

* Total FLASK staked in flexible staking and fixed-term staking (the sum of both). The more FLASK staked, the lower the APR/APY.
* Total locked FLASK in fixed-term staking. The more FLASK locked means more yield boosts, resulting in fewer FLASK rewards for others (especially flexible staking).
* The average lock duration of all FLASK locked in fixed-term staking. If the average lock duration increases, APR/APY will decrease.

### Can I harvest the rewards during the locked period?

No. You can harvest the rewards only when the locked duration is ended. This is based on the yield/return we are providing as well as the technical implementations.

### Can I extend the lock duration?

Yes. Extending the lock duration adds more time to your **initial lock duration**. When choosing to extend your lock duration, note:

New extended lock duration = initial lock duration + added duration

### Can I remove my FLASK from Fixed-Term staking via contract if I change my mind?

No. Your FLASK cannot be removed or withdrawn from fixed-term staking at any point in time until your lock duration ends and your FLASK is unlocked.

### What is the "FLASK Locked" amount?

The "FLASK Locked" amount is a user's initial locked FLASK balance plus FLASK rewards to date.&#x20;

FLASK Locked = Initial locked FLASK balance + FLASK rewards

When adding more FLASK to fixed-term staking, the "FLASK to be locked" amount is the user's initial locked FLASK balance, FLASK rewards to date, and the FLASK being added.

### Can the Fixed-Term Staking FLASK pool APR change after I lock my FLASK?

Yes, the fixed-term staking FLASK pool APR is variable, just like the old FLASK pools. The fixed-term staking FLASK pool APR is not fixed and is dependent on:

* Total FLASK staked in the FLASK pool (the sum of both Flexible + Fixed-Term Staking).
* The average lock duration of all FLASK locked in fixed-term staking.
* A yield boost (similar to a multiplier) calculated from a user's initial lock duration. The longer you lock your FLASK, the higher the yield boost.

For example, if you lock your FLASK for 52 weeks, your yield boost will be larger than if you lock your FLASK for 26 weeks. The yield boost increases linearly the longer you lock your FLASK.

### Can I still participate in IFOs if my FLASK is locked in the Fixed-Term Staking pool, or will I need to buy more FLASK?

No, a separate amount of FLASK is needed. However, locked-staking provides entry for IFO public sales. Check out [iCAKE](../../ifo-initial-farm-offering/icake.md).

### Can I vote if my FLASK is locked in the Fixed-Term Staking pool?

Yes! Check out [vCAKE](../../../protocol/voting/vecake.md).

### Can I use both the Flexible Staking FLASK pool and the Fixed-Term Staking FLASK pool at the same time?

Yes, when you are doing fixed-term FLASK staking. A flexible FLASK staking side-pool will automatically appear for you to choose from.

### Is there a fee for converting Flexible Staked FLASK to Fixed-Term Staked FLASK?

No. There are no additional fees for moving FLASK from flexible staking to fixed-term staking, only gas fees.

### What happens at the end of the lock duration? What is "After Burning"?

{% hint style="warning" %}
**After Burning will burn the future FLASK rewards and the FLASK rewards already earned.** To avoid losing any FLASK rewards you already earned, we recommend starting a new fixed-term staking period or converting your FLASK to flexible staking at the end of your lock staking period.
{% endhint %}

When your fixed-term staking period ends, and your FLASK unlocks, you have 7 days to complete one of two options:

* Lock your FLASK to begin a new fixed-term staking period\
  or
* Convert your staked FLASK to flexible staking (no 72-hour withdrawal fee).

![](<../../../.gitbook/assets/Locked - lock ended - before after burning.png>)

During these 7 days, you will still earn FLASK.

After 7 days, if you have not done one of the two options, your staked FLASK will enter what is called "After Burning". **With "After Burning", your FLASK rewards (including the rewards already earned) will start to be sent to burn.** The % of FLASK rewards being sent to burn will linearly increase in the 90 days "After Burning" period until it reaches 100%, which means all the FLASK rewards are burnt.

So, to avoid missing out on FLASK rewards, we recommend starting a new fixed-term staking period or converting your FLASK to flexible staking at the end of your lock staking period.

Here is an example:

> John staked 100 FLASK for 52 weeks, he earned 50 FLASK during his staking period, and now the staking period has expired.&#x20;
>
> He then didn't perform any actions, and his position went into "After Burning" mode.
>
> During the 90-day After Burning period, all of the 50 FLASK he earned will be burned gradually along with any new FLASK earned.&#x20;
>
> After 90 days, the rewards he actually earns will become 0. However, the 100 FLASK he initially deposited will not be affected.
>
> Start a new fixed-term staking period or convert to flexible staking, and don't be like John.

![](<../../../.gitbook/assets/Locked - lock ended - after burning started.png>)
