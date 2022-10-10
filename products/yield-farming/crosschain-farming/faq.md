# FAQ

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>\</p></figcaption></figure>

### What should I do on PancakeSwap on Ethereum?

Provide liquidity, trade and farm as you always have been. If you are a multichain user already, remember to provide liquidity on PancakeSwap on Ethereum as we have CAKE rewards on BNB Smart Chain for you, allowing you to earn even more CAKE without bridging those assets over!

### **Will there be more pairs?**

Yes, but we will be deploying in steps to ensure we prioritize the safety of user funds and CAKE inflation. Do let us know in the community chats what you think should be added to PancakeSwap on Ethereum.

### **Why the gas cost for staking LP tokens is high?**

A small amount of native token (for example, ETH for Ethereum) is required for the first-time setup. So the first transaction will be slightly costly.

### **Why do staking and unstaking take 30 minutes to complete?**

To ensure safety. All cross-chain transactions will take around 30 minutes to complete.&#x20;

### **Where are my harvested CAKE rewards?**

Your harvested CAKE will be distributed on BNB Smart Chain. Please switch the blockchain network in your wallet to check the balance of CAKE.

### **I can't harvest because my wallet doesn't support switching between different blockchains!**

Please try using a different wallet app that supports multichain and chain switching.

Please note that staking and unstaking LP tokens will also harvest all the earned CAKE to your wallet on BNB Smart Chain. Therefore if you don't want to use a different wallet app, simply stake more, or unstake a tiny amount of LP tokens to harvest your earned CAKE.

### Are there any fees when I do crosschain farming?

Unlike farming natively on BNB Chain, farming on other blockchains requires cross-chain activities. Here are the fees involved:

**1 - Gas fee to create a proxy contract**

A proxy contract has to be created on the BNB Chain for cross-chain farming. The gas cost for proxy contract creation is included in the transaction.

This fee only charges once upon the first "stake" transaction.

**2 - Gas fee for calls on BNB Chain**

When users deposit or withdraw LP tokens. An executor will perform transactions calling on behave of the users on the BNB Chain. The gas cost for these calls is included in the transaction.

This fee is charged in every deposit or withdrawal transaction.

**3 - Gas fee for calls on other blockchains**

When users withdraw LP tokens. An executor will perform the final transactions calling to release the LP tokens on other blockchains (like Ethereum). The gas cost for these calls is included in the transaction.

This fee is only charged in withdrawal transactions.

**4 - Cross-chain messaging fee**

We utilise a message bus powered by Celer to route our cross-chain messages. Therefore a messages fee is included based on the byte length of the message.

This fee is charged in every stake transaction. In unstake transactions, this fee is charged twice since a two-way communication between BNB Chain and other blockchains is required for safety.

