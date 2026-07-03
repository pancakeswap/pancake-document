# CAKE.PADのオーバーフローセールにおける税金の仕組み – 実例付き

1. 税金はCAKE.PADイベントが**超過申込の場合のみ**請求されます
   1. 超過申込とは、全ユーザーの総預け入れ額 > 調達目標額。
   * 税金は参加者の超過コミット資金のみから控除されます。CAKE.PADパートナープロジェクトは手数料を支払いません。
   * CAKE.PADパートナープロジェクトは調達目標額の100%を受け取ります。
   * CAKE.PADの税金はCAKEで徴収され、100%がバーンされます。
   * 手数料は**プールの総申込率**（調達目標に対する%）に基づきます：

**超過申込率 <> 手数料ティア**&#x20;

<table data-full-width="false"><thead><tr><th>超過申込率</th><th>手数料ティア</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1.00%</td></tr><tr><td>≥ 50x</td><td>0.80%</td></tr><tr><td>≥ 100x</td><td>0.60%</td></tr><tr><td>≥ 150x</td><td>0.50%</td></tr><tr><td>≥ 200x</td><td>0.40%</td></tr><tr><td>≥ 250x</td><td>0.30%</td></tr><tr><td>≥ 300x</td><td>0.25%</td></tr><tr><td>≥ 400x</td><td>0.20%</td></tr><tr><td>≥ 500x</td><td>0.15%</td></tr><tr><td>≥ 650x</td><td>0.12%</td></tr><tr><td>≥ 800x</td><td>0.10%</td></tr><tr><td>≥ 1500x</td><td>0.05%</td></tr></tbody></table>



2. **時間軸 – 税金はいつ請求されますか**

* 税金はCAKE.PADイベント**終了時**、ユーザーが配分を受け取る際に請求されます。
* ユーザーが早期に申し込んだ場合（例：申込が調達目標の30%の時点）でも、最終的な税金は**最終プール超過申込水準**に基づきます。
  * 例：プールが最終的に50倍超過申込となった場合、適用される税金は50xティア（0.8%）です。

#### 計算ステップ

1.  **ユーザー配分** = ユーザーが受け取るCAKE.PADパートナートークンプール全体の%

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **ユーザー支払額** = CAKE.PADパートナートークンの受け取りに使用されるユーザーの預け入れ分

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **返金額** = CAKE.PADパートナートークン購入に使用されなかったユーザーの預け入れの余剰分

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **税額** = ユーザーの返金額に適用される控除額

    * 手数料ティアは調達目標に対する%に基づきます（上記の表を参照）。

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **ユーザーへの最終出力**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (if applicable, else = refund_amount)
    ```

#### 数値の例

* **調達目標（raisingAmountPool）：** 100 CAKE
* **ご自身の預け入れ（user\_deposit\_amount）：** 10 CAKE
* **ご自身の預け入れを含む総預け入れ（totalAmountPool）：** 5,100 CAKE（51倍申込 = 調達目標の5,100%、50倍の超過申込率を意味する）
  * 対応する手数料ティア = 0.80%（上記の税率表に基づく）

**ステップ：**

1. `user_allocation = 10 / 5,100 = 0.00196 (0.196% プール配分)`
2. `user_pay_amount = 100 × 0.00196 = 0.196 CAKE`
3. `refund_amount = 10 − 0.196 = 9.804 CAKE`
4. `tax_amount = 9.804 × 0.008 = 0.0784 CAKE`
5. `final_refund = 9.804 − 0.0784 = ~9.72 CAKE`

**ユーザーへの最終受取額**

1. **トークン配分：** 0.196 CAKE相当のCAKE.PADパートナートークン
2. **最終返金：** 約9.72 CAKE（10 CAKE預け入れ − トークン配分0.196 CAKE − 税金0.0784 CAKE）
