# MasterChef V3

## Solidity API

### MasterChefV3

#### PoolInfo

```solidity
struct PoolInfo {
  uint256 allocPoint;
  contract IPancakeV3Pool v3Pool;
  address token0;
  address token1;
  uint24 fee;
  uint256 totalLiquidity;
  uint256 totalBoostLiquidity;
}
```

#### UserPositionInfo

```solidity
struct UserPositionInfo {
  uint128 liquidity;
  uint128 boostLiquidity;
  int24 tickLower;
  int24 tickUpper;
  uint256 rewardGrowthInside;
  uint256 reward;
  address user;
  uint256 pid;
  uint256 boostMultiplier;
}
```

#### poolLength

```solidity
uint256 poolLength
```

#### poolInfo

```solidity
mapping(uint256 => struct MasterChefV3.PoolInfo) poolInfo
```

Info of each MCV3 pool.

#### userPositionInfos

```solidity
mapping(uint256 => struct MasterChefV3.UserPositionInfo) userPositionInfos
```

userPositionInfos\[tokenId] => UserPositionInfo

_TokenId is unique, and we can query the pid by tokenId._

#### v3PoolPid

```solidity
mapping(address => mapping(address => mapping(uint24 => uint256))) v3PoolPid
```

v3PoolPid\[token0]\[token1]\[fee] => pid

#### v3PoolAddressPid

```solidity
mapping(address => uint256) v3PoolAddressPid
```

v3PoolAddressPid\[v3PoolAddress] => pid

#### CAKE

```solidity
contract IERC20 CAKE
```

Address of CAKE contract.

#### WETH

```solidity
address WETH
```

Address of WETH contract.

#### receiver

```solidity
address receiver
```

Address of Receiver contract.

#### nonfungiblePositionManager

```solidity
contract INonfungiblePositionManager nonfungiblePositionManager
```

#### LMPoolDeployer

```solidity
contract ILMPoolDeployer LMPoolDeployer
```

Address of liquidity mining pool deployer contract.

#### FARM\_BOOSTER

```solidity
contract IFarmBooster FARM_BOOSTER
```

Address of farm booster contract.

#### emergency

```solidity
bool emergency
```

Only use for emergency situations.

#### totalAllocPoint

```solidity
uint256 totalAllocPoint
```

Total allocation points. Must be the sum of all pools' allocation points.

#### latestPeriodNumber

```solidity
uint256 latestPeriodNumber
```

#### latestPeriodStartTime

```solidity
uint256 latestPeriodStartTime
```

#### latestPeriodEndTime

```solidity
uint256 latestPeriodEndTime
```

#### latestPeriodCakePerSecond

```solidity
uint256 latestPeriodCakePerSecond
```

#### operatorAddress

```solidity
address operatorAddress
```

Address of the operator.

#### PERIOD\_DURATION

```solidity
uint256 PERIOD_DURATION
```

Default period duration.

#### MAX\_DURATION

```solidity
uint256 MAX_DURATION
```

#### MIN\_DURATION

```solidity
uint256 MIN_DURATION
```

#### PRECISION

```solidity
uint256 PRECISION
```

#### BOOST\_PRECISION

```solidity
uint256 BOOST_PRECISION
```

Basic boost factor, none boosted user's boost factor

#### MAX\_BOOST\_PRECISION

```solidity
uint256 MAX_BOOST_PRECISION
```

Hard limit for maxmium boost factor, it must greater than BOOST\_PRECISION

#### Q128

```solidity
uint256 Q128
```

#### MAX\_U256

```solidity
uint256 MAX_U256
```

#### cakeAmountBelongToMC

```solidity
uint256 cakeAmountBelongToMC
```

Record the cake amount belong to MasterChefV3.

#### ZeroAddress

```solidity
error ZeroAddress()
```

#### NotOwnerOrOperator

```solidity
error NotOwnerOrOperator()
```

#### NoBalance

```solidity
error NoBalance()
```

#### NotPancakeNFT

```solidity
error NotPancakeNFT()
```

#### InvalidNFT

