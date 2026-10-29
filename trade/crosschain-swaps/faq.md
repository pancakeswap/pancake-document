# ❓ FAQ

### 1. How does slippage tolerance work for Crosschain swaps?

For Crosschain swaps, your selected slippage tolerance percentage is applied independently to swaps on both the source and destination chains.

**Example:**

* Swap BNB on BNB Chain to ARB on Arbitrum
* Slippage tolerance set to 1%
* The route could be:
  1. Swap BNB to USDC on BNB Chain
  2. Bridge USDC from BNB Chain to Arbitrum via Across
  3. Swap USDC to ARB on Arbitrum
* In this case, the 1% slippage tolerance applies separately to:
  * The swap on BNB Chain
  * The swap on Arbitrum

This ensures you’re protected from excessive price movements on both legs of the transaction while keeping the bridging process itself unaffected by slippage settings.

### 2. What happens if my transaction fails?

If your Crosschain swap encounters a failure at any stage, here’s how it’s handled:

1.  **Swap/Transaction Failure on Source Chain**

    ➝ You’ll instantly receive your original token back on the source chain.
2.  **Bridge Transaction Failure**

    ➝ Across will process a refund within 90 minutes to 2 hours, and you’ll receive the bridged asset back on the source chain. While Relay processes the refund within a minute in such scenarios between SOL <> EVM.
3.  **Swap Failure on Destination Chain**

    ➝ You’ll receive the bridged asset on the destination chain, without the final swap to your target token.

{% hint style="info" %}
**Note:** You can always check the status of your transactions through the transaction history tab under wallet connect UI.
{% endhint %}

### 3. Are my Crosschain swaps MEV protected?

MEV Guard is only supported on the BNB Chain when swaps are initiated directly from a connected wallet with MEV Guard enabled.

* If your Crosschain swap involves a swap on BNB Chain as the source chain, and you have MEV Guard enabled, that swap will be MEV protected.
* If BNB Chain is the destination chain, the swap is executed by the bridging relayer/system and will not be MEV protected, since it’s not initiated by your connected wallet.

{% hint style="info" %}
**Note:** Other chains like Arbitrum and Base currently do not support MEV Guard protection on PancakeSwap.
{% endhint %}

### 4. Can I swap stablecoins between chains?

Yes — you can swap and bridge stablecoins like USDC, USDT, and DAI directly between any supported chains.

You have two options:

1.  **Direct Bridge:**

    Bridge supported stablecoins (like USDC, USDT, etc) directly from one chain to another.
2.  **Swap to Other Tokens:**

    You can also swap a stablecoin to any other token supported on the destination chain using PancakeSwap’s liquidity pools — either before or after bridging.

{% hint style="info" %}
**Note:** Supported stablecoins for direct bridging may vary by chain.
{% endhint %}

### 5. Will my swaps use PCSX?

No — PCSX is not supported for servicing Crosschain swaps.

Crosschain swaps on PancakeSwap are exclusively routed through:

* **PancakeSwap’s liquidity pools** (v2, v3, Infinity, StableSwap) for on-chain swaps, and
* **Across & Relay protocols** for bridging assets between chains.

PCSX cannot be used to facilitate or route any part of a Crosschain swap transaction.

### 6. Is there a minimum or maximum limit on swap amount?

Yes — both minimum and maximum limits apply to Crosschain transactions.

* **Maximum Limit:**\
  Depends on the available bridge liquidity for the selected token and chain. This value can fluctuate in real-time based on network and liquidity conditions.
* **Minimum Limit:**\
  Set to ensure it’s economically viable for relayers to process the bridge transaction.

{% hint style="info" %}
**Note:** The exact min and max limits vary by bridge token. If your transaction amount is outside the allowed range, the interface will show a clear error message and prompt you to adjust the amount.
{% endhint %}
