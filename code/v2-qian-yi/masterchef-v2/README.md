---
description: 迁移到 MasterChef v2
---

# MasterChef v2

PancakeSwap MasterChef v2 是用于农场的新版主质押合约，同时具备能将 $CAKE 产出灵活分配于 CAKE 池、销毁、以及其他 PancakeSwap 产品等的功能。

### 我需要迁移吗？&#x20;

如果您目前正在使用 PancakeSwap MasterChef ([0x73feaa1eE314F8c655E354234017bE2193C9E24E](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E))，您需要迁移到新的合约([0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652))。

### 概览

#### **存入**&#x20;

如果您目前正在使用当前 PancakeSwap MasterChef 上的 `enterStaking(uint256 _amount)`。您需要迁移到新的 CAKE 池合约。请查看[相关文档](../cake-tang-jiang-chi.md)。&#x20;

农场池的存入功能没有变化。但您需要更新 MasterChef 地址和 `pid` ，请查看[农场列表](nong-chang-lie-biao.md)以获取MasterChef v2 上新的  `pids` 列表。

#### **池子类型**

MasterChef v2 有两种类型的池子：常规农场池和特殊农场池，您可以使用 `poolInfo(_pid).isRegular` 来查询池子的类型。它们共享不同的 `totalAllocPoint`，因此是两种独立的池子。&#x20;

特殊农场池：只有白名单上的地址可以存入资金。它们通常被用于 PancakeSwap 自有产品的奖励分配。&#x20;

常规农场池：常规的 LP 代币农场。例如，CAKE-BNB，BNB-USD，等等。

#### 提取

如果您目前在当前 PancakeSwap MasterChef 上使用`leaveStaking(uint256 _amount)`。您需要迁移到新的 CAKE 糖浆池合约。请查看[相关文档](../cake-tang-jiang-chi.md)。&#x20;

农场池的提款功能没有变化，但您需要更新 MasterChef 的地址和`pid` ，请查看[农场列表](nong-chang-lie-biao.md)以获取MasterChef v2 上新的 `pids` 列表。

#### 质押余额&#x20;

使用`userInfo[_pid][_user].amount` 来查询质押余额。

#### 质押代币

请注意，新的`PoolInfo` 结构中**没有包含** lp token 地址字段，您需要使用`lpToken(_pid)`来查询任何给定池子的质押代币。

#### 总的质押份额/数量

使用`lpToken.balanceOf(MasterChef.address)` 可以得到任何给定农场池的总质押数量。&#x20;

但是，在MasterChef v2中，用户的持份可以被助推（即将推出）。因此，奖励的计算是使用`PoolInfo`中新的`totalBoostedShare`字段作为每个池的总份额。例如，如果 0 号池有 2 个用户，用户 1 质押 100 枚 LP 代币（预设无助推），用户 2 同样质押 100 枚（ `boostMultiplier`倍数为 1.05），那么`totalBoostedShare`将变成 205，使用户 2 获得更多的奖励。

#### 每个区块的 CAKE 奖励&#x20;

您可以使用`cakePerBlock(bool _isRegular)`来查询分配给 PancakeSwap 所有农场的的每区块 CAKE 奖励。

### 主要合约地址

**合约名称:** MasterChef v2\
**合约地址**`0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652`

[View the PancakeSwap: Main Staking Contract v2 on BscScan.](https://bscscan.com/address/0xa5f8C5Dbd5F286960b9d90548680aE5ebFf07652)

### 测试网环境&#x20;

您可以使用以下测试网环境来测试您的项目与新的 PancakeSwap MasterChef v2的集成情况。 如果您有任何问题，请通过现有社媒渠道联系我们的团队，或通过电子邮件联系 bun@pancakeswap.com。

#### 虚拟代币

* $CAKE: `0xFa60D973F7642B748046464e165A65B7323b0DEE`\
  (mintable by using `mint(address _to, uint256 _amount) public`)
* $BUSD: `0x8516Fc284AEEaa0374E66037BD2309349FF728eA`\
  (可通过 `mint(uint256 amount) public`铸造)
* $WBNB: `0xae13d989daC2f0dEbFf460aC112a837C89BAa7cd`

#### 工厂和路由

* 工厂 v2: `0x6725F303b657a9451d8BA641348b6761A6CC7a17`
* 路由 v2: `0xD99D1c33F9fC3444f8101754aBC46c52416550D1`

#### LP 对

* CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`

#### 主厨合约

* v1: `0x1ED62c7b76AD29Bfb80F3329d1ce7e760aAD153d`
  * pid0: Manual CAKE
  * pid4: Dummy Pool for MasterChef v2
  * pid5: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid6: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
* v2: `0xB4A466911556e39210a6bB2FaECBB59E4eB7E43d`
  * pid3: CAKE-BUSD: `0xb98C30fA9f5e9cf6749B7021b4DDc0DBFe73b73e`
  * pid4: CAKE-WBNB: `0xa96818CA65B57bEc2155Ba5c81a70151f63300CD`
