---
description: Syrup Pools
---

# 糖浆池

## Contract info

**Contract name**: pancake::smart\_chef\
**Contract address:**&#x20;

fd1d8a523f1be89277ac0787ae3469312667e3d0b3f75a5f01bfc95530a2dc91::smart\_chef

**Admin multi sig address**: 0xd97268666bad31a7299cc80c1bca26face32718630c5498544fe8e9bcc593d74

[Aptos Explorer](https://explorer.aptoslabs.com/account/0xfd1d8a523f1be89277ac0787ae3469312667e3d0b3f75a5f01bfc95530a2dc91/modules)

## Types

| Name        | Type           | Description                                                    |
| ----------- | -------------- | -------------------------------------------------------------- |
| StakeToken  | `type address` | The coin type address of stake token in pool.                  |
| RewardToken | `type address` | The coin type address of reward token in pool.                 |
| UID         | `type address` | The UID of the pool, can be found in [here](broken-reference). |

## Resources

### SmartChefMetadata

The metadata of the module.

```
struct SmartChefMetadata has key {
    signer_cap: account::SignerCapability,
    admin: address,
    uid: u64,
    create_pool_event: EventHandle<CreatePoolEvent>
}
```

<table><thead><tr><th>Name</th><th width="274.3333333333333">Type</th><th>Description</th></tr></thead><tbody><tr><td>signer_cap</td><td><code>account::SignerCapablity</code></td><td>The signer capability of the resource account.</td></tr><tr><td>admin</td><td><code>address</code></td><td>The admin address of the module.</td></tr><tr><td>uid</td><td><code>u64</code></td><td>The latest id of the latest pool.</td></tr><tr><td>create_pool_event</td><td><code>EventHandle</code></td><td>The event emit when a new pool is created</td></tr></tbody></table>

### PoolInfo

The information of each pool.

```
struct PoolInfo<phantom StakeToken, phantom RewardToken, phantom UID> has key {
    total_staked_token: coin::Coin<StakeToken>,
    total_reward_token: coin::Coin<RewardToken>,
    reward_per_second: u64,
    start_timestamp: u64,
    end_timestamp: u64,
    last_reward_timestamp: u64,
    seconds_for_user_limit: u64,
    pool_limit_per_user: u64,
    acc_token_per_share: u128,
    precision_factor: u128,
    emergency_withdraw_reward_event: EventHandle<EmergencyWithdrawRewardEvent<StakeToken, RewardToken, UID>>,
    stop_reward_event: EventHandle<StopRewardEvent<StakeToken, RewardToken, UID>>,
    new_pool_limit_event: EventHandle<NewPoolLimitEvent<StakeToken, RewardToken, UID>>,
    new_reward_per_second_event: EventHandle<NewRewardPerSecondEvent<StakeToken, RewardToken, UID>>,
    new_start_and_end_timestamp_event: EventHandle<NewStartAndEndTimestampEvent<StakeToken, RewardToken, UID>>,
}
```

<table><thead><tr><th width="334.3333333333333">Name</th><th width="159">Type</th><th>Description</th></tr></thead><tbody><tr><td>total_staked_token</td><td><code>coin::Coin</code></td><td>The total amount of staked token in the pool.</td></tr><tr><td>total_reward_token</td><td><code>coin::Coin</code></td><td>The total amount of reward token in the pool.</td></tr><tr><td>reward_per_second</td><td><code>u64</code></td><td>The reward emitting out per second.</td></tr><tr><td>start_timestamp</td><td><code>u64</code></td><td>The start time in seconds.</td></tr><tr><td>end_timestamp</td><td><code>u64</code></td><td>The end time in seconds.</td></tr><tr><td>last_reward_timestamp</td><td><code>u64</code></td><td>The latest time that reward was distributed.</td></tr><tr><td>seconds_for_user_limit</td><td><code>u64</code></td><td>The time that user limit will apply after the start time.</td></tr><tr><td>pool_limit_per_user</td><td><code>u64</code></td><td>The amount of token allow to be stake within the seconds_for_user_limit.</td></tr><tr><td>acc_token_per_share</td><td><code>u128</code></td><td>The accumulative token per share.</td></tr><tr><td>precision_factor</td><td><code>u128</code></td><td>The precision factor used for calculation.</td></tr><tr><td>emergency_withdraw_reward_event</td><td><code>EventHandle</code></td><td>The event emit when the reward is withdrawn.</td></tr><tr><td>stop_reward_event</td><td><code>EventHandle</code></td><td>The event emit when the admin stop reward.</td></tr><tr><td>new_pool_limit_event</td><td><code>EventHandle</code></td><td>The event emit when the admin update the new pool limit.</td></tr><tr><td>new_reward_per_second_event</td><td><code>EventHandle</code></td><td>The event emit when the admin update the reward per second of the pool.</td></tr><tr><td>new_start_and_end_timestamp_event</td><td><code>EventHandle</code></td><td>The event emit when the admin update the start or end timestamp of the pool.</td></tr></tbody></table>

## Entry Functions

### Deposit

Deposit the stake token into the pool. It will also transfer reward token to the user if there's any.

```
public entry fun deposit<StakeToken, RewardToken, UID>(
    account: &signer,
    amount: u64
)
```

| Name    | Type     | Description                                       |
| ------- | -------- | ------------------------------------------------- |
| account | `signer` | The sender's signer when calling the function.    |
| amount  | `u64`    | The amount of stake token that will be deposited. |

### Withdraw

Withdraw the stake token from the pool. It will also transfer reward token to the user if there's any.

```
public entry fun withdraw<StakeToken, RewardToken, UID>(
    account: &signer,
    amount: u64,
)
```

| Name    | Type     | Description                                       |
| ------- | -------- | ------------------------------------------------- |
| account | `signer` | The sender's signer when calling the function.    |
| amount  | `u64`    | The amount of stake token that will be withdrawn. |

### Emergency Withdraw

Withdraw the stake token from the pool regardless of any rewards.&#x20;

```
public entry fun emergency_withdraw<StakeToken, RewardToken, UID>(account: &signer)
```

| Name    | Type     | Description                                    |
| ------- | -------- | ---------------------------------------------- |
| account | `signer` | The sender's signer when calling the function. |

## Public Functions

### Get Pool Info

Get the pool informations.

```
public fun get_pool_info<StakeToken, RewardToken, UID>(): (u64, u64, u64, u64, u64, u64, u64)
```

#### Return Values

| Position | Type  | Description                                                                 |
| -------- | ----- | --------------------------------------------------------------------------- |
| 0        | `u64` | The total amount of staked token in the pool.                               |
| 1        | `u64` | The total amount of reward token in the pool.                               |
| 2        | `u64` | The reward emitting out per second.                                         |
| 3        | `u64` | The start time in seconds.                                                  |
| 4        | `u64` | The end time in seconds.                                                    |
| 5        | `u64` | The time that user limit will apply after the start time.                   |
| 6        | `u64` | The amount of token allow to be stake within the seconds\_for\_user\_limit. |

### Get User Stake Amount

Get the user stake amount in the pool.

```
public fun get_user_stake_amount<StakeToken, RewardToken, UID>(account: address)
```

#### Input Values

| Name    | Type      | Description            |
| ------- | --------- | ---------------------- |
| account | `address` | The depositor address. |

#### Return Values

| Type  | Description                                             |
| ----- | ------------------------------------------------------- |
| `u64` | The total amount of depositor staked token in the pool. |

### Get Pending Reward

Get the pending reward of the depositor in the pool.

```
public fun get_pending_reward<StakeToken, RewardToken, UID>(account: address): u64 
```

#### Input Values

| Name    | Type      | Description            |
| ------- | --------- | ---------------------- |
| account | `address` | The depositor address. |

#### Return Values

| Type  | Description                                                                         |
| ----- | ----------------------------------------------------------------------------------- |
| `u64` | The amount of pending reward token in the pool that depositor is eligible to claim. |

## Audit

[Zellic's PancakeSwap Aptos Syrup Pool security audit](https://github.com/Zellic/publications/blob/master/PancakeSwap%20Aptos%20-%20Zellic%20Audit%20Report.pdf)
