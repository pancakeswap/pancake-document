# Farms

PancakeSwap Infinity farming is a simple, gas-efficient way for users to earn liquidity rewards without needing to stake their LP tokens. Once liquidity is added to an eligible pool, rewards begin accruing automatically.

#### ⚙️ How It Works

Here’s a quick breakdown of how the system tracks and distributes rewards:\


**✅ No Staking Required**

* Just hold your LP position in your wallet.
* No need to lock your assets or interact with additional smart contracts.
* You start earning rewards automatically when you add liquidity.

#### 📈 Rewards Distribution

* Only in-range positions (those providing active liquidity) receive rewards.
* Rewards are proportional to the fees earned by your position during each period, called an epoch.

#### ⏳ What’s an Epoch?

* An epoch is a fixed time window — currently set to 8 hours.
* Rewards are calculated and distributed after each epoch.
* Epochs are currently scheduled at 00:00, 08:00, and 16:00 UTC.

***

#### 🔄 Farming & Claim Process

1. **Tracking Positions:** The backend system monitors your LP positions across all farms.
2. **Reward Calculation:** At the end of every epoch,
   1. The system calculates your rewards based on your liquidity and the fees generated.
   2. It processes the rewards into a Merkle tree and submits a Merkle root to a smart contract.
3. **Dispute Period:**
   1. After the Merkle root is published, the 1-hour dispute period begins.
   2. During the dispute period:
      1. The newly calculated rewards cannot be claimed.
      2. Rewards from previous epochs remain available to claim.
      3. Automated and community-operated verification tools check the accuracy of the published data. If discrepancies are detected, a dispute may be raised to prevent incorrect distributions.
4. **Claiming Rewards:**
   1. Once the dispute period ends, you can claim your rewards for the latest epoch.
   2. All pending rewards across all farms can be claimed in a single, gas-efficient transaction.
5. **Unclaimed Rewards Roll Over:**
   1. Any unclaimed rewards roll over to subsequent epochs. Each update incorporates previous rewards, ensuring no earnings are lost or expired.

{% hint style="info" %}
Tighter liquidity ranges generally lead to higher earnings but increase the likelihood of a position moving out of range and becoming ineligible for rewards.
{% endhint %}

#### 🌱 Summary

✅ No staking\
✅ Gas-efficient claiming\
✅ Regular reward updates\
✅ Fair and transparent dispute process\
✅ Rewards accumulate until you’re ready to claim
