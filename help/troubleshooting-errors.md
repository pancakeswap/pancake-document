# Troubleshooting Errors

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbAuxEDBWQVyR1QW3QF%2F-MbAxAeo32JUUlQJvtvF%2Fdocs%20masthead%20\(16\).png?alt=media\&token=d61bc04f-7a3c-4b3d-bcaf-1289a4d93ec0)

Sometimes you may find yourself facing a problem that doesn't have a clear solution. These troubleshooting tips may help you solve problems you run into.

## **Issues on the Exchange** <a href="#issues-on-the-exchange" id="issues-on-the-exchange"></a>

### **INSUFFICIENT\_OUTPUT\_AMOUNT** <a href="#insufficient_output_amount" id="insufficient_output_amount"></a>

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.

You're trying to swap tokens, but your slippage tolerance is too low or liquidity is too low.

1. Refresh your page and try again later.
2. Try trading a smaller amount at one time.
3. Increase your slippage tolerance:
   1. Tap the settings icon on the liquidity page.
   2. Increase your slippage tolerance a little and try again. ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MWxtg35bMTu-jgHaZjz%2F-MWyFMaIzjPxS091zEgv%2Fimage.png?alt=media\&token=524e7a9c-7e37-4aa3-a364-e2aad8357955)​
4. Lastly, try inputting an amount with fewer decimal places.

**This usually happens when trading tokens with low liquidity.**

That means there isn't enough of one of the tokens you're trying to swap in the Liquidity Pool: it's probably a small-cap token that few people are trading.

However, there's also the chance that you're trying to trade a scam token which cannot be sold. In this case, PancakeSwap isn't able to block a token or return funds.

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT** <a href="#insufficient_a_amount-or-insufficient_b_amount" id="insufficient_a_amount-or-insufficient_b_amount"></a>

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT' or Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

You're trying to add/remove liquidity from a liquidity pool (LP), but there isn't enough of one of the two tokens in the pair.

**Refresh your page and try again, or try again later.**

Still doesn't work?

1. Tap the settings icon on the liquidity page.
2. Increase your slippage tolerance a little and try again.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MWxtg35bMTu-jgHaZjz%2F-MWyFMaIzjPxS091zEgv%2Fimage.png?alt=media\&token=524e7a9c-7e37-4aa3-a364-e2aad8357955)

The error is caused by trying to add or remove liquidity for a liquidity pool (LP) with an insufficient amount of token A or token B (one of the tokens in the pair).

It might be the case that prices are updating too fast when and your slippage tolerance is too low.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs\_pxdobz\_kY\_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

​

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt\_FAwpEylaIJhff5ZcYlzB\_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)

OK, so you're really determined to fix this. We really don't recommend doing this unless you know what you're doing.

There currently isn't a simple way to solve this issue from the PancakeSwap website: you'll need to interact with the contract directly. You can add liquidity directly via the Router contract, while setting amountAMin to a small amount, then withdrawing all liquidity.

### **Approve the LP contract** <a href="#approve-the-lp-contract" id="approve-the-lp-contract"></a>

Head to the contract of the LP token you're trying to approve. For example, here's the ETH/WBNB pair: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)​

1. Select **Write Contract**, then **Connect to Web3** and connect your wallet. ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)​
2. In **section "1. approve",** approve the LP token for the router by entering
   1. spender (address): enter the contract address of the LP token you're trying to interact with
   2. value (uint256): -1

### Query "balanceOf" <a href="#query-balanceof" id="query-balanceof"></a>

1. Switch to **Read Contract.**
2. In **5. balanceOf**, input your wallet address and hit **Query**.
3. Keep track of the number that's exported. It shows your balance within the LP in the uint256 format, which you'll need in the next step.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MWyRmFs2sNnymML3Z2M%2F-MX0PyVn6ZR6UpbtxcCP%2Fimage.png?alt=media\&token=117ba31f-371c-444f-a585-7796848f2531)

### Add or Remove Liquidity <a href="#add-or-remove-liquidity" id="add-or-remove-liquidity"></a>

Head to the router contract: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)​

1. Select **Write Contract** and **Connect to Web3** as above.
2. Find **addLiquidity** or **removeLiquidity** (whichever one you're trying to do)
3. Enter the token addresses of both of the tokens in the LP.
4. In **liquidity (uint256),** enter the uint256 number which you got from "balanceOf" above.
5. Set a low **amountAMin** or **amountBMin**: try 1 for both.
6. Add your wallet address in **to (address)**.
7. Deadline must be an epoch time greater than the time the tx is executed.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MWxtg35bMTu-jgHaZjz%2F-MWyHFbEisf-f1eCkGBl%2Fimage.png?alt=media\&token=2bf3998f-20c5-4c71-90ea-4f0bd54b04db)

This can cause very high slippage, and can cause the user to lose some funds if frontrun

### PancakeRouter: EXPIRED <a href="#pancakerouter-expired" id="pancakerouter-expired"></a>

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Try again, but confirm (sign and broadcast) the transaction as soon as you generate it.

This happened because you started making a transaction, but you didn't sign and broadcast it until it was past the deadline. That means you didn't hit "Confirm" quickly enough.

### Pancake: K <a href="#pancake-k" id="pancake-k"></a>

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Refresh the page and try again, or increase slippage tolerance via the settings icon and try again.

This probably happened because you're trying to buy or sell tokens during a big price movement. The frontend is getting outdated information (e.g. outAmount) from the smart contract, causing the swap to fail.

### Transaction cannot succeed <a href="#transaction-cannot-succeed" id="transaction-cannot-succeed"></a>

