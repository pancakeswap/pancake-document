# ❓ Bridging FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Before Bridging

1.  **Can I use mobile wallets or wallets other than MetaMask to bridge CAKE?**

    Currently, PancakeSwap CAKE Bridging supports Coinbase Wallet, MetaMask, and MetaMask-compatible wallets. More wallet support is coming soon.

    _Tip:_ To avoid risky copy-pasting of private keys or seed phrases, we recommend creating new wallets via desktop wallet extensions for bridging.
2.  **Why is a route or token unavailable?**

    Some routes depend on bridge capacity, token support, or liquidity. Please check back later or try a different provider. Available tokens per chain are shown directly in the Bridge UI.
3.  **I get an error submitting the bridging transaction.**

    Try entering the amount manually instead of using the “MAX” button, and remove decimals from the amount if necessary.
4.  **Why does my bridging quote show “Insufficient X to cover native fee”**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    Bridging requires gas fees paid in the native token of the source chain, for example:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    Ensure you have enough native tokens in your source wallet to cover fees to complete the transaction.
5.  **Why does the button show “X CAKE Exceeded”?**

    There is a daily capacity limit for bridging CAKE between BSC and Aptos to ensure safety. Try a smaller amount or wait and try again later. Limits are dynamically adjusted by Chefs based on demand.
6.  **Why can’t I find a specific token?**

    The token may not be supported on your chosen route or may lack liquidity. Try another chain or a different amount.
7.  **Can I bridge from BNB Chain to Ethereum but to a different address?**

    No, for safety reasons, bridging only works between the same address on EVM chains.
8.  **Why can’t I bridge less than 0.00000001 CAKE?**

    Aptos tokens, including CAKE on Aptos, have a max of 8 decimal places. Transactions below 0.00000001 will be rejected or rounded down. This applies to Ethereum bridging as well. Any leftover amount remains in your source wallet.

***

## After Bridging

1.  **Can I cancel a bridge transfer after confirming?**

    No, once started, the bridge transaction is handled by the provider and can’t be canceled. To reverse, bridge the assets back via a new transaction.
2.  **What if my transaction is stuck “pending”?**

    Bridging can take up to 30 minutes. Check your transaction status by searching its hash on the respective bridge provider’s explorer:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    If pending after 60 minutes, please contact our admins via [social channels](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
3. **I haven’t received my CAKE. What should I do?**
   * When bridging CAKE to Aptos for the first time, you may need to **manually claim** your CAKE. Ensure your Aptos wallet has enough APT for gas. See [Aptos bridging guide](https://docs.pancakeswap.finance/bridge/bridging/aptos) and [Aptos explanation](https://theaptosbridge.com/faq#registering-claiming-assets).
   * When bridging to BNB Chain or Ethereum, some wallets require you to manually add CAKE’s token address to view your balance. As an example, follow this [MetaMask guide](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) - other wallets should have similar flows.
   * If you still don’t see your CAKE after 60 minutes, contact our admins via [social channels](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
