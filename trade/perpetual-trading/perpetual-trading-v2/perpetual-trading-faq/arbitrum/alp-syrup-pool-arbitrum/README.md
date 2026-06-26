# ALP 糖浆池（Arbitrum）

ALP 是为 PancakeSwap 永续合约 V2 提供流动性的代币。用户使用 USDC、USDT、DAI、ETH 和 BTC 等抵押品代币铸造/购买 ALP。这些代币为由 ApolloX 提供支持的 PancakeSwap 永续合约交易引擎提供流动性。ALP 代币**不能在钱包之间转移**，只能**通过 ALP 合约铸造/出售并在 ALP 池中质押**。

### 分步指南

#### 购买/铸造 ALP

1. 点击进入 [PancakeSwap ALP 池 (V2)](https://perp.pancakeswap.finance/en/ALP) 页面并连接你的钱包
2. 连接钱包后，点击 **Buy ALP**。你可以使用任何 ALP 池资产来购买 ALP。
3. 确认信息后，点击 **Buy ALP** 完成交易。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Buy%20ALP%20Module.png" alt=""><figcaption></figcaption></figure>

**质押 ALP（Arbitrum）**

1. 在 Pancake ALP 仪表盘页面点击 **Stake Now**，或点击[此处](https://pancakeswap.finance/pools?chain=arb)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/png%20%284%29.png" alt=""><figcaption></figcaption></figure>

2. 选择 CAKE-ALP 糖浆池
3. **启用** ALP 并点击 **Stake**
4. 选择要质押的 ALP 数量并点击 **confirm**

**出售 ALP**

1. &#x20;点击进入 ALP 池 (V2) 页面并连接你的钱包
2. 连接钱包后，点击 **Sell ALP**。

出售 ALP 的条件：

* &#x20;用户可在购买后 48 小时出售 ALP
* &#x20;可出售的 ALP 代币数量：min\[(流动性池价值 - 用户仓位价值)\*50%]/ALP 市场价格。例如，流动性池价值为 10,000,000 USDT，用户仓位价值为 5,000,000 USDT，ALP 市场价格为 2 USDT，则 ALP 用户可出售的最大数量为 1,250,000。&#x20;
* 同时，用户出售其 ALP 代币后收到的资产数量不能超过 ALP 流动性池。例如，如果流动性池只有 1000 USDT，用户收到的 USDT 最大数量将为 1000 USDT，剩余的 ALP 可出售换取其他加密货币。
