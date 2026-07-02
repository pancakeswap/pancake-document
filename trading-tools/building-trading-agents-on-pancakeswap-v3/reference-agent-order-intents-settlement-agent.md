# Reference Agent — Order/Intents Settlement Agent

> An ERC-8183 Provider agent that fulfills a single swap-intent Job at a time by routing it through PancakeSwap aggregation and delivering the target token directly to the Client.

### 0. How it maps to ERC-8183

ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation) defines a **Job** with three roles and states Open → Funded → Submitted → Terminal. BNB's **BNBAgent SDK** is the live implementation.

| Role                                                     | In this agent                                                                                                                  |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Client** (Agent-A)                                     | posts a swap intent: "swap X of token A → token B, deliver me ≥ `minOut`", escrows the input + a tip                           |
| **Provider** (Agent-B) — **this is our reference agent** | quotes via **PancakeSwap aggregation**, and if it can meet/beat `minOut`, executes the swap and delivers token B to the Client |
| **Evaluator**                                            | verifies the Client received token-B amount ≥ `minOut`; releases the tip (or refunds the Client)                               |

The deliverable is objective ("did the Client receive ≥ `minOut`?"), which is exactly why this fits ERC-8183 where the rebalancer didn't.

***

### 1. Purpose & one-line scope

> A **Provider** agent that fulfills a single swap-intent Job at a time by routing it through PancakeSwap aggregation and delivering the target token directly to the Client — and nothing else.

***

### 2. What the agent is ALLOWED to do (capability allowlist)

| # | Capability             | Surface                                                     | Notes                                                                      |
| - | ---------------------- | ----------------------------------------------------------- | -------------------------------------------------------------------------- |
| A | Discover open Jobs     | BNBAgent SDK (ERC-8183 registry)                            | Read-only; filter to swap-intent Jobs it can serve                         |
| B | Quote a route          | **PancakeSwap aggregation** (Aggregator API / Smart Router) | Read-only; best price across V3                                            |
| C | Accept a Job           | BNBAgent SDK (Funded → committed)                           | Only if its fresh quote ≥ `minOut` and tip ≥ floor                         |
| D | Execute the swap       | PancakeSwap router                                          | Input pulled from Job escrow; **output recipient = the Client**, in one tx |
| E | Submit the deliverable | BNBAgent SDK (→ Submitted)                                  | The settlement tx hash as proof                                            |
| F | Claim the tip          | ERC-8183 escrow / x402                                      | Only after the Evaluator marks the Job Terminal                            |

**Output of every settlement goes directly to the Client. The agent's only earning is the Job's tip.**

***

### 3. Hard guardrails (the gate to featuring)

| Guardrail                              | Rule                                                                                                                                                              |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Never accept what it can't fulfill** | Accept a Job only if a _fresh_ quote clears `minOut`. If it can't, leave the Job Funded for another Provider.                                                     |
| **Requote at execution**               | Re-quote immediately before settling; abort if the route no longer clears `minOut` (no stale quotes).                                                             |
| **Atomic settlement**                  | Pull-from-escrow → swap → deliver to Client in **one transaction**, output recipient = Client. The agent must never hold the Client's funds across a failed step. |
| **Slippage**                           | Execution slippage bounded; delivered amount must still be ≥ `minOut` after slippage, or the tx reverts. Never `amountOutMin = 0`.                                |
| **Deadline**                           | Short deadline on the settlement tx (≤ 5 min); respect the Job's own deadline.                                                                                    |
| **Min tip / max value**                | Don't accept Jobs below a tip floor or above a per-Job value cap.                                                                                                 |
| **Token safelist**                     | Only serve Jobs whose tokens are on the PancakeSwap token list (anti-honeypot / fake-token).                                                                      |
| **Single-Job concurrency (v1)**        | Fulfill one Job at a time; no over-commitment.                                                                                                                    |
| **Gas precondition**                   | Confirm enough BNB for the full settlement before accepting.                                                                                                      |
| **Idempotent**                         | Never double-submit or re-fulfill a Job already Submitted/Terminal.                                                                                               |

