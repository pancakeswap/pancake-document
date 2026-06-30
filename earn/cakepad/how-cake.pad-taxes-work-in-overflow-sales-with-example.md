# Cách thuế CAKE.PAD hoạt động trong các đợt bán Overflow – Với ví dụ

1. Thuế chỉ được tính **nếu** sự kiện CAKE.PAD **bị đăng ký quá mức**
   1. Đăng ký quá mức = Tổng tiền nạp của tất cả người dùng > Mục tiêu huy động.
   * Thuế chỉ được khấu trừ từ số tiền nạp dư thừa của người tham gia. Không có phí nào do dự án đối tác CAKE.PAD phải trả.
   * Dự án đối tác CAKE.PAD nhận 100% số tiền huy động mục tiêu.
   * Thuế CAKE.PAD được thu bằng CAKE và 100% sẽ bị đốt.
   * Phí dựa trên **tổng tỷ lệ đăng ký của pool** (% mục tiêu huy động):

**Tỷ lệ đăng ký quá mức <> Mức phí**&#x20;

<table data-full-width="false"><thead><tr><th>Tỷ lệ đăng ký quá mức</th><th>Mức phí</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1.00%</td></tr><tr><td>≥ 50x</td><td>0.80%</td></tr><tr><td>≥ 100x</td><td>0.60%</td></tr><tr><td>≥ 150x</td><td>0.50%</td></tr><tr><td>≥ 200x</td><td>0.40%</td></tr><tr><td>≥ 250x</td><td>0.30%</td></tr><tr><td>≥ 300x</td><td>0.25%</td></tr><tr><td>≥ 400x</td><td>0.20%</td></tr><tr><td>≥ 500x</td><td>0.15%</td></tr><tr><td>≥ 650x</td><td>0.12%</td></tr><tr><td>≥ 800x</td><td>0.10%</td></tr><tr><td>≥ 1500x</td><td>0.05%</td></tr></tbody></table>



2. **Thời gian – Khi nào thuế được tính**

* Thuế được tính vào **cuối sự kiện CAKE.PAD**, khi người dùng đổi phân bổ của họ.
* Ngay cả khi người dùng đăng ký sớm (ví dụ: khi đăng ký đạt 30% mục tiêu huy động), thuế cuối cùng dựa trên **mức đăng ký quá mức cuối cùng của pool**.
  * Ví dụ: Nếu pool kết thúc với mức đăng ký 50x, thuế áp dụng là mức 50x (0,8%).

#### Các bước tính toán

1.  **Phân bổ người dùng** = % tổng pool token đối tác CAKE.PAD mà người dùng nhận được

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **Số tiền người dùng phải trả** = Phần tiền nạp của người dùng được dùng để đổi token đối tác CAKE.PAD

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **Số tiền hoàn trả** = Số dư thừa từ tiền nạp của người dùng không dùng để mua token đối tác CAKE.PAD

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Số tiền thuế** = Khoản khấu trừ áp dụng cho số tiền hoàn trả của người dùng

    * Mức phí dựa trên % mục tiêu huy động (xem bảng ở trên).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Kết quả cuối cùng cho người dùng**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (nếu có, ngược lại = refund_amount)
    ```

#### Ví dụ số học

* **Mục tiêu huy động (raisingAmountPool):** 100 CAKE
* **Tiền nạp của bạn (user\_deposit\_amount):** 10 CAKE
* **Tổng tiền nạp bao gồm tiền nạp của bạn (totalAmountPool):** 5.100 CAKE (đăng ký 51x = 5.100% mục tiêu huy động, nghĩa là tỷ lệ đăng ký quá mức 50x)
  * Mức phí tương ứng = 0,80% (dựa trên bảng mức thuế ở trên)

**Các bước:**

1. `user_allocation = 10 / 5,100 = 0.00196 (phân bổ pool 0.196%)`
2. `user_pay_amount = 100 × 0.00196 = 0.196 CAKE`
3. `refund_amount = 10 − 0.196 = 9.804 CAKE`
4. `tax_amount = 9.804 × 0.008 = 0.0784 CAKE`
5. `final_refund = 9.804 − 0.0784 = ~9.72 CAKE`

**Số tiền người dùng nhận cuối cùng**

1. **Phân bổ token:** Token đối tác CAKE.PAD trị giá 0,196 CAKE
2. **Hoàn trả cuối cùng:** \~9,72 CAKE (từ tiền nạp 10 CAKE − 0,196 CAKE cho phân bổ token − 0,0784 CAKE thuế)
