# 🎁 Pancake Gifts

### 🎯 Apa itu Pancake Gifts?

**Pancake Gifts** memungkinkan siapa saja mengirim token — termasuk gas opsional — kepada teman, pengguna, atau komunitas hanya menggunakan **tautan** atau **kode QR**. Pengalaman yang sederhana, aman, dan tanpa gas bagi penerima.

Dibangun untuk membuat orientasi ke kripto semudah mengirim pesan — tanpa perlu mengisi dompet, tanpa bridging, tanpa biaya awal.

### 🤝 Mengapa Kami Membangun Pancake Gifts

Orientasi ke Web3 masih penuh hambatan. Pengguna baru sering menyerah sebelum bahkan memulai karena:

* **Tidak ada gas di dompet** → Tidak dapat melakukan tindakan apa pun di jaringan
* **Tidak ada dana di rantai yang benar** → Bridging diperlukan sebelum menggunakan dApp
* **Perlu membeli kripto hanya untuk memulai** → Memerlukan pendaftaran ke Bursa Terpusat atau fiat on-ramp

Pancake Gifts menghilangkan hambatan ini dengan:

* ✅ **Menyertakan token gas asli** dalam hadiah sehingga penerima dapat langsung berinteraksi
* ✅ **Mensponsori biaya gas di muka** (pengirim membayar biaya kecil)
* ✅ **Memungkinkan klaim melalui tautan atau kode QR sederhana** — tanpa orientasi yang rumit



Ini adalah alat untuk:

* Pengguna baru yang memulai di jaringan
* Komunitas berbasis Web3 yang ingin **meningkatkan adopsi, memberi hadiah kepada pengguna, atau menjalankan kampanye** dengan cara yang lebih ramah

***

### ⚙️ Ringkasan Fitur

| Fitur                       | Deskripsi                                                                |
| --------------------------- | ------------------------------------------------------------------------ |
| **Dukungan Rantai**         | BNB Chain (peluncuran awal)                                              |
| **Jenis Kode Hadiah**       | Tautan **atau** Kode QR                                                  |
| **Sekali Pakai**            | Setiap kode hanya dapat diklaim sekali                                   |
| **Dukungan Token**          | Maks 2 token: 1 BEP-20 (wajib), 1 token gas asli (opsional)             |
| **Jumlah Kustom**           | Atur nilai berbeda per token                                             |
| **Biaya Gas Klaim Hadiah**  | Pengirim membayar gas di muka (\~$0,05 dalam BNB)                        |
| **Riwayat Hadiah**          | Pengguna dapat melihat semua hadiah yang dikirim, status klaim, kedaluwarsa |
| **Pemeriksaan Keamanan**    | Token dengan biaya transfer dan logika kompleks tidak diizinkan          |

### 🚫 Keterbatasan

1. **Satu hadiah per kode** — Pemberian hadiah massal belum didukung.
2. **Hadiah tidak dapat dipulihkan** — Setelah dibatalkan atau kedaluwarsa, tidak dapat digunakan kembali.
3. **Token yang tidak didukung diblokir** — Token dengan biaya transfer atau logika khusus akan menampilkan kesalahan saat pembuatan.
4. **Klaim yang gagal dicoba ulang** — Backend mencoba ulang beberapa kali. Jika masih gagal, hadiah ditandai sebagai **tidak dapat diklaim** dan harus dibatalkan secara manual untuk mengambil kembali dana.
5. **Hadiah harus diklaim di rantai yang sama** — misalnya hadiah ETH harus diklaim di Ethereum. Klaim lintas rantai belum didukung.

***

### 🕒 Logika Pembatalan & Kedaluwarsa

Hadiah mengikuti siklus hidup yang ditentukan berdasarkan status dan waktu:

#### Pembatalan Manual

* **Pembuat** dapat membatalkan hadiah apa pun yang masih **belum diklaim** dan **dalam jendela kedaluwarsa**.
* Token (dikurangi Biaya Gas Klaim Hadiah awal) akan dikembalikan ke pengirim.
* Hadiah yang dibatalkan **tidak dapat** diaktifkan kembali atau digunakan kembali.

#### Kedaluwarsa Otomatis

* Hadiah **secara otomatis kedaluwarsa** setelah periode yang ditentukan pengguna (bawaan: 7 hari).
* Token yang belum diklaim akan **secara otomatis dikembalikan** ke dompet pengirim.
* Hadiah yang kedaluwarsa juga tidak dapat digunakan kembali.

***

### 🔄 Status Hadiah & Artinya

| Status           | Deskripsi                                                                          |
| ---------------- | ---------------------------------------------------------------------------------- |
| **Menunggu**     | Hadiah telah dibuat dan menunggu klaim                                             |
| **Diklaim**      | Hadiah berhasil diklaim oleh penerima                                              |
| **Dibatalkan**   | Hadiah dibatalkan secara manual oleh pengirim                                      |
| **Kedaluwarsa**  | Hadiah melewati waktu kedaluwarsa tanpa diklaim                                    |
| **Tidak Dapat Diklaim** | Jumlah percobaan ulang melebihi batas; hadiah perlu dibatalkan untuk mengambil kembali dana |

***

### ⚠️ Penanganan Kesalahan & Kasus Khusus

1. **Token yang Tidak Didukung**
   * Pembuatan hadiah diblokir untuk token dengan biaya transfer atau logika khusus.
2. **Ketidakcocokan Gas**
   * Jika **biaya gas klaim aktual ≥** biaya yang dibayar di muka oleh pengirim, klaim gagal otomatis untuk mencegah penggunaan berlebihan. Ini akan dicoba ulang setelah tingkat biaya gas dalam jangkauan.
3. **Percobaan Klaim yang Gagal**
   * Percobaan ulang akan dilakukan setelah klaim pertama yang gagal.
   * Jika masih gagal:
     * Penerima melihat "Tidak Dapat Diklaim"
     * Pengirim harus membatalkan hadiah secara manual untuk mengambil kembali dana dan penerima harus meminta kode hadiah baru.
