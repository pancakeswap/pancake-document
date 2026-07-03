# Agen Referensi — Agen Penyelesaian Order/Intent

> Agen Provider ERC-8183 yang memenuhi satu Job swap-intent sekaligus dengan merutekannya melalui agregasi PancakeSwap dan mengirimkan token target langsung ke Client.

### 0. Pemetaan ke ERC-8183

ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation) mendefinisikan **Job** dengan tiga peran dan status Open → Funded → Submitted → Terminal. **BNBAgent SDK** dari BNB adalah implementasi langsungnya.

| Peran                                                        | Dalam agen ini                                                                                                                                     |
| ------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Client** (Agent-A)                                         | memposting swap intent: "tukarkan X dari token A → token B, kirimkan ≥ `minOut`", meng-escrow input beserta tip                                    |
| **Provider** (Agent-B) — **ini adalah agen referensi kita** | mengutip melalui **agregasi PancakeSwap**, dan jika bisa memenuhi/melampaui `minOut`, mengeksekusi swap dan mengirimkan token B ke Client           |
| **Evaluator**                                                | memverifikasi bahwa Client menerima jumlah token-B ≥ `minOut`; melepaskan tip (atau mengembalikan dana ke Client)                                  |

Hasil yang dapat diverifikasi bersifat objektif ("apakah Client menerima ≥ `minOut`?"), itulah mengapa ini cocok dengan ERC-8183 di mana rebalancer tidak cocok.

***

### 1. Tujuan & lingkup satu kalimat

> Agen **Provider** yang memenuhi satu Job swap-intent sekaligus dengan merutekannya melalui agregasi PancakeSwap dan mengirimkan token target langsung ke Client — tidak lebih dari itu.

***

### 2. Yang DIIZINKAN dilakukan agen (daftar izin kapabilitas)

| # | Kapabilitas              | Antarmuka                                                        | Catatan                                                                               |
| - | ------------------------ | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| A | Menemukan Job terbuka    | BNBAgent SDK (registri ERC-8183)                                 | Hanya-baca; filter ke Job swap-intent yang dapat dilayani                             |
| B | Mengutip rute            | **Agregasi PancakeSwap** (Aggregator API / Smart Router)         | Hanya-baca; harga terbaik di seluruh V3                                               |
| C | Menerima Job             | BNBAgent SDK (Funded → committed)                                | Hanya jika kutipan terbaru ≥ `minOut` dan tip ≥ batas minimum                        |
| D | Mengeksekusi swap        | Router PancakeSwap                                               | Input ditarik dari escrow Job; **penerima output = Client**, dalam satu tx            |
| E | Mengirimkan hasil        | BNBAgent SDK (→ Submitted)                                       | Hash transaksi penyelesaian sebagai bukti                                             |
| F | Mengklaim tip            | Escrow ERC-8183 / x402                                           | Hanya setelah Evaluator menandai Job sebagai Terminal                                 |

**Output dari setiap penyelesaian langsung dikirimkan ke Client. Satu-satunya penghasilan agen adalah tip dari Job.**

***

### 3. Batasan keras (gerbang untuk fitur)

| Batasan                                     | Aturan                                                                                                                                                                |
| ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Jangan pernah menerima yang tidak bisa dipenuhi** | Terima Job hanya jika kutipan _terbaru_ memenuhi `minOut`. Jika tidak, biarkan Job Funded untuk Provider lain.                                                  |
| **Kutip ulang saat eksekusi**               | Kutip ulang segera sebelum penyelesaian; batalkan jika rute tidak lagi memenuhi `minOut` (tidak ada kutipan kadaluarsa).                                              |
| **Penyelesaian atomik**                     | Tarik-dari-escrow → swap → kirim ke Client dalam **satu transaksi**, penerima output = Client. Agen tidak boleh menahan dana Client melewati langkah yang gagal.      |
| **Slippage**                                | Slippage eksekusi dibatasi; jumlah yang dikirimkan harus tetap ≥ `minOut` setelah Slippage, atau tx akan revert. Jangan pernah `amountOutMin = 0`.                   |
| **Tenggat waktu**                           | Tenggat waktu singkat pada tx penyelesaian (≤ 5 menit); hormati tenggat waktu Job sendiri.                                                                           |
| **Tip minimum / nilai maksimum**            | Jangan menerima Job di bawah batas minimum tip atau di atas batas nilai per-Job.                                                                                     |
| **Daftar aman token**                       | Hanya melayani Job yang tokennya ada di daftar token PancakeSwap (anti-honeypot / token palsu).                                                                      |
| **Konkurensi satu-Job (v1)**                | Selesaikan satu Job sekaligus; tidak ada komitmen berlebih.                                                                                                           |
| **Prasyarat gas**                           | Pastikan BNB cukup untuk penyelesaian penuh sebelum menerima.                                                                                                        |
| **Idempoten**                               | Jangan pernah mengirimkan ulang atau memenuhi kembali Job yang sudah Submitted/Terminal.                                                                             |

Jika aturan mana pun tidak dapat dipenuhi, **lewati Job** — jangan paksakan penyelesaian.

