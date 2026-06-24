---
description: 迁移到 MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 是一个全新的农场主质押合约，在为调整 $CAKE 释放量提供更多灵活性的同时，还涵盖了 CAKE 池、销毁以及其他 PancakeSwap 产品。

### 我需要迁移吗？

如果你当前正在使用 PancakeSwap MasterChef（[0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E)），则你需要迁移到新合约（[0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)）。

### 概述

#### 存款&#x20;

如果你当前正在当前的 PancakeSwap MasterChef 上使用 `enterStaking(uint256 _amount)`。你需要迁移到新的 CAKE 池合约。查看相关文档[此处](../cake-syrup-pool.md)。

农场矿池的存款函数没有变化。不过，你需要升级 MasterChef 地址和 `pid`，查看[农场列表](list-of-farms.md)了解 MasterChef v2 上新 `pids` 的列表。

#### 矿池类型

MasterChef v2 有两种类型的矿池：常规农场矿池和特殊农场矿池，你可以使用 `poolInfo(_pid).isRegular` 查询矿池类型。它们共享不同的 `totalAllocPoint`，使它们成为两组独立的矿池。

特殊农场矿池：只有列入白名单的地址才能存款。它们通常被 PancakeSwap 内部产品用于奖励分配。

常规农场矿池：常规的 LP 代币农场。例如 CAKE-BNB、BNB-BUSD 等……

#### 取款

如果你当前正在当前的 PancakeSwap MasterChef 上使用 `leaveStaking(uint256 _amount)`。你需要迁移到新的 CAKE 池合约。查看相关文档[此处](../cake-syrup-pool.md)。

农场矿池的取款函数没有变化。不过，你需要更新 MasterChef 地址和 `pid`，查看[农场列表](list-of-farms.md)了解 MasterChef v2 上新 `pids` 的列表。

#### 质押余额

使用 `userInfo[_pid][_user].amount` 查询质押余额。

#### 质押代币&#x20;

请注意，新的 `PoolInfo` 结构体**不**包含 lp 代币地址字段，你需要使用 `lpToken(_pid)` 来查询任何给定矿池的质押代币。&#x20;

#### 总质押份额/数量

使用 `lpToken.balanceOf(MasterChef.address)` 来获取任何给定农场矿池的总质押数量。

不过，在 MasterChef v2 中，用户的份额可以被加成（即将推出）。因此，奖励使用 `PoolInfo` 中一个新的 `totalBoostedShare` 字段作为每个矿池的总份额来计算。例如，如果矿池 0 有 2 个用户，user1 质押 100 个 LP（无加成），user2 质押 100 个（`boostMultiplier` 为 1.05），那么 `totalBoostedShare` 将变为 205。导致 user2 获得更多奖励。

#### CakePerBlock

你可以使用 `cakePerBlock(bool _isRegular)` 查询发放给所有 PancakeSwap 农场的每区块 CAKE 奖励。

### 主网合约地址

**合约名称：** MasterChef v2\
**合约地址：** `0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[在 BscScan 上查看 PancakeSwap: Main Staking Contract v2。](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### 测试网环境

你可以使用以下测试网环境来测试你的项目与新 PancakeSwap MasterChef v2 的集成。如果你有任何问题，请通过现有渠道联系我们的团队，或通过电子邮件联系 bun@pancakeswap.com。

**虚拟代币：**

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  （可通过 `mint(address _to, uint256 _amount) public` 铸造）
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  （可通过 `mint(uint256 amount) public` 铸造）
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### Factory 和 Router

* Factory v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* Router v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP 代币对

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### MasterChefs

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: 手动 CAKE
  * pid4: 用于 MasterChef v2 的虚拟池
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
