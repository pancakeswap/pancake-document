# Wormhole Bridge FAQ

### Q: How can i check my transaction? <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormhole explorer

On the bridge status page. You can see a link which will take you to your transaction on the Wormhole Explorer. When your source chain transaction has been completed but not yet been verified by Wormhole your transaction status will look like this:

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KyaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

The find redeem option is an alternative method that you can follow to complete your destination chain transaction. You can use this method in the case that the wormhole bridge stalls or fails to update your bridge transactions’s status. To redeem your transaction first click the redeem button

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

It will then display this option to resume your transaction. Click this to be navigated to the forum (link in the next question) where you can complete your redemption transaction. \


### Q: I have sent tokens to \<chain> - my tokens did not arrive in my target wallet, but have left my origin wallet. What do I do?[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

You either a) need to redeem them, or, if redeeming was already successful, b) add them to your wallet:

**a) Redeeming:**

* Go to [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem)
* You need to enter your source chain and the corresponding transaction id (which you can find in your wallet, or with your address in the blockchains explorer)

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* Click Recover
* Click Redeem and accept the wallet approval

**b) Add them to your wallet:**

**Metamask:**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* In the Metamask assets tab, click import tokens
* The contract address can be found in the relevant block explorer transaction and clicking the token name. When you click the token name, it will open a new window and the contract address is on the right-hand side in the profile summary.
* You’ll also need a symbol - this can be anything you want to recognize the token as.
* Click add custom token

See the video tutorial - How to add a token into your Metamask wallet [here.](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)

### I bridged X token but cannot swap it now. No DEX has liquid markets,[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

You bridged a token, which has no liquidity on the target chain. You will need to use Portal bridge to bridge this one back. You can do this by pasting the token contract address (which you can find in your wallet or with your address in the blockchains explorer) into the Portal “select a token” search field.

You can find a comprehensive overview of liquid markets [here](https://portalbridge.com/docs/faqs/liquid-markets).

#### How can I redeem my tokens on the target chain?[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

If you've accidentally refreshed the page during the transfer process or did not redeem your tokens, you can follow the tutorial [here](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow).
