# FAQ

### I’ve locked my CAKE or migrated my CAKE pool position. Why do I still have 0 shares? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Shares are updated upon each weekly distribution at 00:00 UTC every Thursday.

Rewards are accumulated whenever you have finished staking for a complete epoch.&#x20;

Epochs are 7-day periods, starting every Thursday, UTC 00:00. For example, if you stake on Tuesday. Your first epoch will start on Thursday. Once you have finished staking till the next Thursday. You will be able to claim your rewards from this Thursday to next Thursday, aka epoch 1.

Check back again each Thursday for updated reward numbers.

### Why are my shares/rewards being 0 despite having an active staking position? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

When calculating rewards. The remaining lock duration is rounded down to weeks. Therefore, to receive shares, you must ensure your staking position unlocks no earlier than the very next Thursday 00:00 UTC.

For example, week 1 starts at 00:00 UTC, Thursday, 1 Jan. To receive rewards for the week 1 distribution. You must:

* Join before 00:00 UTC, 1 Jan.
* Have an active veCAKE staking position, which unlocks equal to or later than 00:00 UTC, 15 Jan. (Thursday on week 3)

Please note that if your staking position unlocks at 00:00 UTC, 8 Jan (Thursday on week 2). You will still receive 0 rewards for week 1 due to your veCAKE balance turning at 00:00 UTC, 8 Jan.

### Can I join a distribution period mid-week? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

No, as mentioned, rewards can only start to accumulate when you are already staking at the beginning of the epoch. Which is every week at 00:00 UTC, Thursday.&#x20;

### How do I receive more rewards? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Since your shares in pools are calculated based on veCAKE balance at the distribution time, which is at 00:00 UTC next coming Thursday. To receive more rewards, simply bump up your veCAKE balance by:

* Locking more CAKE in the veCAKE staking position
* Renewing your staking position

Please note that after adding CAKE or extending, your shares will only update after the beginning of the next epoch, which is 00:00 UTC, the coming Thursday.

### Why are the weekly injected rewards not 100% matching the volume displayed on various trackers (like the Info page)? Why are the weekly CAKE pool rewards not 100% matching the gauges voting results.

The number of CAKE rewards injected weekly may not be 100% matching with the numbers calculated from the volume displayed on various trackers. Multiple external factors may impact the number of CAKE rewards that can be converted:

* CAKE token price while the trading fee is being converted and processed
* Underlying asset prices while the trading fee is being converted and processed
* To save gas and operational cost. Revenues from blockchains other than BNB Chain are processed monthly. They will be injected with a one-month delay with weekly averaging.
* Some trading pairs may have insufficient liquidity while processing the trading fee.
* Some trading pairs may contain tokens with custom logic that prevent their fee from being processed.
* Transaction delays due to infrastructures and supportive system performance.

Chefs are working hard to apply tools and practices to ensure more trading fees generated can be processed and converted into CAKE.
