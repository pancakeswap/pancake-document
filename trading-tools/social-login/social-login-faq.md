# Social Login FAQ

{% hint style="info" %}
For more information view: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 General Overview

**1. What is PancakeSwap’s social login and why should I use it?**

Social login lets you access PancakeSwap using your **Google**, **X (Twitter)**, **Discord**, or **Telegram** account — no wallet extension or seed phrase needed. A self-custodial wallet is created behind the scenes, so you can try DeFi instantly, even with small amounts. This lowers the barrier to entry, especially in time-sensitive moments.

**2. What chains does social login support?**

Your social login wallet works across all chains currently supported by PancakeSwap:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

All wallets are **EVM-compatible** and can be used across these networks natively through PancakeSwap. If you’d like to see support for other chains (including non-EVM), let us know!

**3. Where can I use the social login wallet?**

You can use it directly in any desktop or mobile **browser** through the PancakeSwap web app. It is **not compatible** with external wallet apps or dApp browsers.



### 🛠️ Wallet Setup & Usage

**4. How is the wallet created and secured?**

Your wallet is created automatically upon login and secured using a **2-of-2 key share system**. Both shares are required to reconstruct the key and generate a signature.

For more information on share encryption view:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. How many wallets can I create?**

You get **one wallet per social account per dApp**. For example, if you use your Google login on another app that also uses Privy, it will create a separate wallet.



### 🔐 Security & Privacy

**6. Can someone access my wallet if they steal my device?**

No. Even if someone gains access to your device, they would still need both your **social login** and (if set) your **recovery password**.

**7. What data is stored by PancakeSwap or Privy?**

* PancakeSwap **does not store** any wallet-related key shares.
* Privy stores the **encrypted Auth Share and Recovery Share (if recovery flow is not set)**.

> If you haven’t completed the recovery setup, your Recovery Share remains stored with Privy by default. For more info visit: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 Recovery & Session Management

**8. Can I use the same wallet on a different device or browser?**

Yes! Simply log in with the same social account. If it's a new device, you'll go through the recovery process using your recovery password (if set up).

**9. What happens if I switch devices?**

You’ll be asked to re-login with your social account and go through the recovery flow (password setup). If you haven’t set up a recovery password, social account login is sufficient.

**10. What if I lose access to both my social login and recovery method?**

If you lose access to both your social account and your recovery method, **your wallet cannot be recovered**. There’s no seed phrase fallback, and private key export is not currently supported.

> ⚠️ Remember: Exporting your private key, if enabled in the future, would grant full control of your wallet to anyone who has it — treat it with extreme caution.

**11. How long do active sessions last?**

Sessions last for 30 **days**. After that, you’ll be prompted to **log in again** and (if needed) re-enter your recovery credentials. During an active session, you can transact without needing to manually approve each action.



### ⚙️ Compatibility & Limitations

**12. Can I export or import wallets?**

* **Export**: Not supported by default, for security reasons. This may change in future updates.
* **Import**: Not supported. You cannot import external wallets like MetaMask or Phantom.

**13. Can I connect this wallet to other dApps using WalletConnect?**

Not at this time. The embedded wallet is **limited to PancakeSwap only**. If you're interested in using it more broadly, let us know — future expansions are possible.



### 🚀 Advanced Features

**14. Does the social login wallet support Account Abstraction?**

Yes. It supports **Account Abstraction features** such as transaction batching and **gas sponsorship** through integrations like Biconomy etc.

**15. How are signless transactions enabled?**

* After login, your session is active for up to 30 **days**. During this time, PancakeSwap can request Privy to sign transactions on your behalf using your session credentials.&#x20;
* You won’t see a wallet popup for each action — everything is handled in the background. After 30 days, you’ll need to re-login to continue using this signless experience.
