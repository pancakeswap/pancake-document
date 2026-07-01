# 🎯 PancakeSwap Auto Slippage

PancakeSwap has introduced Auto Slippage to make trading easier and more efficient. Auto Slippage automatically adjusts the slippage for you based on current market conditions, helping to prevent failed trades and reduce the risk of losing money due to slippage errors.

## What is Slippage?

**Slippage** occurs when the price you expect for a trade is different from the price at which the trade is actually completed. This can happen for several reasons:

* Market volatility – Prices can move quickly between when you place and confirm
* Low liquidity – there aren’t enough tokens available at your expected price
* Blockchain delays – confirmation times can cause the price to change before the trade is completed finalized

{% hint style="info" %}
Example:

You try to swap 100 CAKE for BNB, expecting 1 CAKE = 0.01 BNB. But by the time your trade goes through, the price has changed and you only get 0.0098 BNB per CAKE. This small difference is what we call slippage.
{% endhint %}

## What is Slippage Tolerance?

**Slippage tolerance** is the maximum price difference you’re willing to accept before your trade is canceled. If the price moves beyond your set tolerance, your transaction will fail to prevent any unexpected losses.

{% hint style="info" %}
Example:

If you set a 1% slippage tolerance and the price changes by more than 1% before the trade is completed, the trade won’t go through.
{% endhint %}

## What happens if my Slippage Tolernace is too low?

If your slippage tolerance is **set too low**, there’s a higher chance your transaction will fail — especially when:

* The market is volatile
* You’re swapping tokens with low liquidity
* Using tokens with taxes or complex mechanics

{% hint style="warning" %}
Important: Even if the transaction fails, you’ll still consume gas fees for trying.
{% endhint %}

## Introducing Auto Slippage - Why is Auto Slippage helpful?

Auto Slippage automatically adjusts your slippage based on current market conditions, saving you time and reducing the risk of failed trades.&#x20;

With **Auto Slippage**, there's no need to manually adjust your slippage tolerance. This helps prevent common issues such as:

* **Setting slippage too low**, which can cause transactions to fail due to minor price changes during execution.
* **Setting slippage too high**, which may result in receiving fewer tokens than expected due to accepting a wider price range.

{% hint style="info" %}
To ensure the best trading experience, auto slippage has been **toggled on automatically**. If a manual slippage tolerance has been set, the new slippage setting will be applied.
{% endhint %}



## How does Auto Slippage work?

<pre class="language-html"><code class="lang-html"><strong>Auto Slippage (%) = (Gas Cost in USD / Output Token Value in USD) * 100%
</strong></code></pre>

* If the gas cost is high compared to the output token’s value, Auto Slippage will set a higher slippage to ensure the trade goes through.
* If gas is cheap and the output token's value is large, a smaller slippage will be used.

Auto Slippage will choose a value between **0.5%** and **5.0%**, depending on token and network conditions.



## Is Auto Slippage available on all networks?

No — Auto Slippage is only supported on Layer 1 (L1) chains like BNB Chain, Ethereum, etc.

It is not supported on Layer 2 (L2) chains, because:

* The auto slippage formula relies on meaningful gas cost values to calculate a useful slippage setting
* Since L2 gas fees are very low, applying auto slippage on L2s wouldn’t improve trade success rates

{% hint style="success" %}
&#x20;If Auto Slippage is **not supported** on a network:

* Your previously used slippage setting will be applied
* If you haven't set one before, it will default to 0.5%
{% endhint %}



