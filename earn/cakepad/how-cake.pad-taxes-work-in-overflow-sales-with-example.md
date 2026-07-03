# Cara Kerja Pajak CAKE.PAD dalam Penjualan Overflow – Dengan Contoh

1. Pajak hanya dikenakan **jika** acara CAKE.PAD **kelebihan langganan**
   1. Kelebihan langganan = Total deposit oleh semua pengguna > Jumlah target penggalanan dana.
   * Pajak hanya dipotong dari kelebihan dana yang di-commit peserta. Tidak ada biaya yang dibayarkan oleh proyek mitra CAKE.PAD.
   * Proyek mitra CAKE.PAD menerima 100% dari jumlah penggalanan dana yang ditargetkan.
   * Pajak CAKE.PAD dikumpulkan dalam CAKE, dan 100%-nya akan dibakar.
   * Biaya didasarkan pada **tingkat langganan total pool** (% dari target penggalanan dana):

**Tingkat Kelebihan Langganan <> Tingkatan Biaya**&#x20;

<table data-full-width="false"><thead><tr><th>Tingkat Kelebihan Langganan</th><th>Tingkatan Biaya</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1,00%</td></tr><tr><td>≥ 50x</td><td>0,80%</td></tr><tr><td>≥ 100x</td><td>0,60%</td></tr><tr><td>≥ 150x</td><td>0,50%</td></tr><tr><td>≥ 200x</td><td>0,40%</td></tr><tr><td>≥ 250x</td><td>0,30%</td></tr><tr><td>≥ 300x</td><td>0,25%</td></tr><tr><td>≥ 400x</td><td>0,20%</td></tr><tr><td>≥ 500x</td><td>0,15%</td></tr><tr><td>≥ 650x</td><td>0,12%</td></tr><tr><td>≥ 800x</td><td>0,10%</td></tr><tr><td>≥ 1500x</td><td>0,05%</td></tr></tbody></table>



2. **Periode waktu – Kapan pajak dikenakan**

* Pajak dikenakan pada **akhir acara** CAKE.PAD, ketika pengguna menebus alokasinya.
* Bahkan jika pengguna berlangganan lebih awal (misalnya, saat langganan baru 30% dari target penggalanan dana), pajak akhir didasarkan pada **tingkat kelebihan langganan pool akhir**.
  * Contoh: Jika pool akhirnya kelebihan langganan 50x, pajak yang berlaku adalah tingkatan 50x (0,8%).

#### Langkah-langkah Perhitungan

1.  **Alokasi pengguna** = % dari total pool token mitra CAKE.PAD yang diterima pengguna

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **Jumlah yang dibayar pengguna** = Bagian dari deposit pengguna yang digunakan untuk menebus token mitra CAKE.PAD

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **Jumlah pengembalian dana** = Kelebihan dari deposit pengguna yang tidak digunakan untuk pembelian token mitra CAKE.PAD

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Jumlah pajak** = Potongan yang diterapkan pada jumlah pengembalian dana pengguna

    * Tingkatan biaya didasarkan pada % dari target penggalanan dana (lihat tabel di atas).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Output akhir untuk pengguna**

    ```jsx
    1. Token allocation = user_allocation * totalTokensOffered
    2. User tax amount = tax_amount
    3. final_refund = refund_amount - tax_amount (jika berlaku, jika tidak = refund_amount)
    ```

#### Contoh Numerik

* **Target penggalanan dana (raisingAmountPool):** 100 CAKE
* **Deposit Anda (user\_deposit\_amount):** 10 CAKE
* **Total deposit termasuk deposit Anda (totalAmountPool):** 5.100 CAKE (berlangganan 51x = 5.100% dari target penggalanan dana, berarti tingkat kelebihan langganan 50x)
  * Tingkatan biaya yang sesuai = 0,80% (berdasarkan tabel tingkat pajak di atas)

**Langkah-langkah:**

1. `user_allocation = 10 / 5.100 = 0,00196 (alokasi pool 0,196%)`
2. `user_pay_amount = 100 × 0,00196 = 0,196 CAKE`
3. `refund_amount = 10 − 0,196 = 9,804 CAKE`
4. `tax_amount = 9,804 × 0,008 = 0,0784 CAKE`
5. `final_refund = 9,804 − 0,0784 = ~9,72 CAKE`

**Jumlah yang diterima pengguna akhirnya**

1. **Alokasi token:** CAKE senilai 0,196 dari token mitra CAKE.PAD
2. **Pengembalian dana akhir:** \~9,72 CAKE (dari deposit 10 CAKE − 0,196 CAKE untuk alokasi token − 0,0784 CAKE pajak)
