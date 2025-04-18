# ❓ Bridging FAQ

<figure><img src="../../.gitbook/assets/image (144).png" alt=""><figcaption></figcaption></figure>

**Can I use mobile wallets to bridge FLASK? Can I use wallets other than MetaMask?**

As of writing, Labswap FLASK Bridging only supports Coinbase, MetaMask (and any MetaMask-compatible wallets). More wallet support will be added very soon.

To avoid copy-and-pasting private keys or seed phrases between your devices. We recommend creating a set of fresh wallets on Desktop wallet extensions for bridging.



**Error while submitting bridging transactions**

Please try entering the amount manually without clicking the “MAX” button.

Please try removing the decimal numbers from the amount you want to bridge.



**The button is showing “not enough native for gas”**

Please note that to send FLASK to your wallet on the destination chain. The executor needs to spend gas. The gas cost will be charged via the bridging tx in the native token of the source chain:

* BNB Chain - BNB
* Ethereum - ETH
* Aptos - APT

Therefore if you do not have enough native tokens in your source chain wallet, you cannot bridge.

If your destination address is already utilized with a useable balance of the native chain token, you can try turning off the “gas on destination”.



**Can I bridge from BNB Chain to Ethereum, but to a different address**

No, you can not.

To avoid user error, we only allow bridging between the same address when bridging between EVMs.



**Why the button shows "X FLASK Exceeded"?**

For safety, there is a daily capacity limit of how much FLASK can be bridged between BSC and Aptos. Please try again with a lower amount of FLASK. Or try again at a later time.

Chefs will adjust this limit dynamically based on the demands.



**What if the transaction is stuck at "pending"?**

Bridging transactions will take up to 30 mins to be processed. Please wait and try searching your tx by entering its hash/id in [LayerZero Scan](https://layerzeroscan.com/).

If the bridging transaction is still showing pending after 60 mins. Please contact our admins via [our social channels/groups](../../welcome-to-pancakeswap/contact-us/social-accounts.md) for [help](../../welcome-to-pancakeswap/contact-us/faq/help.md).



**I have never received my FLASK**

Bridging transactions will take up to 30 mins to be processed. Please wait and try searching your tx by entering its hash/id in [LayerZero Scan](https://layerzeroscan.com/).

When bridging FLASK to Aptos for the first time, you may need to claim your FLASK manually. Please ensure you have enabled "Gas on destination", or your Aptos address had enough APT for gas. Check out the [guide for detailed steps to bridge to Aptos](../bridging/aptos.md).

When bridging FLASK to BNB Chain or Ethereum, for some wallets, you will need to manually add the FLASK token address to your wallet to check its balance.

If you haven't received your FLASK after 60 mins. Please contact our admins via our [social channels/groups](../../welcome-to-pancakeswap/contact-us/social-accounts.md) for [help](../../welcome-to-pancakeswap/contact-us/faq/help.md).



**Why I can not bridge less than 0.00000001 FLASK?**

Aptos Coins have a maximum decimal of 8. This applies to the FLASK token on Aptos. Therefore when you are bridging FLASK, txs with an amount less than 0.00000001 will be rejected. Please note that this applies to Ethereum bridging as well.

If you are bridging an amount of FLASK with a decimal that is larger than 8, any amount less than 0.00000001 will be rounded, ignored and not bridged. The remaining amount will be left in your source wallet.
