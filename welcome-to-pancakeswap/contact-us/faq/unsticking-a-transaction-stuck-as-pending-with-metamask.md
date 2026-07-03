---
description: Cara "membuka" transaksi tertunda yang macet di MetaMask Anda
---

# Memperbaiki Transaksi Tertunda yang Macet di MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Jika transaksi Anda macet dalam status tertunda di MetaMask, dan tombol "Batal" tidak membantu, Anda mungkin perlu menggunakan metode ini untuk membersihkan antrian transaksi Anda.

Metode ini bekerja dengan pada dasarnya menimpa transaksi yang macet dengan transaksi lain yang memiliki prioritas lebih tinggi.

### **1. Aktifkan Nonce Transaksi yang Disesuaikan**

1\. Buka plugin MetaMask Anda.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Klik ikon lingkaran berwarna di kanan atas dan klik **Settings** dari menu tarik-turun.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Di menu Settings, pilih **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Gulir ke bawah hingga Anda melihat **Advanced gas controls**. Aktifkan ini ke ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Masih di pengaturan Advanced, terus gulir hingga Anda melihat **Customize transaction nonce**. Aktifkan ini ke ON.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Temukan Transaksi yang Macet**

Sekarang kita akan menemukan transaksi yang macet, dan mencatat "nonce"-nya. Itu adalah semacam pengenal, yang akan kita gunakan kembali nanti.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Kembali ke halaman utama MetaMask. Di tab "Assets", temukan jenis token dari transaksi yang macet (dalam hal ini, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6\. Di menu token, temukan transaksi **Tertunda** Anda di area Antrian. Klik transaksi Anda untuk detail lebih lanjut.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7\. Cari entri **Nonce**, dan catat angka ini.

### **3. Timpa Transaksi yang Macet**

Sekarang kita akan membuat transaksi baru untuk menggantikan yang macet. Kita akan menyesuaikan nomor Nonce, sehingga sama dengan yang baru saja Anda catat.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

8\. Buat transaksi baru untuk menggantikan transaksi yang macet. Kali ini, tingkatkan **Biaya Transaksi**. Di sini kita telah meningkatkannya dari 9 menjadi 20. Ini akan membuat transaksi Anda lebih mungkin untuk ditambahkan ke blok.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

9\. Di halaman konfirmasi, pastikan Harga Gas Anda sekarang berada pada jumlah baru yang lebih tinggi.

10\. Temukan entri **CUSTOM NONCE** dan ubah nonce ke angka yang Anda catat di langkah 7. Sekarang klik Konfirmasi.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11\. Transaksi baru Anda seharusnya sekarang diterima ke dalam blok. Untuk memverifikasi, buka MetaMask dan klik tab **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12\. Transaksi yang berhasil akan muncul di bagian atas daftar Activity Anda. Jika masih tertulis "Tertunda" dengan warna oranye, Anda perlu menunggu sedikit lebih lama, atau coba ulangi proses dengan biaya transaksi yang lebih tinggi (harga gas).

Karena tidak ada dompet yang dapat membuat dua transaksi dengan nonce yang sama, jika transaksi pengganti yang Anda buat berhasil, transaksi yang macet akan dibatalkan.<br>
