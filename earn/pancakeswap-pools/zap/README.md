---
description: Adding liquidity in one click
---

# Zap

### What is Zap <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap is a feature that allows you to add liquidity with ease. With Zap, you can provide liquidity with any token you have balance in irrespective of the tokens required in the pool. Simply set the price range, choose the amount to provide, and execute. Your tokens will be automatically balanced to form the liquidity position while being traded in the most efficient way, with the lowest price impact and slippage.

### Supported Chains

* v3 - All pools on BNB Chain, selected pools on Ethereum & Arbitrum networks
* Infinity - All CLAMM pools (without hook) on BNB Chain

### How to Use <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

For now, Zap supports:

* 🆕 Any token!
* Using single token
* 🆕 Using duo tokens
* 🆕 Or... using multiple tokens (yes it's can be used like dust collector)

#### Start <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

To use Zap, simply go to Add Liquidity page, select the trading pair you want to provide liquidity to, fee tier, and the price range.

Then select the token amount you want to provide liquidity to.

Option to Zap will automatically appear when one or more tokens are short on balance.

Click the link to bring up the Zap modal.

#### Initiate Zap <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

Within the new “Zap in” modal. You may find the following fields:

1. The trading pair you are Zapping (providing liquidity) to.
2. The deposit token(s) and the amount(s) to deposit. You may freely add in or remove any tokens for the Zap.
3. The price range of the new position. You may also click the arrows to flip between different price displays.
4. A detailed breakdown of how the Zap feature will handle your deposit tokens.
5. A summary of the stats including:
   1. Estimated value in USD for the new liquidity position.
   2. Estimate token amount in the new liquidity position.
   3. Estimated leftover funds in USD after Zapping. In most cases it should be 0. If the liquidity pool or the tokens have very little liquidity, this value may increase.
   4. The price impact for the token swaps and rebalances while Zapping.
   5. The price impact for the liquidity adding and position building.
   6. Zap fee. Depending on the liquidity pair, fee rate may vary.

{% hint style="warning" %}
Note that you may need to reconfigure the amount to Zap based on your available balance. If you don't have balance on one of the tokens, please remove them.
{% endhint %}

{% hint style="info" %}
You may notice that the settings from “Add V3 Liquidity” are automatically carried to the Zap modal. Including the deposit amount and price range settings.
{% endhint %}

#### Start Zapping <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

Finally click “Approve” and confirm in the wallet popup for token allowance.

Then, click “Preview” to bring up the final confirmation modal. Before proceeding, please kindly review all the stats and estimates shown in the final confirmations modal. Especially the impact figures and max slippage.

Finally, click “Add Liquidity” and confirm in your wallet popup.

After the tx is confirmed, you shall see your shiny new position in “My Position” page

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### More Settings <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

If you want to further customise your Zap experience. Simply click the gear icon in top right hand corner. In the settings, you may configure:

* The max slippage while zapping.
* The timeline on the transaction deadline.
* Whether to use KyberSwap’s aggregated liquidity to perform token rebalance. Toggle this off if you only want to trade in PancakeSwap Pools.
* Degen mode can be used to perform super high slippage Zaps. Not recommended for normal use cases, use it at your own risk.

{% hint style="warning" %}
Please note that the Slippage and Deadline settings are independent to the Swap and Liquidity page.
{% endhint %}

#### Zap in using duo tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Now you may Zap in your liquidity with duo tokens. This is useful when your available balance is not matching with the price settings, and the required token amount and ratio it is calling for. Simply Zap, and the ratio will be automatically rebalanced.

#### Zap in using many tokens

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Yes it works just like a dust token collector. It is suitable for cleaning up small balances in your wallet, and put them into a position to start earning from trading fees.&#x20;