```solidity
error InvalidNFT()
```

#### NotOwner

```solidity
error NotOwner()
```

#### NoLiquidity

```solidity
error NoLiquidity()
```

#### InvalidPeriodDuration

```solidity
error InvalidPeriodDuration()
```

#### NoLMPool

```solidity
error NoLMPool()
```

#### InvalidPid

```solidity
error InvalidPid()
```

#### DuplicatedPool

```solidity
error DuplicatedPool(uint256 pid)
```

#### NotEmpty

```solidity
error NotEmpty()
```

#### WrongReceiver

```solidity
error WrongReceiver()
```

#### InconsistentAmount

```solidity
error InconsistentAmount()
```

#### InsufficientAmount

```solidity
error InsufficientAmount()
```

#### Init

```solidity
event Init()
```

#### AddPool

```solidity
event AddPool(uint256 pid, uint256 allocPoint, contract IPancakeV3Pool v3Pool, contract ILMPool lmPool)
```

#### SetPool

```solidity
event SetPool(uint256 pid, uint256 allocPoint)
```

#### Deposit

```solidity
event Deposit(address from, uint256 pid, uint256 tokenId, uint256 liquidity, int24 tickLower, int24 tickUpper)
```

#### Withdraw

```solidity
event Withdraw(address from, address to, uint256 pid, uint256 tokenId)
```

#### UpdateLiquidity

```solidity
event UpdateLiquidity(address from, uint256 pid, uint256 tokenId, int128 liquidity, int24 tickLower, int24 tickUpper)
```

#### NewOperatorAddress

```solidity
event NewOperatorAddress(address operator)
```

#### NewLMPoolDeployerAddress

```solidity
event NewLMPoolDeployerAddress(address deployer)
```

#### NewReceiver

```solidity
event NewReceiver(address receiver)
```

#### NewPeriodDuration

```solidity
event NewPeriodDuration(uint256 periodDuration)
```

#### Harvest

```solidity
event Harvest(address sender, address to, uint256 pid, uint256 tokenId, uint256 reward)
```

#### NewUpkeepPeriod

```solidity
event NewUpkeepPeriod(uint256 periodNumber, uint256 startTime, uint256 endTime, uint256 cakePerSecond, uint256 cakeAmount)
```

#### UpdateUpkeepPeriod

```solidity
event UpdateUpkeepPeriod(uint256 periodNumber, uint256 oldEndTime, uint256 newEndTime, uint256 remainingCake)
```

#### UpdateFarmBoostContract

```solidity
event UpdateFarmBoostContract(address farmBoostContract)
```

#### SetEmergency

```solidity
event SetEmergency(bool emergency)
```

#### onlyOwnerOrOperator

```solidity
modifier onlyOwnerOrOperator()
```

#### onlyValidPid

```solidity
modifier onlyValidPid(uint256 _pid)
```

#### onlyReceiver

```solidity
modifier onlyReceiver()
```

#### onlyBoostContract

```solidity
modifier onlyBoostContract()
```

_Throws if caller is not the boost contract._

#### constructor

```solidity
constructor(contract IERC20 _CAKE, contract INonfungiblePositionManager _nonfungiblePositionManager, address _WETH) public
```

**Parameters**

| Name                         | Type                                 | Description                                |
| ---------------------------- | ------------------------------------ | ------------------------------------------ |
| \_CAKE                       | contract IERC20                      | The CAKE token contract address.           |
| \_nonfungiblePositionManager | contract INonfungiblePositionManager | the NFT position manager contract address. |
| \_WETH                       | address                              |                                            |

#### getLatestPeriodInfoByPid

```solidity
function getLatestPeriodInfoByPid(uint256 _pid) public view returns (uint256 cakePerSecond, uint256 endTime)
```

Returns the cake per second , period end time.

**Parameters**

| Name  | Type    | Description   |
| ----- | ------- | ------------- |
| \_pid | uint256 | The pool pid. |

#### getLatestPeriodInfo

```solidity
function getLatestPeriodInfo(address _v3Pool) public view returns (uint256 cakePerSecond, uint256 endTime)
```

