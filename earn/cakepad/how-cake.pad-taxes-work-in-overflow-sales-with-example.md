# How CAKE.PAD Taxes Work in Overflow Sales – With Example

1. Taxes are only charged **if the** CAKE.PAD event **is oversubscribed**
   1. Oversubscription = Total deposits by all users > Raise goal amount.
   * Tax is only deducted from participants' excess committed funds. No fees are paid by the CAKE.PAD partner project.
   * The CAKE.PAD partner project receives 100% of its targeted raise amount.
   * CAKE.PAD taxes are collected in CAKE, and 100% of it will be burned.
   * Fees are based on the **total subscription rate of the pool** (% of raise goal):

**Oversubscription rate <> Fee Tier**&#x20;

<table data-full-width="false"><thead><tr><th>Oversubscription Rate</th><th>Fee Tier</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1.00%</td></tr><tr><td>≥ 50x</td><td>0.80%</td></tr><tr><td>≥ 100x</td><td>0.60%</td></tr><tr><td>≥ 150x</td><td>0.50%</td></tr><tr><td>≥ 200x</td><td>0.40%</td></tr><tr><td>≥ 250x</td><td>0.30%</td></tr><tr><td>≥ 300x</td><td>0.25%</td></tr><tr><td>≥ 400x</td><td>0.20%</td></tr><tr><td>≥ 500x</td><td>0.15%</td></tr><tr><td>≥ 650x</td><td>0.12%</td></tr><tr><td>≥ 800x</td><td>0.10%</td></tr><tr><td>≥ 1500x</td><td>0.05%</td></tr></tbody></table>



2. **Time period – When is tax charged**

* Tax is charged at the **end of the** CAKE.PAD event, when the user redeems their allocation.
* Even if a user subscribes early (e.g., when the subscription is 30% of the raise goal), the final tax is based on the **final pool oversubscription level**.
  * Example: If the pool ends up at 50x over-subscribed, the applicable tax is the 50x tier (0.8%).

#### Calculation Steps

1.  **User allocation** = % of total CAKE.PAD partner token pool the user receives

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **User pay amount** = Portion of the user’s deposit used to redeem CAKE.PAD partner tokens

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **Refund amount** = Excess from the user’s deposit not used for CAKE.PAD partner token purchase

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Tax amount** = Deduction applied on the user’s refunded amount

    * Fee tier is based on the % of raise goal (see table above).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Final output for the user**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (if applicable, else = refund_amount)
    ```

#### Numerical Example

* **Target raise (raisingAmountPool):** 100 CAKE
* **Your deposit (user\_deposit\_amount):** 10 CAKE
* **Total deposits incl. of Your deposit (totalAmountPool):** 5,100 CAKE (51x subscribed = 5,100% of raise goal, implies 50x oversubscription rate)
  * Corresponding fee tier = 0.80% (based on the tax rate table above)

**Steps:**

1. `user_allocation = 10 / 5,100 = 0.00196 (0.196% pool allocation)`
2. `user_pay_amount = 100 × 0.00196 = 0.196 CAKE`
3. `refund_amount = 10 − 0.196 = 9.804 CAKE`
4. `tax_amount = 9.804 × 0.008 = 0.0784 CAKE`
5. `final_refund = 9.804 − 0.0784 = ~9.72 CAKE`

**Final User received amounts**

1. **Token allocation:** 0.196 CAKE worth of CAKE.PAD partner tokens
2. **Final refund:** \~9.72 CAKE (from 10 CAKE deposit − 0.196 CAKE for token allocation − 0.0784 CAKE tax)
