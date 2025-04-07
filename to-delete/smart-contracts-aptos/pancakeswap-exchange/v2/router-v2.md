# Router v2

## Contract info

**Contract name**: pancake::router\
**Contract address:** c7efb4076dbe143cbcd98cfaaa929ecfc8f299203dfff63b95ccb6bfe19850fa::router

**Admin Multi Sig**: b11ccaed0056a75472539c2b0d9511c82fc6a36622bec7578216af5fe550dd0d

[View on Aptos Explorer](https://explorer.aptoslabs.com/account/0xc7efb4076dbe143cbcd98cfaaa929ecfc8f299203dfff63b95ccb6bfe19850fa/modules)

## **Types**

| Name | Type           | Description                                   |
| ---- | -------------- | --------------------------------------------- |
| X    | `type address` | The coin type address of token X in the pair. |
| Y    | `type address` | The coin type address of token Y in the pair. |



## Entry Functions

### Create Pair

Create the pool pair for swap.

```
public entry fun create_pair<X, Y>(sender: &signer)
```

#### Params

| Name   | Type     | Descripton                                     |
| ------ | -------- | ---------------------------------------------- |
| sender | `signer` | The sender's signer when calling the function. |

### Add Liquidity

Add liquidity to the pool.

```
public entry fun add_liquidity<X, Y>(
    sender: &signer,
    amount_x_desired: u64,
    amount_y_desired: u64,
    amount_x_min: u64,
    amount_y_min: u64,
)
```

#### Params

| Name               | Type     | Description                                                |
| ------------------ | -------- | ---------------------------------------------------------- |
| sender             | `signer` | The sender's signer when calling the function.             |
| amount\_x\_desired | `u64`    | The amount of tokenX you'd like to provide as liquidity.   |
| amount\_y\_desired | u64      | The amount of tokenY you'd like to provide as liquidity.   |
| amount\_x\_min     | u64      | The minimum amount of tokenX to provide (slippage impact). |
| amount\_y\_min     | u64      | The minimum amount of tokenY to provide (slippage impact). |

### Remove Liquidity

Remove liquidity from the pool.

```
public entry fun remove_liquidity<X, Y>(
    sender: &signer,
    liquidity: u64,
    amount_x_min: u64,
    amount_y_min: u64
)
```

#### Params

| Name           | Type     | Description                                               |
| -------------- | -------- | --------------------------------------------------------- |
| sender         | `signer` | The sender's signer when calling the function.            |
| liquidity      | `u64`    | The amount of LP Tokens to remove.                        |
| amount\_x\_min | `u64`    | The minimum amount of tokenX to remove (slippage impact). |
| amount\_y\_min | `u64`    | The minimum amount of tokenY to remove (slippage impact). |

### Swap Exact Input

Swap exact amount of tokenX to tokenY.

```
public entry fun swap_exact_input<X, Y>(
    sender: &signer,
    x_in: u64,
    y_min_out: u64,
)
```

#### Params

| Name        | Type     | Description                                    |
| ----------- | -------- | ---------------------------------------------- |
| sender      | `signer` | The sender's signer when calling the function. |
| x\_in       | `u64`    | Payable amount of input tokenX.                |
| y\_min\_out | `u64`    | The minimum amount tokenY to receive.          |

### Swap Exact Output

Swap tokenX to exact amount of tokenY.

```
public entry fun swap_exact_output<X, Y>(
    sender: &signer,
    y_out: u64,
    x_max_in: u64,
)
```

#### Params

| Name       | Type     | Description                                    |
| ---------- | -------- | ---------------------------------------------- |
| sender     | `signer` | The sender's signer when calling the function. |
| y\_out     | `u64`    | Payable amount of output tokenY.               |
| x\_max\_in | `u64`    | The maximum amount tokenX to input.            |

### Swap Exact Input Double Hop

Swap exact amount of tokenX to tokenZ using 2 pools (Pool XY and Pool YZ).

```
public entry fun swap_exact_input_doublehop<X, Y, Z>(
    sender: &signer,
    x_in: u64,
    z_min_out: u64,
)
```

#### Params

| Name        | Type     | Description                                    |
| ----------- | -------- | ---------------------------------------------- |
| sender      | `signer` | The sender's signer when calling the function. |
| x\_in       | `u64`    | Payable amount of input tokenX.                |
| z\_min\_out | `u64`    | The minimum amount tokenZ to receive.          |

### Swap Exact Output Double Hop

Swap tokenX to exact amount of tokenZ using 2 pools (Pool XY and Pool YZ).

```
public entry fun swap_exact_output_doublehop<X, Y, Z>(
    sender: &signer,
    z_out: u64,
    x_max_in: u64,
)
```

#### Params

| Name       | Type     | Description                                    |
| ---------- | -------- | ---------------------------------------------- |
| sender     | `signer` | The sender's signer when calling the function. |
| z\_out     | `u64`    | Payable amount of output tokenZ.               |
| x\_max\_in | `u64`    | The maximum amount tokenX to input.            |

### Swap Exact Input Triple Hop

Swap exact amount of tokenX to tokenA using 3 pools (Pool XY, Pool YZ and Pool ZA).

```
public entry fun swap_exact_input_triplehop<X, Y, Z, A>(
    sender: &signer,
    x_in: u64,
    a_min_out: u64,
) 
```

#### Params

| Name        | Type     | Description                                    |
| ----------- | -------- | ---------------------------------------------- |
| sender      | `signer` | The sender's signer when calling the function. |
| x\_in       | `u64`    | Payable amount of input tokenX.                |
| a\_min\_out | `u64`    | The minimum amount tokenA to receive.          |

### Swap Exact Output Triple Hop

Swap tokenX to exact amount of tokenA using 3 pools (Pool XY, Pool YZ and Pool ZA).

```
public entry fun swap_exact_output_triplehop<X, Y, Z, A>(
    sender: &signer,
    a_out: u64,
    x_max_in: u64,
) 
```

| Name       | Type     | Description                                    |
| ---------- | -------- | ---------------------------------------------- |
| sender     | `signer` | The sender's signer when calling the function. |
| a\_out     | `u64`    | Payable amount of output tokenA.               |
| x\_max\_in | u64      | The maximum amount tokenX to input.            |

### Swap Exact Input Quadruple Hop

Swap exact amount of tokenX to tokenB using 3 pools (Pool XY, Pool YZ, Pool ZA and Pool AB).

```
public entry fun swap_exact_input_quadruplehop<X, Y, Z, A, B>(
    sender: &signer,
    x_in: u64,
    b_min_out: u64,
)
```

| Name        | Type     | Description                                    |
| ----------- | -------- | ---------------------------------------------- |
| sender      | `signer` | The sender's signer when calling the function. |
| x\_in       | `u64`    | Payable amount of input tokenX.                |
| b\_min\_out | `u64`    | The minimum amount tokenB to receive.          |

### Swap Exact Output Quadruple Hop

Swap tokenX to exact amount of tokenB using 3 pools (Pool XY, Pool YZ, Pool ZA and Pool AB).

```
public entry fun swap_exact_output_quadruplehop<X, Y, Z, A, B>(
    sender: &signer,
    b_out: u64,
    x_max_in: u64,
)
```

| Name       | Type     | Description                                    |
| ---------- | -------- | ---------------------------------------------- |
| sender     | `signer` | The sender's signer when calling the function. |
| b\_out     | `u64`    | Payable amount of output tokenB.               |
| x\_max\_in | u64      | The maximum amount tokenX to input.            |

## Public Functions

#### Swap Exact X to Y

Swap exact amount of tokenX to tokenY.

```
public fun swap_exact_x_to_y_direct_external<X, Y>(x_in: coin::Coin<X>): coin::Coin<Y> 
```

#### Input Values

| Name  | Type         | Description                                          |
| ----- | ------------ | ---------------------------------------------------- |
| x\_in | `coin::Coin` | The coin resource of tokenX that the user will swap. |

#### Return Values

| Type         | Description                                             |
| ------------ | ------------------------------------------------------- |
| `coin::Coin` | The coin resource of tokenY that the user will receive. |

#### Swap X to Exact Y

Swap tokenX to the exact amount of tokenY.

```
public fun swap_x_to_exact_y_direct_external<X, Y>(x_in: coin::Coin<X>, y_out_amount:u64): (coin::Coin<X>, coin::Coin<Y>)
```

#### Input Values

| Name           | Type         | Description                                           |
| -------------- | ------------ | ----------------------------------------------------- |
| x\_in          | `coin::Coin` | The coin resource of tokenX that the user will swap.  |
| y\_out\_amount | `u64`        | The expected amount of tokenY that user will receive. |

#### Return Values

| Position | Type         | Description                                          |
| -------- | ------------ | ---------------------------------------------------- |
| 0        | `coin::Coin` | The coin resource of tokenX that the user will swap. |
| 1        | `coin::Coin` | The coin resource of tokenY that user will receive.  |

### Get Amount In

The amount required in order to the the output amount.

```
public fun get_amount_in<X, Y>(y_out_amount: u64): u64
```

#### Input Values

| Name           | Type  | Description                                  |
| -------------- | ----- | -------------------------------------------- |
| y\_out\_amount | `u64` | The amount of tokenY that user will receive. |

#### Return Values

| Type  |                                                            |
| ----- | ---------------------------------------------------------- |
| `u64` | The amount of tokenX required to get the amount of tokenY. |
