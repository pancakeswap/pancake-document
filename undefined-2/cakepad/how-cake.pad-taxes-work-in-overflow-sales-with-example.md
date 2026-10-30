# CAKE.PAD 오버플로우 세일의 세금 구조 – 예시 포함

1. 세금은 CAKE.PAD 이벤트가 **초과 청약된 경우에만** 부과됩니다
   1. 초과 청약 = 모든 사용자의 총 예치금 > 모금 목표 금액.
   * 세금은 참가자가 초과로 커밋한 자금에서만 차감됩니다. CAKE.PAD 파트너 프로젝트는 어떠한 수수료도 지불하지 않습니다.
   * CAKE.PAD 파트너 프로젝트는 목표 모금액의 100%를 받습니다.
   * CAKE.PAD 세금은 CAKE로 징수되며, 100%가 소각됩니다.
   * 수수료는 **풀의 총 청약률**(모금 목표 대비 %)을 기준으로 합니다.

**초과 청약률 <> 수수료 등급**

<table data-full-width="false"><thead><tr><th>초과 청약률</th><th>수수료 등급</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1.00%</td></tr><tr><td>≥ 50x</td><td>0.80%</td></tr><tr><td>≥ 100x</td><td>0.60%</td></tr><tr><td>≥ 150x</td><td>0.50%</td></tr><tr><td>≥ 200x</td><td>0.40%</td></tr><tr><td>≥ 250x</td><td>0.30%</td></tr><tr><td>≥ 300x</td><td>0.25%</td></tr><tr><td>≥ 400x</td><td>0.20%</td></tr><tr><td>≥ 500x</td><td>0.15%</td></tr><tr><td>≥ 650x</td><td>0.12%</td></tr><tr><td>≥ 800x</td><td>0.10%</td></tr><tr><td>≥ 1500x</td><td>0.05%</td></tr></tbody></table>

2. **기간 – 세금이 부과되는 시점**

* 세금은 CAKE.PAD 이벤트 **종료 시**, 사용자가 할당량을 수령할 때 부과됩니다.
* 사용자가 일찍 청약하더라도(예: 청약률이 모금 목표의 30%일 때), 최종 세금은 **최종 풀 초과 청약 수준**을 기준으로 합니다.
  * 예시: 풀이 최종적으로 50x 초과 청약되면 적용되는 세금은 50x 등급(0.8%)입니다.

#### 계산 단계

1.  **사용자 할당량** = 사용자가 받는 CAKE.PAD 파트너 토큰 풀의 비율(%)

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **사용자 지불 금액** = CAKE.PAD 파트너 토큰을 수령하는 데 사용된 사용자 예치금의 일부

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **환불 금액** = CAKE.PAD 파트너 토큰 구매에 사용되지 않은 사용자 예치금의 초과분

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **세금 금액** = 사용자의 환불 금액에 적용되는 공제액

    * 수수료 등급은 모금 목표 대비 %를 기준으로 합니다(위 표 참조).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **사용자 최종 결과**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (if applicable, else = refund_amount)
    ```

#### 수치 예시

* **목표 모금액 (raisingAmountPool):** 100 CAKE
* **내 예치금 (user\_deposit\_amount):** 10 CAKE
* **내 예치금을 포함한 총 예치금 (totalAmountPool):** 5,100 CAKE (51x 청약 = 모금 목표의 5,100%, 초과 청약률 50x에 해당)
  * 해당 수수료 등급 = 0.80% (위 세율 표 기준)

**단계:**

1. `user_allocation = 10 / 5,100 = 0.00196 (0.196% pool allocation)`
2. `user_pay_amount = 100 × 0.00196 = 0.196 CAKE`
3. `refund_amount = 10 − 0.196 = 9.804 CAKE`
4. `tax_amount = 9.804 × 0.008 = 0.0784 CAKE`
5. `final_refund = 9.804 − 0.0784 = ~9.72 CAKE`

**사용자가 최종적으로 받는 금액**

1. **토큰 할당량:** 0.196 CAKE 상당의 CAKE.PAD 파트너 토큰
2. **최종 환불액:** \~9.72 CAKE (예치금 10 CAKE − 토큰 할당에 사용된 0.196 CAKE − 세금 0.0784 CAKE)