Returns the cake per second , period end time. This is for liquidity mining pool.

**Parameters**

| Name     | Type    | Description             |
| -------- | ------- | ----------------------- |
| \_v3Pool | address | Address of the V3 pool. |

#### pendingCake

```solidity
function pendingCake(uint256 _tokenId) external view returns (uint256 reward)
```

View function for checking pending CAKE rewards.

_The pending cake amount is based on the last state in LMPool. The actual amount will happen whenever liquidity changes or harvest._

**Parameters**

| Name      | Type    | Description      |
| --------- | ------- | ---------------- |
| \_tokenId | uint256 | Token Id of NFT. |

#### setEmergency

```solidity
function setEmergency(bool _emergency) external
```

For emergency use only.

#### setReceiver

```solidity
function setReceiver(address _receiver) external
```

#### setLMPoolDeployer

```solidity
function setLMPoolDeployer(contract ILMPoolDeployer _LMPoolDeployer) external
```

#### add

```solidity
function add(uint256 _allocPoint, contract IPancakeV3Pool _v3Pool, bool _withUpdate) external
```

Add a new pool. Can only be called by the owner. One v3 pool can only create one pool.

**Parameters**

| Name         | Type                    | Description                                   |
| ------------ | ----------------------- | --------------------------------------------- |
| \_allocPoint | uint256                 | Number of allocation points for the new pool. |
| \_v3Pool     | contract IPancakeV3Pool | Address of the V3 pool.                       |
| \_withUpdate | bool                    | Whether call "massUpdatePools" operation.     |

#### set

```solidity
function set(uint256 _pid, uint256 _allocPoint, bool _withUpdate) external
```

Update the given pool's CAKE allocation point. Can only be called by the owner.

**Parameters**

| Name         | Type    | Description                                   |
| ------------ | ------- | --------------------------------------------- |
| \_pid        | uint256 | The id of the pool. See `poolInfo`.           |
| \_allocPoint | uint256 | New number of allocation points for the pool. |
| \_withUpdate | bool    | Whether call "massUpdatePools" operation.     |

#### DepositCache

```solidity
struct DepositCache {
  address token0;
  address token1;
  uint24 fee;
  int24 tickLower;
  int24 tickUpper;
  uint128 liquidity;
}
```

#### onERC721Received

```solidity
function onERC721Received(address, address _from, uint256 _tokenId, bytes) external returns (bytes4)
```

Upon receiving a ERC721

#### harvest

```solidity
function harvest(uint256 _tokenId, address _to) external returns (uint256 reward)
```

harvest cake from pool.

**Parameters**

| Name      | Type    | Description      |
| --------- | ------- | ---------------- |
| \_tokenId | uint256 | Token Id of NFT. |
| \_to      | address | Address to.      |

#### harvestOperation

```solidity
function harvestOperation(struct MasterChefV3.UserPositionInfo positionInfo, uint256 _tokenId, address _to) internal returns (uint256 reward)
```

#### withdraw

```solidity
function withdraw(uint256 _tokenId, address _to) external returns (uint256 reward)
```

Withdraw LP tokens from pool.

**Parameters**

| Name      | Type    | Description                             |
| --------- | ------- | --------------------------------------- |
| \_tokenId | uint256 | Token Id of NFT to deposit.             |
| \_to      | address | Address to which NFT token to withdraw. |

#### updateLiquidity

```solidity
function updateLiquidity(uint256 _tokenId) external
```

Update liquidity for the NFT position.

**Parameters**

| Name      | Type    | Description                |
| --------- | ------- | -------------------------- |
| \_tokenId | uint256 | Token Id of NFT to update. |

#### updateBoostMultiplier

```solidity
function updateBoostMultiplier(uint256 _tokenId, uint256 _newMultiplier) external
```

Update farm boost multiplier for the NFT position.

**Parameters**

| Name            | Type    | Description                |
| --------------- | ------- | -------------------------- |
| \_tokenId       | uint256 | Token Id of NFT to update. |
| \_newMultiplier | uint256 | New boost multiplier.      |