Try trading a smaller amount, or increase slippage tolerance via the settings icon and try again. This is caused by low liquidity.

### **Price Impact too High** <a href="#price-impact-too-high" id="price-impact-too-high"></a>

Try trading a smaller amount, or increase slippage tolerance via the settings icon and try again. This is caused by low liquidity.

### estimateGas failed <a href="#estimategas-failed" id="estimategas-failed"></a>

> This transaction would fail. Please contact support

**Contact the project team of the token you're trying to swap.**

This issue must be resolved by the project team.

**This issue is caused by tokens which have hard-coded the V1 PancakeSwap router into their contract.**

While this practice is ill-advised at best, the reason for these projects having done this appears to be due to their tokenomics, in which each purchase sends a % of the token to LPs.

The projects affected will likely not work with the V2 router: they will most likely need to create new versions of their tokens pointing to our new router address, and migrate any existing token holders to their new token.

We recommend that any projects which created such tokens should also make efforts to prevent their users from adding them to V2 LP.

The up-to-date router address is [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)​

## **Issues with Syrup Pools** <a href="#issues-with-syrup-pools" id="issues-with-syrup-pools"></a>

### BEP20: burn amount exceeds balance <a href="#bep-20-burn-amount-exceeds-balance" id="bep-20-burn-amount-exceeds-balance"></a>

> Fail with error 'BEP20: burn amount exceeds balance'

You don't have enough SYRUP in your wallet to unstake from the CAKE-CAKE pool.

**Get at least as much SYRUP as the amount of CAKE that you’re trying to unstake.**

1. Buy SYRUP on the exchange. If you want to unstake 100 CAKE, you need at least 100 SYRUP.
2. Try unstaking again.

If that still fails, you can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1.
2. Click **“Connect to Web3”** and connect your wallet. ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)​
3. In section **“4. emergencyWithdraw”**, enter "0" and click “Write”.

This will unstake your staked tokens and lose any uncollected CAKE yield.

**This will lose any yield that you haven’t harvested yet.**

To stop this happening again, **don’t sell your SYRUP.** You still need it to unstake from the “Stake CAKE Earn CAKE” pool.

This error has happened because you have sold or transferred SYRUP tokens. SYRUP is minted in a 1:1 ratio to CAKE when you stake in the CAKE-CAKE Syrup Pool. SYRUP must be burned at a 1:1 ratio to CAKE when calling leaveStaking (unstaking your CAKE from the pool), so if you don't have enough, you can't unstake from the pool.

​

![](https://lh4.googleusercontent.com/KchAcnM6cpX2BotEGppAxPAnY4Xbona6yI6ZWg9FlUUBfPi\_YO9ulM1s6htXJVXMzEwl0Uxcvdk8o4yhI7ar5g0TRpLVFjkS4YLKL7FS8Z4uFqeC37sw-TIkrPr7BCZQVpuD-5jO)

### Out of Gas error <a href="#out-of-gas-error" id="out-of-gas-error"></a>

> Warning! Error encountered during contract execution \[out of gas]

You have set a low gas limit when trying to make a transaction.

Try manually increasing the **gas limit** (not gas price!) in your wallet before signing the transaction.

A limit of 200000 is usually enough.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MWxtg35bMTu-jgHaZjz%2F-MWy0GU0AvB9KPJgcCYV%2Fimage.png?alt=media\&token=e4850a43-199f-4dac-8c0d-fdbc68453121)

The above example is from Metamask; check your wallet's documentation if you aren't sure how to adjust the gas limit.

Basically, your wallet (Metamask, Trust Wallet, etc.) can't finish what it's trying to do.

Your wallet estimates that the gas limit is too low, so the function call runs out of gas before the function call is finished.

### BEP20: transfer amount exceeds balance <a href="#bep-20-transfer-amount-exceeds-balance" id="bep-20-transfer-amount-exceeds-balance"></a>

> Fail with error 'BEP20: transfer amount exceeds balance'

You're trying to unstake from a Syrup Pool with low rewards in it.

You can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Find the contract address of the Syrup Pool you're trying to unstake from. You can find it in your wallet's transaction log.
2. Go to [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) and in the search bar, enter the contract address.
3. Select **Write Contract.**
4. Click **“Connect to Web3”** and connect your wallet.![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)​
5. In section **“4. emergencyWithdraw”,** enter "0" and click “Write”.

This will unstake your staked tokens and lose any uncollected yield.

**This will lose any yield that you haven’t harvested yet.**

This error tends to appear when you're trying to unstake from an old Syrup Pool, but there aren't enough rewards in the pool left for you to harvest when withdrawing. This causes the transaction to fail.

## **Other issues** <a href="#other-issues" id="other-issues"></a>

### Provider Error: No provider was found <a href="#provider-error-no-provider-was-found" id="provider-error-no-provider-was-found"></a>

* Clear your cache and cookies
* Disconnect and reconnect your wallet
* Restart your device

### Unsupported Chain ID <a href="#unsupported-chain-id" id="unsupported-chain-id"></a>

Switch your chain to Binance Smart Chain. Check your wallet's documentation for a guide if you need help.

### Issues buying SAFEMOON and similar tokens <a href="#issues-buying-safemoon-and-similar-tokens" id="issues-buying-safemoon-and-similar-tokens"></a>

To trade SAFEMOON, you must click on the settings icon and **set your slippage tolerance to 12% or more.** This is because **SafeMoon taxes a 10% fee on each transaction**:

* 5% fee = redistributed to all existing holders
* 5% fee = used to add liquidity

This is also why you might not receive as much of the token as you expect when you purchase. Read more on [How to Buy Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).
