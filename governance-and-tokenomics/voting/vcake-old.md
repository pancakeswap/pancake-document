# vCAKE (old)

{% hint style="info" %}
We are transitioning from vCAKE to veCAKE for our governance system. Once the migration is done, not all information on this page will apply.
{% endhint %}

### What is vCAKE?

vCAKE is a number representing the boosted voting power based on a user’s fixed-term CAKE staking position.

The vCAKE number will be added to your total voting power.

**Similar to iCAKE, vCAKE is NOT a new token.**

vCAKE IS NOT transferrable or tradeable.

### How is vCAKE calculated?

vCAKE is calculated based on two variables:

1. The amount of CAKE located in the Fixed-Term Staking Pool
2. The remaining lock durations of the staking positions

For point 2., it is important to clarify that the remaining lock duration is not (a) how many weeks you committed your CAKE for when you first locked it up (e.g. 52 weeks), but (b) the time remaining on your lock. In this case, if you locked CAKE for 52 weeks around 10 weeks ago, your remaining lock duration is 42 weeks, not 52 weeks.

If your remaining staking duration is less than or equals one week, your vCAKE is equal to the amount of CAKE locked in the CAKE pool.

If your remaining staking duration is more than one week, your vCAKE is equal to the amount of CAKE locked, multiplied by the number of weeks left in the staking position.

For example:

* Alice locked 100 CAKE for 52 weeks; after 12 weeks, her remaining lock duration is 40 weeks. She has \`100 x 40 = 4000 vCAKE\` at that moment.
* Bob locked 100 CAKE for 52 weeks; his remaining lock duration is 52 weeks. He has \`100 x 52 = 5200 vCAKE\` at that moment.
* Carole locked 100 CAKE for 10 weeks; and after 10 weeks, her staking position ended. She has \`100 vCAKE\` at that moment.

![](<../../.gitbook/assets/image (3) (2) (1).png>)

### How to check the vCAKE number?

If you are casting a vote, you will find the number of vCAKE in the voting power breakdown by clicking the ">" button on the "Confirm Vote" window.

![](<../../.gitbook/assets/how-to-vote-5 (1).png>)

If you are making a community proposal, you can check your voting power by clicking "Check your voting power" at the bottom of the "Actions" panel.
