# How to Trade

![](../../.gitbook/assets/how-to-trade-on-pancakeswap-header.png)

Trading on PancakeSwap is very easy compared to most exchanges. You aren't going to be overwhelmed by charts or jargon, and trading routes and calculations are all handled for you by the PancakeSwap Smart Router.

**Getting set up to trade**

Before you can trade, you will need a wallet that is compatible with BNB Chain or Ethereum. You can learn how to get one [here](https://docs.pancakeswap.finance/get-started/wallet-guide). You will also need to have some BEP-20 or ERC-20 tokens to trade with. You can learn how to get some [here](https://docs.pancakeswap.finance/get-started/bep20-guide).

Alternatively, you can learn how to get an Aptos-compatible wallet [here](https://docs.pancakeswap.finance/get-started-aptos/wallet-guide), and how to get some Aptos coins to swap within [here](https://docs.pancakeswap.finance/get-started-aptos/aptos-coin-guide).

### Trading on the PancakeSwap exchange

1 - Go to the exchange page [here](https://pancakeswap.finance/swap).



2 - Unlock your wallet by clicking Connect **Wallet** (you can also **Connect** in the top right-hand corner). If you haven't yet connected your wallet to PancakeSwap, you can view the guide [here](https://docs.pancakeswap.finance/get-started/connection-guide).

![](<../../.gitbook/assets/image (15) (1).png>)



3 - Choose the token you want to trade from the dropdown menu in the upper section. Whichever token you choose, you will need to make sure you have a sufficient amount of them in your wallet to trade with. Your balance is shown above the token dropdown menu.

![](<../../.gitbook/assets/image (18) (1).png>)



4 - Choose the token you want to trade to in the lower section as above.



5 - Next, either type an amount in the upper section to input the number of tokens you want to swap (spending amount). Or, type an amount in the lower section to input the number of tokens you want to swap to (receiving amount).&#x20;

Whichever section you input your amount, the amount in the other section will be estimated automatically.



6 - Check all the details, and click the **Swap** button.

If you are trading a token for the first time, you may need first to click "Enable XXX (your token)" to approve.

![](<../../.gitbook/assets/image (12) (1).png>)



7 - A window with more details will appear. Check the details are correct. When you are ready, click the **Confirm Swap** button. Your wallet will ask you to confirm the action.

![](<../../.gitbook/assets/image (28) (1).png>)



8 - Done! You can check your transaction on blockchain explorer by clicking the link shown above.

![](<../../.gitbook/assets/image (1) (2).png>)

## **What is Smart Router, and how to use it?**

PancakeSwap Smart Router is a routing algorithm that links V3, V2, StableSwap (BNB Chain), and the AMM and market makers (BNB Chain & Ethereum), to always provide liquidity and pricing. On default, it executes trades across multiple pools to find the best price for traders.

Smart Router is now the default route for PancakeSwap Exchange V3. However, users are free to customize it for their needs.

To learn more about how to customize your trade routes, [click here](fees-and-routes.md).&#x20;

For more information on StableSwap, [click here](../stableswap/), and for the Market Maker integration, [click here](market-maker-integration.md).

## FAQ

### How come my transaction won't go through?

PancakeSwap is a DeFi application such that it interacts with the wallet to complete on-chain transactions for swapping, creating LPs, staking in farms and pools, etc. &#x20;

### Gas Fees

As such, the first thing is to **make sure you have enough BNB to pay for the gas fee** of the on-chain transactions. Typically, gas fee fluctuates depending on the number of transactions in the queue, if there are more transactions, a higher gas fee may be required to push through the transaction. On BNB Smart Chain, the gas fee typically ranges from cents to a dollar USD in BNB. Learn more about [gas fee here](https://academy.binance.com/en/glossary/gas).&#x20;

### Transaction Fees

If your swapping action still doesn't go through and it is displaying an error for you to revise the slippage -- you may want to check if the tokens you are trying to swap has **any fees and restrictions on transactions**.

It is not uncommon for tokens on BNB Smart Chain to include a **transaction fee** in their contracts, usually these fees could be used for burning, funding a treasury of a fair launch project -- for example, this [APX token has an 1% tax on every transaction](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) for sending to a burn address, such that more transactions would mean more burning, accruing value to APX token holders.&#x20;

With the transaction fee, whether it is inclusive (a portion of the swap amount is sent elsewhere than your address so the output is less than expected for the estimated input) or exclusive (requiring an additional transfer from your address to send extra tokens so the input is more than expected for the estimated output), it affects the input and output amount that you agree for signing the transaction. In many cases, the transaction cannot meet the input and output requirements because of the tax.

### Swapping with Transaction Fees

Before you swap any tokens, make sure you have visited their website to understand if they have a transaction fee mechanism (or _tax_ as many projects put it). If there is, make sure you set a slippage that is sufficient to accommodate the transaction fee -- e.g. if there is a transaction fee of 5%, your slippage will have to be set at at least 5% plus the normal trading slippage depending on your trading amount and the token's liquidity, say 5.5%-6%.&#x20;

In some extreme cases including some scams, some tokens even have a block on most or all transfers on chain, or only allowing certain addresses to sell, in such case it is impossible to swap the token successfully. Do learn about the token you are trying to swap and be aware of any fees and restrictions!
