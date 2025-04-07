# Perpetuals V1 Glossary

**Here you will find defined all the terms inherent in futures trading**

### **Perpetual Trading**

&#x20;Perpetuals, perpetual swaps, or perps are a special type of futures contract without an expiration date.



### **Leverage**

Leverage is a trading mechanism. Traders can use it to increase their exposure to the market by allowing them to pay less than the full amount of the investment. In simple words, you borrow money to leverage your investment.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9\_QPioIxT9sFRuY-EEtuSXgCn\_D8Muwqh60PFr3EcEu3kkH)

### **Margin**

is the guarantee you put for your leveraged positions. It has two Modes to use it:

* Cross Margin Mode: All cross positions under the same margin asset share the same asset cross margin balance. In the event of liquidation, your assets full margin balance along with any remaining open positions under the asset may be forfeited.
* Isolated Margin Mode: Manage your risk on individual positions by restricting the amount of margin allocated to each. If the margin ratio of a position reached 100%, the position will be liquidated. Margin can be added or removed to positions using this mode.

![](https://lh3.googleusercontent.com/zVEa2C\_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55\_ZKRNTy8WoCpUs)

**Margin Ratio**: Margin Ratio = Maintenance Margin / Margin Balance. Your positions will be liquidated once Margin Ratio reaches 100%.

**Maintenance Ratio**: The minimum amount of margin balance required to keep your open positions.

**Margin Balance** = Wallet Balance + Unrealized PNL. Your positions will be liquidated once Margin Balance <= Maintenance Margin.

![](https://lh6.googleusercontent.com/BGaNOmsOkew\_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Assets:

**Deposit**: Deposit your funds into your futures account

**Withdraw**: Withdraw your funds from your futures account to your wallet

**Balance**: Wallet Balance = Total Net Transfer + Total Realized Profit + Total Net Funding Fee - Total Commission.

**Unrealized PNL**: Unrealized profit and loss on this position calculated based on Mark Price, and return on equity percentage.

**Modes:**&#x20;

* Single Asset Mode: Supports USDⓈ-M Futures trading by only using the single margin asset of the symbol. PNL of the same margin asset positions can be offset. Supports Cross Margin Mode and Isolated Margin Mode.
* Multi-Assets Mode: USDⓈ-M Futures trading across multiple margin assets. PNL can be offset among the different margin asset positions. Only supports Cross Margin Mode.

{% hint style="info" %}
Note: If there are open positions or open orders in USDⓈ-M Futures, Multi-Assets Mode cannot be activated. Multi-Assets Mode only applies to USDⓈ-M Futures. Before activating Multi-Assets Mode, please read the guide in detail to better manage USDⓈ-M Futures account risk accordingly when using Multi-Assets Mode.\

{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa\_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-\_3KzjAl3f8VSGyoLrtudoUqBr)

### Orders

**Buy/Long:** Open a Long order. In this order you purchase an asset and wait to sell when the price goes up. "Buy" and "long" are used interchangeably.

**Sell/Short:** Open a Short order. In this order, you borrow an asset, sell it, and hope to buy it back when the price goes down. "Sell" and "short" are used interchangeably.

**Limit Order:** A limit order is an order to buy or sell at a specific price or better. Limit orders are not guaranteed to execute.

**Market Order:** A market order is an order to buy or sell at the best available current price. It is executed against the limit orders that were previously placed on the order book. When placing a market order, you will pay fees as a market taker.

**Stop Limit Order:** The easiest way to understand a stop-limit order is to break it down into stop price, and limit price. The stop price is simply the price that triggers the limit order, and the limit price is the price of the limit order that is triggered. This means that once your stop price has been reached, your limit order will be immediately placed on the order book.

**Stop Market Order:** Similar to a stop-limit order, a stop market order uses a stop price as a trigger. However, when the stop price is reached, it triggers a market order instead.

**Trailing Stop:** A trailing stop is an order type designed to lock in profits or limit losses as a trade moves favorably. Trailing stops only move if the price moves favorably. Once it moves to lock in a profit or reduce a loss, it does not move back in the other direction.

**Post Only:** Post-only Mode means that Traders can only place an Order if it would be posted to the Order Book as a Maker Order. An Order which would be posted as a Taker Order will be rejected. No Market Orders may be placed and no Orders will be filled. Resting orders may be canceled in post-only mode.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf\_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym\_aSz\_)

**Reduce Only:** Reduce-Only order will only reduce your position, not increase it.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME\_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF instructions** allow you to specify the amount of time that your orders will remain active before they are executed or expired. You can select one of these options for TIF instructions:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7\_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93\_7bq7gDmyg1-jyblSQ8eANv\_fH9bvJ-)

* **GTC** (Good Till Cancel): The order will remain active until it is either filled or canceled.&#x20;
* **IOC** (Immediate Or Cancel): The order will execute immediately (either fully or partially). If it is only partially executed, the unfilled portion of the order will be canceled.&#x20;
* **FOK** (Fill Or Kill): The order must be fully filled immediately. If not, it won’t be executed at all.

