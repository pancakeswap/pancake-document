---
description: Router for stateless execution of swaps against PancakeSwap V2
---

# V2SwapRouter

## Solidity API

#### swapExactTokensForTokens

```solidity
function swapExactTokensForTokens(uint256 amountIn, uint256 amountOutMin, address[] path, address to) external payable returns (uint256 amountOut)
```

Swaps `amountIn` of one token for as much as possible of another token

_Setting `amountIn` to 0 will cause the contract to look up its own balance, and swap the entire amount, enabling contracts to send tokens before calling this function._

**Parameters**

| Name         | Type       | Description                                        |
| ------------ | ---------- | -------------------------------------------------- |
| amountIn     | uint256    | The amount of token to swap                        |
| amountOutMin | uint256    | The minimum amount of output that must be received |
| path         | address\[] | The ordered list of tokens to swap through         |
| to           | address    | The recipient address                              |

**Return Values**

| Name      | Type    | Description                      |
| --------- | ------- | -------------------------------- |
| amountOut | uint256 | The amount of the received token |

#### swapTokensForExactTokens

```solidity
function swapTokensForExactTokens(uint256 amountOut, uint256 amountInMax, address[] path, address to) external payable returns (uint256 amountIn)
```

Swaps as little as possible of one token for an exact amount of another token

**Parameters**

| Name        | Type       | Description                                          |
| ----------- | ---------- | ---------------------------------------------------- |
| amountOut   | uint256    | The amount of token to swap for                      |
| amountInMax | uint256    | The maximum amount of input that the caller will pay |
| path        | address\[] | The ordered list of tokens to swap through           |
| to          | address    | The recipient address                                |

**Return Values**

| Name     | Type    | Description                |
| -------- | ------- | -------------------------- |
| amountIn | uint256 | The amount of token to pay |