***

### 4. Di luar lingkup — agen TIDAK BOLEH

1. **Menggunakan dana Client untuk selain swap yang ditentukan.** Penerima output selalu Client.
2. **Menggunakan inventaris sendiri / mengambil risiko principal.** v1 adalah **hanya-tarik-escrow** — ia merutekkan input Client yang di-escrow; tidak mengisi dari saldo sendiri.
3. **Merutekkan melalui kontrak non-PancakeSwap atau yang tidak terverifikasi**, atau menyelesaikan di luar agregasi PancakeSwap.
4. **Melayani Job dengan token yang tidak ada di daftar aman**, atau (v1) token scaled-UI / RWA apa pun (§5).
5. **Menggunakan leverage, perps, margin, atau pinjaman.**
6. **Mengirimkan hasil yang tidak benar-benar dipenuhi** (tidak ada attestasi palsu) atau **mengevaluasi Job sendiri** (konflik kepentingan).
7. **Memanggil fungsi owner/admin** pada kontrak PancakeSwap atau ERC-8183.
8. **Menyimpan persetujuan token tetap** melampaui satu penyelesaian; batasi persetujuan ke jumlah Job.

***

### 5. Logika khusus PancakeSwap (kebenaran aplikasi)

* **Rutekkan melalui agregasi PancakeSwap**, bukan satu pool — eksekusi terbaik di seluruh V2 / V3 / Stable adalah proposisi nilai utamanya ("harga terbaik memenangkan tip").
* **Kirimkan secara atomik ke Client** dengan mengatur `recipient` router ke alamat Client; jangan pernah dua langkah "swap ke diri sendiri, lalu transfer."
* **Kesegaran kutipan** — harga on-chain bergerak antara penemuan dan penyelesaian; kutip ulang saat eksekusi (batasan §3).
* **`minOut` dalam satuan mentah.** Untuk **token scaled-UI / ERC-8056** (Binance Stock Tokens / ekuitas RWA) mentah ≠ yang ditampilkan; penanganan yang salah akan menyebabkan pengiriman yang tidak tepat secara diam-diam. **Kecualikan token scaled-UI dari v1** sampai tim teknik mengkonfirmasi penanganan satuan mentah secara menyeluruh.
* **Minimum Slippage** pada swap penyelesaian harus diturunkan sehingga jumlah yang _dikirimkan_ ≥ `minOut`, dengan memperhitungkan pembagian tip/biaya.

***

### 6. Perilaku kegagalan & pemulihan

* **Kutipan gagal `minOut` saat eksekusi** → batalkan sebelum/secara atomik dengan penarikan escrow; Job tetap Funded untuk Provider lain. Tidak ada status parsial.
* **Sudah Submitted/Terminal** → lewati (idempoten).
* **Tx penyelesaian revert** → Job tetap dapat diklaim oleh pihak lain; agen mencatat kegagalan dan melanjutkan.
* **Kegagalan berulang pada satu Job** → masukkan Job ke daftar hitam lokal dan kirim peringatan, alih-alih mencoba ulang dalam loop.

***

### 7. Titik integrasi (bagian BNB / ERC-8183)

Ini disediakan oleh BNB Agent Studio / BNBAgent SDK, bukan dibangun oleh PancakeSwap — tetapi spesifikasi bergantung padanya:

* **Siklus hidup Job** (temukan Open → terima Funded → Submitted → klaim) melalui BNBAgent SDK.
* **Identitas Provider** melalui ERC-8004.
* **Escrow + pembayaran** melalui escrow ERC-8183 / x402.
* **Evaluator** — predikat harus berupa "saldo token-B Client meningkat sebesar ≥ `minOut`." Konfirmasi dengan BNB **siapa yang menjalankan Evaluator** (netral/protokol vs. Client) dan bahwa predikat dapat ditegakkan on-chain.

***

### 8. Postur v1 yang direkomendasikan & keputusan terbuka

1. **Hanya-tarik-escrow, satu Job sekaligus, hanya token-safelist, tidak ada token scaled-UI.** Permukaan aman terkecil untuk diluncurkan.
2. **Konfirmasi antarmuka swap PancakeSwap** — **Aggregator (`aggr`) HTTP API** vs **Smart Router SDK**. Catatan Jerry menyebutkan "gunakan pcs aggr api"; perlu dikonfirmasi mana yang dipanggil agen, karena ini mengubah integrasi (dan apakah panduan memerlukan bagian agregasi).
3. **Konfirmasi mekanisme escrow** dengan BNB — apakah Provider dapat menarik input Client yang di-escrow untuk merutekkan swap, dan apakah pengiriman-ke-Client dapat ditegakkan sebagai hasil yang dapat diverifikasi?
4. **Konfirmasi pemilik Evaluator dan predikat** (§7).

> Persetujuan teknik sebelum peluncuran: perutean atomik tarik-escrow → swap → kirim-ke-Client; kutip-ulang-saat-eksekusi; matematika `minOut`-setelah-Slippage; penegakan daftar aman; penanganan Job idempoten.
