# FAQ

<figure><img src="../../.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### How are the shares (rCAKE) calculated? <a href="#50b7c683-feb0-47f6-809f-39c1a0976bb5" id="50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

Upon each weekly distribution, each user’s shares are re-calculated based on:

1. The amount of locked CAKE they have
2. The remaining lock duration of their locked CAKE rounded down to weeks, and the maximum allowed lock time (currently 52 weeks)

For example:

If a user has 50 CAKE locked and the remaining lock time is 10.3 weeks, then the user has `50 * (10 / 52 ) ~= 9.61` shares.

### I’ve updated my position; why do I still have 0 shares? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Shares (rCAKE) are updated upon each weekly distribution at 23:59 UTC every Wednesday. Check back again after the very next weekly distribution to view your updated shares.

### Why are my shares being 0 despite having an active staking position? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

When calculating shares (rCAKE), the remaining lock duration is rounded down to weeks. Therefore to receive shares, you must ensure your staking position unlocks no earlier than the very next distribution.

For example, to receive shares for the week 1 distribution. You must:

* Join before 23:59 UTC, 2 August.
* Have an active fixed-term CAKE staking position which unlocks later than 23:59 UTC, 9 August.

If your staking position unlocks earlier than 23:59 UTC, 9 August, you will receive 0 shares for week 1.

### Can I join a distribution period mid-week? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

No, as mentioned shares are calculated at the beginning of the distribution period at 23:59 UTC on Wednesday every week. Therefore you will receive shares starting from the next distribution and start accumulating rewards by then.

### How do I receive more shares? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Since shares are calculated based on CAKE amount and remaining lock duration, to receive more shares, you may:

* Lock more CAKE
* Extend your staking position

Please note that after adding CAKE or extending, shares are NOT updated in real time and only updated upon each week’s weekly distributions.

### Do I need to update my staking position when I add more CAKE or extend the staking? <a href="#71d1d397-ac1c-454b-abd9-15492860f05c" id="71d1d397-ac1c-454b-abd9-15492860f05c"></a>

No, you will only need to enrol once. All subsequent CAKE staking pool operations will automatically inform the revenue sharing pool and update your shares upon the next weekly distributions.

\
