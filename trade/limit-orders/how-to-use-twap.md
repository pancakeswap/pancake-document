# How to use TWAP

## What is TWAP?

TWAP (Time-weighted Average Price) is a common order type used in CeFi that breaks an order into smaller trade sizes and executes them at regular intervals. The main goal of a TWAP order is to reduce the order’s price impact. It can also be useful if a user wants to implement a dollar-cost averaging strategy (DCA) and buy a certain token on a consistent schedule (i.e. once a month).

Therefore, TWAP is best used when the order size is large compared to the available liquidity, or when a user anticipates a high price volatility period with no clear up or downward trend.

## How to set up a TWAP order?

1. Go to the Swap page and select the TWAP order option by clicking TWAP
2. Select the “From” and “To” tokens and enter the amount you wish to trade.
3. The UI enables both dTWAP-market orders, which execute all trades at the available market price, and dTWAP-limit orders, which only execute individual trades if they are within the price limit set by the user. \
   In this example we chose to execute the TWAP orders at market price.
4. Next, we specify the TWAP parameters. There are 3 main parameters that control the effectiveness of the dTWAP order:
   1. Total trades: Allows the user to specify the number of individual trades that their order will be broken into. The UI slider starts with 1 trade and allows the user to increase the amount of individual trades, or allows the user to manually input the total trades in the input field directly.\
      Users should note that there is a certain tradeoff when specifying this parameter: more trades means smaller individual trade size, which means smaller price impact. However, more trades also means more transactions and higher overall gas fees.&#x20;
   2. Trade Interval: Sets the time gap between each individual trade. The UI starts with the minimum allowed (2 mins), which leaves the minimum amount of time for the taker bidding war and block settlement between each chunk. The user can set it to be any duration desired. A trade will never execute before this time elapses after the previous trade.\
      Again users should be mindful when setting this parameter: longer intervals would allow arbitrageurs a longer window to close any price discrepancies on the affected pools and bring the reserves back to equilibrium (on par with spot price). However, it would take longer for the order to be filled would add uncertainty to the final fill price, especially in times of heightened volatility
   3. Max Duration: The maximum time during which the total amount of all individual trades making up the full dTWAP order may be executed. After this deadline the trade expires, regardless of actual amounts swapped.\
      Note that all chunks may not execute in limit orders, depending on whether the price stays within the set parameters. \
      The default recommended duration is calculated by multiplying the number of intervals by the trade interval, and then doubling this amount in order to serve as a buffer to allow sufficient time for on-chain activity. (note that setting a duration that is shorter than the above default may result in a partially filled order).

As can be seen, these parameters provide significant flexibility in customizing each order, taking into account factors like market conditions, current gas fees, etc.

8. Press “Place order”. Double check your order details, accept the disclaimer and press “Confirm order”.
9. Once the transaction is processed, you will be able to see your order’s status in the order history section, under “Open orders”.
10. Open orders can be canceled at any time by expanding the order and clicking the “Cancel Order” button.

Things to take into consideration

* Orders are executed in smaller trades over a specified period of time and are subject to market conditions and other risks.
* Your trade may be executed at a price that is significantly different from the current market price (although not worse than your limit price, if you set one), which could result in significant losses. If the available market price is worse than the limit price you have set, some of the trades of your order may not be executed, resulting in a partially filled order.
* The trades are based on a decentralized protocol that utilizes off-chain takers which compete to fill orders. These takers are entitled to request a fee, which the protocol removes for the winning taker from the output tokens.&#x20;
* Takers may take into account gas fees for your transactions when setting their fees, which may result in fluctuations in the fee amounts.

\
