---
description: Wraps Pancake V3 positions in the ERC721 non-fungible token interface
---

# 非同质化仓位

非同质化仓位（NonfungiblePositionManager）。

### Contract Info

[Contract address](broken-reference)

## Solidity API

#### Position

```solidity
struct Position {
  uint96 nonce;
  address operator;
  uint80 poolId;
  int24 tickLower;
  int24 tickUpper;
  uint128 liquidity;
  uint256 feeGrowthInside0LastX128;
  uint256 feeGrowthInside1LastX128;
  uint128 tokensOwed0;
  uint128 tokensOwed1;
}
```

#### constructor

```solidity
constructor(address _deployer, address _factory, address _WETH9, address _tokenDescriptor_) public
```

#### positions

```solidity
function positions(uint256 tokenId) external view returns (uint96 nonce, address operator, address token0, address token1, uint24 fee, int24 tickLower, int24 tickUpper, uint128 liquidity, uint256 feeGrowthInside0LastX128, uint256 feeGrowthInside1LastX128, uint128 tokensOwed0, uint128 tokensOwed1)
```

Returns the position information associated with a given token ID.

_Throws if the token ID is not valid._

**Parameters**

| Name    | Type    | Description                                      |
| ------- | ------- | ------------------------------------------------ |
| tokenId | uint256 | The ID of the token that represents the position |

**Return Values**

<table><thead><tr><th width="261">Name</th><th width="190">Type</th><th>Description</th></tr></thead><tbody><tr><td>nonce</td><td>uint96</td><td>The nonce for permits</td></tr><tr><td>operator</td><td>address</td><td>The address that is approved for spending</td></tr><tr><td>token0</td><td>address</td><td>The address of the token0 for a specific pool</td></tr><tr><td>token1</td><td>address</td><td>The address of the token0 for a specific pool</td></tr><tr><td>fee</td><td>uint24</td><td>The fee associated with the pool</td></tr><tr><td>tickLower</td><td>int24</td><td>The lower end of the tick range for the position</td></tr><tr><td>tickUpper</td><td>int24</td><td>The higher end of the tick range for the position</td></tr><tr><td>liquidity</td><td>uint128</td><td>The liquidity of the position</td></tr><tr><td>feeGrowthInside0LastX128</td><td>uint256</td><td>The fee growth of token0 as of the last action on the individual position</td></tr><tr><td>feeGrowthInside1LastX128</td><td>uint256</td><td>The fee growth of token1 as of the last action on the individual position</td></tr><tr><td>tokensOwed0</td><td>uint128</td><td>The uncollected amount of token0 owed to the position as of the last computation</td></tr><tr><td>tokensOwed1</td><td>uint128</td><td>The uncollected amount of token1 owed to the position as of the last computation</td></tr></tbody></table>

#### mint

```solidity
function mint(struct INonfungiblePositionManager.MintParams params) external payable returns (uint256 tokenId, uint128 liquidity, uint256 amount0, uint256 amount1)
```

Creates a new position wrapped in a NFT

_Call this when the pool does exist and is initialized. Note that if the pool is created but not initialized a method does not exist, i.e. the pool is assumed to be initialized._

**Parameters**

| Name   | Type                                          | Description                                                                  |
| ------ | --------------------------------------------- | ---------------------------------------------------------------------------- |
| params | struct INonfungiblePositionManager.MintParams | The params necessary to mint a position, encoded as `MintParams` in calldata |

**Return Values**

| Name      | Type    | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| tokenId   | uint256 | The ID of the token that represents the minted position |
| liquidity | uint128 | The amount of liquidity for this position               |
| amount0   | uint256 | The amount of token0                                    |
| amount1   | uint256 | The amount of token1                                    |

#### isAuthorizedForToken

```solidity
modifier isAuthorizedForToken(uint256 tokenId)
```

#### tokenURI

```solidity
function tokenURI(uint256 tokenId) public view returns (string)
```

#### baseURI

```solidity
function baseURI() public pure returns (string)
```

