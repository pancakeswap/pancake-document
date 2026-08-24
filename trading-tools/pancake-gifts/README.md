# 🎁 Pancake Gifts

### 🎯 What is Pancake Gifts?

**Pancake Gifts** lets anyone send tokens — including optional gas — to friends, users, or communities using just a **link** or **QR code**. It’s a simple, secure, and gasless experience for the recipient.

It’s built to make onboarding into crypto as easy as sending a message — no wallet funding, no bridging, no upfront fees.

### 🤝 Why We Built Pancake Gifts

Onboarding to Web3 is still full of friction. New users often give up before they even get started due to:

* **No gas in wallet** → Can’t perform any onchain action
* **No funds on the correct chain** → Bridging is required before using dApps
* **Need to buy crypto just to get started** → Requires CEX signup or fiat on-ramp

Pancake Gifts eliminates these blockers by:

* ✅ **Including native gas tokens** in the gift so recipients can interact instantly
* ✅ **Sponsoring the gas fee upfront** (sender pays a small fee)
* ✅ **Enabling claim via a simple link or QR** — no complex onboarding



It’s a tool for both:

* New users getting started onchain
* Web3-native communities looking to **boost adoption, reward users, or run campaigns** in a friendlier way

***

### ⚙️ Feature Summary

| Feature                | Description                                                      |
| ---------------------- | ---------------------------------------------------------------- |
| **Chain Support**      | BNB Chain (initial launch)                                       |
| **Gift Code Types**    | Link **or** QR Code                                              |
| **One-time Use**       | Each code can only be claimed once                               |
| **Token Support**      | Max 2 tokens: 1 BEP-20 (required), 1 native gas token (optional) |
| **Custom Amounts**     | Set different values per token                                   |
| **Gift Claim Gas Fee** | Sender prepays gas (\~$0.05 in BNB)                              |
| **Gift History**       | Users can view all sent gifts, claim status, expiry              |
| **Security Checks**    | Fee-on-transfer and complex logic tokens are disallowed          |

### 🚫 Limitations

1. **One gift per code** — Mass gifting is not yet supported.
2. **Gifts cannot be reinstated** — Once cancelled or expired, they cannot be reused.
3. **Unsupported tokens are blocked** — Tokens with transfer fees or special logic will show an error on creation.
4. **Unsuccessful claims are retried** — Backend retries a few times. If still failed, the gift is marked **unclaimable** and must be cancelled manually to retrieve funds.
5. **Gift must be claimed on the same chain** — e.g. ETH gift must be claimed on Ethereum. Cross-chain claiming is not supported yet.

***

### 🕒 Cancel & Expiry Logic

Gifts follow a defined lifecycle based on status and time:

#### Manual Cancel

* The **creator** can cancel any gift that is still **unclaimed** and **within the expiry window**.
* Tokens (minus the initial Gift Claim Gas Fee) will be returned to the sender.
* Cancelled gifts **cannot** be reactivated or reused.

#### Auto Expiry

* Gifts **automatically expire** after a user-defined period (default: 7 days).
* Unclaimed tokens will be **auto-returned** to the sender’s wallet.
* Expired gifts are also non-reusable.

***

### 🔄 Gift Statuses & What They Mean

| Status          | Description                                                              |
| --------------- | ------------------------------------------------------------------------ |
| **Pending**     | Gift has been created and is awaiting claim                              |
| **Claimed**     | Gift was successfully claimed by a recipient                             |
| **Cancelled**   | Gift was manually cancelled by the sender                                |
| **Expired**     | Gift passed the expiry time without being claimed                        |
| **Unclaimable** | Number of retries exceeded; gift needs to be cancelled to retrieve funds |

***

### ⚠️ Error Handling & Edge Cases

1. **Unsupported Token**
   * Gift creation is blocked for tokens with transfer fees or special logic.
2. **Gas Mismatch**
   * If **actual claim gas cost ≥** the sender’s prepaid fee, the claim fails automatically to prevent overuse. This will be retried once gas fee levels are within range.
3. **Failed Claim Attempts**
   * Retries will be attempted upon first unsuccessful claim.
   * If still unsuccessful:
     * Recipient sees “Unclaimable”
     * Sender must manually cancel the gift to retrieve funds and the recipient will have to request a new gift code.
