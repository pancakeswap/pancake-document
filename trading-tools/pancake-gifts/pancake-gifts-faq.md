# Pancake Gifts FAQ

This FAQ covers how Pancake Gifts work behind the scenes, what to expect in different scenarios, and why certain design choices were made.

***

## 1. 🔐 Gift Code Behavior & Access

### **1.1 Why isn’t the gift code stored?**

We **intentionally do not store** the gift code in:

* Frontend local storage
* Backend databases

This protects:

* User privacy
* Security against device compromise
* Accidental or malicious gift claims

### **1.2 Can I regenerate or retrieve the gift code later?**

No. The gift code:

* Is shown **only once** during creation
* Is embedded in the **link** or **QR code** generated
* Will **not be displayed again** in the UI or history

{% hint style="warning" %}
If the code is lost and you didn’t save the link or QR, the gift cannot be claimed manually. Instead, to retrieve your gift amount, you may manually cancel it.
{% endhint %}

### **1.3 Will the gift code still be embedded in the share link or QR?**

Yes:

* Share link includes the gift code (e.g. `pancakeswap.finance/gift#code=xxxx`)
* QR code also embeds the gift code, but **cannot be regenerated later.**&#x20;

{% hint style="success" %}
**Pro Tip:** Download the image once it's generated
{% endhint %}

* Manual claims require the actual gift code — no fallback if the link/QR is lost

## 2. 🎁 Gift Status & Expiry

### **2.1 Can I view whether a gift has been claimed, cancelled, or expired?**

Yes. The **Gift History** section shows:

* Status: Pending / Claimed / Cancelled / Expired / Unclaimable
* Gift details (token, amount, type, chain, timestamps)

### **2.2 What happens when a gift expires?**

If a gift is not claimed within the default **7-day window**:

* The **entire gift amount is refunded** to the creator’s wallet
* The fixed **claim gas fee (\~$0.05) is not returned**

## 3. 🧠 Claim Logic & Limitations

### **3.1 Can users claim a gift on a different chain from the one it was created on?**

No. A gift is **chain-bound**:

* A gift created on **BSC** must be claimed on **BSC**
* Cross-chain gifting is not currently supported

## 4. ⛽ Gas Fees & Design

### **4.1 How is the fixed gas amount for gift creation decided?**

We set a flat gas price based on current BNB chain conditions (\~5 times current recommended Gas amount).

This buffer:

* Protects against sudden gas spikes
* Ensures gifts remain claimable under normal volatility

\
Example

* **Current recommended: 0.1 Gwei** (see: [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Therefore, Fixed gas claim fee= 0.1 Gwei x 5 = 0.5 Gwei**