If any rule can't be met, **skip the Job** — never force a settlement.

***

### 4. Out of scope — the agent MUST NOT

1. **Use Client funds for anything but the specified swap.** Output recipient is always the Client.
2. **Front its own inventory / take principal risk.** v1 is **escrow-pull only** — it routes the Client's escrowed input; it does not fill from its own balance.
3. **Route through non-PancakeSwap or unverified contracts**, or settle outside PancakeSwap aggregation.
4. **Serve Jobs with non-safelisted tokens**, or (v1) any scaled-UI / RWA token (§5).
5. **Use leverage, perps, margin, or lending.**
6. **Submit a deliverable it didn't actually fulfill** (no false attestation) or **evaluate its own Jobs** (conflict of interest).
7. **Call any owner/admin function** on PancakeSwap or the ERC-8183 contracts.
8. **Hold standing token approvals** beyond a single settlement; scope approvals to the Job amount.

***

### 5. PancakeSwap-specific logic (application correctness)

* **Route via PancakeSwap aggregation**, not a single pool — best execution across V2 / V3 / Stable is the whole value proposition ("best price wins the tip").
* **Deliver atomically to the Client** by setting the router's `recipient` to the Client address; never a two-step "swap to self, then transfer."
* **Quote freshness** — the on-chain price moves between discovery and settlement; requote at execution (guardrail §3).
* **`minOut` is in raw units.** For **scaled-UI / ERC-8056 tokens** (Binance Stock Tokens / RWA equities) raw ≠ displayed; mishandling silently mis-delivers. **Exclude scaled-UI tokens from v1** until eng confirms raw-unit handling end-to-end.
* **Slippage minimum** on the settlement swap must be derived so the _delivered_ amount ≥ `minOut`, accounting for the tip/fee split.

***

### 6. Failure & recovery behavior

* **Quote fails `minOut` at execution** → abort before/atomically with the escrow pull; the Job stays Funded for another Provider. No partial state.
* **Already Submitted/Terminal** → skip (idempotent).
* **Settlement tx reverts** → Job remains claimable by others; the agent records the failure and moves on.
* **Repeated failures on a Job** → blacklist that Job locally and alert, rather than retry-looping.

***

### 7. Integration points (the BNB / ERC-8183 half)

These are provided by BNB Agent Studio / BNBAgent SDK, not built by PancakeSwap — but the spec depends on them:

* **Job lifecycle** (discover Open → accept Funded → Submitted → claim) via BNBAgent SDK.
* **Provider identity** via ERC-8004.
* **Escrow + payout** via the ERC-8183 escrow / x402.
* **Evaluator** — the predicate must be "Client's token-B balance increased by ≥ `minOut`." Confirm with BNB **who runs the Evaluator** (neutral/protocol vs. Client) and that the predicate is enforceable on-chain.

***

### 8. Recommended v1 posture & open decisions

1. **Escrow-pull only, single Job at a time, token-safelist only, no scaled-UI tokens.** Smallest safe surface to feature at launch.
2. **Confirm the PancakeSwap swap interface** — the **Aggregator (`aggr`) HTTP API** vs the **Smart Router SDK**. Jerry's note says "use pcs aggr api"; needs confirming which the agent calls, as it changes the integration (and whether the guide needs an aggregation section).
3. **Confirm the escrow mechanic** with BNB — can the Provider pull the Client's escrowed input to route the swap, and is delivery-to-Client enforceable as the deliverable?
4. **Confirm the Evaluator owner and predicate** (§7).

> Eng sign-off before featuring: atomic escrow-pull → swap → deliver-to-Client routing; requote-at-execution; `minOut`-after-slippage math; safelist enforcement; idempotent Job handling.
