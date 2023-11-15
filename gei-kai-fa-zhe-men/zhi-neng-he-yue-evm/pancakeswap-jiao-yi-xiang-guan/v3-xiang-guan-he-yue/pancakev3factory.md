# PancakeV3Factory

## PancakeV3Factory

Deploys PancakeSwap V3 pools and manages ownership and control over pool protocol fees

### Contract info <a href="#contract-info" id="contract-info"></a>

**Contract name:** PancakeFactory​[Contract address](https://docs.pancakeswap.finance/developers/smart-contracts/pancakeswap-exchange/v3-contracts#address)​​

### Solidity API <a href="#solidity-api" id="solidity-api"></a>

#### PancakeV3Factory <a href="#pancakev3factory" id="pancakev3factory"></a>

Deploys PancakeSwap V3 pools and manages ownership and control over pool protocol fees

**owner**

address ownerReturns the current owner of the factory_Can be changed by the current owner via setOwner_**Return Values**

**poolDeployer**

address poolDeployerReturns the current pool deployer

**feeAmountTickSpacing**

mapping(uint24 => int24) feeAmountTickSpacingReturns the tick spacing for a given fee amount, if enabled, or 0 if not enabled_A fee amount can never be removed, so this value should be hard coded or cached in the calling context_**ParametersReturn Values**

**getPool**

mapping(address => mapping(address => mapping(uint24 => address))) getPoolReturns the pool address for a given pair of tokens and a fee, or address 0 if it does not exist_tokenA and tokenB may be passed in either token0/token1 or token1/token0 order_**ParametersReturn Values**

**feeAmountTickSpacingExtraInfo**

mapping(uint24 => struct IPancakeV3Factory.TickSpacingExtraInfo) feeAmountTickSpacingExtraInfoReturns the tick spacing extra info_A fee amount can never be removed, so this value should be hard coded or cached in the calling context_**ParametersReturn Values**

**constructor**

constructor(address \_poolDeployer) public

**createPool**

function createPool(address tokenA, address tokenB, uint24 fee) external returns (address pool)Creates a pool for the given two tokens and fee_tokenA and tokenB may be passed in either order: token0/token1 or token1/token0. tickSpacing is retrieved from the fee. The call will revert if the pool already exists, the fee is invalid, or the token arguments are invalid._**Parameters**

| Name   | Type    | Description                                     |
| ------ | ------- | ----------------------------------------------- |
| tokenA | address | One of the two tokens in the desired pool       |
| tokenB | address | The other of the two tokens in the desired pool |
| fee    | uint24  | The desired fee for the pool                    |

**Return Values**

| Name | Type    | Description                           |
| ---- | ------- | ------------------------------------- |
| pool | address | The address of the newly created pool |

**setOwner**

function setOwner(address \_owner) externalUpdates the owner of the factory_Must be called by the current owner_**Parameters**

| Name    | Type    | Description                  |
| ------- | ------- | ---------------------------- |
| \_owner | address | The new owner of the factory |

**enableFeeAmount**

function enableFeeAmount(uint24 fee, int24 tickSpacing) publicEnables a fee amount with the given tickSpacing_Fee amounts may never be removed once enabled_**Parameters**

| Name        | Type   | Description                                                                              |
| ----------- | ------ | ---------------------------------------------------------------------------------------- |
| fee         | uint24 | The fee amount to enable, denominated in hundredths of a bip (i.e. 1e-6)                 |
| tickSpacing | int24  | The spacing between ticks to be enforced for all pools created with the given fee amount |

**setWhiteListAddress**

function setWhiteListAddress(address user, bool verified) publicSet an address into white list_Address can be updated by owner with boolean value false_**Parameters**

| Name     | Type    | Description                               |
| -------- | ------- | ----------------------------------------- |
| user     | address | The user address that add into white list |
| verified | bool    | ​                                         |

**setFeeAmountExtraInfo**

function setFeeAmountExtraInfo(uint24 fee, bool whitelistRequested, bool enabled) publicSet a fee amount extra info_Fee amounts can be updated by owner with extra info_**Parameters**

| Name               | Type   | Description                                      |
| ------------------ | ------ | ------------------------------------------------ |
| fee                | uint24 | ​                                                |
| whitelistRequested | bool   | The flag whether should be created by owner only |
| enabled            | bool   | The flag is the fee is enabled or not            |
