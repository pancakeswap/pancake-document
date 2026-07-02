---
hidden: true
---

# How to use Limit Orders

## What is Limit Orders

A limit order is a tool to enable users to buy or sell assets at a specified price or better, instead of relying on the market price at the time of execution. In a limit order, while the price is guaranteed, the order being executed is not - limit orders will be executed only if the price meets the order qualifications.

## How to set up a limit order

1. Go to the Swap page and select the limit order option by clicking “LIMIT”, or, use this link: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. Select the “From” and “To” tokens you wish to trade. In this example we chose USDC and ETH respectively, meaning we want to buy ETH with USDC.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. Enter the amount you wish to trade. Notice the limit price will show the current market price which will then estimate the output amount of destination tokens (ETH)
2. Set the desired limit price. Trades will ONLY be executed when the available market price is better than or equal to the limit price. The destination token output amount will update accordingly.

In the example below, we wish to buy ETH when the price is $1,900 or better. The amount of ETH received will be equal or greater than 0.037 ETH. Only bids equal or better than this amount will be eligible to fill the order. This amount takes into account gas costs and fees. &#x20;

{% hint style="info" %}
Important note: As the fees are paid from the output token amount, the limit price includes the gas & trading fees and so users should take this into account when setting up the price. For example, a very small order’s gas fees can total a very large percentage of the order output, reflecting an actual limit price that is not competitive with the spot market price.
{% endhint %}

3.  Press “Place order”. Double check your order details, accept the disclaimer and press “Confirm order”.

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. Once the transaction is through, you will be able to see your order in the order history section, under “Open orders”. \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. Open orders can be canceled at any time by expanding the order and clicking the “Cancel Order” button.

Things to take into consideration:

* Your order may not be executed if the available market price is worse than the limit price you have set.
* The trades are based on a decentralized protocol that utilizes off-chain takers which compete to fill orders. These takers are entitled to request a fee, which the protocol removes for the winning taker from the output tokens.&#x20;
* Takers may take into account gas fees for your transactions when setting their fees, which may result in fluctuations in the fee amounts.
* When specifying a limit price, users will see in the UI the minimum amount of destination tokens they will receive if the order is filled. Only takers making bids equal or better than this amount will be eligible to fill the order. This amount takes into account gas costs and trading fees.
