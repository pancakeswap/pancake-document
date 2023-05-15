# Swap Core V2

## Contract info

**Contract name**: pancake::swap\
**Contract address:** c7efb4076dbe143cbcd98cfaaa929ecfc8f299203dfff63b95ccb6bfe19850fa::swap

**Admin Multi Sig**: b11ccaed0056a75472539c2b0d9511c82fc6a36622bec7578216af5fe550dd0d

[View on Aptos Explorer](https://explorer.aptoslabs.com/account/0xc7efb4076dbe143cbcd98cfaaa929ecfc8f299203dfff63b95ccb6bfe19850fa/modules)

## Types

| Name | Type           | Description                                   |
| ---- | -------------- | --------------------------------------------- |
| X    | `type address` | The coin type address of token X in the pair. |
| Y    | `type address` | The coin type address of token Y in the pair. |

## Resources

### LPToken

The liquidity token corresponds to each pool XY.

```
struct LPToken<phantom X, phantom Y> has key {}
```

### TokenPairMetadata

The metadata of pool XY.

```
struct TokenPairMetadata<phantom X, phantom Y> has key {
    creator: address,
    fee_amount: coin::Coin<LPToken<X, Y>>,
    k_last: u128,
    balance_x: coin::Coin<X>,
    balance_y: coin::Coin<Y>,
    mint_cap: coin::MintCapability<LPToken<X, Y>>,
    burn_cap: coin::BurnCapability<LPToken<X, Y>>,
    freeze_cap: coin::FreezeCapability<LPToken<X, Y>>,
}
```

| Name        | Type                   | Description                                                               |
| ----------- | ---------------------- | ------------------------------------------------------------------------- |
| creator     | `address`              | The creator address of pool.                                              |
| fee\_amount | `coin::Coin`           | The total LP token collected from all the swaps in the pool.              |
| k\_last     | `u128`                 | The multiply of reserve\_x and reserve\_y in the pool from the last swap. |
| balance\_x  | `coin::Coin`           | The total amount of token X in the pool.                                  |
| balance\_y  | `coin::Coin`           | The total amount of token Y in the pool.                                  |
| mint\_cap   | `coin::MintCapability` | The mint capability created when the LP is created.                       |
| burn\_cap   | `coin::BurnCapability` | The burn capability created when the LP is created.                       |
| freeze\_cap | coin::FreezeCapability | The freeze capability created when the LP is created.                     |

### TokenPairReserve

The tokens reserves of pool XY.

```
struct TokenPairReserve<phantom X, phantom Y> has key {
    reserve_x: u64,
    reserve_y: u64,
    block_timestamp_last: u64
}
```

| Name                  | Type  | Description                              |
| --------------------- | ----- | ---------------------------------------- |
| reserve\_x            | `u64` | The total amount of token X in the pool. |
| reserve\_y            | `u64` | The total amount of token Y in the pool. |
| block\_timstamp\_last | `u64` | The timestamp when reserves get updated. |

### SwapInfo

The metadata of the module

```
struct SwapInfo has key {
    signer_cap: account::SignerCapability,
    fee_to: address,
    admin: address,
    pair_created: event::EventHandle<PairCreatedEvent>
}
```

| Name          | Type                       | Description                                                |
| ------------- | -------------------------- | ---------------------------------------------------------- |
| signer\_cap   | `account::SignerCapabilty` | The signer capability created when the module is deployed. |
| fee\_to       | `address`                  | The address that the fee will be sent to.                  |
| admin         | `address`                  | The admin address of the module                            |
| pair\_created | `event::EventHandle`       | The event emit when the pool is created.                   |

## Public Functions

### Register LP

Register the LP token to the account.

```
public fun register_lp<X, Y>(sender: &signer)
```

#### Input Values

| Name   | Type     | Description                                    |
| ------ | -------- | ---------------------------------------------- |
| sender | `signer` | The sender's signer when calling the function. |

### Is Paired Created

Check if the pool XY is created or not.

```
public fun is_pair_created<X, Y>(): bool
```

#### Return Values

| Type | Description                         |
| ---- | ----------------------------------- |
| bool | Whether the pool is created or not. |

### LP Balance

Check LP balance of user.

```
public fun lp_balance<X, Y>(addr: address): u64
```

#### Input Values

| Name | Type      | Description       |
| ---- | --------- | ----------------- |
| addr | `address` | The user address. |

#### Return Values

| Type   | Description                |
| ------ | -------------------------- |
| `u128` | The amount of LP user own. |

### Total LP Supply

The total amount of LP exist created from pool XY.

```
public fun total_lp_supply<X, Y>(): u128
```

#### Return Values

| Type   | Description                    |
| ------ | ------------------------------ |
| `u128` | The total supply of LP tokens. |

### Token Reserve

The token reserves of the pool XY.

```
public fun token_reserves<X, Y>(): (u64, u64, u64)
```

#### Return Values

| Position | Type  | Description                              |
| -------- | ----- | ---------------------------------------- |
| 0        | `u64` | The total amount of token X in the pool. |
| 1        | `u64` | The total amount of token Y in the pool. |
| 2        | `u64` | The timestamp when reserves get updated. |

### Token Balance

The token balance of the pool XY.

```
public fun token_balances<X, Y>(): (u64, u64)
```

#### Return Values

| Position | Type  |                                          |
| -------- | ----- | ---------------------------------------- |
| 0        | `u64` | The total amount of token X in the pool. |
| 1        | `u64` | The total amount of token Y in the pool. |
