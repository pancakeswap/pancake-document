# Mini-Program FAQ

### &#x20;<a href="#what-are-the-future-developments-of-the-mini-program" id="what-are-the-future-developments-of-the-mini-program"></a>

Since the first version launched in March 2022, thousands of users now use it daily. As the first large-scale Mini-Program, the team at Binance is also discovering some new infrastructure and performance issues together with us, thus upgrading their architecture. Before adding more features, we are focused on improving the overall performance and user experience of the Mini-Program. As well, we are working with Binance to gradually add more entrances to the Mini-Program so it can be more easily discovered by Binance users – such as within search or earn functions in the application.

### &#x20;<a href="#how-will-the-mini-program-help-pancakeswap" id="how-will-the-mini-program-help-pancakeswap"></a>

PancakeSwap is currently the most popular decentralized platform (in terms of number of users) but the Kitchen is always looking for more ways to invite new users to our platform. While most DeFi users in the market should already have heard of or used PancakeSwap, imagine the potential of newcomers to crypto onboarded by Binance and its CEX. These new users may not have the experience of creating a Web3 wallet, adding liquidity, farming, staking, trading a wide variety of assets, etc. The PancakeSwap Mini-Program provides the best avenue to invite and educate these users to the DeFi experience.

### &#x20;<a href="#is-it-controlled-by-binance-or-pancakeswap" id="is-it-controlled-by-binance-or-pancakeswap"></a>

The Mini-Program frontend is developed under Binance’s guidelines and architecture of its Mini-Program system, Binance also has the right to review and approve any content and function in the Mini-Program. However, the underlying smart contracts you interact with within the Mini-Program are the same set of smart contracts as on our web.

### &#x20;<a href="#when-will-other-features-be-added-into-the-mini-program" id="when-will-other-features-be-added-into-the-mini-program"></a>

Due to regulatory concerns, other features like Lottery, IFO, profiles are not able to be added to the Mini-Program yet. Our aim is to educate Binance’s users on the basics of DeFi first and then gradually attract them to come to our web version to experience the full suite of our features!

### &#x20;<a href="#why-should-i-use-the-mini-program-when-i-can-use-the-web-version-with-a-browser-wallet" id="why-should-i-use-the-mini-program-when-i-can-use-the-web-version-with-a-browser-wallet"></a>

The Mini-Program is designed as a simplified version to attract Binance users who are not familiar with DeFi – these users may not have the experience of creating a Web3 wallet, adding liquidity, farming, staking, trading a wide variety of assets, etc. For experienced users who are familiar with browser wallets and interacting with the web version of PancakeSwap, the web version offers a full suite of features. It is also our goal to educate these new users on the basics of DeFi first and then attract them to come to our web version!

### &#x20;<a href="#how-come-my-transaction-wont-go-through" id="how-come-my-transaction-wont-go-through"></a>

The Mini-Program is in fact still fully a DeFi application such that it operates the same as the web-end user interface -- it interacts with the wallet (Binance DeFi wallet in this case) to complete on-chain transactions for swapping, creating LPs, staking in farms and pools.

### &#x20;<a href="#gas-fees" id="gas-fees"></a>

As such, the first thing is to **make sure you have enough BNB to pay for the gas fee** of the on-chain transactions. Typically, gas fee fluctuates depending on the number of transactions in the queue, if there are more transactions, a higher gas fee may be required to push through the transaction. On BNB Smart Chain on where the Mini-Program is operated, the gas fee typically ranges from cents to a dollar USD in BNB. Learn more about [gas fee here](https://academy.binance.com/en/glossary/gas).

### &#x20;<a href="#transaction-fees" id="transaction-fees"></a>

If your swapping action still doesn't go through and it is displaying an error for you to revise the slippage -- you may want to check if the tokens you are trying to swap has **any fees and restrictions on transactions**.

It is not uncommon for tokens on BNB Smart Chain to include a **transaction fee** in their contracts, usually these fees could be used for burning, funding a treasury of a fair launch project -- for example, this [APX token has an 1% tax on every transaction](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) for sending to a burn address, such that more transactions would mean more burning, accruing value to APX token holders.

With the transaction fee, whether it is inclusive (a portion of the swap amount is sent elsewhere than your address so the output is less than expected for the estimated input) or exclusive (requiring an additional transfer from your address to send extra tokens so the input is more than expected for the estimated output), it affects the input and output amount that you agree for signing the transaction. In many cases, the transaction cannot meet the input and output requirements because of the tax.

### &#x20;<a href="#swapping-with-transaction-fees" id="swapping-with-transaction-fees"></a>

Before you swap any tokens, make sure you have visited their website to understand if they have a transaction fee mechanism (or _tax_ as many projects put it). If there is, make sure you set a slippage that is sufficient to accommodate the transaction fee -- e.g. if there is a transaction fee of 5%, your slippage will have to be set at at least 5% plus the normal trading slippage depending on your trading amount and the token's liquidity, say 5.5%-6%.

In some extreme cases including some scams, some tokens even have a block on most or all transfers on chain, or only allowing certain addresses to sell, in such case it is impossible to swap the token successfully. Do learn about the token you are trying to swap and be aware of any fees and restrictions!

### &#x20;<a href="#where-can-i-provide-feedback-for-the-mini-program" id="where-can-i-provide-feedback-for-the-mini-program"></a>

We welcome all feedback and we’re always trying to improve for our community. For any feedback on the Mini-Program, other than the usual [Telegram](https://t.me/pancakeswap) or [Discord](https://discord.gg/pancakeswap), you can also submit your feedback within the Mini-Program, in the feedback button after you click on the three dots on the top-right corner.