\_Returns the base URI set via {_setBaseURI}. This will be automatically added as a prefix in {tokenURI} to each token's URI, or to the token ID if no specific URI is set for that token ID._

#### increaseLiquidity

```solidity
function increaseLiquidity(struct INonfungiblePositionManager.IncreaseLiquidityParams params) external payable returns (uint128 liquidity, uint256 amount0, uint256 amount1)
```

Increases the amount of liquidity in a position, with tokens paid by the `msg.sender`

**Parameters**

| Name   | Type                                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------ | ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| params | struct INonfungiblePositionManager.IncreaseLiquidityParams | tokenId The ID of the token for which liquidity is being increased, amount0Desired The desired amount of token0 to be spent, amount1Desired The desired amount of token1 to be spent, amount0Min The minimum amount of token0 to spend, which serves as a slippage check, amount1Min The minimum amount of token1 to spend, which serves as a slippage check, deadline The time by which the transaction must be included to effect the change |

**Return Values**

| Name      | Type    | Description                                          |
| --------- | ------- | ---------------------------------------------------- |
| liquidity | uint128 | The new liquidity amount as a result of the increase |
| amount0   | uint256 | The amount of token0 to acheive resulting liquidity  |
| amount1   | uint256 | The amount of token1 to acheive resulting liquidity  |

#### decreaseLiquidity

```solidity
function decreaseLiquidity(struct INonfungiblePositionManager.DecreaseLiquidityParams params) external payable returns (uint256 amount0, uint256 amount1)
```

Decreases the amount of liquidity in a position and accounts it to the position

**Parameters**

| Name   | Type                                                       | Description                                                                                                                                                                                                                                                                                                                                                                                        |
| ------ | ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| params | struct INonfungiblePositionManager.DecreaseLiquidityParams | tokenId The ID of the token for which liquidity is being decreased, amount The amount by which liquidity will be decreased, amount0Min The minimum amount of token0 that should be accounted for the burned liquidity, amount1Min The minimum amount of token1 that should be accounted for the burned liquidity, deadline The time by which the transaction must be included to effect the change |

**Return Values**

| Name    | Type    | Description                                                  |
| ------- | ------- | ------------------------------------------------------------ |
| amount0 | uint256 | The amount of token0 accounted to the position's tokens owed |
| amount1 | uint256 | The amount of token1 accounted to the position's tokens owed |

#### collect

```solidity
function collect(struct INonfungiblePositionManager.CollectParams params) external payable returns (uint256 amount0, uint256 amount1)
```

Collects up to a maximum amount of fees owed to a specific position to the recipient

**Parameters**

| Name   | Type                                             | Description                                                                                                                                                                                                                  |
| ------ | ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| params | struct INonfungiblePositionManager.CollectParams | tokenId The ID of the NFT for which tokens are being collected, recipient The account that should receive the tokens, amount0Max The maximum amount of token0 to collect, amount1Max The maximum amount of token1 to collect |

**Return Values**

| Name    | Type    | Description                            |
| ------- | ------- | -------------------------------------- |
| amount0 | unit256 | The amount of fees collected in token0 |
| amount1 | uint256 | The amount of fees collected in token1 |

#### burn

```solidity
function burn(uint256 tokenId) external payable
```

Burns a token ID, which deletes it from the NFT contract. The token must have 0 liquidity and all tokens must be collected first.

**Parameters**

| Name    | Type    | Description                              |
| ------- | ------- | ---------------------------------------- |
| tokenId | uint256 | The ID of the token that is being burned |

#### \_getAndIncrementNonce

```solidity
function _getAndIncrementNonce(uint256 tokenId) internal returns (uint256)
```

_Gets the current nonce for a token ID and then increments it, returning the original value_

#### getApproved

```solidity
function getApproved(uint256 tokenId) public view returns (address)
```

\_Returns the account approved for `tokenId` token.

Requirements:

* `tokenId` must exist.\_

#### \_approve

```solidity
function _approve(address to, uint256 tokenId) internal
```

\_Overrides _approve to use the operator in the position, which is packed with the position permit nonce_
