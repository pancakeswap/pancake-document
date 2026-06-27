# 常见问题解答

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### 我应该在其他区块链上的 PancakeSwap 上做什么？

像往常一样提供流动性、交易和农场挖矿。如果你已经是多链用户，请记得在我们已部署的其他区块链上的 PancakeSwap（如 Ethereum）上提供流动性，因为我们在 BNB Smart Chain 上为你准备了 CAKE 奖励，让你无需跨链转移这些资产就能赚取更多 CAKE！

### **会有更多交易对吗？**

会的，但我们将分步部署，以确保优先保障用户资金的安全和 CAKE 的通胀控制。请在社区聊天中告诉我们，你认为应该向其他区块链上的 PancakeSwap 添加什么，以及我们应该在哪些其他区块链上部署 PancakeSwap。

### **为什么质押 LP 代币的 gas 成本很高？**

首次设置需要少量原生代币（例如，Ethereum 上的 ETH）。因此第一笔交易的成本会稍高一些。

此外，跨链农场挖矿还涉及其他费用（主要是 gas 成本）。查看[这个](faq.md#are-there-any-fees-when-i-do-crosschain-farming)专门的部分以了解更多。

### **为什么质押和取消质押需要 30 分钟才能完成？**

所有跨链交易大约需要 30 分钟才能完成。这是因为：

* 交易必须在农场挖矿区块链（如 Ethereum）和 BNB Chain 上同时执行。
* 传递跨链消息需要时间。
* 为确保安全，并使所有数据在不同区块链之间同步一致。

### **我收获的 CAKE 奖励在哪里？**

你收获的 CAKE 将在 BNB Smart Chain 上分发。请在钱包中切换区块链网络以查看 CAKE 余额。

### **我无法收获，因为我的钱包不支持在不同区块链之间切换！**

请尝试使用支持多链和链切换的其他钱包应用。

请注意，质押和取消质押 LP 代币也会将所有已赚取的 CAKE 收获到你在 BNB Smart Chain 上的钱包。因此，如果你不想使用其他钱包应用，只需质押更多，或取消质押少量 LP 代币即可收获已赚取的 CAKE。

### 进行跨链农场挖矿时是否有任何费用？

与在 BNB Chain 上原生进行农场挖矿不同，在其他区块链上进行农场挖矿需要跨链活动。以下是涉及的费用：

**1 - 创建代理合约的 gas 费**

跨链农场挖矿必须在 BNB Chain 上创建一个代理合约。代理合约创建的 gas 成本包含在交易中。

此费用仅在首次“质押”交易时收取一次。

**2 - BNB Chain 上调用的 gas 费**

当用户存入或提取 LP 代币时，执行器将在 BNB Chain 上代表用户执行调用交易。这些调用的 gas 成本包含在交易中。

此费用在每次存入或提取交易中收取。

**3 - 其他区块链上调用的 gas 费**

当用户提取 LP 代币时，执行器将执行最终的调用交易，以在其他区块链（如 Ethereum）上释放 LP 代币。这些调用的 gas 成本包含在交易中。

此费用仅在提取交易中收取。

**4 - 跨链消息传递费**

我们利用由 Celer 驱动的消息总线来路由我们的跨链消息。因此，会根据消息的字节长度收取一笔消息费。

此费用在每次质押交易中收取。在取消质押交易中，由于出于安全考虑需要 BNB Chain 与其他区块链之间的双向通信，因此此费用会收取两次。

```
messagingFee = feeBase + message.length * feePerByte;
```

你可以在消息总线合约中找到公式中的变量：

* Ethereum：`0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain：`0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - 启动资金**

严格来说这并不是一种“费用”。&#x20;

对于每个开始进行 PancakeSwap 跨链农场挖矿的新用户，在第一笔“质押”交易中，我们将向其 BNB Chain 钱包存入 0.005 BNB。相应数量的农场挖矿链上的原生代币（如 Ethereum 上的 ETH）将从存入交易中扣除，使用价格预言机提供的市场汇率。

这是为了帮助用户轻松开启他们的 BNB Chain 之旅。我们理解那种拥有所有已收获的 CAKE，却因找不到其他方式获取 BNB 作为 gas 而无法探索充满活力的 PancakeSwap 生态系统的痛苦。

此费用仅在首次“质押”交易时收取一次。

### 排放来自哪里？&#x20;

_更新于 2022 年 10 月 10 日_

目前，主厨们已从 CAKE 资金池中将每个区块 0.0189 CAKE 转移到所有跨链农场。&#x20;

以下是排放明细：

<table><thead><tr><th width="249"></th><th>倍数</th><th>每区块 CAKE</th></tr></thead><tbody><tr><td><strong>CAKE 资金池</strong></td><td>-</td><td><strong>8.9811</strong></td></tr><tr><td><strong>所有跨链农场</strong></td><td>-</td><td><strong>0.0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0.5x</td><td>0.0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0.2x</td><td>0.0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0.2x</td><td>0.0042</td></tr></tbody></table>

### 在存入、收获和提取过程中发生了什么？

PancakeSwap 跨链农场挖矿就像使用一个“替身”LP 代币，在 BNB Chain 上用同一个 PancakeSwap MasterChef 进行农场挖矿。CAKE 奖励在 BNB Chain 上计算和分发，由同一个 MasterChef 合约控制和守护。

#### 存入时：

1. 用户在农场挖矿区块链（如 Ethereum）上请求存入 LP 代币。
2. LP 代币被转移到农场挖矿金库合约。
3. 利用 Celer 消息总线将“存入”消息传递到 BNB Chain。
4. BNB Chain 上的执行器铸造相同数量的农场挖矿代币作为“替身”，然后将它们存入农场。

#### 收获时：

由于 CAKE 奖励在 BNB Chain 上计算和分发，用户可以通过单笔 BNB Chain 交易领取他们的 CAKE 奖励，而无需进行跨链操作。

#### 提取时：

1. 用户在农场挖矿区块链（如 Ethereum）上请求提取 LP 代币。
2. 利用 Celer 消息总线将“提取”消息传递到 BNB Chain。
3. BNB Chain 上的执行器从农场中提取农场挖矿代币，销毁这些代币，将赚取的 CAKE 转给用户，并利用 Celer 消息总线将确认消息传回原始农场挖矿区块链。
4. 农场挖矿区块链上的执行器确认一切后，从金库合约中释放 LP 代币。
