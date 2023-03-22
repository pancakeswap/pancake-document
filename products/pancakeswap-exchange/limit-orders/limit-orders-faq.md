# Limit Orders FAQ

{% hint style="info" %}
Use the sidebar to quickly find the answers to your questions!
{% endhint %}

## General Questions

### Why was my order not executed?

Limit orders are executed when they reach their desired price, however, due to gas fluctuations, the actual execution price might vary from the price you specified on the interface. Usually, the execution price and the desired price should be almost identical, however, if you submitted a particularly small order (\~<1000$) the execution price might be slightly higher to account for fees.&#x20;

Therefore your order may not be executed because:

* It wasn’t possible to fill the whole order at the desired price and amount due to price impact.
* One of the tokens in the limit order has fee on transfer (see below).

**Before submitting an order, please consult the UI denoting the real execution price.**

{% hint style="info" %}
Please note: the order history table gets the data from Subgraph and can show slightly delayed information.
{% endhint %}

### Can I submit a limit order for tokens with fee on transfer?

**No.** The tokens with a fee on transfer should not be used with limit orders. Proceed at your own risk.

### How do I set slippage while using limit orders?

Slippage is not relevant in limit orders. You specify input amount (e.g. 1000 CAKE) and output amount (e.g. 20 BNB), Limit orders guarantee that you will receive no less than the specified output amount (20 BNB) for your input amount (1000 CAKE) if the price for the pair reaches the desired price. **Note that tokens with fee on transfer should not be used with limit orders** (read above)

### The real execution price shows "never executes". What's this?

It basically means that you're trying to swap a very small amount of tokens therefore there are not enough tokens to be accounted for the gas fee. In general, you need to increase the amount of the "input" field to get rid of this error.&#x20;

### Is there an expiration date for my limit orders?

Open orders have an expiration date of 90 days. After your order is expired it might never be executed. Please cancel your order once expired.&#x20;

A customizable expiration date feature is planned for the near future.

### Why can’t I create limit orders below the market price?

To sell below market price, you need **Stop Limit Orders**, not limit orders. Stop Limit Orders feature is coming soon.

### I made an order and it is not shown in the order table or stuck at “pending” status.

The order history comes from the subgraph and therefore might show slightly delayed information. Usually, delays are no longer than a couple of minutes at worst. Please refer to the subgraph indicator at the bottom right corner of the order history table.

