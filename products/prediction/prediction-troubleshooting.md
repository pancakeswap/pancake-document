# Prediction Troubleshooting

{% hint style="info" %}
Use the sidebar to quickly find the answers to your questions!
{% endhint %}

### Why can’t I see my winnings in my wallet?

When you collect winnings, they might not appear in your wallet’s transaction logs as usual.\
This is because they use a different type of transaction: Internal transactions.\
Enter your wallet address on BscScan, then check the “Internal Txns” tab to confirm that they’ve arrived.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP\_uWeFDYsa0\_nxN3sKUiIwFdACy\_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### Why aren't the results of my round showing?

There’s a 15 block buffer on each round, which can cause delays of up to 45 seconds after the end of a round.\
This buffer is to accommodate for the fact that we may not be able to reliably fetch a price and end a round immediately: various blockchain factors affect the speed in which transactions get confirmed on the network.

### I can’t collect my winnings!

Make sure you have enough BNB in your wallet to pay for gas fees. You’ll need a little BNB to trigger the smart contract.

### **I can't claim winnings from a prediction round on site.**

You might be able to claim your winnings directly from the contract. Follow the steps in the 3 tabs below.

{% tabs %}
{% tab title="Check rounds you played" %}
How to check the history of rounds you played

1. Go to BscScan page of [BNB](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda#readContract) or [CAKE Prediction contract](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract).
2. Scroll down to “8. getUserRounds”.
3. Type in your wallet address under “user(address)”.
4. Set “cursor(uint256)" to 0 and “size(uint256)" to 1000.
5. Tap “Query”
6. Rounds you entered will show below in the first row. (after “uint256\[]:”)
{% endtab %}

{% tab title="Check if you can claim" %}
First, check whether you should actually be able to claim from the round you played.

1. Go to the BscScan page of [BNB](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda#readContract) or [CAKE Prediction contract](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract), and go to the Read tab
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

1. Go to the BscScan page of [BNB](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda#writeContract) or [CAKE Prediction contract](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract), and go to the Write tab
2. Tap “🔴 Connect to Web3”
3. Use MetaMask or WalletConnect to connect.
4. Scroll down to “3. claim”
5.  Type in the round number you want to claim in this format, including the \[] brackets: `[12345]`&#x20;

    If you want to claim from multiple rounds together, separate the rounds with a comma like this: `[12345,12346,12347]`
6. Tap “Write”
7. Confirm on wallet&#x20;
{% endtab %}
{% endtabs %}

