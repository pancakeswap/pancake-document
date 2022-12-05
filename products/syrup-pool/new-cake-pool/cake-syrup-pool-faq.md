# CAKE Syrup Pool FAQ

## FAQ

### What lock duration can we choose?

You can choose from 1-52 weeks. What do you prefer?

### What variables affect the new CAKE Syrup Pool yield %s (Flexible and Fixed-Term Staking options)?

Since flexible staking and fixed-term staking options are part of the same pool, the following variables affect the yield% (APR/APY) of both:

* Total CAKE staked in flexible staking and fixed-term staking (the sum of both). The more CAKE staked, the lower the APR/APY.
* Total locked CAKE in fixed-term staking. The more CAKE locked means more yield boosts, resulting in fewer CAKE rewards for others (especially flexible staking).
* The average lock duration of all CAKE locked in fixed-term staking. If the average lock duration increases, APR/APY will decrease.

### Can I harvest the rewards during the locked period?

No. You can harvest the rewards only when the locked duration is ended. This is based on the yield/return we are providing as well as the technical implementations.

### Can I extend the lock duration?

Yes. Extending the lock duration adds more time to your **initial lock duration**. When choosing to extend your lock duration, note:

New extended lock duration = initial lock duration + added duration

### Can I remove my CAKE from Fixed-Term staking via contract if I change my mind?

No. Your CAKE cannot be removed or withdrawn from fixed-term staking at any point in time until your lock duration ends and your CAKE is unlocked.

### What is the "CAKE Locked" amount?

The "CAKE Locked" amount is a user's initial locked CAKE balance plus CAKE rewards to date.&#x20;

CAKE Locked = Initial locked CAKE balance + CAKE rewards

When adding more CAKE to fixed-term staking, the "CAKE to be locked" amount is the user's initial locked CAKE balance, CAKE rewards to date, and the CAKE being added.

### Can the Fixed-Term Staking CAKE pool APR change after I lock my CAKE?

Yes, the fixed-term staking CAKE pool APR is variable, just like the old CAKE pools. The fixed-term staking CAKE pool APR is not fixed and is dependent on:

* Total CAKE staked in the CAKE pool (the sum of both Flexible + Fixed-Term Staking).
* The average lock duration of all CAKE locked in fixed-term staking.
* A yield boost (similar to a multiplier) calculated from a user's initial lock duration. The longer you lock your CAKE, the higher the yield boost.

For example, if you lock your CAKE for 52 weeks, your yield boost will be larger than if you lock your CAKE for 26 weeks. The yield boost increases linearly the longer you lock your CAKE.

### Can I still participate in IFOs if my CAKE is locked in the Fixed-Term Staking pool, or will I need to buy more CAKE?

No, a separate amount of CAKE is needed. However, locked-staking provides entry for IFO public sales. Check out [iCAKE](../../ifo-initial-farm-offering/icake.md).

### Can I vote if my CAKE is locked in the Fixed-Term Staking pool?

Yes! Check out [vCAKE](../../voting/vcake.md).

### Can I use both the Flexible Staking CAKE pool and the Fixed-Term Staking CAKE pool at the same time?

Yes, when you are doing fixed-term CAKE staking. A flexible CAKE staking side-pool will automatically appear for you to choose from.

### Is there a fee for converting Flexible Staked CAKE to Fixed-Term Staked CAKE?

No. There are no additional fees for moving CAKE from flexible staking to fixed-term staking, only gas fees.

### What happens at the end of the lock duration? What is "After Burning"?

When your fixed-term staking period ends, and your CAKE unlocks, you have 7 days to complete one of two options:

* Lock your CAKE to begin a new fixed-term staking period\
  or
* Convert your staked CAKE to flexible staking (no 72-hour withdrawal fee).

![](<../../../.gitbook/assets/Locked - lock ended - before after burning.png>)

During these 7 days, you will still earn CAKE.

After 7 days, if you have not done one of the two options, your staked CAKE will enter what is called "After Burning". With "After Burning", your CAKE rewards will start to be sent to burn. The % of CAKE rewards being sent to burn will linearly increase in the 90 days "After Burning" period until it reaches 100%, which means all the CAKE rewards are burnt.

So, to avoid missing out on CAKE rewards, we recommend starting a new fixed-term staking period or converting your CAKE to flexible staking at the end of your lock staking period.

![](<../../../.gitbook/assets/Locked - lock ended - after burning started.png>)
