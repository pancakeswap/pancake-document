---
description: Common error messages. Use the sidebar to jump to the error you're seeing.
---

# Troubleshooting Errors

## **Issues on the Exchange**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.

You're trying to swap tokens, but your slippage tolerance is too low or liquidity is too low.

{% tabs %}
{% tab title="Solution" %}
1. Refresh your page and try again later.
2. Try trading a smaller amount at one time.
3. Increase your slippage tolerance:
   1. Tap the settings icon on the liquidity page.
   2. Increase your slippage tolerance a little and try again. ![](../.gitbook/assets/image%20%289%29%20%284%29%20%282%29%20%284%29.png)
4. Lastly, try inputting an amount with fewer decimal places.
{% endtab %}

{% tab title="Reason" %}
**This usually happens when trading tokens with low liquidity.**

That means there isn't enough of one of the tokens you're trying to swap in the Liquidity Pool: it's probably a small-cap token that few people are trading.

However, there's also the chance that you're trying to trade a scam token which cannot be sold. In this case, PancakeSwap isn't able to block a token or return funds.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'  
> or  
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

You're trying to add/remove liquidity from a liquidity pool \(LP\), but there isn't enough of one of the two tokens in the pair.

{% tabs %}
{% tab title="Solution" %}
**Refresh your page and try again, or try again later.**

Still doesn't work?

1. Tap the settings icon on the liquidity page.
2. Increase your slippage tolerance a little and try again.

![](../.gitbook/assets/image%20%289%29%20%284%29%20%282%29%20%284%29.png)
{% endtab %}

{% tab title="Reason" %}
The error is caused by trying to add or remove liquidity for a liquidity pool \(LP\) with an insufficient amount of token A or token B \(one of the tokens in the pair\).

It might be the case that prices are updating too fast when and your slippage tolerance is too low.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)



![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solution for nerds" %}
OK, so you're really determined to fix this. We really don't recommend doing this unless you know what you're doing.

There currently isn't a simple way to solve this issue from the PancakeSwap website: you'll need to interact with the contract directly. You can add liquidity directly via the Router contract, while setting amountAMin to a small amount, then withdrawing all liquidity.

### **Approve the LP contract**

Head to the contract of the LP token you're trying to approve.   
For example, here's the ETH/WBNB pair: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Select **Write Contract**, then **Connect to Web3** and connect your wallet. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. In **section "1. approve",** approve the LP token for the router by entering
   1. spender \(address\): enter the contract address of the LP token you're trying to interact with
   2. value \(uint256\): -1

### Query "balanceOf"

1. Switch to **Read Contract.**
2. In **5. balanceOf**, input your wallet address and hit **Query**.
3. Keep track of the number that's exported. It shows your balance within the LP in the uint256 format, which you'll need in the next step.

![](../.gitbook/assets/image%20%2832%29.png)

### Add or Remove Liquidity

Head to the router contract: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f\#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Select **Write Contract** and **Connect to Web3** as above.
2. Find **addLiquidity** or **removeLiquidity** \(whichever one you're trying to do\)
3. Enter the token addresses of both of the tokens in the LP.
4. In **liquidity \(uint256\),** enter the uint256 number which you got from "balanceOf" above.
5. Set a low **amountAMin** or **amountBMin**: try 1 for both.
6. Add your wallet address in **to \(address\)**.
7. Deadline must be an epoch time greater than the time the tx is executed.

![](../.gitbook/assets/image%20%2819%29.png)

{% hint style="warning" %}
This can cause very high slippage, and can cause the user to lose some funds if frontrun
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Try again, but confirm \(sign and broadcast\) the transaction as soon as you generate it. 

This happened because you started making a transaction, but you didn't sign and broadcast it until it was past the deadline. That means you didn't hit "Confirm" quickly enough. 

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Refresh the page and try again, or increase slippage tolerance via the settings icon and try again.

This probably happened because you're trying to buy or sell tokens during a big price movement. The frontend is getting outdated information \(e.g. outAmount\) from the smart contract, causing the swap to fail.



## **Issues with Syrup Pools**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

You don't have enough SYRUP in your wallet to unstake from the CAKE-CAKE pool.

{% tabs %}
{% tab title="Solution 1" %}
**Get at least as much SYRUP as the amount of CAKE that you’re trying to unstake.**

1. Buy SYRUP on the exchange. If you want to unstake 100 CAKE, you need at least 100 SYRUP.
2. Try unstaking again.
{% endtab %}

{% tab title="Solution 2" %}
If that still fails, you can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Go to: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E\#writeContract ](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract%20)
2. Click **“Connect to Web3”** and connect your wallet. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. In section **“4. emergencyWithdraw”**, enter "0" and click “Write”.

This will unstake your staked tokens and lose any uncollected CAKE yield.

{% hint style="warning" %}
**This will lose any yield that you haven’t harvested yet.**
{% endhint %}
{% endtab %}

{% tab title="Reason" %}
To stop this happening again, **don’t sell your SYRUP.** You still need it to unstake from the “Stake CAKE Earn CAKE” pool.

This error has happened because you have sold or transferred SYRUP tokens. SYRUP is minted in a 1:1 ratio to CAKE when you stake in the CAKE-CAKE Syrup Pool. SYRUP must be burned at a 1:1 ratio to CAKE when calling leaveStaking \(unstaking your CAKE from the pool\), so if you don't have enough, you can't unstake from the pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}



![](https://lh4.googleusercontent.com/KchAcnM6cpX2BotEGppAxPAnY4Xbona6yI6ZWg9FlUUBfPi_YO9ulM1s6htXJVXMzEwl0Uxcvdk8o4yhI7ar5g0TRpLVFjkS4YLKL7FS8Z4uFqeC37sw-TIkrPr7BCZQVpuD-5jO)
{% endtab %}
{% endtabs %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas\]

You have set a low gas limit when trying to make a transaction.

{% tabs %}
{% tab title="Solution" %}
Try manually increasing the **gas limit** \(not gas price!\) in your wallet before signing the transaction. 

A limit of 200000 is usually enough.

![](../.gitbook/assets/image%20%28169%29.png)

The above example is from Metamask; check your wallet's documentation if you aren't sure how to adjust the gas limit.
{% endtab %}

{% tab title="Reason" %}
Basically, your wallet \(Metamask, Trust Wallet, etc.\) can't finish what it's trying to do.

Your wallet estimates that the gas limit is too low, so the function call runs out of gas before the function call is finished.  
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

You're trying to unstake from a Syrup Pool with low rewards in it.

{% tabs %}
{% tab title="Solution" %}
You can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Find the contract address of the Syrup Pool you're trying to unstake from. You can find it in your wallet's transaction log.
2. Go to [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract%20) and in the search bar, enter the contract address.
3. Select **Write Contract.**
4. Click **“Connect to Web3”** and connect your wallet.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. In section **“4. emergencyWithdraw”,** enter "0" and click “Write”.

This will unstake your staked tokens and lose any uncollected yield.

{% hint style="warning" %}
**This will lose any yield that you haven’t harvested yet.**
{% endhint %}
{% endtab %}

{% tab title="Reason" %}
This error tends to appear when you're trying to unstake from an old Syrup Pool, but there aren't enough rewards in the pool left for you to harvest when withdrawing. This causes the transaction to fail.
{% endtab %}
{% endtabs %}

## \*\*\*\*

