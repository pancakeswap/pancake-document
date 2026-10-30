# Options Primer



{% hint style="danger" %}
\[ARCHIVED] Options – As of March 11, 2025\
If you still have liquidity to withdraw, please do so immediately by visiting https://www.stryke.xyz/en/trade.
{% endhint %}



## What are Options?

Options are derivative contracts that provide the buyer with the right, but not the obligation, to buy (call option) or sell (put option) an underlying asset at a predetermined price (strike price) within a specified period (expiration date).

## Types of Options?

### Call Options

A call option gives the holder the right to buy the underlying asset at the agreed-upon strike price at or before the expiration date. Traders buy call options when they anticipate the price of the underlying asset to rise. This allows them to benefit from potential price appreciation without having to own the underlying asset outright.

> A trader purchases a call option on Bitcoin with a strike price of $50,000 expiring in one month. If the price of Bitcoin rises above $50,000 within that month, the investor can exercise the option to buy Bitcoin at $50,000, potentially profiting from the price difference.

### Put Options

A put option gives the holder the right to sell the underlying asset at the agreed-upon strike price at or before the expiration date. Traders buy put options when they expect the price of the underlying asset to fall. This allows them to profit from potential price declines without having to short sell the underlying asset. Typically put options are also used to hedge against any downside risks to the investment portfolios.

> A trader buys a put option on Ethereum with a strike price of $3,000 expiring in two weeks. If the price of Ethereum falls below $3,000 within that time frame, the trader can exercise the option to sell Ethereum at $3,000, thereby mitigating potential losses.

<figure><img src="../../../.gitbook/assets/trading-campaign (2).jpg" alt=""><figcaption></figcaption></figure>

## Options Positions

For each type of option, there exist two potential positions:

### **Long Option (Option Buyer)**&#x20;

This position involves paying an upfront premium to acquire the option. If the option ends up in profit, the holder receives a settlement.

### **Short Option (Option Writer/Seller)**

In this position, the seller receives an upfront premium for issuing the option. However, if the option ends up in profit (for the buyer; based on the underlying price, strike price, and type of the option), the seller is obligated to pay a settlement.

## American vs. European Options

* **American Options:** Can be exercised at any time before the expiration date. This flexibility makes them more valuable than European options.
* **European Options:** Can only be exercised at the expiration date. They are generally less expensive than American options due to their lack of flexibility.

## When to use Options?

Here are some example use cases:

1. **Speculation:** An investor believes that the price of Bitcoin will increase over the next month. They buy call options on Bitcoin to profit from the anticipated price rise.
2. **Hedging:** A cryptocurrency validator wants to hedge against potential price decreases in Ethereum. They purchase put options on Ethereum to protect against losses if the price falls below a certain level.
3. **Income Generation:** A crypto investor who holds a large amount of Ether decides to write call options on their holdings, earning premiums while still participating in potential upside price movements.

## Options Pricing

Options pricing is complex and involves various factors, with the Black-Scholes model being the most commonly used.&#x20;

Key factors influencing options pricing include:

* **Underlying Asset Price:** The current market price of the underlying asset.
* **Strike Price:** The price at which the option holder can buy or sell the underlying asset.
* **Volatility:** The degree of price fluctuations in the underlying asset.&#x20;
* **Time to Expiration:** The remaining time until the option expires.
* **Interest Rates:** The risk-free rate of return.

Options pricing determines the premium/fee a writer receives when an option trader purchases their option. Option writers are exposed to the risk of paying settlement if their options expire In-The-Money or ITM (profitable for the buyer). As such, the premiums they earn from purchasers must fairly reflect the probability of an ITM event.

PancakeSwap CLAMM options premiums are derived from the Black-Scholes model with the following assumptions:

* The risk-free rate is assumed to be zero.
* Volatility is based on the 30-day historical volatility of the underlying \[used as a proxy for implied volatility (IV)].

A few exceptions include:

* $ETH and $BTC IV are taken directly from Deribit if strike prices match. If strike prices do not match, the closest upper and lower strikes from Deribit are weighted based on the degree of offset to set IV.
* $ARB uses 30-day beta-based historical volatility by calculating the effective strike price of the base asset against $ETH to extrapolate IV which is multiplied by the beta of the base asset against $ETH

Assets with high volatility would have a more expensive premium than assets with less volatility as there is a greater risk to writers of the option expiring ITM.

## Options Settlement

### Settlement Conditions

* Settlement is determined based on the moneyness of the option at expiration.
* Settlement is calculated only if the option is In-The-Money (ITM) during exercise.

### ITM Conditions

* **Call Option:** If the Spot Price at Settlement > Strike Price
* **Put Option:** If the Spot Price at Settlement < Strike Price

### Settlement Calculation

* **Call Option:** #Options \* (Spot Price at Settlement - Strike Price)
* **Put Option:** #Options \* (Strike Price - Spot Price at Settlement)

### Moneyness

Moneyness refers to an option's intrinsic value, determined by comparing its strike price to its spot price at the time of execution.

### Classification

1. Out-of-The-Money (OTM):
   1. An option is OTM if the spot price at settlement differs from the strike price and no value is to be exchanged if settlement occurs immediately.
   2. Conditions:
      1. Call Option: Spot Price < Strike Price
      2. Put Option: Spot Price > Strike Price

{% hint style="info" %}
An $ETH call option with a strike price of $2,000 would be OTM if the spot price is $1,800 ($1,800 < $2,000 i.e. OTM).
{% endhint %}

2. At-The-Money (ATM):
   1. An option is ATM if the spot price at settlement is equal to the strike price and no value is to be exchanged if settlement occurs immediately.
   2. Conditions: Both Call and Put Options: Spot Price = Strike Price

{% hint style="info" %}
Both an $ETH call option and put option with a strike price of $1,800 would be ATM if the spot price is also $1,800 ($1,800 = $1,800 i.e. ATM).
{% endhint %}

3. In-The-Money (ITM):
   1. An option is ITM if the spot price at settlement differs from the strike price and there is value to be exchanged if settlement were to occur immediately.
   2. Conditions:
      1. Call Option: Spot Price > Strike Price
      2. Put Option: Spot Price < Strike Price

{% hint style="info" %}
An $ETH call option with a strike price of $1,600 would be ITM if the spot price is $1,800 ($1,800 > $1,600 i.e. ITM).
{% endhint %}

Settlement earned by the option buyer equals the collateral lost by the option writer. Settlement excludes options premium paid, which are factored in when computing profits or losses for option buyers and writers.
