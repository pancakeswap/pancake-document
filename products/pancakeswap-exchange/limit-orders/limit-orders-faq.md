# Limit Orders FAQ

{% hint style="info" %}
Use the sidebar to quickly find the answers to your questions!
{% endhint %}

## General Questions

### Why was my order not executed?

Limit orders are executed when it reaches the desired price, however due to gas fluctuations the actual execution price might be a bit higher than the price you specified in the UI. Usually execution price and desired price are almost identical, however if you submitted a particularly small order (\~<1000$) the execution price might be slightly bigger to account for fees.&#x20;

Therefore your order may not be executed because

* It wasn’t possible to fill the whole order at the desired price and amount due to price impact.
* One of the tokens in the limit order has fee on transfer (see below).

**Please consult the UI denoting real execution price when submitting an order.**

{% hint style="info" %}
Also note that the order history table gets the data from subgraph and can show slightly delayed information.
{% endhint %}

****

### Can I submit a limit order for tokens with fee on transfer?

**No.** The tokens with fee on transfer should not be used with limit orders.\
If you really want to use limit orders for them, use at your own risk.



### How do I set slippage while using limit orders?

Slippage is not relevant in limit orders. You specify input amount (e.g. 1000 CAKE) and output amount (e.g. 20 BNB), Limit orders guarantee that you will receive no less than the specified output amount (20 BNB) for your input amount (1000 CAKE) if the price for the pair reaches the desired price. **Note that tokens with fee on transfer should not be used with limit orders** (read above)

### Real execution price shows "never executes". What's this?

It basically means that you're trying to swap very small amount of token. In general you just need to increase your input to get rid of this error.&#x20;

### Is there expiration date for my limit order?

Open orders will remain open indefinitely until your order gets executed or you cancel it. Optional expiration date customization is planned for the near future.



### Why can’t I sell below market price?

To sell below market price, you need to use **Stop Limit Orders**, not limit orders. Stop Limit Orders feature is coming soon.



### I made an order and it is not shown in the order table or stuck at “pending” status.

The order history comes from the subgraph and therefore might show slightly delayed information. Usually delays are no longer than couple of minutes at worst. Please refer to the subgraph indicator at the bottom of the order history table.

