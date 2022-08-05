# 🍯 Pottery

![](https://lh4.googleusercontent.com/ADDYnmpe6t1befgamqDj-6KYXqYWWp\_5ed6zL27QmyGcu9GqHd1HMh6JXIJdXgUYVISNuXDQEkvIhsFB5mCyTJRt99iW0-WfvszMMZQB3z9z3OAT9lzH3FsTeKZnoa2UaGdft3iYVU4\_t5oEsViNKvQ)

Pottery combines CAKE lock-staking with lottery elements to give you a chance to win a bigger yield on your CAKE deposit! It is easy and safe as you will always at least get back all the CAKE you deposit.

## Specifics:

* Deposit CAKE in the Pottery page with a minimum of 1 CAKE&#x20;
* Deposit closes on the first Monday of each month for a different Pottery cohort (23:59 UTC on that Monday) and is open from the Friday before that at around 10:00 UTC, unless there are special arrangements which will be announced in advance (first Pottery is closing on Aug 8 2022 23:59 UTC)
* During the beta stage of the product, there is a cap to the total CAKE deposit for each Pottery cohort (the maximum deposit cap is 600,000 CAKE)
* CAKE deposited will be directed to the lock-staking pool and locked for ten (10) weeks 80% of the total staking rewards will be sent to the Pottery pool for drawing, 20% will be reserved for your withdrawal&#x20;
* For each Pottery cohort (one per month), there will be ten (10) weekly draws on each Friday (at noon UTC) upon deposit producing eight (8) winners per week, each address may win more than one of the eight winner slots each week&#x20;
* The larger your deposit relative to the overall pool, the higher the chance of winning, winners can claim their prize right after each draw&#x20;
* Each Pottery cohort conducts the draw separately&#x20;
* Only after 10 weeks from the Pottery cohort lock date, you can withdraw your CAKE&#x20;
* Pottery uses Chainlink's implementation of VRF for true, secure randomness

## Pottery Cohort&#x20;

On the first Monday of each month, a Pottery cohort will be open for you to deposit CAKE and participate in it for the next 10 weeks. This arrangement combines the deposit to direct to the locked staking pool, such that the Pottery contract of the cohort is able to coordinate the staking rewards of the deposit from the locked staking pool.

Each deposit and lock date will be a separate cohort – one for each month – e.g. all deposits on Sep 5 2022 will be in one cohort, all deposits on Oct 3 2022 will be in another cohort.

While draws may happen concurrently for different cohorts, the prize pools for each cohort are separated to be fair.

![(For illustration purposes only, actual cohort lock date for the first Pottery has been set to Aug 8 2022)](https://lh5.googleusercontent.com/KamNAZK7s2N454cI\_cvnjHJpuAH8HfgWlmEXZevzDVW\_uxiw\_pymKZCp97L9hSjcGGzjjQeGuSt7oOIOXECq\_xoU47zEC4rhJp2IA37ROeUOUSqXKgqKjNqcJnHOopC8mi5IeqR9UAprhNF5zM4PLjc)

For example, there are 2 separate draws on Sep 9 2022, one for the Aug 1 cohort as the sixth weekly draw and another for the Sep 5 cohort as the first weekly draw. If the Aug 1 cohort has a total of 100,000 CAKE deposited and the Sep 5 cohort has a total of 300,000 CAKE deposited, the weekly prize for the Aug 1 cohort will only come from the staking rewards of those 100,000 CAKE, while the weekly prize for the Sep 5 cohort will only come from the staking rewards of those 300,000 CAKE. If you only deposited CAKE in the Aug 1 cohort, you have a chance to win the weekly prize on Sep 9 based on the staking rewards of 100,000 CAKE. If you deposited CAKE in both the Aug 1 and Sep 5 cohort, you have a chance to win both weekly prizes on Sep 9.

## **Prize Funding & Staking Rewards Allocation**

The deposits are grouped into monthly cohorts for more efficient arrangement of the staking rewards which are also grouped together for each cohort. The staking rewards are used to fund the prize pool and some staking rewards for depositing into the Pottery.

80% of the staking rewards will be directed to fund the prize pool for 10 weekly draws and the rest 20% will be reserved as staking rewards when you withdraw your CAKE deposit after 10 weeks.

However, since the staking rewards of the CAKE locked staking pool are only distributed after the lock duration – 10 weeks in this case, for better product experience and to facilitate the weekly draws right after the deposit date, the contract is borrowing 80% of the estimated total staking rewards from the cohort from the CAKE treasury based on the APY at the time of locking. The borrowed CAKE is used for the payout for each weekly draw.

At the end of the 10 weeks, when the rewards are distributed from the staking pool, the CAKE treasury will be repaid first, then the rest will be directed back to the vault for users to withdraw together with their initial deposit in the cohort.

![](https://lh5.googleusercontent.com/7AEqm\_m542SHUGbc69uu8v\_7Xfa\_hKym8De3fBscEF6IySHEmy1P1k5S3W\_PvnFMBSOZOUFpPNDKhEp3sHOB8jCuLfjA8QJxsurqK-hZ0umrw0w8bIRPvMZKuQ4TnNTfKRdU8s3UXO1n0Smnp8\_6sAg)

For example, if the Pottery cohort on Aug 1 2022 has attracted 100,000 CAKE deposits in total, the estimated return for 10 weeks of locked staking is around 3,674 CAKE. The contract will borrow 80% of it, or around 2,940 CAKE, for the prize pool for 10 weekly draws, i.e. 294 CAKE in total prizes for each weekly draw before fees.

It is important to note that the rewards and APY at the end of the duration from the deposit may change over the 10-week duration based on other deposits and their lock-periods in the locked CAKE pool, there may be a small deviance from the percentages specified (+/- 10%).

All staking rewards net of fees will be returned to depositors through prize pool or rewards. If the actual APY is lower than the estimated APY at the time of locking, it means more rewards are distributed to the depositors during the weekly draws, and less for the staking rewards portion. If the actual APY is higher than the estimated APY at the time of locking, less rewards are distributed through the weekly draws and more are reserved for the staking rewards available for withdrawal. Ultimately, the expected value is the same.

## **How to Win – Odds Calculation**

Odds are calculated based on the share of deposit amount relative to the total deposit size of the cohort. Simply, the more CAKE you deposited, the higher the chance of winning each weekly draw. For example, if you have deposited 10,000 CAKE and the total deposit of the cohort is 100,000 CAKE, there’s a 10% chance that you will win at each weekly draw.

Each address can win more than 1 of the 8 winner slots each week.

In the extreme case, if all of the cohort’s 100,000 CAKE are deposited by you, you will win all the prizes of each weekly draw. However, that means the final return that you will get is the same as putting 100,000 CAKE into the locked staking pool for 10 weeks, but you will also be paying the Pottery fees.

## **Risks – Important!**

You will be guaranteed to get back 100% of what you deposited in 10 weeks. However, you can _only_ withdraw your CAKE deposit after 10 weeks of locking, without any other way to withdraw early.

By participating in the Pottery, you will be risking the staking rewards, together with other locked-CAKE utilities like iCAKE and vCAKE. In case that you did not win anything from the 10 weekly draws, you would have lost 80% of the staking rewards you were supposed to get if you locked your CAKE in the staking pool for 10 weeks.

Please participate based on your risk preference, once the CAKE are deposited, there is nothing anyone can do to help you withdraw early.

## **Fees**

Eight percent (8%) of the prize pot distributed each week will be charged as fees for burning. We aim to review and adjust the fee structure accordingly after the beta stage of the **** product.

## **Ready to Participate?**

If you are clear about the product structure, the risks and the fees – see this page on [how to participate](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery) from the PancakeSwap web UI and other [Pottery FAQ](https://docs.pancakeswap.finance/products/pottery/pottery-faq)!
