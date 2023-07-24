---
description: Bridge CAKE between Aptos and EVM chains
---

# Between EVM and Aptos

<figure><img src="../../.gitbook/assets/image (37) (3).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The following guide uses BNB Chain as an example of an EVM chain. The same process can be applied to Ethereum.
{% endhint %}

## Bridge CAKE from BNB Smart Chain to Aptos

1 - Make sure your wallet supports both BNB Smart Chain and Aptos Mainnet. Or you have both of the wallets installed in your browser.&#x20;

Then open the [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)



2 - First, we need to connect our BNB Smart Chain wallet.&#x20;

Click "Connect" and choose the wallet you prefer under the "EVM" section. Then confirm and approve in your wallet popup. (As of writing, only MetaMask is supported. Support for more wallets is coming soon)

![](<../../.gitbook/assets/bridging-wallet-connect-modal (1).png>)



3 - Then, we need to connect our Aptos wallet.

In the wallet connect modal, choose the wallet you prefer under the "Aptos" section. Then confirm and approve in your wallet popup.

![](<../../.gitbook/assets/bridging-default-state (1).png>)



4 - Click the "v" in the upper token selection field and choose "CAKE".

![](../../.gitbook/assets/upper-field.png)



5 - Input the number of CAKE you want to bridge to Aptos.

![](../../.gitbook/assets/bridging-amount-entered.png)



6 - If your Aptos wallet is freshly created and doesn't have any APT (Aptos Coin) balance. We recommend keeping the "gas on destination" option at its default. The bridge will deposit a small amount of APT to your wallet, not only to help you kickstart your journey on Aptos, but you will also need APT for gas to register and claim your bridged CAKE.

Altering this option might cause bridging to fail.

![](../../.gitbook/assets/bridging-gas-on-dest.png)



7 - Click "Transfer" to initiate the bridging transaction and confirm via the wallet confirmation pop up.

Please note that depending on the condition on your BNB Smart Chain wallet and Aptos wallet. You may need to approve **multiple** wallet confirmations. For example if you are bridging CAKE to Aptos for the first time, you will need to:

* Approve CAKE spending on the bridging contract (coming from your BNB Smart Chain wallet)
* Register CAKE (coming from your Aptos wallet)

For more detail please check out [this breakdown](aptos.md#bridging-cake-to-aptos-for-the-first-time).



8 - Sit back and relax. It should only take a few minutes. Once the bridging is complete, CAKE will be deposited into your Aptos wallet. You can track the progress by the progress bar.

![](../../.gitbook/assets/bridging-complete-half.png)



## Bridging CAKE to Aptos for the First Time

Bridging CAKE to Aptos wallets requires registration and claim transactions. This is done to enhance user security and is unique to Aptos.&#x20;

### If you already have APT (Aptos Coin) in your wallet.

In this scenario, you will be prompted to register CAKE on your Aptos wallet if it has not already been registered. You will not be required to submit an additional claim transaction in this scenario.&#x20;

### If you do not have APT (Aptos Coin) in your wallet.

You will only have to claim your CAKE once the transaction is finished. You will receive APT tokens (for gas fees) on the destination wallet to pay for the cost of claiming their assets. This APT is paid for by your source wallet and is transferred through to the destination.

Remember, these registration and claim requirements only apply when you interact with a token for the first time. Follow-up transfers of the same token will not require these transactions.

## Bridge CAKE from Aptos to BNB Smart Chain

1 - Make sure your wallet supports both BNB Smart Chain and Aptos Mainnet. Or you have both of the wallets installed in your browser.&#x20;

Then open the [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)



2 - First, we need to connect our BNB Smart Chain wallet.&#x20;

Click "Connect" and choose the wallet you prefer under the "EVM" section. Then confirm and approve in your wallet popup. (As of writing, only MetaMask is supported. Support for more wallets is coming soon)

![](../../.gitbook/assets/bridging-wallet-connect-modal.png)



3 - Then, we need to connect our Aptos wallet.

In the wallet connect modal, choose the wallet you prefer under the "Aptos" section. Then confirm and approve in your wallet popup.

![](../../.gitbook/assets/bridging-default-state.png)



4 - Click the "v" in the upper token selection field and choose "CAKE". Then click the double arrow button in the middle of the page to flip the direction of the bridging.

Please make sure the "Aptos" network is in the upper field.

![](../../.gitbook/assets/upper-field-aptos.png)



5 - Input the number of CAKE you want to bridge to BNB Smart Chain.

![](../../.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)



6 - If your BNB Smart Chain wallet is freshly created and doesn't have any BNB (gas token) balance. We recommend keeping the "gas on destination" option at its default. The bridge will deposit a small amount of BNB into your wallet. It will help you kickstart your journey on BNB Smart Chain and explore the vivid PancakeSwap ecosystem.



7 - Click "Transfer" and approve the transactions from your wallet popup.



8 - Sit back and relax. It should only take a few minutes. Once the bridging is complete, CAKE will be deposited into your BNB Smart Chain wallet. You can track the progress by the progress bar.

