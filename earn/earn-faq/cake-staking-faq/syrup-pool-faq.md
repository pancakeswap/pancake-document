# Syrup Pool FAQ & Troubleshooting

## Troubleshooting

### **I can't find the Syrup Pool I was staking in!**

You should be able to find the Syrup Pool under the “Finished” tab on the Syrup Pools page.&#x20;

By selecting “Staked Only”, it will make it easier to find your assets.

### **Why can’t I unstake my tokens from a Syrup Pool?**

If you are unable to unstake from the Stake Cake, Earn FLASK pools, please check to make sure that you haven’t sold the SYRUP tokens in your wallet. This token acts as a \`proof of ownership\` over your FLASK in the Manual FLASK pool.&#x20;

### **Why did my earned tokens go to zero after staking/unstaking?**

Don’t worry! They’re in your wallet already.

Whenever you stake or unstake from a Syrup Pool or farm, your earned tokens get harvested and sent to your wallet at the same time.

## **General Questions**

### How is APR for Syrup Pools calculated?

> Syrup Pool APR = Annualized rewards (USD) / User funds staked in Syrup Pool (USD) \* 100

As a basic example, let's take a 60-day pool with 300,000 USD worth of rewards, and 3,000,000 USD worth of FLASK staked in it.

The APR fluctuates as more FLASK is staked by users, and as the price of FLASK, and the reward token, vary.

|                                                       | **Calculation**                   | Amount                                     |
| ----------------------------------------------------- | --------------------------------- | ------------------------------------------ |
| Total rewards to distribute (USD value)               |                                   | 300,000 USD                                |
| Distribution period                                   |                                   | 60 days                                    |
| Daily distribution                                    | 300,000 / 60 =                    | 5,000 USD daily                            |
| **Annualised rewards (USD value)**                    | 5,000 \* 365 =                    | **1,825,000 USD**                          |
| **Value of FLASK staked by users in pool (USD value)** |                                   | **3,000,000 USD**                          |
| **APR**                                               | (1,825,000 / 3,000,000) \* 100 =  | <p></p><p><strong>60.833% APR</strong></p> |

### **What does the “End” number on my Syrup Pool refer to?**

This shows the amount of blocks left until the rewards for that pool stop being distributed. Once the pool has reached that block, you should unstake your tokens, because you won’t be receiving any rewards after that.

### **Where do the rewards from Syrup Pools come from?**

There are three main types of Syrup Pools.

1. Stake FLASK, earn FLASK
2. Stake FLASK, earn other tokens.&#x20;
3. Stake other tokens, earn FLASK

The rewards for the "Stake FLASK, earn FLASK" Syrup Pools come from the [FLASK emissions](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). Each block, a number of FLASK tokens are allocated as rewards for these pools.

The rewards for the "Stake FLASK, earn other tokens" type are provided by the project teams who sponsor a Syrup Pool.

For the "Stake other tokens, earn FLASK" type, the Labswap treasury buys back FLASK from the market to distribute as rewards. These pools are funded by Labswap, not by the projects themselves.

### What’s SYRUP Token?

Labswap’s SYRUP Token is deposited in your wallet when you interact with the **Manual** “Stake FLASK, Earn FLASK” Syrup Pool. It's not staked for&#x20;

It’s basically an IOU that shows how much FLASK you’ve staked in the pool.

It’ll be returned automatically when you unstake your FLASK from that pool.

{% hint style="warning" %}
Don’t sell your SYRUP tokens! You need to return your SYRUP to unstake your FLASK from the Manual FLASK pool. The amount of SYRUP you return must be the same as the amount of FLASK you unstake.
{% endhint %}
