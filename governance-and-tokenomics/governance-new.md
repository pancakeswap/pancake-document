# Governance (new)

{% hint style="info" %}
We are transitioning from vCAKE to veCAKE for our governance system. Before the migration is done, not all information on this page will be accurate.
{% endhint %}

<figure><img src="../.gitbook/assets/image (204).png" alt=""><figcaption></figcaption></figure>

#### Overview

veCAKE holders have voting rights in PancakeSwap’s governance system. These are the topics that are within the scope of governance:

1. \[Core] High-level CAKE emission adjustments (allocating CAKE to Core Pools and other high-level categories)
2. \[Core] Protocol adjustments (product changes, fee changes)
3. \[Core] Multichain warchest spending
4. \[Community] Gauge approvals
5. \[Community] Regular gauge weight voting (every 2 weeks)

Core topics must be voted on by veCAKE holders, but can only be proposed by the PancakeSwap Core Team.&#x20;

Community topics may be proposed by anyone, and must be voted on by veCAKE holders as well. A minimum of 10,000 veCAKE is required to start a Snapshot poll (this will be implemented at a later date when we migrate from vCAKE to veCAKE). The result of the poll will be executed by the Core Team.

#### Veto

The PancakeSwap Core Team has veto rights, and can perform corrective actions when it concerns the security or proper functioning of the protocol, without going through a Snapshot poll. In the case of any veto action, the PancakeSwap Core Team will provide an explanation.

Possible actions include, but are not limited to:

1. Pausing relevant smart contracts while fixing a critical bug in the protocol
2. Rejecting a gauge that was successfully voted for if the token(s) in question is deemed unsafe, malicious, and/or detrimental to the PancakeSwap ecosystem

#### Governance Process

The overview of the PancakeSwap governance process is as follows:

1. Post a Temperature Check to the forum
2. Discuss
3. Start a Snapshot poll (minimum 24 hours voting period)
4. Execute

**Step 1: Post a Temperature Check to the forum**

* The purpose of a Temperature Check is to measure the community’s rough consensus of the proposal before starting an official Snapshot poll
* While PancakeSwap welcomes communities of diverse backgrounds, the forum will currently only accept proposals written in English. Please speak to our Ambassadors in our [various regional Telegram groups](https://docs.pancakeswap.finance/contact-us/social-accounts-and-communities) if you need help with translation
* Proposers must include \[Temp Check] in the title when posting in the forum

**Step 2: Discuss**

* We encourage all Temperature Check proposals to go through 48 hours of discussion in the forum before a Snapshot poll is started, although it is not strictly necessary
* This is to give sufficient time to measure the community’s sentiment and incorporate any feedback into the proposal

**Step 3: Start a Snapshot poll**

* Anyone with 10,000 veCAKE voting power (will be implemented at a later date) can start a Snapshot poll and post the link to the respective Topic in the forum
* The veCAKE requirement mitigates low quality proposals and ensures a poll can only be started by PancakeSwap-aligned community members
* The Snapshot poll must last for a minimum of 48 hours, or a minimum of 24 hours if it’s a Core topic
* The quorum for a Snapshot poll is 250,000 veCAKE votes (will be implemented at a later date), including Abstain Votes (this requirement is subject to further revision to ensure high-quality proposals)

**Step 4: Execute**

* If the Snapshot poll hits quorum by the end of the voting period and receives >50% vote approval, the PancakeSwap Core Team will execute based on the vote outcome
* Formula to measure vote approval percentage: For Votes / (For Votes + Against Votes)
