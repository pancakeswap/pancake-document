# FAQ

<figure><img src="../../../.gitbook/assets/image (4) (1) (3).png" alt=""><figcaption><p>\</p></figcaption></figure>

### What should I do on PancakeSwap on other blockchains?

Provide liquidity, trade and farm as you always have been. If you are a multichain user already, remember to provide liquidity on PancakeSwap on other blockchains that we've deployed on (like Ethereum), as we have CAKE rewards on BNB Smart Chain for you, allowing you to earn even more CAKE without bridging those assets over!

### **Will there be more pairs?**

Yes, but we will be deploying in steps to ensure we prioritize the safety of user funds and CAKE inflation. Do let us know in the community chats what you think should be added to PancakeSwap on other blockchains, as well as what other blockchains we should deploy PancakeSwap on.

### **Why the gas cost for staking LP tokens is high?**

A small amount of native token (for example, ETH on Ethereum) is required for the first-time setup. So the first transaction will be slightly costly.

Plus, there are other fees (mostly gas costs) involved in cross-chain farming. Check out [this](faq.md#are-there-any-fees-when-i-do-crosschain-farming) dedicated section to learn more.

### **Why do staking and unstaking take 30 minutes to complete?**

All cross-chain transactions will take around 30 minutes to complete. It is because:

* Transactions have to be executed on both the farming blockchain (like Ethereum) and the BNB Chain.
* Delivering cross-chain messages takes time.
* To ensure safety and all the data are synced and consistent between different blockchains.

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

```
messagingFee = feeBase + message.length * feePerByte;
```

You may find the variables in the formula with in the message bus contract:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - The starter fund**

This is not strictly a "fee".&#x20;

For every new user who started doing PancakeSwap cross-chain farming. In the first “stake” transaction, we will deposit 0.005 BNB into their BNB Chain wallet. The corresponding amount of native tokens on the farming chain (like ETH on Ethereum) will be charged from the deposit transaction, using the market rate provided by the price oracle.

This is to help users start their BNB Chain journey with ease. We understand the painfulness of having all the harvested CAKE but not being able to explore the vivid PancakeSwap ecosystem without finding another way to acquire BNB for gas.

This fee only charges once upon the first "stake" transaction.

### Where are the emissions coming from?&#x20;

_updated on Oct 10 2022_

For now, Chefs have diverted 0.0189 CAKE per block from the CAKE pool to all crosschain farms.&#x20;

Here is the emissions breakdown:

<table><thead><tr><th width="249"></th><th>Multiplier</th><th>CAKE per block</th></tr></thead><tbody><tr><td><strong>CAKE Pool</strong></td><td>-</td><td><strong>8.9811</strong></td></tr><tr><td><strong>All Crosschain Farms</strong></td><td>-</td><td><strong>0.0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0.5x</td><td>0.0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0.2x</td><td>0.0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0.2x</td><td>0.0042</td></tr></tbody></table>

### What happened during the deposit, harvest and withdrawal?

PancakeSwap crosschain farming is like using a "stand-in" LP token to farm on the BNB Chain, with the same PancakeSwap MasterChef. The CAKE rewards are calculated and distributed on BNB Chain, controlled and guarded by the same MasterChef contract.

#### Upon Deposit:

1. Users request depositing LP tokens on farming blockchains (like Ethereum).
2. LP tokens are being transferred to farming vault contracts.
3. Celer message bus is utilised to deliver the "deposit" message to BNB Chain.
4. An executor on BNB Chain mints the same amount of farming tokens as "stand-ins", and then deposits them into the farms.

#### Upon Harvesting:

Since CAKE rewards are calculated and distributed on BNB Chain. Users can claim their CAKE rewards with a single BNB Chain transaction without the need for cross-chain operations.

#### Upon Withdrawal:

1. Users request withdrawing LP tokens on farming blockchains (like Ethereum).
2. Celer message bus is utilised to deliver the "withdraw" message to BNB Chain.
3. An executor on BNB Chain withdraws the farming tokens from the farms, burns those tokens, transfers the earned CAKE to users, and utilises the Celer message bus to deliver the confirmation message back to the original farming blockchain.
4. An executor on the farming blockchain confirms everything and then releases the LP tokens from the vault contracts.
