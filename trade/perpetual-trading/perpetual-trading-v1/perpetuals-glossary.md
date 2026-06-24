# 永续合约 V1 术语表

**在这里您将找到期货交易中所有相关术语的定义**

### **永续合约交易**

&#x20;永续合约（Perpetuals、perpetual swaps 或 perps）是一种特殊的期货合约，没有到期日。



### **杠杆**

杠杆是一种交易机制。交易者可以使用它来增加对市场的敞口，使他们能够支付低于全额投资的金额。简单来说，您借入资金来加杠杆放大您的投资。

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **保证金**

是您为杠杆仓位提供的担保。它有两种使用模式：

* 全仓保证金模式（Cross Margin Mode）：在同一保证金资产下的所有全仓仓位共享相同的资产全仓保证金余额。在清算情况下，您该资产的全部保证金余额以及该资产下任何剩余的未平仓仓位都可能被没收。
* 逐仓保证金模式（Isolated Margin Mode）：通过限制分配给每个仓位的保证金数额来管理单个仓位的风险。如果某个仓位的保证金率达到 100%，该仓位将被清算。使用此模式可以为仓位添加或移除保证金。

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**保证金率（Margin Ratio）**：保证金率 = 维持保证金 / 保证金余额。一旦保证金率达到 100%，您的仓位将被清算。

**维持率（Maintenance Ratio）**：维持您的未平仓仓位所需的最低保证金余额数额。

**保证金余额（Margin Balance）** = 钱包余额 + 未实现盈亏（PNL）。一旦保证金余额 <= 维持保证金，您的仓位将被清算。

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### 资产：

**存款（Deposit）**：将您的资金存入您的期货账户

**取款（Withdraw）**：将您的资金从您的期货账户取出到您的钱包

**余额（Balance）**：钱包余额 = 净转账总额 + 已实现利润总额 + 净资金费用总额 - 佣金总额。

**未实现盈亏（Unrealized PNL）**：基于标记价格（Mark Price）计算的该仓位的未实现盈亏，以及股本回报率百分比。

**模式（Modes）：**&#x20;

* 单一资产模式（Single Asset Mode）：仅使用该交易对的单一保证金资产来支持 USDⓈ-M 期货交易。相同保证金资产仓位的盈亏（PNL）可以相互抵消。支持全仓保证金模式和逐仓保证金模式。
* 多资产模式（Multi-Assets Mode）：跨多种保证金资产的 USDⓈ-M 期货交易。盈亏（PNL）可以在不同保证金资产仓位之间相互抵消。仅支持全仓保证金模式。

{% hint style="info" %}
注意：如果 USDⓈ-M 期货中有未平仓仓位或未成交订单，则无法启用多资产模式。多资产模式仅适用于 USDⓈ-M 期货。在启用多资产模式之前，请详细阅读指南，以便在使用多资产模式时相应地更好地管理 USDⓈ-M 期货账户风险。<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### 订单

**买入/做多（Buy/Long）：** 开立一个做多订单。在此订单中，您购买一项资产，并等待价格上涨时卖出。"买入" 和 "做多" 可互换使用。

**卖出/做空（Sell/Short）：** 开立一个做空订单。在此订单中，您借入一项资产，将其卖出，并期望在价格下跌时将其买回。"卖出" 和 "做空" 可互换使用。

**限价订单（Limit Order）：** 限价订单是以特定价格或更优价格买入或卖出的订单。限价订单不保证一定能成交。

**市价订单（Market Order）：** 市价订单是以当前最佳可用价格买入或卖出的订单。它会与之前挂在订单簿上的限价订单成交。下市价订单时，您将作为市场吃单方（taker）支付费用。

**止损限价订单（Stop Limit Order）：** 理解止损限价订单最简单的方法是将其分解为止损价和限价。止损价就是触发限价订单的价格，而限价是被触发的限价订单的价格。这意味着一旦达到您的止损价，您的限价订单将立即挂到订单簿上。

**止损市价订单（Stop Market Order）：** 与止损限价订单类似，止损市价订单使用止损价作为触发条件。但是，当达到止损价时，它触发的是市价订单。

**追踪止损（Trailing Stop）：** 追踪止损是一种订单类型，旨在随着交易朝有利方向变动而锁定利润或限制损失。追踪止损仅在价格朝有利方向变动时才会移动。一旦它移动以锁定利润或减少损失，就不会反向移回。

**只挂单（Post Only）：** 只挂单模式意味着交易者只能在订单将作为挂单方订单（Maker Order）挂到订单簿上时才能下单。将作为吃单方订单（Taker Order）挂出的订单将被拒绝。不能下市价订单，也不会有订单成交。在只挂单模式下，挂着的订单可以被取消。

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**只减仓（Reduce Only）：** 只减仓订单只会减少您的仓位，而不会增加它。

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF（订单有效时间）指令**允许您指定订单在执行或过期之前保持有效的时间。您可以为 TIF 指令选择以下选项之一：

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC**（Good Till Cancel，撤销前有效）：订单将保持有效，直到成交或被取消。&#x20;
* **IOC**（Immediate Or Cancel，立即成交并取消剩余）：订单将立即执行（全部或部分）。如果仅部分执行，订单未成交的部分将被取消。&#x20;
* **FOK**（Fill Or Kill，全部成交或立即取消）：订单必须立即全部成交。如果不能，则完全不执行。
