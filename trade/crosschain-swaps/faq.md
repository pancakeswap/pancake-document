# ❓ FAQ

### 1. Bagaimana toleransi Slippage bekerja untuk Crosschain Swap?

Untuk Crosschain Swap, persentase toleransi Slippage yang Anda pilih diterapkan secara independen untuk Swap di jaringan sumber maupun tujuan.

**Contoh:**

* Tukar BNB di BNB Chain ke ARB di Arbitrum
* Toleransi Slippage diatur ke 1%
* Rutenya bisa berupa:
  1. Tukar BNB ke USDC di BNB Chain
  2. Bridge USDC dari BNB Chain ke Arbitrum melalui Across
  3. Tukar USDC ke ARB di Arbitrum
* Dalam hal ini, toleransi Slippage 1% diterapkan secara terpisah untuk:
  * Swap di BNB Chain
  * Swap di Arbitrum

Ini memastikan Anda terlindungi dari pergerakan harga yang berlebihan di kedua bagian transaksi, sementara proses Bridging itu sendiri tidak terpengaruh oleh pengaturan Slippage.

### 2. Apa yang terjadi jika transaksi saya gagal?

Jika Crosschain Swap Anda mengalami kegagalan pada tahap mana pun, berikut cara penanganannya:

1.  **Kegagalan Swap/Transaksi di Jaringan Sumber**

    ➝ Anda akan segera menerima kembali token asli Anda di jaringan sumber.
2.  **Kegagalan Transaksi Bridge**

    ➝ Across akan memproses pengembalian dana dalam 90 menit hingga 2 jam, dan Anda akan menerima kembali aset yang di-bridge di jaringan sumber. Sementara Relay memproses pengembalian dana dalam satu menit untuk skenario antara SOL <> EVM.
3.  **Kegagalan Swap di Jaringan Tujuan**

    ➝ Anda akan menerima aset yang di-bridge di jaringan tujuan, tanpa Swap akhir ke token target Anda.

{% hint style="info" %}
**Catatan:** Anda selalu dapat memeriksa status transaksi Anda melalui tab riwayat transaksi di bawah antarmuka penghubung dompet.
{% endhint %}

### 3. Apakah Crosschain Swap saya dilindungi dari MEV?

MEV Guard hanya didukung di BNB Chain ketika Swap dimulai langsung dari dompet yang terhubung dengan MEV Guard diaktifkan.

* Jika Crosschain Swap Anda melibatkan Swap di BNB Chain sebagai jaringan sumber, dan Anda mengaktifkan MEV Guard, maka Swap tersebut akan dilindungi dari MEV.
* Jika BNB Chain adalah jaringan tujuan, Swap dieksekusi oleh relayer/sistem Bridging dan tidak akan dilindungi dari MEV, karena tidak dimulai dari dompet yang terhubung milik Anda.

{% hint style="info" %}
**Catatan:** Jaringan lain seperti Arbitrum dan Base saat ini tidak mendukung perlindungan MEV Guard di PancakeSwap.
{% endhint %}

### 4. Bisakah saya menukar stablecoin antar jaringan?

Ya — Anda dapat menukar dan melakukan Bridge stablecoin seperti USDC, USDT, dan DAI secara langsung antara jaringan yang didukung.

Anda memiliki dua pilihan:

1.  **Bridge Langsung:**

    Lakukan Bridge stablecoin yang didukung (seperti USDC, USDT, dll.) langsung dari satu jaringan ke jaringan lain.
2.  **Tukar ke Token Lain:**

    Anda juga dapat menukar stablecoin ke token lain yang didukung di jaringan tujuan menggunakan pool likuiditas PancakeSwap — baik sebelum maupun setelah Bridging.

{% hint style="info" %}
**Catatan:** Stablecoin yang didukung untuk Bridge langsung dapat bervariasi per jaringan.
{% endhint %}

### 5. Apakah Swap saya akan menggunakan PCSX?

Tidak — PCSX tidak didukung untuk melayani Crosschain Swap.

Crosschain Swap di PancakeSwap secara eksklusif dirutekan melalui:

* **Pool likuiditas PancakeSwap** (v2, v3, Infinity, StableSwap) untuk Swap on-chain, dan
* **Protokol Across & Relay** untuk Bridging aset antar jaringan.

PCSX tidak dapat digunakan untuk memfasilitasi atau merutekan bagian mana pun dari transaksi Crosschain Swap.

### 6. Apakah ada batas minimum atau maksimum jumlah Swap?

Ya — batas minimum dan maksimum berlaku untuk transaksi Cross-chain.

* **Batas Maksimum:**\
  Bergantung pada likuiditas Bridge yang tersedia untuk token dan jaringan yang dipilih. Nilai ini dapat berfluktuasi secara real-time berdasarkan kondisi jaringan dan likuiditas.
* **Batas Minimum:**\
  Ditetapkan untuk memastikan secara ekonomis layak bagi relayer untuk memproses transaksi Bridge.

{% hint style="info" %}
**Catatan:** Batas min dan maks yang tepat bervariasi per token Bridge. Jika jumlah transaksi Anda berada di luar rentang yang diizinkan, antarmuka akan menampilkan pesan kesalahan yang jelas dan meminta Anda untuk menyesuaikan jumlah.
{% endhint %}
