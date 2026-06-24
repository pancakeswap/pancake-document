# CAKE.PAD 税费在超额认购销售中如何运作 – 含示例

1. 仅在 CAKE.PAD 活动**超额认购时**才收取税费
   1. 超额认购 = 所有用户的总存入金额 > 募集目标金额。
   * 税费仅从参与者超额投入的资金中扣除。CAKE.PAD 合作伙伴项目无需支付任何费用。
   * CAKE.PAD 合作伙伴项目可获得其募集目标金额的 100%。
   * CAKE.PAD 税费以 CAKE 收取，并将 100% 销毁。
   * 费用基于**矿池的总认购率**（占募集目标的百分比）：

**超额认购率 <> 费用分级**&#x20;

<table data-full-width="false"><thead><tr><th>超额认购率</th><th>费用分级</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1.00%</td></tr><tr><td>≥ 50x</td><td>0.80%</td></tr><tr><td>≥ 100x</td><td>0.60%</td></tr><tr><td>≥ 150x</td><td>0.50%</td></tr><tr><td>≥ 200x</td><td>0.40%</td></tr><tr><td>≥ 250x</td><td>0.30%</td></tr><tr><td>≥ 300x</td><td>0.25%</td></tr><tr><td>≥ 400x</td><td>0.20%</td></tr><tr><td>≥ 500x</td><td>0.15%</td></tr><tr><td>≥ 650x</td><td>0.12%</td></tr><tr><td>≥ 800x</td><td>0.10%</td></tr><tr><td>≥ 1500x</td><td>0.05%</td></tr></tbody></table>



2. **时间段 – 何时收取税费**

* 税费在 CAKE.PAD 活动**结束时**收取，即用户兑换其额度之时。
* 即使用户提前认购（例如，在认购达到募集目标的 30% 时），最终税费也基于**最终的矿池超额认购水平**。
  * 示例：如果矿池最终达到 50 倍超额认购，则适用的税费为 50x 分级（0.8%）。

#### 计算步骤

1.  **用户额度** = 用户获得的 CAKE.PAD 合作伙伴代币总池的百分比

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **用户支付金额** = 用户存入金额中用于兑换 CAKE.PAD 合作伙伴代币的部分

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **退款金额** = 用户存入金额中未用于购买 CAKE.PAD 合作伙伴代币的超额部分

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **税费金额** = 对用户退款金额所收取的扣除额

    * 费用分级基于占募集目标的百分比（见上表）。

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **用户的最终结果**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (if applicable, else = refund_amount)
    ```

#### 数值示例

* **目标募集金额（raisingAmountPool）：** 100 CAKE
* **你的存入金额（user\_deposit\_amount）：** 10 CAKE
* **包含你存入金额在内的总存入金额（totalAmountPool）：** 5,100 CAKE（认购 51 倍 = 募集目标的 5,100%，意味着 50 倍超额认购率）
  * 对应的费用分级 = 0.80%（基于上方的税率表）

**步骤：**

1. `user_allocation = 10 / 5,100 = 0.00196 (0.196% pool allocation)`
2. `user_pay_amount = 100 × 0.00196 = 0.196 CAKE`
3. `refund_amount = 10 − 0.196 = 9.804 CAKE`
4. `tax_amount = 9.804 × 0.008 = 0.0784 CAKE`
5. `final_refund = 9.804 − 0.0784 = ~9.72 CAKE`

**用户最终收到的金额**

1. **代币额度：** 价值 0.196 CAKE 的 CAKE.PAD 合作伙伴代币
2. **最终退款：** \~9.72 CAKE（来自 10 CAKE 存入金额 − 0.196 CAKE 用于代币额度 − 0.0784 CAKE 税费）
