# Prediction FAQ

{% hint style="info" %}
Use the sidebar to quickly find the answers to your questions!
{% endhint %}

## A) General Questions

### **1. What are the fees?**

3% of each round's total pot will go to the treasury, of which 100% will be used to buyback and burn CAKE.

### 2. How is the payout calculated?

* Payout Ratio for UP Pool = Total Value of Both Pools ÷ Value of UP Pool
* Payout Ratio for DOWN Pool = Total Value of Both Pools ÷ Value of DOWN Pool

**Example - Bet 2 BNB "DOWN", outcome = "DOWN":**

* DOWN side = 15 BNB, total prize pool = 150 BNB&#x20;
* DOWN payout ratio = 150 BNB / 15 BNB = 10x
* Payout Amount = Payout Ratio × Position × (1 - Treasury Fee)
  * If you bet 2 BNB on DOWN, payout = (2 × 10) × (1 − 0.03) = 19.4 BNB
* Profit = 19.4 − 2 = 17.4 BNB

### 3. Is there a time limit before I can collect my winnings?

No, you’ll be able to collect your winnings at any time in the future.

### 4. What’s the PancakeSwap Prediction contract address?

**BNB Chain**

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Positions & Results

### 1. **Can I change or remove my position?**

No. Once you enter a position, you can NOT change the direction, add to, or remove your position. It's locked in, so make sure you're 100% happy with your position direction before confirming. &#x20;

### 2. When will markets be cancelled? What happens then?

* **When:** Oracle or backend service failure, or other extraneous circumstances.
* **Outcome:** Users can claim 100% of their original bet amount (no fee).

### 3. The round's result changed after the round ended! Why?

Sometimes, after a round closes, the final result may be different from the last result shown while the round was live. If you watch a round end on "DOWN", it may appear to flip to "UP" a few seconds later.

This is because we use the Oracle price feed to determine the final outcome of a round. The period between the end of one round and the start of the next is 30 seconds, but the Oracle refreshes every 20 seconds. It's possible that during this short period, the Oracle might send an update while the transaction to trigger the next round is being minted. This can appear to "flip" the outcome of the previous round.

### 4. What is Locked Price & Closed Price?

* **Locked Price:** Price at the start of the LIVE phase.
* **Closed Price:** Price at the end of the round, used to determine winners.

**Example – Round 400 (BNB Prediction):**

1. **12:00–12:05:** Place Bet → User bets 0.1 BNB on "UP"
2. **12:05–12:10:** Lock Phase → Locked Price = $850
3. **12:10:** Close Phase → Closed Price = $860
4. **Result: "UP"** bet wins

**Notes:**

* Oracle price may take up to 20 seconds to update.
* House win: All bets goes to the House

### 5. What situations are considered a HOUSE WIN?

**Scenarios:**

1. No opposing bets exist and the user loses (e.g., only one user bets UP and outcome = DOWN)
2. Locked Price = Closed Price

**What happens:**

* PancakeSwap takes 100% of the pool; all funds go to CAKE burn.
* Users on either side lose their intial bet amount.

**Example - No opposing bets:**

* User A bets UP, no DOWN bets exist, outcome = DOWN → User A loses; 100% of funds go to treasury.
* User B bets UP, no DOWN bets exist, outcome = UP → User B reclaims 97% of deposit.



## C) Market Pauses

### 1. What does it mean when markets are paused?

Markets are paused when there are conditions which affect the reliability of the contract. Markets being paused means that no bets will be taking place for any rounds.

### 2. What causes PancakeSwap Prediction market to pause?

The prediction market will pause under the following conditions:

1. The prediction contract has been unable to obtain the price from the ChainLink oracle due to the oracle not having posted the price at the time the round has ended.
2. The prediction contract has been unable to execute an action (ending a round or getting a price from the oracle) due to the tx being stuck in the mempool for longer than 15 blocks.
3. PancakeSwap has decided to discontinue prediction for that market / asset.

### 3. What happens to my position if the market pauses?

If the markets pause while you have a live position, your funds will be available to reclaim, the same way as you would normally claim your winnings.

To reclaim funds, you’ll need to pay some gas fees. We can’t compensate you for the gas fees, so please bear this small risk in mind before participating.

### 4. When will the markets resume after being paused?

The markets will resume when an admin (one of the chefs) manually resumes the market.



## D) Troubleshooting & Claims

### 1. How do I claim past winnings from the CAKEUSD market on BNB Chain?&#x20;

* Go to [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc)
* Check the history tab for historical round winnings

### 2. Why can’t I see my winnings in my wallet?

When you collect winnings, they might not appear in your wallet’s transaction logs as usual.\
This is because they use a different type of transaction: Internal transactions.\
Enter your wallet address on BscScan, then check the “Internal Txns” tab to confirm that they’ve arrived.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. Why aren't the results of my round showing?

There’s a 15 block buffer on each round, which can cause delays of up to 45 seconds after the end of a round.\
This buffer is to accommodate for the fact that we may not be able to reliably fetch a price and end a round immediately: various blockchain factors affect the speed in which transactions get confirmed on the network.

### 4. I can’t collect my winnings, what should I do?

Make sure you have enough BNB in your wallet to pay for gas fees. You’ll need a little BNB to trigger the smart contract.

### **5. What if I can't claim winnings from the website?**

You might be able to claim your winnings directly from the contract. Follow the steps in the 3 tabs below.

{% tabs %}
{% tab title="Check rounds you played" %}
How to check the history of rounds you played

1. Go to BscScan page of the [Prediction contract](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (e.g. BNBUSD).
2. Scroll down to “8. getUserRounds”.
3. Type in your wallet address under “user(address)”.
4. Set “cursor(uint256)" to 0 and “size(uint256)" to 1000.
5. Tap “Query”
6. Rounds you entered will show below in the first row. (after “uint256\[]:”)
{% endtab %}

{% tab title="Check if you can claim" %}
First, check whether you should actually be able to claim from the round you played.

1. Go to BscScan page of the [Prediction contract](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (e.g. BNBUSD), and go to the Read tab
2. Scroll down to “4. claimable”.
3. Type in the round id you want to check under "epoch(uint256)”.
4. Type in your wallet address under “user(address)”.
5. Tap “Query”
6. If a round is claimable, it will show “true”.
7. If the result is "false". Please repeat the above steps and try with "19. refundable".&#x20;
8. Note: ⬆️ If you see a round returns "false" on both "4. claimable" and "19. refundable", but it shows on the website, it's probably been claimed already and the website is lagging.
{% endtab %}

{% tab title="Claim from a round" %}
How to claim

1. Go to BscScan page of the [Prediction contract](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (e.g. BNBUSD), and go to the Write tab
2. Tap “🔴 Connect to Web3”
3. Use MetaMask or WalletConnect to connect.
4. Scroll down to “3. claim”
5.  Type in the round number you want to claim in this format, including the \[] brackets: `[12345]`&#x20;

    If you want to claim from multiple rounds together, separate the rounds with a comma like this: `[12345,12346,12347]`
6. Tap “Write”
7. Confirm on wallet&#x20;
{% endtab %}
{% endtabs %}

