# 🔮 预测

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap 预测是一个有趣而简单的去中心化预测市场。

> #### 预测 BNB、BTC 或 ETH 的价格将上涨还是下跌——猜对即可获胜！

### 平台

你可以在以下平台玩 PancakeSwap 预测：

* **桌面端/ dApp**：[PancakeSwap 预测指南](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram 小程序（仅限 BNBUSD）**：[预测机器人](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### 概要：运作方式

1. **选择一项资产进行下注**：目前在 **BNB Chain**、**zkSync Era** 和 **Arbitrum One** 上可用。
2. **选择看涨或看跌**：预测当 "LIVE"（实时）阶段结束时资产价格会更高还是更低（每回合 = 5 分钟）。
3. 设置你的下注金额：任意 BNB 金额
4. **锁定你的仓位**：一旦下注，你的注无法更改。
5. **输赢**：
   * 如果你选择**看涨**，当回合结束时 _收盘价_ > _锁定价_，你就获胜。
   * 如果你选择**看跌**，当回合结束时 _收盘价_ < _锁定价_，你就获胜。

### 机制与手续费

* **支持的链：BNB Chain、zkSync Era、Arbitrum One**
* **回合频率**：每 **5 分钟**（滚动回合）。
* **参与费**：每回合总奖池的 **3%**，其中一部分用于 **CAKE 回购**。
* **奖金**：结果最终确定后可随时领取。
* **派彩**基于每个奖池中下注的比例：
  * 派彩比率（看涨奖池）= _(两个奖池的总价值 ÷ 看涨奖池的价值)_
  * 派彩比率（看跌奖池）= _(两个奖池的总价值 ÷ 看跌奖池的价值)_
  * 请参阅：[常见问题解答](prediction-faq.md)了解计算示例

### 结果

* **获胜：**你与其他获胜者分享整个奖池（扣除 3% 手续费后）
* **失败：**你将失去全部下注金额

**特殊情况**：

* **平局**（锁定价 = 收盘价）：庄家赢得所有下注。
* 如果没有相反方向的下注：
  * 如果你获胜：取回你初始下注的 97%（适用 3% 手续费）。
  * 如果你失败：将你的全部下注归庄家所有。
* **取消：**例如预言机故障，用户将获得其初始下注金额的退款。

### 价格源（预言机）

| 链     | 市场                                  | 用途                                                                 | 预言机                     |
| --------- | ---------------------------------------- | ----------------------------------------------------------------------- | -------------------------- |
| BNB Chain | BNBUSD、BTCUSD、ETHUSD、CAKEUSD（已暂停） | 设定 _锁定价_ 和 _收盘价_（更新间隔约最多 20 秒）。 | **Chainlink**              |
| BNB Chain | 全部                                      | 为 UI 上的实时图表提供支持（仅供参考）。                   | Binance / TradingView 价格源 |

#### **ChainLink 预言机**

* 用于每个预测市场回合的锁定价和结束价。其更新间隔最多为 20 秒。
* 我们的预测合约使用 BNB Chain 上的 ChainLink 预言机价格源来设定用于判定用户是否获胜的价格。
* 用于界面上的 "Chainlink" 图表。

#### **Binance**

* 用于 PancakeSwap 预测市场界面上的实时价格更新。
* 用于界面上的 "TradingView" 图表。

由于我们使用两个不同的价格源，来自 Binance 的实时价格更新与 ChainLink 预言机价格可能会有少量差异。然而，它们不应有显著的差异。

### 合约地址

BNB Chain：

* **BNBUSD**：[0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**：[0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**：[0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
