---
description: Migrate to MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 is a new main staking contract for Farms while providing more flexibility for adjusting the $CAKE emissions, including CAKE pool, burn and other PancakeSwap products.

### Do I need to migrate?

If you are currently using PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)), you will need to migrate to the new contract ([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)).

### Overview

#### Deposit&#x20;

If you are currently using the `enterStaking(uint256 _amount)` on the current PancakeSwap MasterChef. You need to migrate to the new CAKE pool contract. Check out the related documentation [here](../cake-syrup-pool.md).

The deposit function for the farm pools is unchanged. However, you will need to upgrade the MasterChef address and the `pid` , check out the [list of farms](list-of-farms.md) for the list of new `pids` on MasterChef v2.

#### Pool types

MasterChef v2 have 2 types of pool: Regular farm pools and Special farm pools, which you can use `poolInfo(_pid).isRegular` to query the pool type. They share a different `totalAllocPoint`, making them two sets of independent pools.

Special farm pools: only whitelisted addresses can deposit. They are usually utilized by internal PancakeSwap products for rewards distributions.

Regular farm pools: the regular LP tokens farms. For example CAKE-BNB, BNB-BUSD, etc…

#### Withdraw

If you are currently using the `leaveStaking(uint256 _amount)` on the current PancakeSwap MasterChef. You need to migrate to the new CAKE pool contract. Check out the related documentation [here](../cake-syrup-pool.md).

The withdraw function for the farm pools is unchanged. However, you will need to update the MasterChef address and the `pid` , check out the [list of farms](list-of-farms.md) for the list of new `pids` on MasterChef v2.

#### Staking Balance

Use `userInfo[_pid][_user].amount` to query the staking balance.

#### Staking Token&#x20;

Note that the new `PoolInfo` struct **does not** contain the lp token address field, you will need to use `lpToken(_pid)` to query any given pool's staking token.&#x20;

#### Total Staking Shares/Amount

Use `lpToken.balanceOf(MasterChef.address)` to get the total staking amount for any given farm pool.

However, In MasterChef v2, the users' share can be boosted (coming soon). Therefore, rewards are calculated using a new `totalBoostedShare` field in `PoolInfo` as each pool’s total shares. For example, if pool 0 has 2 users, user1 stake 100 LPs (without boost), user2 stake 100 (with `boostMultiplier` being 1.05), then the `totalBoostedShare` will become 205. Resulting in user2 gaining more rewards.

#### CakePerBlock

You can use `cakePerBlock(bool _isRegular)` to query the CAKE reward per block that goes to all the PancakeSwap farms.

### Testnet Environment

You can use the following testnet environment to test the integration of your project with the new PancakeSwap MasterChef v2. If you have any questions, please contact our team via the existing channels, or reach out to bun@pancakeswap.com via Email.

**Dummy Tokens:**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable by using `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  ``(mintable by using `mint(uint256 amount) public`)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory and Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP Pairs

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`

