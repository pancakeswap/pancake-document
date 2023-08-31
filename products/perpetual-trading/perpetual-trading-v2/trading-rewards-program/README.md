---
description: ApolloX will launch Trading Rewards Program on V2
---

# Trading Rewards Program

### Reward Program Overview

The details are as follows:

Activity period: Dates vary from cycle to cycle and for different chains

Rewards Distribution Time: Each cycle is 00:00 (UTC) to 23:59 (UTC) daily. Rewards are issued on the next day at around 03:00 (UTC). Users have to claim their rewards within 30 days after the rewards are issued. If they do not, the platform will revoke the rewards.&#x20;

Reward amount: Capped at $15,000 USD worth of APX per day

Activity rules: Users who trade on V2 earn from a reward prize pool. Those who stake APX in DAO to obtain veNFT will enjoy boosting multipliers corresponding to the Power value calculated from the veNFT.&#x20;

| Power Value               | Boosting Multiplier  |
| ------------------------- | -------------------- |
| 50,000 < Power =<100,000  | 1.5                  |
| 100,000 < Power =<300,000 | 2                    |
| Power > 300,000           | 2.5                  |

Trading Rewards calculation formula:&#x20;

At the end of each trading reward cycle, the user’s effective trading fees and staking amount in that cycle will be calculated to determine the weightage and amount of APX rewards. The formula is as follows:

r = R\*W / sum(Wi)



Parameters:

| r       | User’s APX reward for this cycle                                                                                                                                                                                                                                                                                        |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Determined by the user’s V2 trading fee contribution on the previous day and latest APX token price                                                                                                                                                                                                                     |
| W       | <p>Individual total weight score W=f*w, where;</p><p>f refers to the effective trading fees contributed by the user in this cycle, which will be converted into USD.</p><p>w is the Boosting Multiplier obtained by the user in this cycle from staking APX in DAO. (Refer to the above table for more information)</p> |
| sum(Wi) | The total score of all users. Wi represents any individual user’s score, and sum(Wi) represents the sum of all user scores                                                                                                                                                                                              |

&#x20;

The calculation formula for R is as follows:

R=Min(Dollar value multiplier \* Trading Fee, Dollar value Cap)/ Max(APX Last Price,APX Price Floor)

* Dollar value multiplier: 0.70 this epoch
* Trading Fee: Value of previous day’s V2 fee income converted into USD
* Dollar value Cap: 15,000 based on system configuration
* APX Last Price: Based on latest APX token price
* APX Price Floor: 0.04 this epoch

Terms and Conditions

* After the end of each cycle, ApolloX may adjust the program rules according to users’ feedback and market conditions. Rewards will be released non-linearly.
* During the activity, the platform will reduce the percentage of V2 trading fee income injected into the ALP pool from 50% to 20%. The remaining 30% will be used to repurchase APX.
* Due to the difference in trading fees for each trading pair on V2, the rewards users receive may vary even though their effective trading volumes are the same.
* The rewards to be distributed for each cycle will be stored in the following contract address: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX reserves the right of final interpretation for this activity.

Risk Warning: Crypto futures trading carries a substantial risk. All trading activities are done at your discretion and at your own risk. The information here should not be regarded as financial or investment advice from ApolloX. ApolloX will not be liable for any loss that might arise from your use of ApolloX.

### Claiming Rewards

As the trading reward program is hosted by our friends at ApolloX, please proceed with the following steps to claim your reward:\
\
Step 1: Head to our [PancakeSwap Perpetuals Page](https://perp.pancakeswap.finance/en/futures/v2/)

Step 2: Click the Trading Reward (V2) tab at the top of the page

<figure><img src="../../../../.gitbook/assets/Trading Reward.png" alt=""><figcaption></figcaption></figure>

Step 3: You'll be redirected to ApolloX rewards claim page to check your current reward status. Click "Claim" to claim your rewards during the activity period.

<figure><img src="../../../../.gitbook/assets/Screenshot 2023-06-29 at 10.26.11 AM.png" alt=""><figcaption></figcaption></figure>
