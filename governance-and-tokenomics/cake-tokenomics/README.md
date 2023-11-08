# CAKE Tokenomics



<figure><img src="../../.gitbook/assets/image (184).png" alt=""><figcaption></figcaption></figure>

## **Emission rate** <a href="#emission-rate" id="emission-rate"></a>

### **Per block**

| **Metric**             | **Emission/block (CAKE)** | **Emission/day (CAKE)** |
| ---------------------- | ------------------------: | ----------------------: |
| Emission               |                        40 |               1,152,000 |
| Burned Weekly          |                 \~38.5558 |             \~1,110,407 |
| **Effective Emission** |            **\~1.4442\*** |          **\~41,593\*** |

{% hint style="info" %}
On August 11, 2022, Chefs implemented some configuration upgrades to take full advantage of MasterChef v2. It eliminates the 45,000 CAKE daily burn for the legacy lottery injections. Those burns will now be handled by MasterChef v2 directly along with the usual weekly CAKE burn. Therefore, the effective emissions are now even lower.
{% endhint %}

{% hint style="warning" %}
In addition to the above, a dynamic amount of CAKE is also [minted to the Dev address](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) at a rate of 9.09%. This means that if 100 CAKE are harvested, then 9.09 CAKE is minted in addition and sent to the Dev Address.

All CAKE minted to the Dev address is burned in the weekly burn and never enters circulation.&#x20;

As such, we haven't included it in the above emission rate.
{% endhint %}

## Distribution <a href="#distribution" id="distribution"></a>

<table data-header-hidden><thead><tr><th>Distributed to</th><th width="154" align="right">Reward/block (% of emission)</th><th width="158" align="right">Reward/block (total CAKE)</th><th align="right">Reward/day</th></tr></thead><tbody><tr><td>Distributed to</td><td align="right"><p>Reward/block</p><p>(% of emission)</p></td><td align="right"><p>Reward/block</p><p>(total CAKE)</p></td><td align="right">Reward/day</td></tr><tr><td>Trading</td><td align="right">~2.39%</td><td align="right">~0.9553</td><td align="right">27,513 (approx)</td></tr><tr><td>Staking</td><td align="right">~0.88%</td><td align="right">~0.35</td><td align="right">10,080 (approx)</td></tr><tr><td>Other</td><td align="right">~0.35%</td><td align="right">~0.1389</td><td align="right">4,000 (approx)</td></tr><tr><td><strong>Total Daily CAKE Emission</strong></td><td align="right"></td><td align="right"></td><td align="right"><strong>~41,593 (approx)</strong></td></tr></tbody></table>

## **Other Deflationary Mechanics** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
The burning process is currently manual. [View burn transactions here](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

As well as the above, CAKE is also burned in the following ways:

* **0.001\~0.23%** of every trade made on Exchange V3 (on all our chain deployments less Aptos)
* **0.0575%** of every trade made on Exchange V2 (on all our chain deployments)
* **0.004%\~0.016%** of every trade made on StableSwap
* **100%** of CAKE sent to the Dev address
* **100%** of CAKE performance fees from IFOs
* **100%** of CAKE spent on Profile Creation and NFT minting
* **100%** of CAKE bid by winners during Farm Auctions
* **20%** of CAKE spent on lottery tickets
* **20%** of all profits from Perpetual Trading
* **8%** of the Pottery prize pot distributed each week
* **3%** of every BNB Prediction markets round is used to buy CAKE for burning
* **3%** of every CAKE Prediction markets round
* **2%** of every yield harvest from all the flexible staking positions in CAKE pool
* **2%** of every NFT sale on the NFT Market is used to buy CAKE for burning

## Why is the CAKE burn manual?

To hit the ground running, PancakeSwap launched as an MVP (minimum viable product) with the MasterChef contract emitting 40 CAKE per block. For that reason, the early team didn't add additional functions such as the ability to customize the CAKE minting logic. The team has been controlling CAKE emissions through a manual burn process by creating two pools in MasterChef v1:

* Legacy Lottery Pool (PID - 137) - burned CAKE from the lottery
* Burn Pool (PID - 138) - burned CAKE per block

These pools work similarly to the farms, where the Chefs can adjust the percentage of the 40 CAKE per block allocated to it after each CAKE emission reduction vote.

**However, in April 2022, PancakeSwap migrated to a new MasterChef v2 contract.** The ratio of the CAKE burn per block is finally controlled by a dedicated contract. This allows the burn to be much more accurate.

{% hint style="warning" %}
Due to MasterChef v2 occasionally harvesting the full 40 CAKE per block. The supply shown on the homepage (or some 3rd party trackers) might suddenly jump by several million CAKE.

Don't worry - **emission is now controlled carefully by MasterChef V2. CAKE to burn will NEVER actually enters circulation!**
{% endhint %}

## How to Confirm CAKE Supply for yourself

To confirm that the circulating CAKE supply shown on the PancakeSwap homepage is correct,&#x20;

1. Head to the CAKE token contract on BscScan and [see how much CAKE is held by the Burn Address.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) That's the total amount of CAKE that's been burned (removed from circulation FOREVER, and impossible to ever retrieve).
2. Then, subtract this burned amount from the "Total Supply" that BscScan shows.
3. This gives you the actual CAKE supply.



#### **Read more about CAKE's deflationary mechanics on the next page.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
