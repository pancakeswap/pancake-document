# 🍩 Dual Investment

<figure><img src="../.gitbook/assets/Frame 1 (2).png" alt=""><figcaption></figcaption></figure>

Dual Investment lets you commit funds at a target price and earn a fixed reward, whichever way the market settles. Pick an asset, choose whether you want to **Buy Low** or **Sell High**, and select a target price and settlement date. At settlement, you receive your principal plus the reward, either in the asset you deposited or converted at your target price.

Dual Investment is live on BNB Chain with **BTCB** and **BNB**, paired against **USDT**.

{% hint style="info" %}
Dual Investment is not a savings product. Depending on the settlement price, your funds may be converted into another asset at your target price, and that asset may be worth less than what you deposited.
{% endhint %}

***

## What is Dual Investment?

#### **Two outcomes, one fixed reward**

Each Dual Investment product has a target price and a settlement date. When you subscribe, your reward is locked in at the APR shown. At settlement, the market price decides which of two outcomes you get:

* **The price does not reach your target.** You get back your original asset plus the reward.
* **The price reaches your target.** Your principal and reward are converted into the other asset at your target price.

You earn the reward in both cases. The only thing that changes is which asset you receive.

#### **Buy Low**

Use Buy Low when you would be happy to buy BTCB or BNB below today's price. You deposit **USDT** and pick a target price below the current price.

| Settlement price        | You receive                                                     |
| ----------------------- | --------------------------------------------------------------- |
| At or above your target | USDT (principal + reward)                                       |
| Below your target       | BTCB or BNB, bought at your target price along with your reward |

#### **Sell High**

Use Sell High when you would be happy to sell BTCB or BNB above today's price. You deposit **BTCB or BNB** and pick a target price above the current price.

| Settlement price        | You receive                                            |
| ----------------------- | ------------------------------------------------------ |
| At or below your target | BTCB or BNB (principal + reward)                       |
| Above your target       | USDT, sold at your target price along with your reward |

#### **How the APR works**

The APR depends on how close the target price is to the current price and how long the product runs. Targets closer to the current price pay a higher APR because they are more likely to be converted. Targets further away pay less but are more likely to return your original asset.

Your reward is calculated as:

`Reward = Subscription amount × APR × (Days to settlement ÷ 365)`

#### **Example: Buy Low**

BTCB is trading at $83,467. You subscribe 1,000 USDT to a 1-day Buy Low product with a $82,000 target at 14.68% APR. Your reward is about 0.40 USDT.

| Settlement price | You receive                           |
| ---------------- | ------------------------------------- |
| $82,000 or above | 1,000.40 USDT                         |
| Below $82,000    | 0.0122 BTCB (1,000.40 USDT ÷ $82,000) |

If BTCB settles at $78,000, you still buy at $82,000. You would hold 0.0122 BTCB worth about 951.60 USDT, which is less than you deposited.

#### **Example: Sell High**

BTCB is trading at $83,467. You subscribe 0.01 BTCB to a 1-day Sell High product with a $84,500 target at 89.28% APR. Your reward is about 0.0000245 BTCB.

| Settlement price | You receive                            |
| ---------------- | -------------------------------------- |
| $84,500 or below | 0.0100245 BTCB                         |
| Above $84,500    | 847.07 USDT (0.0100245 BTCB × $84,500) |

If BTCB settles at $88,000, you still sell at $84,500. You would receive 847.07 USDT for BTCB that would have been worth about 882 USDT.

#### **Who is on the other side?**

Each product is quoted by a market maker, who takes the other side of your position. Market makers post a bond that secures your payout. If a market maker defaults, your claim is covered by their bond.

***

## How to use Dual Investment

#### **Go to the Dual Investment page**

Head to [pancakeswap.finance/dual-investment](https://pancakeswap.finance/dual-investment?chain=bsc) or click **Dual Investment** in the main PancakeSwap navigation bar.

#### **1. Choose a target asset**

Select **BTCB** or **BNB**. Each card shows the current price and the APR range available across all products for that asset.

<figure><img src="../.gitbook/assets/image (407).png" alt=""><figcaption></figcaption></figure>

#### **2. Choose a direction**

Select **Buy Low** to deposit USDT and buy the asset at a lower price, or **Sell High** to deposit the asset and sell it at a higher price.

<figure><img src="../.gitbook/assets/image (430).png" alt=""><figcaption></figcaption></figure>

#### **3. Pick a settlement date and target price**

Use the duration filters (**1 Day**, **< 3 Days**, **< 7 Days**, and longer) to narrow the list. Products are grouped by settlement date. Each row shows the target price, its distance from the current price, and the APR.

The countdown next to each settlement date shows how long you have left to subscribe. Subscriptions close before settlement.

<figure><img src="../.gitbook/assets/image (475).png" alt=""><figcaption></figcaption></figure>

#### **4. Enter your subscription amount**

Click **Subscribe** on the target you want, then enter an amount or tap **MAX**. Each product has a minimum and maximum per subscription, and a fixed total capacity. Once a target is fully subscribed, it cannot reopen, so you will need to pick another target price.

<figure><img src="../.gitbook/assets/image (476).png" alt="" width="375"><figcaption></figcaption></figure>

#### **5. Review and confirm**

Review the direction, target price, settlement date and both outcomes.&#x20;

The rate is held for a short time while you confirm. If it expires or moves, the page fetches a new rate and asks you to accept it before you continue.

#### **6. Claim your payout**

After settlement, click **Claim** on a position, or **Claim all** to claim every settled position at once. Your payout is sent to your wallet in the asset determined by the settlement outcome.

***

## Dual Investment FAQ

#### **What is Dual Investment?**

Dual Investment is a product that lets you commit funds at a target price and earn a fixed reward. At settlement, you receive your principal plus the reward, either in your original asset or converted into the other asset at your target price.

#### **Which assets are supported?**

BTCB and BNB, paired against USDT, on BNB Chain.

#### **What is the difference between Buy Low and Sell High?**

Buy Low lets you deposit USDT and buy BTCB or BNB at a target price below the current price. Sell High lets you deposit BTCB or BNB and sell it at a target price above the current price.

#### **Do I earn the reward in both outcomes?**

Yes. The reward is fixed when you subscribe and is paid in both outcomes. It is paid together with your principal, in whichever asset you receive at settlement.

#### **Can I withdraw before the settlement date?**

No. Once you subscribe, your funds are locked until settlement and the subscription cannot be cancelled.

#### **Why do APRs differ between products?**

Targets closer to the current price, and shorter settlement dates, generally pay higher APRs because they carry a higher chance of conversion. Rates are quoted live and can change between when you open a product and when you confirm.

#### **Why did the rate change while I was subscribing?**

Rates are quoted live by market makers and are only held for a short time. If the rate expires, moves, or another user fills that price first, the page fetches a new rate and asks you to accept it before you continue.

#### **Do I need to claim my payout?**

Yes. After settlement, claim your payout from **Your Holdings**. You can claim positions one by one or use **Claim all**.

#### **Who takes the other side of my position?**

Market makers quote each product and take the other side of your position. They post a bond that secures your payout, and if a market maker defaults, your claim is covered by that bond.

#### **What fees are charged?**

It's free of charge.
