# FAQ

## Swap

### What’s new in Exchange V3?

* Concentrated liquidity - liquidity will be concentrated on the most actively traded price range, which means:
  * Lower trading slippage for traders
  * Potentially more LP fee rewards for liquidity providers
* A flexible trading fee structure - Liquidity providers can choose between multiple trading fee tiers when creating liquidity pairs or providing liquidity
* Customisable price range - Liquidity providers can also choose what price ranges they want to provide liquidity to
* Non-fungible liquidity positions - Each liquidity position will have its own unique ID corresponding to its configurations (such as price range). Therefore, you will be able to create and maintain multiple positions with the same trading pair but with different configurations and liquidity amount
* Backwards compatible - v3 Exchange will also utilise the legacy v2 and stable swap liquidity pairs to always provide the best trading route
* Built-in limit order - Pro users can utilise the new customisable price range in liquidity provisioning to effectively create a limit order which will convert all the tokens to the desired one when the price hits the target



### Can I add my own tokens to Exchange V3?

Everyone can create liquidity pools by depositing liquidity on V3.

However, the following tokens are currently **NOT** supported:

* Fee-on-transfer tokens
* Rebase tokens

For these token, please do **NOT** add liquidity on Exchange V3. Your assets may stuck in the liquidity position.



### **How come my transaction won't go through?**

PancakeSwap is a DeFi application such that it interacts with the wallet to complete on-chain transactions for swapping, creating LPs, staking in farms and pools, etc.

**Gas Fees**

