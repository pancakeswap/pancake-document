# FAQ

<figure><img src="../../.gitbook/assets/image (198).png" alt=""><figcaption></figcaption></figure>

#### What’s the difference between locked CAKE and veCAKE? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE is a new version of fixed-term CAKE staking with more benefits and power for locked CAKE holders. Including gauge weight voting, extra incentives, yield boosting, and more.

#### What happens to CAKE pool rewards when the new veCAKE is deployed <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

CAKE pool reward emissions will be diverted to reward all veCAKE holders according to their veCAKE balance against the total supply.

CAKE rewards and the weekly revenue-sharing rewards can now be claimed weekly on Thursday.

Please note that to continue receiving rewards, users will need to migrate to the new veCAKE staking.

#### What is the maximum duration I can lock my CAKE <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

The maximum duration you can lock your CAKE has now been extended to 4 years.

#### Is veCAKE a new token? Can it be transferred? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE is a live-generated number based on the number of CAKE locked and the remaining lock time. It is not a standard token and can not be transferred.

#### Why did my veCAKE balance change? How to calculate its balance? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

veCAKE balance is linearly decreasing to 0 based on the remaining lock duration. Therefore when we are approaching the unlock time, your balance decreases.

veCAKE balance can be calculated by:

```javascript
lockedAmount // amount of CAKE locked
currentTime // current time
lockEndTime // the unlock time
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // max lock time (4 years)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### How to increase my veCAKE? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Once you have an active veCAKE position, you can either add more CAKE or renew/extend your lock duration to boost your veCAKE balance.

#### What happens when the position unlocks? Can I renew rightaway? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

When the veCAKE staking position is unlocked, you may withdraw all the staked CAKE.

To renew your position, you need to withdraw all the CAKE and set up a new staking position by choosing the amount to lock and the lock duration.

#### I locked for 1 week, why the remaining lock time is less than 1 week? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

When you lock with the new veCAKE, the unlock time is being rounded forward to the nearest Thursday with UTC time. For example, when you lock for 1 week on Tuesday, your actual unlock time will be the upcoming Thursday, which is 2 days later.

You can preview your actual unlock time at the bottom.

#### Can I lock more CAKE in CAKE pool? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

No.

Once veCAKE is deployed, the CAKE staking pool will be deprecated and no longer accepts any further CAKE extension or deposits.

To lock CAKE and enjoy its benefits, go to the veCAKE page.

#### Why can’t I migrate? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

Migrating from CAKE pool to veCAKE requires you to have an active position. If your CAKE pool staking position is already unlocked, simply withdraw those CAKE and create a native veCAKE staking position.

In some cases, migration can not be performed when your remaining CAKE pool lock time is less than 7 days. In such case, simply wait for the unlock, withdraw those CAKE and create a native veCAKE staking position.

#### Can I early withdraw my locked CAKE? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

No.

Once locked, CAKE will be staked in the veCAKE contract until the unlock time.

#### Can I partially migrate my CAKE? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

No.

You can only migrate your entire CAKE pool position at once.

#### What will happen to iCAKE, bCAKE, vCAKE and rCAKE? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**For iCAKE:**

IFO iCAKE has now been upgraded to support veCAKE. Check out:

{% content-ref url="../ifo-initial-farm-offering/icake.md" %}
[icake.md](../ifo-initial-farm-offering/icake.md)
{% endcontent-ref %}

**For bCAKE:**

Farm boosting bCAKE has now been upgraded to support veCAKE. Check out:

{% content-ref url="../yield-farming/bcake/" %}
[bcake](../yield-farming/bcake/)
{% endcontent-ref %}

**For vCAKE:**

Voting vCAKE has now been upgraded to support veCAKE. Check out:

{% content-ref url="../../governance-and-tokenomics/voting/voting-guide/" %}
[voting-guide](../../governance-and-tokenomics/voting/voting-guide/)
{% endcontent-ref %}

**For rCAKE:**

All veCAKE holders (either native or migrated) will automatically enrolled in the new revenue sharing pool. Revenue shares are distributed according to the existing schedule. The old revenue sharing pool will be discontinued, users can claim their pending rewards by going to the benefit card. Check out:

{% content-ref url="../revenue-sharing/" %}
[revenue-sharing](../revenue-sharing/)
{% endcontent-ref %}

#### Can multisig wallets be used for interacting with veCAKE?

Yes

However, there was a `noContract` modifier implemented in the veCAKE staking contract for addresses that are not whitelisted. To enable staking or migrating from fixed-term CAKE staking pool. All contract-based multisig wallets must perform a one-time, self-whitelisting action.

To whitelist, visit either of the following pages:

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

A prompt should appear. Click "Whitelist" and proceed with the tx in your multisig wallet.

A tx will be fired to the owner of the veCAKE, which is a contract with a permission-less write function to allow any contract to perform self-whitelisting.
