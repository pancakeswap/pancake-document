---
description: Router for stateless execution of swaps against PancakeSwap V3
---

# V3SwapRouter

## Solidity API

#### SwapCallbackData

```solidity
struct SwapCallbackData {
  bytes path;
  address payer;
}
```

#### pancakeV3SwapCallback

```solidity
function pancakeV3SwapCallback(int256 amount0Delta, int256 amount1Delta, bytes _data) external
```

Called to `msg.sender` after executing a swap via IPancakeV3Pool#swap.

_In the implementation you must pay the pool tokens owed for the swap. The caller of this method must be checked to be a PancakeV3Pool deployed by the canonical PancakeV3Factory. amount0Delta and amount1Delta can both be 0 if no tokens were swapped._

**Parameters**

| Name         | Type   | Description                                                                                                                                                                             |
| ------------ | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| amount0Delta | int256 | The amount of token0 that was sent (negative) or must be received (positive) by the pool by the end of the swap. If positive, the callback must send that amount of token0 to the pool. |
| amount1Delta | int256 | The amount of token1 that was sent (negative) or must be received (positive) by the pool by the end of the swap. If positive, the callback must send that amount of token1 to the pool. |
| \_data       | bytes  |                                                                                                                                                                                         |

#### exactInputSingle

```solidity
function exactInputSingle(struct IV3SwapRouter.ExactInputSingleParams params) external payable returns (uint256 amountOut)
```

Swaps `amountIn` of one token for as much as possible of another token

_Setting `amountIn` to 0 will cause the contract to look up its own balance, and swap the entire amount, enabling contracts to send tokens before calling this function._

**Parameters**

| Name   | Type                                        | Description                                                                            |
| ------ | ------------------------------------------- | -------------------------------------------------------------------------------------- |
| params | struct IV3SwapRouter.ExactInputSingleParams | The parameters necessary for the swap, encoded as `ExactInputSingleParams` in calldata |

**Return Values**

| Name      | Type    | Description                      |
| --------- | ------- | -------------------------------- |
| amountOut | uint256 | The amount of the received token |

#### exactInput

```solidity
function exactInput(struct IV3SwapRouter.ExactInputParams params) external payable returns (uint256 amountOut)
```

Swaps `amountIn` of one token for as much as possible of another along the specified path

_Setting `amountIn` to 0 will cause the contract to look up its own balance, and swap the entire amount, enabling contracts to send tokens before calling this function._

**Parameters**

| Name   | Type                                  | Description                                                                                |
| ------ | ------------------------------------- | ------------------------------------------------------------------------------------------ |
| params | struct IV3SwapRouter.ExactInputParams | The parameters necessary for the multi-hop swap, encoded as `ExactInputParams` in calldata |

**Return Values**

| Name      | Type    | Description                      |
| --------- | ------- | -------------------------------- |
| amountOut | uint256 | The amount of the received token |

#### exactOutputSingle

```solidity
function exactOutputSingle(struct IV3SwapRouter.ExactOutputSingleParams params) external payable returns (uint256 amountIn)
```

Swaps as little as possible of one token for `amountOut` of another token that may remain in the router after the swap.

**Parameters**

| Name   | Type                                         | Description                                                                             |
| ------ | -------------------------------------------- | --------------------------------------------------------------------------------------- |
| params | struct IV3SwapRouter.ExactOutputSingleParams | The parameters necessary for the swap, encoded as `ExactOutputSingleParams` in calldata |

**Return Values**

| Name     | Type    | Description                   |
| -------- | ------- | ----------------------------- |
| amountIn | uint256 | The amount of the input token |

#### exactOutput

```solidity
function exactOutput(struct IV3SwapRouter.ExactOutputParams params) external payable returns (uint256 amountIn)
```

Swaps as little as possible of one token for `amountOut` of another along the specified path (reversed) that may remain in the router after the swap.

**Parameters**

| Name   | Type                                   | Description                                                                                 |
| ------ | -------------------------------------- | ------------------------------------------------------------------------------------------- |
| params | struct IV3SwapRouter.ExactOutputParams | The parameters necessary for the multi-hop swap, encoded as `ExactOutputParams` in calldata |

**Return Values**

| Name     | Type    | Description                   |
| -------- | ------- | ----------------------------- |
| amountIn | uint256 | The amount of the input token |