#### updateLiquidityOperation

```solidity
function updateLiquidityOperation(struct MasterChefV3.UserPositionInfo positionInfo, uint256 _tokenId, uint256 _newMultiplier) internal
```

#### increaseLiquidity

```solidity
function increaseLiquidity(struct INonfungiblePositionManagerStruct.IncreaseLiquidityParams params) external payable returns (uint128 liquidity, uint256 amount0, uint256 amount1)
```

Increases the amount of liquidity in a position, with tokens paid by the `msg.sender`

**Parameters**

| Name   | Type                                                             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------ | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| params | struct INonfungiblePositionManagerStruct.IncreaseLiquidityParams | tokenId The ID of the token for which liquidity is being increased, amount0Desired The desired amount of token0 to be spent, amount1Desired The desired amount of token1 to be spent, amount0Min The minimum amount of token0 to spend, which serves as a slippage check, amount1Min The minimum amount of token1 to spend, which serves as a slippage check, deadline The time by which the transaction must be included to effect the change |

**Return Values**

| Name      | Type    | Description                                          |
| --------- | ------- | ---------------------------------------------------- |
| liquidity | uint128 | The new liquidity amount as a result of the increase |
| amount0   | uint256 | The amount of token0 to acheive resulting liquidity  |
| amount1   | uint256 | The amount of token1 to acheive resulting liquidity  |

#### pay

```solidity
function pay(address _token, uint256 _amount) internal
```

Pay.

**Parameters**

| Name     | Type    | Description       |
| -------- | ------- | ----------------- |
| \_token  | address | The token to pay  |
| \_amount | uint256 | The amount to pay |

#### refund

```solidity
function refund(address _token, uint256 _amount) internal
```

Refund.

**Parameters**

| Name     | Type    | Description          |
| -------- | ------- | -------------------- |
| \_token  | address | The token to refund  |
| \_amount | uint256 | The amount to refund |

#### decreaseLiquidity

```solidity
function decreaseLiquidity(struct INonfungiblePositionManagerStruct.DecreaseLiquidityParams params) external returns (uint256 amount0, uint256 amount1)
```

Decreases the amount of liquidity in a position and accounts it to the position

**Parameters**

| Name   | Type                                                             | Description                                                                                                                                                                                                                                                                                                                                                                                        |
| ------ | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| params | struct INonfungiblePositionManagerStruct.DecreaseLiquidityParams | tokenId The ID of the token for which liquidity is being decreased, amount The amount by which liquidity will be decreased, amount0Min The minimum amount of token0 that should be accounted for the burned liquidity, amount1Min The minimum amount of token1 that should be accounted for the burned liquidity, deadline The time by which the transaction must be included to effect the change |

**Return Values**

| Name    | Type    | Description                                                  |
| ------- | ------- | ------------------------------------------------------------ |
| amount0 | uint256 | The amount of token0 accounted to the position's tokens owed |
| amount1 | uint256 | The amount of token1 accounted to the position's tokens owed |

#### collect

```solidity
function collect(struct INonfungiblePositionManagerStruct.CollectParams params) external returns (uint256 amount0, uint256 amount1)
```

Collects up to a maximum amount of fees owed to a specific position to the recipient

_Warning!!! Please make sure to use multicall to call unwrapWETH9 or sweepToken when set recipient address(0), or you will lose your funds. amount0Max The maximum amount of token0 to collect, amount1Max The maximum amount of token1 to collect_

**Parameters**

| Name   | Type                                                   | Description                                                                                                           |
| ------ | ------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| params | struct INonfungiblePositionManagerStruct.CollectParams | tokenId The ID of the NFT for which tokens are being collected, recipient The account that should receive the tokens, |

**Return Values**

| Name    | Type    | Description                            |
| ------- | ------- | -------------------------------------- |
| amount0 | uint256 | The amount of fees collected in token0 |
| amount1 | uint256 | The amount of fees collected in token1 |

#### collectTo

```solidity
function collectTo(struct INonfungiblePositionManagerStruct.CollectParams params, address to) external returns (uint256 amount0, uint256 amount1)
```

