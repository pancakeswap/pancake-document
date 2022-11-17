# vCAKE

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

If your remaining staking duration is less than one week, your vCAKE is equal to the amount of CAKE locked in the CAKE pool.

If your remaining staking duration is more than one week, your vCAKE is equal to the amount of CAKE locked, multiplied by the number of weeks left in the staking position.

For example:

* Alice locked 100 CAKE for 52 weeks; her staking position will unlock in 40 weeks. She has \`100 x 40 = 4000 vCAKE\`
* Bob locked 100 CAKE for 52 weeks; his staking position will unlock in 52 weeks. He has \`100 x 52 = 5200 vCAKE\`
* Carole locked 100 CAKE for ten weeks; and her staking position has ended. She has \`100 vCAKE\`

![](<../../.gitbook/assets/image (3) (2).png>)

### How to check the vCAKE number?

If you are casting a vote, you will find the number of vCAKE in the voting power breakdown by clicking the ">" button on the "Confirm Vote" window.

![](<../../.gitbook/assets/how-to-vote-5 (1).png>)

If you are making a community proposal, you can check your voting power by clicking "Check your voting power" at the bottom of the "Actions" panel.
