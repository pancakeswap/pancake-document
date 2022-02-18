---
description: Common error messages. Use the sidebar ➡️to jump to the error you're seeing.
---

# Troubleshooting Errors

![](<../.gitbook/assets/docs masthead (16).png>)

Sometimes you may find yourself facing a problem that doesn't have a clear solution. These troubleshooting tips may help you solve problems you run into.

## **Issues on the Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

You're trying to swap tokens, but your slippage tolerance is too low or liquidity is too low.

{% tabs %}
{% tab title="Solution" %}
1. Refresh your page and try again later.
2. Try trading a smaller amount at one time.
3. Increase your slippage tolerance:
   1. Tap the settings icon on the liquidity page.
   2. Increase your slippage tolerance a little and try again. ![](<../.gitbook/assets/image (9) (4) (2) (4).png>)
4. Lastly, try inputting an amount with fewer decimal places.
{% endtab %}

{% tab title="Reason" %}
**This usually happens when trading tokens with low liquidity.**

That means there isn't enough of one of the tokens you're trying to swap in the Liquidity Pool: it's probably a small-cap token that few people are trading.

However, there's also the chance that you're trying to trade a scam token which cannot be sold. In this case, PancakeSwap isn't able to block a token or return funds.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

You're trying to add/remove liquidity from a liquidity pool (LP), but there isn't enough of one of the two tokens in the pair.

{% tabs %}
{% tab title="Solution" %}
**Refresh your page and try again, or try again later.**

Still doesn't work?

1. Tap the settings icon on the liquidity page.
2. Increase your slippage tolerance a little and try again.

![](<../.gitbook/assets/image (9) (4).png>)
{% endtab %}

{% tab title="Reason" %}
The error is caused by trying to add or remove liquidity for a liquidity pool (LP) with an insufficient amount of token A or token B (one of the tokens in the pair).

It might be the case that prices are updating too fast when and your slippage tolerance is too low.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs\_pxdobz\_kY\_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt\_FAwpEylaIJhff5ZcYlzB\_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solution for nerds" %}
OK, so you're really determined to fix this. We really don't recommend doing this unless you know what you're doing.

There currently isn't a simple way to solve this issue from the PancakeSwap website: you'll need to interact with the contract directly. You can add liquidity directly via the Router contract, while setting amountAMin to a small amount, then withdrawing all liquidity.

#### **Approve the LP contract**

Head to the contract of the LP token you're trying to approve.\
For example, here's the ETH/WBNB pair: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Select **Write Contract**, then **Connect to Web3** and connect your wallet. ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
2. In **section "1. approve",** approve the LP token for the router by entering
   1. spender (address): enter the contract address of the LP token you're trying to interact with
   2. value (uint256): -1

#### Query "balanceOf"

1. Switch to **Read Contract.**
2. In **5. balanceOf**, input your wallet address and hit **Query**.
3. Keep track of the number that's exported. It shows your balance within the LP in the uint256 format, which you'll need in the next step.

![](<../.gitbook/assets/image (7).png>)

#### Add or Remove Liquidity

