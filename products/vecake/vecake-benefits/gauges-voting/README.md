---
description: Use your veCAKE to vote and decide how CAKE emission is distributed
---

# Gauges Voting

<figure><img src="../../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

To understand gauges voting. You may think of any products that require CAKE emissions as a series of gauges. Like farms, CAKE weekly reward pool, position managers, etc...&#x20;

veCAKE holders can now use their veCAKE as votes to decide how much % of CAKE goes to which product.&#x20;

For example, if I'm currently farming with the CAKE-BNB farm on the BNB Chain, I would like to increase the amount of CAKE emission that goes to this particular farm. I can use my veCAKE to vote on this farm.&#x20;

## How to Vote?

### 1 - Understand the voting schedule

<figure><img src="../../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Gauges weight voting is conducted every two weeks. The beginning of an epoch, just like revenue sharing, is at 00:00 UTC every even Thursdays.

In the above example:

* Epoch 1 is starting at 00:00 UTC, 1st, Thursday on week 1.
* Epoch 1 is ending 2 weeks later, at 00:00 UTC, 15th, Thursday on week 3.
* Users can vote during 00:00 UTC from 1st to 14th.
* **NO** votes can be cast during 00:00 UTC from 14th to 15th as votes are being adjusted and tallied.
* Voting results will be snapshotted at 00:00 UTC on the 15th. The end of epoch 1.
* Voting results will be applied within 72 hrs after an epoch is closed.

### 2 - Become eligible

<figure><img src="../../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Since veCAKE is gradually decreasing according to the remaining lock time. Voting results will be snapshot at the end of every epoch. This includes the number of total veCAKE, and the veCAKE each user has.

In the above example:

* Results for epoch 1, will be based on the veCAKE balances at 00:00 UTC, 15th.
* Users whose veCAKE position is unlocking before or equal to 15th, will have 0 veCAKE balance at the snapshot time. Therefore they have no voting power for epoch 1.

Therefore, to become eligible, you must obtain an active veCAKE position, which unlocks **LATER** than the end/snapshot time of the current epoch.&#x20;

In the above example:

* If you want to vote in epoch 1, you must have a veCAKE position which unlocks on the 21st or later than the 21st, or Thursday on week 3.

### 3 - Check the current voting results

Head to "CAKE staking", scroll down and look for the "Gauges Voting" section, then click "Check Gauges".

<figure><img src="../../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

At the top-left section. You may find:

* Your veCAKE.
* Snapshot time and voting end time for the current epoch.
* The total number of CAKE rewards to be distributed in the next epoch is based on the voting results from the current epoch.
* The total amount of veCAKE votes cast.

At the top-right, you may find a pie chart representing the % of each gauge received.

At the bottom, there is a complete list of every voting gauges. With the number of votes they received and the expected % weight, they are gaining in the current epoch. There is also a "boost" and "caps" field, detailing two important gauge characteristics. Continue reading for more details.

#### Gauge Boost and Caps

To ensure CAKE rewards go to the most productive gauges. Each gauge can be applied with a boost and/or a cap. Two of the characteristics can both exist at the same time.

Boost is a multiplier applied to the number of votes a gauge receives.

Cap is a maximum cap on the % weight a gauge can gain.

For example:

* A gauge has 10 votes, 2x boost and 15% cap. The total vote is 100.&#x20;
* After applying the boost, this gauge will have 20 votes, 20% weight against the total (100).
* However, since it has a 15% cap, the final % of CAKE rewards this gauge receives in the next epoch will be adjusted to 15%.

{% hint style="info" %}
Please note that the voting results are updated weekly. Numbers are calculated based on the veCAKE balances at 00:00 UTC, the coming Thursday.  &#x20;
{% endhint %}

### 4 - Add gauges to vote

<figure><img src="../../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

To vote on a gauge, scroll down and look for "My Votes" section. Click "Add Gauge".

In the pop-up window, you may add gauges to your list of votes by clicking the blue "+" icon. You may find the current voting results in the list, along with boost and caps.

To quickly locate a gauge, you can use filtering to filter gauges by blockchains, fee tiers and liquidity types. Or type in the token ticker into the search field.

### 5 - Select how much % veCAKE to vote on each gauges

<figure><img src="../../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

Once you have added the gauges, you may select how much % of your veCAKE goes to each of the gauges.

This is because:

* veCAKE gradually decreases with the remaining lock time. It is impractical to estimate and calculate how many exact veCAKE to vote.
* It is troublesome to re-vote in every upcoming epoch. Therefore, gauges voting is designed to carry your voting decisions throughout all the upcoming epoch until you cast a new one.

In the above example:

* At the moment, I have 2.62 veCAKE.
* I decided to allocate 80% to CAKE-BNB, which is 2.10 veCAKE at the moment.
* 20% to USDC-ETH, which is 0.52 veCAKE, again, at the moment.
* My total veCAKE will gradually decrease along with the remaining lock time. At the snapshot time, I may have less veCAKE, but my decision of 80% - 20% split will still be applied to the final results.
* On top of that, this 80% - 20% decision will be applied to every coming epoch until I update it by casting a new vote request. Or until my veCAKE goes to 0 due to unlocking.

Once you have confirmed your decision, click "Submit vote" and confirm in your wallet.

### 6 - Update your votes

<figure><img src="../../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Once your vote is submitted, you may see your votes being updated to "Current Votes". And the remaining veCAKE gets updated.

Please note that the voting decision for each gauge can only be updated every 10 days. Once you submit a vote request, all voted gauges will be applied a 10-day cooldown period before you can submit another request for updates.

To update your vote decision, change the % percentage and submit again.

{% hint style="info" %}
Please note that after gaining more veCAKE by adding CAKE or extending lock time. You need to manually update every gauges by re-submitting the vote request.

The 10 days cooldown period still applies regardless if you changed your % decisions.
{% endhint %}
