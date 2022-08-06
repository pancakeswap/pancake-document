# Pottery FAQ

### &#x20;<a href="#why-do-we-need-pottery-when-we-already-have-the-lottery-v2" id="why-do-we-need-pottery-when-we-already-have-the-lottery-v2"></a>

Pottery is a completely different product compared to Lottery v2. It is a combination of the locked CAKE pool and the lottery function utilizing the Chainlink's implementation of VRF for true, secure randomness. By participating in Pottery, you will not lose any of the CAKE you deposited, you are only risking the staking rewards of the CAKE you deposited. This product is designed for CAKErs who are more risk-averse but still would like to participate in a product of this nature. It’s an easy, fun and safe way to get a chance to win some CAKE. Learn more about [the product structure here](https://docs.pancakeswap.finance/products/pottery).

### &#x20;<a href="#is-pottery-replacing-the-original-lottery-v2" id="is-pottery-replacing-the-original-lottery-v2"></a>

Pottery is not replacing the original Lottery v2. These two products are operated and run separately. You can participate in both!

### &#x20;<a href="#how-does-pottery-help-pancakeswap-and-cake" id="how-does-pottery-help-pancakeswap-and-cake"></a>

Eight percent (8%) of the prize pot distributed each week will be charged as fees for burning, which accrues value to CAKE. We aim to review and adjust the fee structure accordingly after the beta stage of the product.

### &#x20;<a href="#what-is-the-beta-stage-of-pottery-for" id="what-is-the-beta-stage-of-pottery-for"></a>

Because of the operations of this new product such as borrowing from treasury, cohort management and drawing. The product will start off in the beta stage with a capped total deposit for each Pottery to make sure everything runs smoothly. Once we pass the beta stage, we may review and adjust different parameters based on operations and community feedback such as the fees, the frequency of each cohort, lock period, etc.

### &#x20;<a href="#why-does-it-have-to-lock-my-cake-for-10-weeks" id="why-does-it-have-to-lock-my-cake-for-10-weeks"></a>

If the Pottery can just use the flexible staking pool, its product structure would be much simpler - similar to products like PoolTogether and Moonpot. However, the current yield from the flexible staking pool is not sufficient for us to produce a meaningful prize pool for drawing. Hence, the decision is to lock the CAKE for a moderate duration to balance the rewards that can be used to fund the prize pool. With more operations and community feedback, we may review and adjust the lock duration down the road.

### &#x20;<a href="#why-cant-i-withdraw" id="why-cant-i-withdraw"></a>

Please note that the withdrawal button will light up and be available only after 10 weeks of the lock date. The date for withdrawal is based on 10 weeks after the lock date and time – 23:59 UTC on the first Monday of each month.

### &#x20;<a href="#why-cant-i-view-my-deposit" id="why-cant-i-view-my-deposit"></a>

There might occasionally be some delay because of the Subgraph reading, there will be a signal when there are delays – usually it should show the correct amount if you check again in 15 minutes.

### &#x20;<a href="#how-do-i-know-if-i-have-won-in-the-weekly-draw" id="how-do-i-know-if-i-have-won-in-the-weekly-draw"></a>

After each draw on Friday at around noon UTC, you can view the results and winners in the Finished Rounds panel. Another way to check if you have won in any weekly draws is to check in the Claim panel to see if there is any prize to be claimed. Check out [this page on how to participate](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery)!

### &#x20;<a href="#what-is-the-funding-source-of-the-prize" id="what-is-the-funding-source-of-the-prize"></a>

The prize pools are funded by the staking rewards of the deposits. However, since the staking rewards of the CAKE locked staking pool are only distributed after the lock duration – 10 weeks in this case, for better product experience and to facilitate the weekly draws right after the deposit date, the contract is borrowing 80% of the estimated total staking rewards from the cohort from the CAKE treasury based on the APY at the time of locking. The borrowed CAKE is used for the payout for each weekly draw. Learn more about [the product structure here](https://docs.pancakeswap.finance/products/pottery)!

### &#x20;<a href="#if-i-win-do-i-need-to-manually-claim-the-prize" id="if-i-win-do-i-need-to-manually-claim-the-prize"></a>

Yes, you will need to click the Claim button under the Claim panel on the Pottery page.

### &#x20;<a href="#how-often-is-the-pottery" id="how-often-is-the-pottery"></a>

Each Pottery cohort is open for deposit on the Friday before at around 10:00 UTC and closes on the first Monday of each month at 23:59 UTC, unless any special arrangement and notice in advance. Each cohort will have 10 weekly draws on 10 subsequent Fridays at noon UTC.

The first Pottery will open deposit on Aug 5 2022 and lock on Aug 8 2022 at 23:59 UTC.

### &#x20;<a href="#why-does-the-pottery-deposit-only-open-once-a-month" id="why-does-the-pottery-deposit-only-open-once-a-month"></a>

This arrangement combines the deposit to direct to the locked staking pool, such that the Pottery contract of the cohort is able to coordinate the staking rewards of the deposit from the locked staking pool. With more operations and community feedback, we may review and adjust the frequency down the road.

### &#x20;<a href="#what-is-the-limit-for-depositing" id="what-is-the-limit-for-depositing"></a>

There is a minimum deposit of 1 CAKE. At the beta stage of the product, there will also be a maximum deposit cap for each cohort which you can view in the Deposit panel when you are making the deposit. This is to make sure everything on the operation side including the borrowing from treasury, locked staking and drawing runs smoothly. While the maximum you can deposit is the maximum deposit cap of that cohort (if no one else has deposited any CAKE), you would win all the prizes, however, that also means the final return that you will get is the same as putting your CAKE into the locked staking pool for 10 weeks, but you will also be paying the Pottery fees.

### &#x20;<a href="#where-can-i-provide-feedback-for-this-product" id="where-can-i-provide-feedback-for-this-product"></a>

Please feel free to reach out to us on [Telegram](https://t.me/pancakeswap) or [Discord](https://discord.gg/pancakeswap) if you're still unsure about the format or if you have any feedback for us to improve this further!
