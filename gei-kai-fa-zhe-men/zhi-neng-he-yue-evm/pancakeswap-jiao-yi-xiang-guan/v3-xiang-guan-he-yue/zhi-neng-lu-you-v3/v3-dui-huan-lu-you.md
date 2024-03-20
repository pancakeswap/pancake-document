---
description: 用于对 PancakeSwap V3 进行无状态交换的路由器
---

# V3 兑换路由

V3 兑换路由 （V3SwapRouter）。

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

通过 IPancakeV3Pool#swap 执行交换后调用“msg.sender”。

_在实施中，您必须支付交换所欠的池代币。必须检查此方法的调用方是否为规范 PancakeV3Factory 部署的 PancakeV3Pool。如果未交换任何代币，则 amount0Delta 和 amount1Delta 都可以为 0。_

**参数**

| 名字           | 类型     | 描述                                                               |
|--------------|--------|------------------------------------------------------------------|
| amount0Delta | int256 | 在交换结束时，池已发送（负数）或必须接收（正数）的 token0 数量。如果为正，则回调必须将该数量的 token0 发送到池。 |
| amount1Delta | int256 | 在交换结束时，池已发送（负数）或必须接收（正数）的 token1 数量。如果为正，则回调必须将该数量的 token1 发送到池。 |
| \_data       | bytes  |                                                                  |

#### exactInputSingle

```solidity
function exactInputSingle(struct IV3SwapRouter.ExactInputSingleParams params) external payable returns (uint256 amountOut)
```

将一个代币的“amountIn”换成尽可能多的另一个代币

_将 'amountIn' 设置为 0 将导致合约查找自己的余额，并交换全部金额，使合约能够在调用此函数之前发送代币。_

**参数**

| 名字     | 类型                                          | 描述                                              |
|--------|---------------------------------------------|-------------------------------------------------|
| params | struct IV3SwapRouter.ExactInputSingleParams | 交换所需的参数，在 calldata 中编码为“ExactInputSingleParams” |

**返回值**

| 名字        | 类型      | 描述       |
|-----------|---------|----------|
| amountOut | uint256 | 收到的代币的数量 |

#### exactInput

```solidity
function exactInput(struct IV3SwapRouter.ExactInputParams params) external payable returns (uint256 amountOut)
```

沿指定路径将一个代币的“amountIn”尽可能多地交换另一个代币

_将 'amountIn' 设置为 0 将导致合约查找自己的余额，并交换全部金额，使合约能够在调用此函数之前发送代币。_

**参数**

| 名字     | 类型                                    | 描述                                          |
|--------|---------------------------------------|---------------------------------------------|
| params | struct IV3SwapRouter.ExactInputParams | 多跳交换所需的参数，在 calldata 中编码为“ExactInputParams” |

**返回值**

| 名字        | 类型      | 描述       |
|-----------|---------|----------|
| amountOut | uint256 | 收到的代币的数量 |

#### exactOutputSingle

```solidity
function exactOutputSingle(struct IV3SwapRouter.ExactOutputSingleParams params) external payable returns (uint256 amountIn)
```

尽可能少地将一个代币交换为交换后可能保留在路由器中的另一个代币的“amountOut”。

**参数**

| 名字     | 类型                                           | 描述                                               |
|--------|----------------------------------------------|--------------------------------------------------|
| params | struct IV3SwapRouter.ExactOutputSingleParams | 交换所需的参数，在 calldata 中编码为“ExactOutputSingleParams” |

**返回值**

| 名字       | 类型      | 描述      |
|----------|---------|---------|
| amountIn | uint256 | 输入代币的数量 |

#### exactOutput

```solidity
function exactOutput(struct IV3SwapRouter.ExactOutputParams params) external payable returns (uint256 amountIn)
```

尽可能少地将一个代币交换为另一个代币的“amountOut”，该代币沿交换后可能保留在路由器中的指定路径（反向）。

**参数**

| 名字     | 类型                                     | 描述                                           |
|--------|----------------------------------------|----------------------------------------------|
| params | struct IV3SwapRouter.ExactOutputParams | 多跳交换所需的参数，在 calldata 中编码为“ExactOutputParams” |

**返回值**

| 名字       | 类型      | 描述      |
|----------|---------|---------|
| amountIn | uint256 | 输入代币的数量 |