Head to the router contract: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Select **Write Contract** and **Connect to Web3** as above.
2. Find **addLiquidity** or **removeLiquidity** (whichever one you're trying to do)
3. Enter the token addresses of both of the tokens in the LP.
4. In **liquidity (uint256),** enter the uint256 number which you got from "balanceOf" above.
5. Set a low **amountAMin** or **amountBMin**: try 1 for both.
6. Add your wallet address in **to (address)**.
7. Deadline must be an epoch time greater than the time the tx is executed.

![](<../.gitbook/assets/image (5).png>)

{% hint style="warning" %}
This can cause very high slippage, and can cause the user to lose some funds if frontrun
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Try again, but confirm (sign and broadcast) the transaction as soon as you generate it.

This happened because you started making a transaction, but you didn't sign and broadcast it until it was past the deadline. That means you didn't hit "Confirm" quickly enough.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Try modifying the amount on “To” field. Therefore putting "(estimated)" symbol on “From”. Then initiate the swap immediately.

![](<../.gitbook/assets/Pancake-K-Solution (2).png>)

This usually happen when you are trying to swap a token with its own fee.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

Make sure you have 30% more tokens in your wallet than you intend to trade, or try to trade a lower amount. If you want to sell the maximum possible, try 70% or 69% instead of 100%.\
Caused by the design of Restorative Rebase tokens like tDoge or tBTC.\
[Understand how restorative rebase tokens work](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Another possible cause of this issue is the malicious token issuer just suspended the trading for their token. Or they made selling action only possible for selected wallet addresses. Please always do your own research to avoid any potential fraud. If the token you are trying to swap but failed with this error code is coming from an airdrop, that is most likely a scam. Please do not perform any token approval or follow any links, your fund may be at risk if you try to do so.

### Transaction cannot succeed

Try trading a smaller amount, or increase slippage tolerance via the settings icon and try again. This is caused by low liquidity.

### **Price Impact too High**

Try trading a smaller amount, or increase slippage tolerance via the settings icon and try again. This is caused by low liquidity.

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Solution" %}
**If you got this error while removing liquidity from a BNB pair:**

Please select "Receive WBNB" and retry.

**If you got this error while trying to swap:**

Please contact the project team of the token you're trying to swap. \*\*\*\* This issue must be resolved by the project team.
{% endtab %}

{% tab title="Reason" %}
**This issue (while swapping) is caused by tokens which have hard-coded the V1 PancakeSwap router into their contract.**

While this practice is ill-advised at best, the reason for these projects having done this appears to be due to their tokenomics, in which each purchase sends a % of the token to LPs.

The projects affected will likely not work with the V2 router: they will most likely need to create new versions of their tokens pointing to our new router address, and migrate any existing token holders to their new token.

We recommend that any projects which created such tokens should also make efforts to prevent their users from adding them to V2 LP.

The up-to-date router address is [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

When trying to swap tokens, the transaction fails and this error message is displayed. This error has been reported on mobile devices using Trust Wallet.

{% tabs %}
{% tab title="Solution" %}
1. Attempt the transaction again with increased slippage allowance.
2. If 1. does not resolve your problem, consider using another wallet such as SafePal for your transaction.
{% endtab %}

{% tab title="Reason" %}
**This usually happens when trading tokens with insufficient slippage allowance on Trust Wallet.**

The exact details of the problem are still being investigated.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

When trying to swap tokens, the transaction fails and this error message is displayed. This error has been reported across platforms.

{% tabs %}
{% tab title="Solution" %}
1. Check to make sure you have sufficient funds available.
2. Ensure you have given the contract allowance to spend the amount of funds you're attempting to trade with.
{% endtab %}

{% tab title="Reason" %}
This error happens when trading tokens with insufficient allowance, or when a wallet has insufficient funds.\
If you're trading tokens with Restorative Rebase like tau assets tDoge or tBTC, make sure you understand how they work first with this [guide to Rebase tokens](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

## **Issues with Syrup Pools**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

You don't have enough SYRUP in your wallet to unstake from the CAKE-CAKE pool.

**Get at least as much SYRUP as the amount of CAKE that you’re trying to unstake.**

1. Buy SYRUP on the exchange. If you want to unstake 100 CAKE, you need at least 100 SYRUP.
2. Try unstaking again.

If that still fails, you can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Go to: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Click **“Connect to Web3”** and connect your wallet. ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
3. In section **“4. emergencyWithdraw”**, enter "0" and click “Write”.

This will unstake your staked tokens and lose any uncollected CAKE yield.

{% hint style="warning" %}
**This will lose any yield that you haven’t harvested yet.**
{% endhint %}

To stop this happening again, **don’t sell your SYRUP.** You still need it to unstake from the “Stake CAKE Earn CAKE” pool.

This error has happened because you have sold or transferred SYRUP tokens. SYRUP is minted in a 1:1 ratio to CAKE when you stake in the CAKE-CAKE Syrup Pool. SYRUP must be burned at a 1:1 ratio to CAKE when calling leaveStaking (unstaking your CAKE from the pool), so if you don't have enough, you can't unstake from the pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}
![](https://lh4.googleusercontent.com/KchAcnM6cpX2BotEGppAxPAnY4Xbona6yI6ZWg9FlUUBfPi\_YO9ulM1s6htXJVXMzEwl0Uxcvdk8o4yhI7ar5g0TRpLVFjkS4YLKL7FS8Z4uFqeC37sw-TIkrPr7BCZQVpuD-5jO)
{% endembed %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas]

You have set a low gas limit when trying to make a transaction.

{% tabs %}
{% tab title="Solution" %}
Try manually increasing the **gas limit** (not gas price!) in your wallet before signing the transaction.

A limit of 200000 is usually enough.

![](<../.gitbook/assets/image (2).png>)

The above example is from Metamask; check your wallet's documentation if you aren't sure how to adjust the gas limit.
{% endtab %}

{% tab title="Reason" %}
Basically, your wallet (Metamask, Trust Wallet, etc.) can't finish what it's trying to do.

Your wallet estimates that the gas limit is too low, so the function call runs out of gas before the function call is finished.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Solution" %}
1. Use Unrekt.net to revoke approval for the smart contract you're trying to interact with
2. Approve the contract again, without setting a limit on spend allowance
3. Try interacting with the contract again.
{% endtab %}

{% tab title="Reason" %}
This happens when you set a limit on your spend allowance when you first approved the contract, then try to swap more than the limit.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

You're probably trying to unstake from a Syrup Pool with low rewards in it. Solution below.

If not, you may be trying to send tokens that you don't have in your wallet (for example, trying to send a token that is already assigned to a pending transaction). In this case, just make sure you have the tokens you're trying to use.

{% tabs %}
{% tab title="Solution" %}
Firstly,[ let the team know](../contact-us/telegram.md) which pool you're trying to unstake from, so they can top up the rewards. If you're in a hurry to unstake and you don't mind losing your pending yield, try an emergencyWithdraw:

You can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Find the contract address of the Syrup Pool you're trying to unstake from. You can find it in your wallet's transaction log.
2. Go to [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) and in the search bar, enter the contract address.
3. Select **Write Contract.**
4. Click **“Connect to Web3”** and connect your wallet.![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
5. In section **“3. emergencyWithdraw”,** and click “Write”.

This will unstake your staked tokens and lose any uncollected yield.

{% hint style="warning" %}
**This will lose any yield that you haven’t harvested yet.**
{% endhint %}
{% endtab %}

{% tab title="Reason" %}
This error tends to appear when you're trying to unstake from an old Syrup Pool, but there aren't enough rewards in the pool left for you to harvest when withdrawing. This causes the transaction to fail.
{% endtab %}
{% endtabs %}

## **Issues with Prediction**

Check [prediction-troubleshooting.md](../products/prediction/prediction-troubleshooting.md "mention")

## **Other issues**

### Provider Error

> Provider Error\
> No provider was found

This happens when you try to connect via a browser extension like MetaMask or Binance Chain Wallet, but you haven’t installed the extension.

{% tabs %}
{% tab title="Solution" %}
Install the official browser extension to connect, or read our guide on [how to connect a wallet to PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide).
{% endtab %}
{% endtabs %}

### Unsupported Chain ID

Switch your chain to BNB Smart Chain. Check your wallet's documentation for a guide if you need help.

### Already processing eth\_requestAccounts. Please wait.

Make sure you are signed in to your wallet app and it's connected to BNB Smart Chain.

### Issues buying SAFEMOON and similar tokens

To trade SAFEMOON, you must click on the settings icon and **set your slippage tolerance to 12% or more.**\
This is because **SafeMoon taxes a 10% fee on each transaction**:

* 5% fee = redistributed to all existing holders
* 5% fee = used to add liquidity

This is also why you might not receive as much of the token as you expect when you purchase.\
Read more on [How to Buy Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Internal JSON-RPC errors

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Happens when trying to remove liquidity on some tokens via Metamask. Root cause is still unknown. Try using an alternative wallet.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

You don't have enough BNB to pay for the transaction fees. You need more BEP-20 network BNB in your wallet.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Increase the gas limit for the transaction in your wallet. Check your wallet's documentation to learn how to increase gas limit.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Cause unclear. Try these steps before trying again:

1. Increase gas limit
2. Increase slippage
3. Clear cache

## **Issues with Profile**

### Oops! We couldn't find any Pancake Collectibles in your wallet.

We're investigating the logic behind this issue. Meanwhile please try the workaround.

{% tabs %}
{% tab title="Workaround 1" %}
1. Go to “Collectible” page, then come back to profile page.\
   If you can’t find the link, go to [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles) directly.
2. Retry profile creation.
{% endtab %}

{% tab title="Workaround 2" %}
Change the environment.

* Clear the cache and retry.
* Retry on different browser.
* Retry on different wallet apps.
* Retry on the different network (switch between Wi-Fi and cellular)
{% endtab %}
{% endtabs %}

### Checking username keeps spinning

There are two possible causes.

1. You have multiple wallets installed on the browser.
2. Network issue.

{% tabs %}
{% tab title="Solution 1" %}
Root cause: You have multiple wallets installed on the browser.\
\
It may make a conflict between wallets. This is out of PancakeSwap's control and we can do nothing.

1. Have only single wallet installed on browser, remove the others.
2. Reconnect the wallet and retry setting username again.
{% endtab %}

{% tab title="Solution 2" %}
Root cause: Network is unstable.

You have to retry.

1. Delete whatever has been entered in the text field completely.
2. Re-type username, then please wait for seconds.
3. If it doesn’t work, reload the page and retry again.
{% endtab %}
{% endtabs %}