As such, the first thing is to **make sure you have enough BNB to pay for the gas fee** of the on-chain transactions. Typically, gas fee fluctuates depending on the number of transactions in the queue, if there are more transactions, a higher gas fee may be required to push through the transaction. On BNB Smart Chain, the gas fee typically ranges from cents to a dollar USD in BNB. Learn more about [gas fee here](https://academy.binance.com/en/glossary/gas).

**Transaction Fees**

If your swapping action still doesn't go through and it is displaying an error for you to revise the slippage -- you may want to check if the tokens you are trying to swap has **any fees and restrictions on transactions**.

It is not uncommon for tokens on BNB Smart Chain to include a **transaction fee** in their contracts, usually these fees could be used for burning, funding a treasury of a fair launch project -- for example, this [APX token has an 1% tax on every transaction](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) for sending to a burn address, such that more transactions would mean more burning, accruing value to APX token holders.

With the transaction fee, whether it is inclusive (a portion of the swap amount is sent elsewhere than your address so the output is less than expected for the estimated input) or exclusive (requiring an additional transfer from your address to send extra tokens so the input is more than expected for the estimated output), it affects the input and output amount that you agree for signing the transaction. In many cases, the transaction cannot meet the input and output requirements because of the tax.

**Swapping with Transaction Fees**

Before you swap any tokens, make sure you have visited their website to understand if they have a transaction fee mechanism (or _tax_ as many projects put it). If there is, make sure you set a slippage that is sufficient to accommodate the transaction fee -- e.g. if there is a transaction fee of 5%, your slippage will have to be set at at least 5% plus the normal trading slippage depending on your trading amount and the token's liquidity, say 5.5%-6%.

In some extreme cases including some scams, some tokens even have a block on most or all transfers on chain, or only allowing certain addresses to sell, in such case it is impossible to swap the token successfully. Do learn about the token you are trying to swap and be aware of any fees and restrictions!



### Does the new Swap interface use v2 or stable swap liquidity?

Yes. The new Swap v3 uses liquidity from PancakeSwap v3, v2 and stable swap to get the best trading route.



### What is split routing?

In Swap v3, your trade might be broken into multiple routes to execute your trade with the best rate.

To view more detail of how your trade is routed, tap the “v” button on the “Route” section to expand and view the details.

Learn more in [here](fees-and-routes.md#customize-routing-preferences).



### How to customise or disable certain liquidity sources?

The new Swap v3 uses liquidity from PancakeSwap v3, v2 and stable swap to get the best trading route. However, you can customize or disable certain liquidity sources if you do not want your trade to route through them.

When viewing a trading route, click the “Customize Routing” button. Or click the cog ⚙️ button on the top right hand corner of the Swap interface and choose “Customize Routing”.

Within the “Customize Routing” pop up, you are able to choose which liquidity source you want to utilise. Or disable multihops completely.

Note: disabling multihops could lead to increased slippage or worse trading rate on specific trading pairs. Proceed with caution.

Learn more in [here](fees-and-routes.md#customize-liquidity-sources).



## Liquidity

### What are fee tiers and how to pick the correct one?

In Exchange v3, when you are providing liquidity, you can choose between several different trading fees (0.01%, 0.05%, 0.25%, and 1%) for the same token pair.

For example, for CAKE-BNB, there might be a 0.25% pair, which means a 0.25% trading fee is in place for every trade. However, some liquidity providers might choose to provide liquidity to a CAKE-BNB trading pair with a 0.05% fee rate, offers a better quote and attract more trading volume.

There is no “correct” answer for which trading fee configuration to choose. It depends on the tokens within the trading pair. Usually, volatile tokens should have a higher trading fee to better compensate for the impermanent loss brought by the volatility. On the other hand, tokens like stable coins have smaller price movements and lower impermanent losses, therefore their trading fee should be lower.

When selecting a token pair, the “Add Liquidity” interface will automatically choose the most popular fee tier for you.



### Why two of my deposit tokens are not equal in USD value?

In Exchange V3, underlying assets in a liquidity position will not always have an equal value in USD. It will depend on the price range settings of a position and the current price of the pair.

In fact. If your position goes out of range, all tokens will be converted to one single asset. Plus, you can provide liquidity to a price range that does not cover the current price and deposit one single asset only. Continue reading to learn more ⬇️



### What happens if my liquidity position goes out of range?

You will not earn any trading fee rewards if the current price goes out of the price range defined in your position.

On top of that, all tokens will be converted to one single asset depending on the direction of the price condition.

For example, if a position of CAKE/BUSD is configured with a price range of 3 BUSD per CAKE to 5 BUSD per CAKE. And all assets in the position will be converted to BUSD if the CAKE price is higher or equal to 5 BUSD per CAKE, and vice versa.

Please not that if the price moves back in the range, you will start receiving trading fee rewards again. No additional actions are required.



### Is it better to always provide liquidity with a smaller range?

Providing liquidity to a smaller price range will help concentrate your liquidity to a spesific price range, boosting your relative shares again the total liquidity within the price range, potentially earning more trading fee rewards.

However, please bear in mind that only active liquidity positions will earn trading fee rewards from trades. This means you will only earn rewards when the current trading price is within the price range defined in the liquidity position.



### Are there any ways to automatically adjust my position so it is always in range and earning fee rewards?

Automatic position managing feature is coming soon to PancakeSwap v3 with one-click liquidity depositing (Zap!). Stay tuned for more detail.



### What will be the trading fee breakdown for v3 Exchange?

|                         | 0.01% | 0.05% | 0.25% | 1%  |
| ----------------------- | ----- | ----- | ----- | --- |
| Liquidity Provider      | 67%   | 66%   | 68%   | 68% |
| CAKE Burn               | 10%   | 10%   | 23%   | 23% |
| Treasury                | 18%   | 19%   | 9%    | 9%  |
| Fixed Term CAKE Stakers | 5%    | 5%    | 0%    | 0%  |



### Are LP fee rewards automatically compounded like Exchange v2?

No.

In Exchange v3 you will need to claim trading fee rewards manually. You may do that on the position detail page. You may find all your v3 liquidity positions on the liquidity page.



### What affects LP APR?

In Exchange v3, LP fee reward APR could vary between liquidity positions. It is based on the following factors:

* Trading volume\
  \- more volume generates more fee rewards
* Liquidity pair fee tier\
  \- higher fee tier generates more fee rewards from individual trades
* The number of tokens deposited\
  \- more token in the position translates to a larger relative share against the total active liquidity, which gets more trading fee rewards from trades
* The selected price range\
  \- smaller price range allows a higher concentration for the same amount of token deposited, which translates to a larger relative share against the total active liquidity, and gets more trading fee rewards from trades
* The amount of liquidity currently active\
  \- if there are more users who deposit and concentrate their liquidity with the same range as you, you will earn less trading fee due to a smaller relative share against the total
* Whether the liquidity position is active\
  \- only active liquidity positions will earn trading fee rewards



### Can I provide v2 liquidity?

Providing v2 liquidity is no longer advisable. We recommend using v3 liquidity to take advantage of the new features to improve efficiency.

If you want to proceed with adding v2 liquidity:

* If the token pair does not have a v3 pool, or it has more liquidity in v2 than the largest pool in v3. A “Add V2 Liquidity” will appear. Simply click to switch to adding v2 liquidity
* Alternatively, use `/v2` in the URL to always use v2 liquidity provisioning



### Why can’t I add liquidity to a pair I just created?

Due to a bug from the legacy Exchange V2 (present in every UniSwap V2 forks), you will not be able to add liquidity to a pair using the normal PancakeSwap liquidity UI and its contract calls if a pair is:

* Created by calling `createPair` on FactoryV2 without depositing initial liquidity and minting the initial LP tokens
* Then, one of the tokens in the pair has been manually transferred into the pool contract while calling `sync`

{% hint style="info" %}
Recently, an increase amount of such attacks were spotted on PancakeSwap Exchange V2 on BNB Chain.&#x20;

We strongly recommend using our UI to create the trading pair for your token by adding the initial liquidity with the pair creation.
{% endhint %}

While Chefs are working hard on a solution to resolve this issue, here is a step-by-step guide to resolve this using BscScan:

#### Locate the pool address and its BscScan page

\[img: the error prompt (pending)]

If your pair is affected, you will see the link to the BscScan page for the trading pair/pool in the error prompt.

Alternatively, you can head to Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)), go to “Read Contract”, “6. getPair”, enter the address of the two tokens in your trading pair, and click “Query”. You should see the pair address in the return field.

#### Check which token has been deposited and transfer the other token into the pair manually

![](<../../.gitbook/assets/image (181).png>)

From the token balance field on BscScan, you can check which token has been deposited into the pool. Usually, it should be the paired token. (Like WBNB, USDT, etc…)

Once confirmed, you must manually transfer the other asset into the pool contract. You may do that in the wallet app you prefer by entering the pool address as the receiver.

You can transfer any amount but since this is effectively “donating” assets to a pool. You will be transfering your assets into a liquidity without minting liquidity tokens. So we recommend keeping this amount minimal.

{% hint style="warning" %}
IMPORTANT: Once you’ve transferred the token, you must call `sync()`immediately on the pool.
{% endhint %}

You can do so by heading to the BscScan page for the trading pair, going to “Write Contract”, “8. Sync”, and clicking the “Write” button. You will need to connect your wallet before performing the transaction.

Once the transaction is confirmed, you can add the subsequent liquidity on PancakeSwap UI.

#### What if I want to define the launch price?

You must adjust the pool to the launch price while transferring the token and fixing the pool.

The amount to transfer can be calculated using:

* `tokenInside`: the token that is already transferred into the pool. Usually it should be the paired token. (Like WBNB, USDT, etc…)
* `tokenToSend`: the token that is about to be sent to the pool. Usually it should be your project token
* `tokenInside.price`: the USD price of tokenInside
* `tokenToSend.price`: the USD price of tokenToSend (the launch price)
* `pool`: the V2 pool

With the following formula:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

If the result is smaller than 0 (usually happens when the launch price is very large. You may need to first deposit more `tokenInside` into the pool)



### How to manage stable LP, and legacy v2 LP?

You can manage them as usual by going to the [Liquidity](https://pancakeswap.finance/liquidity) page.



### Why do I need to reset approval on USDT before enabling/approving?

When operating on the Ethereum mainnet, the USDT token follows a different logic for managing approvals and token allowance.&#x20;

Therefore, when spending allowances are too low. It requires you to reset the approval before setting a new one.
