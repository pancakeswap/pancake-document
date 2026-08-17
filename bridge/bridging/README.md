---
description: Bridge CAKE between Ethereum, BNB Chain, Aptos, and many more
---

# 🌉 Bridging

<figure><img src="../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Bridging to/from EVMs (New site): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Bridging to/from Aptos (V1 Bridge): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## What is bridging in crypto?

* Bridging in crypto refers to the process of transferring assets between different blockchain networks.
* It enhances interoperability, allowing for data and asset transfers across various networks.

\
Here are some reasons you may want to bridge:

* Buy different cryptocurrency tokens
* Mint an NFT only available on a specific network
* Save money with cheaper transactions
* Use a dapp only available on another network

***

## CAKE, a multichain token

With our multichain expansion and deployment, CAKE is now a multichain token that is native to BNB Chain, but also available across Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB, and Aptos.

CAKE on any of the other chains is equal to CAKE on BNB Smart Chain. It can always be bridged between these chains at a 1:1 ratio and without any fee in CAKE.

**Please note that there is only one CAKE.** There are no different versions of CAKE on different chains. The total supply of CAKE across all blockchains is capped at 400M, as outlined in this [vote proposal](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5).

***

## What is the PancakeSwap Bridge?

The PancakeSwap Bridge is a convenient, in-app tool that allows you to move assets between different blockchains directly through the PancakeSwap interface. Instead of visiting external bridge sites, you can bridge supported tokens between chains like BNB Chain, Ethereum, Base, Arbitrum, and more—all from one place.

The PancakeSwap Bridge is powered by trusted third-party providers and works as an **aggregator**—selecting the best route based on price, speed, and reliability.

To learn how to bridge CAKE, check out the tutorials and FAQ in the following sections.

***

## 🔗 How It Works

### Bridging via Aggregators

The PancakeSwap Bridge acts as a smart layer over trusted third-party bridge protocols. When you initiate a bridge transfer, PancakeSwap:

* Checks multiple integrated bridges for optimal routes
* Sends your transaction to the selected provider

Bridging is non-custodial—your assets do not touch PancakeSwap custody. Transfers are handled directly by the bridge providers.

### Supported Bridge Providers

We currently integrate with:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Note: Each provider has different bridging mechanics, supported chains, fees, and limits.

***

### Supported Chains and Tokens

#### Chains Currently Supported

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Solana
* Aptos (V1 site)

#### Tokens Available for Bridging

Available tokens vary by chain and route. Common supported tokens include (but are not limited to):

* CAKE
* USDT
* USDC
* ETH

***

#### Limitations & Exclusions

Some tokens may not be supported due to bridge limitations or liquidity constraints. These have been filtered out for the best user experience. For example:

**For cBridge:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**For deBridge:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_The above are examples. The actual available tokens per chain are shown directly in the Bridge UI._

***

### 💸 Fees and Costs

#### Bridge Fees

* Charged by the underlying bridge provider
* Typically includes a small fee per transfer
* Clearly shown before you confirm your bridge

***

#### Gas Costs

* You pay gas fees on the **source chain** to initiate the transaction
* Some providers may also require gas on the **destination chain**
* **Tip:** Always keep native tokens (e.g., ETH, BNB) on both sides of the bridge

***

#### Minimum Amounts & Restrictions

Some bridge routes enforce:

* **Minimum/maximum bridge amounts** (e.g., minimum of 10 USDC)
* **Supported token decimals or formats** (e.g., only ERC-20 tokens)

The UI will automatically detect and display invalid transfers.

***

### ⏳ Transaction Times & Tracking

#### How Long Does Bridging Take?

Bridge transfers typically complete within a few **minutes**, depending on:

* Source and destination chains
* Network congestion
* Bridge provider efficiency

#### Tracking Your Transfer

Once submitted, you can view the transaction status through provider-specific explorers:

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

If a transaction is stuck for a long time, check the relevant explorer or reach out to our admins via [social channels](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) for [help](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help).

***

### 🧠 Tips Before You Bridge

* **Keep gas tokens on both chains** (e.g., ETH + BNB)
* **Start small** if it’s your first time bridging
* Avoid bridging during periods of high chain activity (can result in higher gas fees)
* Confirm token compatibility on both chains
* Always double-check source and destination networks

***

### Additional: CAKE Omni-chain Fungible Token (OFT) Addresses

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))

