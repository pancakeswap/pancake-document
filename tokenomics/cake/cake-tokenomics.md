# CAKE Tokenomics

### &#x20;<a href="#emission-rate" id="emission-rate"></a>

### &#x20;<a href="#per-block" id="per-block"></a>

\*Effective Emission is in fact slightly below this amount: an additional 45,000 CAKE per day is diverted from the amount allocated to the lottery, and burned.

In addition to the above, a dynamic amount of CAKE is also [minted to the Dev address](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) at a rate of 9.09%. This means that if 100 CAKE are harvested, then 9.09 CAKE is minted in addition and sent to the Dev Address.

All CAKE minted to the Dev address is burned in the weekly burn and never enters circulation.

As such, we haven't included it in the above emission rate.

### &#x20;<a href="#distribution" id="distribution"></a>

Reward/block (% of emission)

Reward/block (total CAKE)

of which diverted and burned

**Total Daily CAKE Emission**

### &#x20;<a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

As well as the above, CAKE is also burned in the following ways:

* **0.0575%** of every trade made on PancakeSwap V2
* **100%** of CAKE sent to the Dev address
* **100%** of CAKE performance fees from IFOs
* **100%** of CAKE spent on Profile Creation and NFT minting
* **100%** of CAKE bid during Farm Auctions
* **20%** of CAKE spent on lottery tickets
* **20%** of all profits from Perpetual Trading
* **45,000** CAKE per day (historically assigned to the lottery)
* **3%** of every BNB Prediction markets round is used to buy CAKE for burning
* **3%** of every CAKE Prediction markets round
* **2%** of every yield harvest from all the flexible staking positions in CAKE pool
* **2%** of every NFT sale on the NFT Market is used to buy CAKE for burning

### &#x20;<a href="#why-is-the-cake-burn-manual" id="why-is-the-cake-burn-manual"></a>

To hit the ground running, PancakeSwap launched as an MVP (minimum viable product) with the MasterChef contract emitting 40 CAKE per block. For that reason, the early team didn't add additional functions such as the ability to customize the CAKE minting logic. The team has been controlling CAKE emissions through a manual burn process by creating two pools in MasterChef v1:

* Legacy Lottery Pool (PID - 137) - burned CAKE from the lottery
* Burn Pool (PID - 138) - burned CAKE per block

These pools work similarly to the farms, where the Chefs can adjust the percentage of the 40 CAKE per block allocated to it after each CAKE emission reduction vote.

However, in April 2022, PancakeSwap migrated to a new MasterChef v2 contract. The ratio of the CAKE burn per block is finally controlled by a dedicated contract. This allows the burn to be much more accurate.

On the day of the burn, the supply shown on the homepage might suddenly jump by several million CAKE.

Don't worry - **THIS CAKE NEVER ACTUALLY ENTERS CIRCULATION:**

This apparent jump is just because of how all the CAKE that's allocated for the burn is stored during the week.

The CAKE allocated to burn are harvested before completing the weekly token burns, and this makes the Total Supply shown on the site jump by \~6M. This is because pending CAKE sometimes doesn't get registered in the Total Supply until it's harvested on the burn day. Once the token burn transaction is completed, the \~6M is shown in the Burned to Date.

### &#x20;<a href="#how-to-confirm-cake-supply-for-yourself" id="how-to-confirm-cake-supply-for-yourself"></a>

To confirm that the circulating CAKE supply shown on the PancakeSwap homepage is correct,

1.  2\.

    Then, subtract this burned amount from the "Total Supply" that BscScan shows.
2.  3\.

    This gives you the actual CAKE supply.

#### &#x20;<a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
