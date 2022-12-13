# Aptos FAQ

<figure><img src="../.gitbook/assets/Aptos-faq-header.png" alt=""><figcaption></figcaption></figure>

This FAQ page answers some of the more commonly asked questions from the PancakeSwap community about our Aptos Deployment.

## General

### How to bridge from BSC (Binance Smart Chain) to Aptos?

Check out [our bridging guide](aptos-coin-guide.md) for various bridging solutions.

If you want to bridge CAKE token, check out our [CAKE bridging guide](cake-bridging-guide.md).

### Which wallet I can use for Aptos Chain?

Check out [our wallet guide](wallet-guide.md) to download and set up your wallet for Aptos.

### Showing "Price Impact Too High" when swapping coins

This is likely due to bad network connections to blockchain nodes. Refresh the page, and check your network connection.

If the error persists, it means the pair of coins you are trying to swap has insufficient liquidity for the amount you are trying to swap. The liquidity for major coins will slowly and steadily be improved over time, and the liquidity issue will likely be solved when our Aptos Farms are deployed. (SOON!)

### I couldn't find the coin I wanted to swap

The default list on Aptos Swap only shows coins from well-known projects with a sufficient amount of liquidity.

If you want to swap other coins that are not on the default list, import them using their coin address.

### Why I can’t trade CAKE on Aptos Swap?

_updated on 2022-12-13_

CAKE token/coin is now live on Aptos. Check out our [CAKE bridging guide](cake-bridging-guide.md) to learn more about bridging CAKE tokens between Aptos and BNB Smart Chain.

### Do I need to stake CAKE on Aptos to participate in Aptos IFOs?

PancakeSwap IFO has not yet been deployed on Aptos. (SOON!) Keep staking your CAKE, and stay tuned for more news.

## CAKE Bridging

### Why do the pop-up and the progress bar show a huge waiting time?

Please note that for assets other than CAKE, outbound transfers from Aptos are subject to 1M block confirmations, estimated to last \~4 days. Timing may change due to fluctuations in blocktimes.

**For CAKE bridging, the waiting time should be around 3-10 mins.**

### Can I use mobile wallets to bridge CAKE? Can I use wallets other than MetaMask?

As of writing, PancakeSwap Aptos Bridge only supports MetaMask (and any MetaMask-compatible wallets) on the Desktop browser. More wallet support will be added very soon.

To avoid copy-and-pasting private keys or seed phrases between your devices. We recommend creating a set of fresh wallets on Desktop wallet extensions for bridging.

### Why the button shows "X CAKE Exceeded"?

For safety, there is a daily capacity limit of how much CAKE can be bridged between BSC and Aptos. Please try again with a lower amount of CAKE. Or try again at a later time.

Chefs will adjust this limit dynamically based on the demands.

### What if the transaction is stuck at "pending"?&#x20;

Bridging transactions will take up to 30 mins to be processed. Please wait and try searching your tx by entering its hash/id in [LayerZero Scan](https://layerzeroscan.com/).

If the bridging transaction is still showing pending after 60 mins. Please contact our admins via our [social channels/groups](../contact-us/telegram.md) for [help](../help/).

Please note that for assets other than CAKE, outbound transfers from Aptos are subject to 1M block confirmations, estimated to last \~4 days. Timing may change due to fluctuations in blocktimes.

### I have never received my CAKE

Bridging transactions will take up to 30 mins to be processed. Please wait and try searching your tx by entering its hash/id in [LayerZero Scan](https://layerzeroscan.com/).

When bridging CAKE to Aptos for the first time, you must claim your CAKE manually. Please make sure you have enabled "Gas on destination", or your Aptos address had enough APT for gas. Check out the [guide](cake-bridging-guide.md) for detailed steps to bridge.

When bridging CAKE to BNB Smart Chain, for some wallets, you will need to manually add the CAKE token address to your wallet to check its balance.

If you haven't received your CAKE after 60 mins. Please contact our admins via our [social channels/groups](../contact-us/telegram.md) for [help](../help/).

### Why I can not bridge less than 0.00000001 CAKE?

Aptos Coins have a maximum decimal of 8. This applies to the CAKE token on Aptos. So when you are bridging CAKE to Aptos, txs with an amount less than 0.00000001 will be rejected.&#x20;

If you are bridging an amount of CAKE with a decimal that is larger than 8, any amount less than 0.00000001 will be rounded, ignored and not bridged. The remaining amount will be left in your BNB Smart Chain wallet.

