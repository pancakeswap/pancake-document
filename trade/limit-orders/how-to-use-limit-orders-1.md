# 如何使用限价单

PancakeSwap 上赚取手续费的限价单与传统限价单的运作方式不同。当用户下达限价单时，他们实际上是在向 PancakeSwap Infinity 池提供**单边流动性**。

随着市场价格变动，池中的兑换可以使用用户的流动性。当这种情况发生时，存入的代币会被完全转换为输出代币，用户将收到：

* 输出代币，以及
* 从针对其流动性执行的兑换中赚取的交易手续费。

***

**示例：将 BNB 卖出换成 USDT**

* **BNB/USDT 池中的当前价格：** 每 BNB 600 USDT
* **用户的目标价格 / 限价价格：** 每 BNB 700 USDT

流程：

1. 用户设置一个在 700 USDT 卖出 BNB 的限价单。
2. 他们的 BNB 被存入池中最接近每 BNB 700 USDT 价格的 tick。
3. 当外部市场价格达到 700 USDT 时，池价格会随之调整以匹配（由于套利机会 / 更优定价）。
4. 此时，用户的 BNB 被兑换成 USDT。
5. 在此过程中，用户从每笔消耗其流动性的兑换中赚取手续费。
6. 一旦流动性被完全消耗，转换后的 USDT（加上手续费）将自动提取并发送到用户的钱包。

***

### 分步指南

选择一个代币对（例如 BNB/CAKE）以及你想要卖出 / 买入的金额

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%E2%80%AFAM.png" alt="" width="375"><figcaption></figcaption></figure>

设置你的目标价格 / 限价价格

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%E2%80%AFAM.png" alt="" width="375"><figcaption></figcaption></figure>

下达限价单并点击"Confirm"。系统将代表你在最接近限价价格的 tick 处放置流动性

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%E2%80%AFAM.png" alt="" width="375"><figcaption></figcaption></figure>

一旦池价格达到你的目标，你的订单就会执行。所需的输出代币 + 手续费将自动提取并发送到你的钱包。

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%E2%80%AFPM.png" alt="" width="370"><figcaption></figcaption></figure>



### 订单状态

你可以点击此处查看你的订单状态

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%E2%80%AFPM.png" alt="" width="375"><figcaption></figcaption></figure>

**你的订单可能处于以下状态之一：**

| 状态             | 描述                                                                                     |
| ---------------- | ---------------------------------------------------------------------------------------- |
| 待处理 (Pending) | 等待价格达到你的目标                                                                      |
| 已成交 (Filled)  | 订单已执行，资金已发送到你的钱包                                                          |
| 部分成交 (Partially Filled) | 你的订单仅部分执行。你将同时持有两种代币（例如，一部分 BNB，一部分 USDT）       |
| 已取消 (Cancelled) | 你已取消订单。你的所有资金均已退还给你                                                  |

### 常见问题解答

**问：我需要支付手续费来下达限价单吗？**

答：不需要。相反，当你的订单执行时，你会赚取 0.1% 的交易手续费。

**问：我可以为任何交易对下单吗？**

答：上线时仅支持精选的交易对。后续将添加更多交易对。

**问：最小订单规模是多少？**

答：50 美元。这可以防止可能导致过多 gas 的微小订单。&#x20;

**问：如果我的订单仅部分成交会怎样？**

答：你将同时持有两种代币。你可以随时取消并提取两种代币以及赚取的手续费。

**问：我的订单已成交，但我的钱包中尚未收到资金？**

答：在极少数情况下可能会发生这种情况，但你的资金始终是安全的。只需使用订单详情 UI 中的"Withdraw"按钮即可手动领取资金。
