# FAQ

### I have an active position, why I can not vote? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Please ensure your unlock time is equal to or later than 1 week after the snapshot time of the current epoch.&#x20;

If your position is unlocking at the snapshot time, it means you have 0 veCAKE at the snapshot time. Therefore you are not able to vote.



### Can vote right after I set up a veCAKE position?

Yes.

Once your position is set up, you can use your cake to vote right away.

However:

* No votes can be cast within the last 24 hours of an epoch.
* You can not update your voting decision on a specific gauge more frequently than 10 days.
* Please ensure your position is not unlocking earlier than or at the snapshot time.



### Can I gain more veCAKE or votes?

Yes, simply add more CAKE or extend your lock position.

Please note that after gaining more veCAKE by adding CAKE or extending lock time. You need to manually update every gauges by re-submitting the vote request.



### Why did the voting results change after the tallying period?

During tallying period, the PancakeSwap Kitchen will cast its votes based on various metrics from all the gauges.&#x20;

The goal is to:

* Ensuring core liquidity pools are provided a competitive return on their LP positions
* Ensuring that existing Syrup Pool partner arrangements are met before migrating them fully to the veCAKE gauge voting system
* Ensuring that any of the smaller farms which did not receive any votes after the launch of veCAKE will receive at least some allocation in the initial rollout, capped at their current emission levels.

Check out this proposal for more detail: [https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c](https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c)



### Why my vote numbers are decreasing?

Because when we vote on gauges, we vote using our veCAKE. And veCAKE balance gradually decreases with the remaining lock time.&#x20;

Your votes will decrease all the way to 0 upon your veCAKE position unlocking.

To gain more votes, acquire more veCAKE by adding more CAKE to the lock, or extending the lock.



### After getting more veCAKE, why can't I vote for more gauges?

When voting on gauges, we cast our votes by defining how much % of our veCAKE goes to each gauge.

Therefore, even though you gained more veCAKE. If you have allocated 100% of your veCAKE in the previous 10 days, you can not change the decision until the end of the 10-day cooldown period.



### Voting results are tallied, why emission rate is not changing?

It takes roughly 72 hours to apply the voting results to various emission products on PancakeSwap. Chefs will continue to automate this process to shorten the gap as well as improve accuracy.



### Why did the gauge I voted for not receive any CAKE emissions in the next epoch?

Whitelisted gauges need to receive votes that correspond to minimally 1 CAKE per day in emissions, before they can receive any CAKE.
