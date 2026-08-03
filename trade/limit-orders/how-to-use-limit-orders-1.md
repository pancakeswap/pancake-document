# How to use Limit Orders

Fee-earning limit orders on PancakeSwap work differently from traditional limit orders. When a user places a limit order, they are effectively providing **one-sided liquidity** to a PancakeSwap Infinity pool.

As the market price moves, swaps in the pool can use the user’s liquidity. When this happens, the deposited tokens are fully converted into the output tokens, and the user receives:

* The output tokens, and
* The trading fees earned from swaps executed against their liquidity.

***

**Example: Selling BNB for USDT**

* **Current price in BNB/USDT pool:** 600 USDT per BNB
* **User’s target / limit price:** 700 USDT per BNB

Process:

1. The user sets a limit order to sell BNB at 700 USDT.
2. Their BNB is deposited into the tick closest to price 700 USDT per BNB in the pool.
3. When the external market price reaches 700 USDT, the pool price adjusts to match (due to arbitrage opportunities / better pricing).
4. At that point, the user’s BNB is swapped into USDT.
5. During this process, the user earns fees from each swap that consumes their liquidity.
6. Once the liquidity is fully consumed, the converted USDT (plus fees) is automatically withdrawn and sent to the user’s wallet.

***

### Step-by-step guide

Choose a token pair (e.g., BNB/CAKE) and amount you would like to sell / buy

<figure><img src="../../.gitbook/assets/Screenshot 2025-09-28 at 11.07.07 AM.png" alt="" width="375"><figcaption></figcaption></figure>

Set your target / limit price

<figure><img src="../../.gitbook/assets/Screenshot 2025-09-28 at 11.07.35 AM.png" alt="" width="375"><figcaption></figcaption></figure>

Place the limit order and “Confirm”. Liquidity is placed on your behalf at the tick closest to limit price

<figure><img src="../../.gitbook/assets/Screenshot 2025-09-28 at 11.08.49 AM.png" alt="" width="375"><figcaption></figcaption></figure>

Once the pool price hits your target, your order executes. Desired output tokens + fees are automatically withdrawn and sent to your wallet.

<figure><img src="../../.gitbook/assets/Screenshot 2025-09-28 at 1.01.47 PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Order Status

You can view your order status by clicking here

<figure><img src="../../.gitbook/assets/Screenshot 2025-09-28 at 2.12.50 PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Your order can be in one of the following states:**

| Status           | Description                                                                              |
| ---------------- | ---------------------------------------------------------------------------------------- |
| Pending          | Waiting for price to reach your target                                                   |
| Filled           | Order executed and funds sent to your wallet                                             |
| Partially Filled | Only part of your order is executed. You’ll hold both tokens (e.g., part BNB, part USDT) |
| Cancelled        | You cancelled the order. All your funds are returned to you                              |

### FAQs

**Q: Do I need to pay fees to place a limit order?**

A: No. Instead, you earn trading fees when your order executes — choose a 0.01% (faster execution) or 0.1% (best returns) fee tier.

**Q: Can I place orders for any pair?**

A: At launch, only selected pairs are supported. More pairs will be added later.

**Q: What’s the minimum order size?**

A: $50. This prevents tiny orders that could result in excess gas.&#x20;

**Q: What happens if only part of my order is filled?**

A: You’ll hold both tokens. You can cancel anytime and withdraw both tokens plus earned fees.

**Q: My order is filled but I haven't received funds yet in my wallet?**

A: In very rare scenarios this could happen but your funds are always safe. Just use the "Withdraw" button in the order details UI to claim the funds manually.
