# Solana FAQ

### V3 Pools – Frequently Asked Questions (FAQ)

#### 1. What fee tiers are available?

**Supported Fee Tiers:**\
The following fee tiers are available for V3 (concentrated liquidity) pools:

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**Fee Distribution (applies to all fee tiers):**

* 84% to liquidity providers (LPs)
* 16% to the protocol
  * 8% is burned
  * 8% goes to the protocol treasury

#### 2. Can anyone create a pool?

Yes. Pool creation is permissionless, with a few exceptions:

* Only one pool can exist for a given **token pair + fee tier** combination (e.g. only one SOL<> USDC 0.1% pool can exist at one time)
* Only **SPL tokens** and selected **Token-2022** tokens are supported at this time.

#### 3. How long does it take for a newly created pool to appear?

* Pools typically appear in the pool list approximately **5 minutes** after creation.
* If it doesn't appear:
  * Use the **search bar** to locate it manually.
  * Pools may be filtered from the list due to **low TVL**.

#### 4. Why does my pool’s APR or TVL still show as zero?

This is expected right after a new pool is created:

* APR and TVL data will only populate once **at least one swap** has occurred in the pool.
* After a swap, these metrics will begin displaying within approximately **15 minutes**.

#### 5. How do I add a custom token to create a pool?

To add a new token:

* In the pool creation interface, open the token selector.

<figure><img src="../../../.gitbook/assets/image (410).png" alt="" width="248"><figcaption></figcaption></figure>

* Paste the token’s address into the search bar.

<figure><img src="../../../.gitbook/assets/image (411).png" alt="" width="247"><figcaption></figcaption></figure>

* Click **"Add Token"**.

<figure><img src="../../../.gitbook/assets/image (414).png" alt="" width="251"><figcaption></figcaption></figure>

* The token will now be searchable in the list.

<figure><img src="../../../.gitbook/assets/image (412).png" alt="" width="249"><figcaption></figcaption></figure>

* To manage tokens:
  * Click **"View Token List"**.
  *   Toggle different lists on or off, including the **User Added Token List**, which includes any manually added tokens.

      <figure><img src="../../../.gitbook/assets/image (413).png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Why does my first transaction on Solana seem more expensive?

Solana uses **Associated Token Accounts (ATAs)** to manage token balances for each wallet. When interacting with a token for the first time, your wallet must create an ATA, which incurs an initial one-time cost (paid in SOL).

* This ATA creation fee is required by the Solana protocol and is not specific to PancakeSwap.
* If the ATA is later closed, the **original SOL used can be refunded** back to your wallet.