Collect fees and refund.

#### transferToken

```solidity
function transferToken(address _token, address _to) internal
```

Transfer token from MasterChef V3.

**Parameters**

| Name    | Type    | Description            |
| ------- | ------- | ---------------------- |
| \_token | address | The token to transfer. |
| \_to    | address | The to address.        |

#### unwrapWETH9

```solidity
function unwrapWETH9(uint256 amountMinimum, address recipient) external
```

Unwraps the contract's WETH9 balance and sends it to recipient as ETH.

_The amountMinimum parameter prevents malicious contracts from stealing WETH9 from users._

**Parameters**

| Name          | Type    | Description                           |
| ------------- | ------- | ------------------------------------- |
| amountMinimum | uint256 | The minimum amount of WETH9 to unwrap |
| recipient     | address | The address receiving ETH             |

#### sweepToken

```solidity
function sweepToken(address token, uint256 amountMinimum, address recipient) external
```

Transfers the full amount of a token held by this contract to recipient

_The amountMinimum parameter prevents malicious contracts from stealing the token from users_

**Parameters**

| Name          | Type    | Description                                                                |
| ------------- | ------- | -------------------------------------------------------------------------- |
| token         | address | The contract address of the token which will be transferred to `recipient` |
| amountMinimum | uint256 | The minimum amount of token required for a transfer                        |
| recipient     | address | The destination address of the token                                       |

#### burn

```solidity
function burn(uint256 _tokenId) external
```

Burns a token ID, which deletes it from the NFT contract. The token must have 0 liquidity and all tokens must be collected first.

**Parameters**

| Name      | Type    | Description                              |
| --------- | ------- | ---------------------------------------- |
| \_tokenId | uint256 | The ID of the token that is being burned |

#### upkeep

```solidity
function upkeep(uint256 _amount, uint256 _duration, bool _withUpdate) external
```

Upkeep period.

**Parameters**

| Name         | Type    | Description                               |
| ------------ | ------- | ----------------------------------------- |
| \_amount     | uint256 | The amount of cake injected.              |
| \_duration   | uint256 | The period duration.                      |
| \_withUpdate | bool    | Whether call "massUpdatePools" operation. |

#### massUpdatePools

```solidity
function massUpdatePools() internal
```

Update cake reward for all the liquidity mining pool.

#### updatePools

```solidity
function updatePools(uint256[] pids) external
```

Update cake reward for the liquidity mining pool.

_Avoid too many pools, and a single transaction cannot be fully executed for all pools._

#### setOperator

```solidity
function setOperator(address _operatorAddress) external
```

Set operator address.

_Callable by owner_

**Parameters**

| Name              | Type    | Description           |
| ----------------- | ------- | --------------------- |
| \_operatorAddress | address | New operator address. |

#### setPeriodDuration

```solidity
function setPeriodDuration(uint256 _periodDuration) external
```

Set period duration.

_Callable by owner_

**Parameters**

| Name             | Type    | Description          |
| ---------------- | ------- | -------------------- |
| \_periodDuration | uint256 | New period duration. |

#### updateFarmBoostContract

```solidity
function updateFarmBoostContract(address _newFarmBoostContract) external
```

Update farm boost contract address.

**Parameters**

| Name                   | Type    | Description                   |
| ---------------------- | ------- | ----------------------------- |
| \_newFarmBoostContract | address | The new farm booster address. |

#### safeTransferETH

```solidity
function safeTransferETH(address to, uint256 value) internal
```

Transfer ETH in a safe way

**Parameters**

| Name  | Type    | Description |
| ----- | ------- | ----------- |
| to    | address |             |
| value | uint256 |             |

#### \_safeTransfer

```solidity
function _safeTransfer(address _to, uint256 _amount) internal
```

Safe Transfer CAKE.

**Parameters**

| Name     | Type    | Description                |
| -------- | ------- | -------------------------- |
| \_to     | address | The CAKE receiver address. |
| \_amount | uint256 | Transfer CAKE amounts.     |

#### receive

```solidity
receive() external payable
```
