# FAQ

<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

**Can I use mobile wallets to bridge CAKE? Can I use wallets other than MetaMask?**

As of writing, PancakeSwap CAKE Bridging only supports Coinbase, MetaMask (and any MetaMask-compatible wallets). More wallet support will be added very soon.

To avoid copy-and-pasting private keys or seed phrases between your devices. We recommend creating a set of fresh wallets on Desktop wallet extensions for bridging.



**Error while submitting bridging transactions**

Please try entering the amount manually without clicking the “MAX” button.

Please try removing the decimal numbers from the amount you want to bridge.



**The button is showing “not enough native for gas”**

Please note that to send CAKE to your wallet on the destination chain. The executor needs to spend gas. The gas cost will be charged via the bridging tx in the native token of the source chain:

* BNB Chain - BNB
* Ethereum - ETH
* Aptos - APT

Therefore if you do not have enough native tokens in your source chain wallet, you cannot bridge.

If your destination address is already utilized with a useable balance of the native chain token, you can try turning off the “gas on destination”.



**Can I bridge from BNB Chain to Ethereum, but to a different address**

No, you can not.

To avoid user error, we only allow bridging between the same address when bridging between EVMs.



**Why the button shows "X CAKE Exceeded"?**

For safety, there is a daily capacity limit of how much CAKE can be bridged between BSC and Aptos. Please try again with a lower amount of CAKE. Or try again at a later time.

Chefs will adjust this limit dynamically based on the demands.



**What if the transaction is stuck at "pending"?**

Bridging transactions will take up to 30 mins to be processed. Please wait and try searching your tx by entering its hash/id in [LayerZero Scan](https://layerzeroscan.com/).

If the bridging transaction is still showing pending after 60 mins. Please contact our admins via [our social channels/groups](../../contact-us/telegram.md) for [help](../../readme/help/).



**I have never received my CAKE**

Bridging transactions will take up to 30 mins to be processed. Please wait and try searching your tx by entering its hash/id in [LayerZero Scan](https://layerzeroscan.com/).

When bridging CAKE to Aptos for the first time, you may need to claim your CAKE manually. Please ensure you have enabled "Gas on destination", or your Aptos address had enough APT for gas. Check out the [guide for detailed steps to bridge to Aptos](aptos.md).

When bridging CAKE to BNB Chain or Ethereum, for some wallets, you will need to manually add the CAKE token address to your wallet to check its balance.

If you haven't received your CAKE after 60 mins. Please contact our admins via our [social channels/groups](../../contact-us/telegram.md) for [help](../../readme/help/).



**Why I can not bridge less than 0.00000001 CAKE?**

Aptos Coins have a maximum decimal of 8. This applies to the CAKE token on Aptos. Therefore when you are bridging CAKE, txs with an amount less than 0.00000001 will be rejected. Please note that this applies to Ethereum bridging as well.

If you are bridging an amount of CAKE with a decimal that is larger than 8, any amount less than 0.00000001 will be rounded, ignored and not bridged. The remaining amount will be left in your source wallet.
