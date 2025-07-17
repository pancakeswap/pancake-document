# Solana Farming FAQ

### 1. How does SOL Farming work?

* V3 Farming is **campaign-based**, meaning farms are active only for a set duration.
* During the campaign:
  * Reward tokens are distributed **every second** to **active liquidity positions**.
  * Farming APR will be shown on the pool list page and my positions page
* After the campaign ends:
  1. **No more rewards** will be distributed.
  2. **Farming APR will no longer be shown** on the pool list page and my positions page
  3. The farm becomes **inactive**, but may be restarted by the creator by adding more rewards.

### 2. Do I need to stake my LP NFT to earn farming rewards?

* **No staking is required**.
* As long as your liquidity position is **active (in-range)** in a pool with an active farm, you will earn rewards automatically.

### 3. Are there any farm boosters?

* **No**, V3 farms do **not** support any boosting mechanisms.
* Rewards are solely based on your share of active liquidity in the pool.

### 4. Can multiple farms be created for the same pool?

* **No**, only **one farm per token pair and fee tier** can exist.

### 5. How are SOL farms configured?

#### A. Token Rewards

* Up to **3 different reward tokens** can be assigned per farm.
* Once set, the reward token types **cannot be changed**.
* The farm creator can:
  * **Top up** the allocated reward tokens.
  * **Extend the farming duration** after the campaign ends.

#### B. Campaign Duration

* Campaigns must last a minimum of **7 days** and a maximum of **90 days**.

### 6. Can a farm be edited after creation?

Farm creators can edit the following parameters **after farm creation**:

1. Reward distribution rate (per second)
2. Campaign end date
3. Add a reward token and corresponding reward amount (only if fewer than 3 tokens were initially assigned)
