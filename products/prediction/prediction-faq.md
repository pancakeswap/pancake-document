# Prediction FAQ & Troubleshooting

{% hint style="info" %}
Use the sidebar to quickly find the answers to your questions!
{% endhint %}

## Troubleshooting <a id="docs-internal-guid-361a9c15-7fff-0185-2f69-1125f1a3fe13"></a>

### Why can’t I see my winnings in my wallet?

When you collect winnings, they might not appear in your wallet’s transaction logs as usual.  
This is because they use a different type of transaction: Internal transactions.  
Enter your wallet address on BscScan, then check the “Internal Txns” tab to confirm that they’ve arrived.  
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### Why aren't the results of my round showing?

There’s a 15 block buffer on each round, which can cause delays of up to 45 seconds after the end of a round.  
This buffer is to accommodate for the fact that we may not be able to reliably fetch a price and end a round immediately: various blockchain factors affect the speed in which transactions get confirmed on the network.

### I can’t collect my winnings!

Make sure you have enough BNB in your wallet to pay for gas fees. You’ll need a little BNB to trigger the smart contract.

## Market Pauses

### What does it mean when markets are paused?

Markets are paused when there are conditions which affect the reliability of the contract. Markets being paused means that no bets will be taking place for any rounds.

### What causes PancakeSwap Prediction market to pause?

The prediction market will pause under the following conditions:

1. The prediction contract has been unable to obtain the price from the ChainLink oracle due to the oracle not having posted the price at the time the round has ended.
2. The prediction contract has been unable to execute an action \(ending a round or getting a price from the oracle\) due to the tx being stuck in the mempool for longer than 15 blocks.

### When will the markets resume after being paused?

The markets will resume when an admin \(one of the chefs\) manually resumes the market.

### What happens to my position if the market pauses?

If the markets pause while you have a live position, your funds will be available to reclaim, the same way as you would normally claim your winnings.

To reclaim funds, you’ll need to pay some gas fees. We can’t compensate you for the gas fees, so please bear this small risk in mind before participating.

## About Positions

### **What happens if no one enters an opposing position?**

If only one side of a round has positions entered into it, then that side loses, the losing funds will be sent to the treasury. 

For example: User A enters an UP position, no one else enters a DOWN position. User A loses, and there are no opposing positions for the winnings to be paid out to. Funds are sent to treasury.

### **What happens if the Locked Price and Closed Price are the exact same?**

In the very rare occurrence that the Locked Price is exactly the same as the Closed Price, no one wins, and all funds entered into positions will be sent to the treasury to be used for CAKE buybacks to burn.

### **Can I change or remove my position?**

No. Once you enter a position, you can NOT change the directtion, add to, or remove your position. It's locked in, so make sure you're 100% happy with your position direction before confirming. 

## General Questions

### What’s the PancakeSwap Prediction contract address?

Verified contract address: [https://bscscan.com/address/0x516ffd7D1e0Ca40b1879935B2De87cb20Fc1124b](https://bscscan.com/address/0x516ffd7D1e0Ca40b1879935B2De87cb20Fc1124b)

### Is there a time limit before I can collect my winnings?

No, you’ll be able to collect your winnings at any time in the future.

### How is the payout calculated?

* Payout Ratio for UP Pool = Total Value of Both Pools ÷ Value of UP Pool
* Payout Ratio for DOWN Pool = Total Value of Both Pools ÷ Value of DOWN Pool

For example, if there’s 15 BNB in the DOWN side of a round, and the overall prize pool is 150BNB, the DOWN payout ratio will be \(150/15\)=10x.

* Payout Amount = Payout Ratio × Position × \(1 - Treasury Fee\)

In the above case, if the round ends on a DOWN result, if you committed 2 BNB to a DOWN position, you’d get a payout of \(2\*10\) × \(1-0.03\) = 19.4 BNB. Your profit would be 17.4 BNB \(19.4 - 2\).

The treasury fee is currently set at 3%: this may be subject to changes, which would be announced on PancakeSwap’s official communication channels. Treasury fees are used to buy back and burn CAKE tokens.

### **What are the fees?**

3% of each round's total pot will go to the treasury, which will be used to buyback and burn CAKE every Monday.

### What are you using for your price feed?

PancakeSwap uses two sources for our price feeds. They each have their own purpose within the prediction market:

#### ChainLink Oracle

* Used for the Lock price and End price of each prediction market round. This updates in intervals of 5 minutes.
* Our prediction contract uses the ChainLink Oracle price feed to set the prices used to dictate whether a user has won or not.

#### Binance BNB/USDT

* Used for real-time price updates on the PancakeSwap prediction market interface.

Since we’re using two different price feeds, the real-time price updates from Binance and the ChainLink Oracle price may differ by a small amount. However, they shouldn’t vary significantly.

### The round's result changed after the round ended! Why?

Sometimes, after a round closes, the final result may be different from the last result shown while the round was live. If you watch a round end on "DOWN", it may appear to flip to "UP" a few seconds later.

This is because we use the ChainLink Oracle price feed to determine the final outcome of a round. The period between the end of one round and the start of the next is 30 seconds, but the Oracle refreshes every 20 seconds. It's possible that during this short period, the Oracle might send an update while the transaction to trigger the next round is being minted. This can appear to "flip" the outcome of the previous round.

