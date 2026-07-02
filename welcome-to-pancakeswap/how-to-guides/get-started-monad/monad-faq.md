# Monad FAQ

#### 1. What fee tiers are available on PancakeSwap liquidity pools?

**Supported Fee Tiers:**

* The following fee tiers are available for V3 (concentrated liquidity) pools: `0.01%, 0.05%, 0.25%, 1%`&#x20;
* For V2 pools only 0.25% fee tier pools are supported

#### 2. Can anyone create a pool?

Yes. Pool creation is permissionless, with a few exceptions:

* Only one pool can exist for a given **token pair + fee tier** combination (e.g. only one WMON <> USDC 0.05% pool can exist at one time)

#### 3. How long does it take for a newly created pool to appear?

* Pools typically appear in the pool list approximately **5 minutes** after creation.
* If it doesn't appear:
  * Use the **search bar** to locate it manually.
  * Pools may be filtered from the list due to **low TVL**.

#### 4. Why does my pool’s APR or TVL still show as zero?

This is expected right after a new pool is created:

* APR and TVL data will only populate once **at least one swap** has occurred in the pool.
* After a swap, these metrics will begin displaying within approximately **15 minutes**.

#### **5. Why do my transactions sometimes fail if my wallet has less than 10 MON?**

Monad has a rule that every account should keep a **minimum safety buffer of 10 MON**. If your balance is low and you send too many transactions too quickly, the network may **stop accepting new ones**.

#### **6. Why do the first 1–2 transactions work, but the next ones fail?**

Monad processes blocks using a slightly “behind” view of your balance. So:

* Your **first** transaction is usually fine.
* Your **second** might also go through.
* But if you send **multiple transactions within a short time**, the network thinks you might not have enough MON to pay all the gas fees.

So it **blocks** the next transaction. This is normal and part of the safety system.

#### **7. Why does it feel stricter on smart accounts (contract wallets)?**

Smart accounts follow **stricter rules**:

* They must **always** keep at least **10 MON** while running contract code.
* If your smart account is below 10 MON, the transaction can **revert immediately**, even if EOAs still work for a couple of tx.

This is why smart-account users see failures sooner.

#### **8. Does this mean I can’t use Monad with less than 10 MON?**

You _can_ still use it, especially with a normal EOA — but:

* Don’t send several transactions back-to-back.
* Wait a few blocks between transactions.
* Keep a little MON in your wallet to avoid issues.

#### **9. How do I avoid these failures?**

Simple tips:

* Keep **10 MON or more** in your wallet if possible.
* If you’re low on MON, **space out your transactions** (don’t spam them).
* Smart-account users should keep a **bit more than 10 MON**, since contract calls use extra gas.
