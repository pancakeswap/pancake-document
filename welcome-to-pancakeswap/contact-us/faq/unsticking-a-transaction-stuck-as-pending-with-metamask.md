---
description: Cara "melepaskan" transaksi tertunda yang tersangkut di MetaMask Anda
---

# Memperbaiki Transaksi Pending yang Tersangkut di MetaMask

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-fix-a-stuck-transaction-header.png)

Jika transaksi Anda tersangkut dalam status pending di Metamask, dan tombol “Cancel” tidak membantu, Anda mungkin perlu menggunakan metode ini untuk membersihkan antrean tertunda Anda.

Metode ini bekerja dengan cara menimpa transaksi yang tersangkut dengan transaksi lain yang berprioritas lebih tinggi.

### **1. Aktifkan Nonce Transaksi Kustom**

1\. Buka plugin MetaMask Anda.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-1-MetaMask_plugin.png)

2\. Klik ikon lingkaran berwarna di kanan atas, lalu klik **Settings** dari menu tarik-turun.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-2-MetaMask_settings%20%281%29.png)

3\. Di menu Settings, pilih **Advanced**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-3-MetaMask_advanced.png)

4\. Gulir ke bawah hingga Anda melihat **Advanced gas controls**. Aktifkan opsi ini (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

5\. Masih di pengaturan Advanced, terus gulir hingga Anda melihat **Customize transaction nonce**. Aktifkan opsi ini (ON).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/1-4-MetaMask_gas_control_on.png)

### **2. Temukan Transaksi Anda yang Tersangkut**

Sekarang kita akan menemukan transaksi yang tersangkut, dan mencatat “nonce”-nya. Nonce adalah semacam pengenal, yang akan kita gunakan kembali nanti.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6\. Kembali ke halaman utama MetaMask. Di tab “Assets”, temukan jenis token dari transaksi Anda yang tersangkut (dalam contoh ini, CAKE).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

7\. Di menu token, temukan transaksi **Pending** Anda di area Queue. Klik transaksi Anda untuk melihat detail lebih lanjut.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

8\. Cari entri **Nonce**, dan catat angka tersebut.

### **3. Timpa Transaksi yang Tersangkut**

Sekarang kita akan membuat transaksi baru untuk menggantikan transaksi yang tersangkut. Kita akan mengatur nomor Nonce secara kustom, agar sama dengan nomor yang baru saja Anda catat.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28176%29.png)

9\. Buat transaksi baru untuk menggantikan transaksi Anda yang tersangkut. Kali ini, naikkan **Transaction Fee**. Di sini kami menaikkannya dari 9 menjadi 20. Hal ini akan membuat transaksi Anda lebih mungkin dimasukkan ke dalam blok.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2834%29.png)

10\. Di halaman konfirmasi, pastikan Gas Price Anda kini berada pada jumlah baru yang lebih tinggi.

11\. Temukan entri **CUSTOM NONCE** dan ubah nonce menjadi angka yang Anda catat pada langkah 8. Sekarang klik Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

12\. Transaksi baru Anda seharusnya kini diterima ke dalam blok. Untuk memeriksanya, buka MetaMask dan klik tab **Activity**.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

13\. Transaksi Anda yang telah selesai seharusnya tampil di bagian atas daftar Activity Anda. Jika masih tertulis “Pending” berwarna oranye, Anda perlu menunggu sedikit lebih lama, atau mencoba proses ini lagi dengan biaya transaksi (gas price) yang lebih tinggi.

Karena tidak ada dompet yang dapat membuat dua transaksi dengan nonce yang sama, jika transaksi pengganti yang Anda buat berhasil, transaksi Anda yang tersangkut akan dibatalkan.<br>
