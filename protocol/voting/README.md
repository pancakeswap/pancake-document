# 📔 Governance

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
As part of the [Tokenomics 3.0 upgrade](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3), this page has been updated on 15th May 2025
{% endhint %}

Voting gives a voice to the PancakeSwap community, letting the community have a say in how PancakeSwap develops into the future.

Check out [PancakeSwap's native voting portal](https://pancakeswap.finance/voting) and our [Forum](https://forum.pancakeswap.finance/) page.

## Voting Mechanics

:notebook\_with\_decorative\_cover:Summary - What Changed (after [Tokenomics 3.0 Update](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3))

<table><thead><tr><th width="200.6015625">Governance Component</th><th width="218.01953125">Before Tokenomics 3.0</th><th width="205.1796875">After Tokenomics 3.0</th><th>Status<select><option value="q1dVFsCri7zA" label="✅ Changed" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Unchanged" color="blue"></option></select></th></tr></thead><tbody><tr><td>Voting Power</td><td>1 veCAKE = 1 voting power</td><td>1 CAKE = 1 voting power</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Delegation</td><td>Allowed (via veCAKE mechanics)</td><td>Delegation is not allowed</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Proposal Submission Threshold</td><td>Snapshot 100K veCAKE required</td><td>Snapshot 100K CAKE required</td><td><span data-option="q1dVFsCri7zA">✅ Changed</span></td></tr><tr><td>Core vs Community Proposals</td><td>Defined roles and purposes for each proposal type</td><td>No change</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Voting Period</td><td>Community: Fixed<br>Core: Variable</td><td>No change</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Snapshot Timing</td><td>At proposal posted block</td><td>No change</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr><tr><td>Quorum</td><td>No minimum quorum</td><td>No change</td><td><span data-option="4AGl26rwjYcI">🔁 Unchanged</span></td></tr></tbody></table>

### 1. **Voting Power (Changed)**

* **All CAKE holders have direct voting rights.**
* **Voting power directly corresponds to the number of CAKE held in wallet address during snapshot**
  * **1 CAKE = 1 voting power**
  * **CAKE staked in Syrup Pools does not count** toward your voting power, as it is not part of your wallet balance at the time of the snapshot
  * Snapshot balance = Same block proposal posted
* **Delegation is no longer supported.** Every CAKE holder must vote individually.

### 2. **Proposal Submission (Unchanged)**

* **How to Submit a Proposal**
  * Submit on [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)
  * Must include:
    * Title
    * Content
    * Description
    * On-chain action(s) (if needed)
    * Voting Duration
* Types of Proposals
  1.  Core Proposals

      * Can only be proposed by the **PancakeSwap Core Team**.
      * Require a vote by CAKE holders.
      * If passed, will be implemented by the PancakeSwap team.

      Examples

      1. Protocol adjustments (product changes, fee changes)
      2. Significant uses of Ecosystem Growth funds not covered by previous proposals
  2. Community Proposals
     * **Community** proposals are posted by the PancakeSwap community. These are used to propose ideas and express the community's point of view. These are **non-binding suggestions** from the community.
     * Anyone with **100,000 CAKE (snapshot balance)** can submit.
     * The PancakeSwap team may adopt strong proposals into future Core Proposals
     * Community members may also utilize our [Forum](https://forum.pancakeswap.finance/) to provide feedback and make suggestions to the protocol.

### **3. Voting Duration (Unchanged)**

* All CAKE holders can vote **during the voting window** for each proposal.
  * Community proposal: Fixed at 3 days
  * Core Proposal: Variable, set by PancakeSwap
* Your voting power is determined by a **snapshot of your CAKE balance at the block when the proposal is posted**.
* **Adding more CAKE after the proposal is posted will not increase your voting power** for that specific vote.

For full details, see the [Voting Guide](https://docs.pancakeswap.finance/protocol/voting/voting-guide).

### **4. Voting Outcome (Unchanged)**

* The outcome is based on **total votes cast** (total CAKE used for voting)
* **There is currently no minimum quorum required** for a proposal to pass.

## Note: Veto Rights

To protect the protocol, the **PancakeSwap Core Team reserves the right to intervene in critical situations**—such as security threats or issues affecting the stable operation of the platform—**without requiring a community vote or Snapshot poll**.

In any case where a veto action is taken, the Core Team will **publicly share a clear explanation** of the decision.

**Possible veto actions may include:**

1. **Temporarily pausing smart contracts** to fix urgent bugs or vulnerabilities.
