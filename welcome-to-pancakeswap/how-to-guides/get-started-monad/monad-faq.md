# FAQ Monad

#### 1. Tingkatan biaya apa saja yang tersedia di pool Likuiditas PancakeSwap?

**Tingkatan Biaya yang Didukung:**

* Tingkatan biaya berikut tersedia untuk pool V3 (likuiditas terkonsentrasi): `0.01%, 0.05%, 0.25%, 1%`&#x20;
* Untuk pool V2 hanya tingkatan biaya 0.25% yang didukung

#### 2. Apakah siapa saja dapat membuat pool?

Ya. Pembuatan pool bersifat tanpa izin, dengan beberapa pengecualian:

* Hanya satu pool yang dapat ada untuk kombinasi **pasangan token + tingkatan biaya** tertentu (misalnya hanya satu pool WMON <> USDC 0.05% yang dapat ada pada satu waktu)

#### 3. Berapa lama pool yang baru dibuat akan muncul?

* Pool biasanya muncul dalam daftar pool sekitar **5 menit** setelah pembuatan.
* Jika tidak muncul:
  * Gunakan **bilah pencarian** untuk menemukan secara manual.
  * Pool mungkin difilter dari daftar karena **TVL yang rendah**.

#### 4. Mengapa APR atau TVL pool saya masih menampilkan nol?

Ini adalah hal yang wajar terjadi segera setelah pool baru dibuat:

* Data APR dan TVL hanya akan muncul setelah **setidaknya satu Swap** telah terjadi di pool tersebut.
* Setelah Swap terjadi, metrik-metrik ini akan mulai ditampilkan dalam sekitar **15 menit**.

#### **5. Mengapa transaksi saya kadang gagal jika saldo Dompet saya kurang dari 10 MON?**

Monad memiliki aturan bahwa setiap akun harus menyimpan **buffer keamanan minimum sebesar 10 MON**. Jika saldo Anda rendah dan Anda mengirim terlalu banyak transaksi terlalu cepat, jaringan mungkin **berhenti menerima yang baru**.

#### **6. Mengapa 1–2 transaksi pertama berhasil, tetapi transaksi berikutnya gagal?**

Monad memproses blok menggunakan tampilan saldo Anda yang sedikit "tertinggal". Jadi:

* Transaksi **pertama** Anda biasanya baik-baik saja.
* Transaksi **kedua** Anda mungkin juga berhasil.
* Tetapi jika Anda mengirim **beberapa transaksi dalam waktu singkat**, jaringan berpikir Anda mungkin tidak memiliki MON yang cukup untuk membayar semua biaya gas.

Sehingga jaringan **memblokir** transaksi berikutnya. Ini normal dan merupakan bagian dari sistem keamanan.

#### **7. Mengapa tampaknya lebih ketat pada akun pintar (contract wallet)?**

Akun pintar mengikuti **aturan yang lebih ketat**:

* Mereka harus **selalu** menyimpan setidaknya **10 MON** saat menjalankan kode kontrak.
* Jika akun pintar Anda di bawah 10 MON, transaksi dapat **langsung dibatalkan**, bahkan jika EOA masih berfungsi untuk beberapa transaksi.

Inilah mengapa pengguna akun pintar melihat kegagalan lebih cepat.

#### **8. Apakah ini berarti saya tidak bisa menggunakan Monad dengan kurang dari 10 MON?**

Anda _masih dapat_ menggunakannya, terutama dengan EOA biasa — tetapi:

* Jangan mengirim beberapa transaksi secara berturut-turut.
* Tunggu beberapa blok di antara transaksi.
* Simpan sedikit MON di Dompet Anda untuk menghindari masalah.

#### **9. Bagaimana cara menghindari kegagalan ini?**

Tips sederhana:

* Simpan **10 MON atau lebih** di Dompet Anda jika memungkinkan.
* Jika MON Anda rendah, **beri jarak antar transaksi** (jangan mengirim secara beruntun).
* Pengguna akun pintar sebaiknya menyimpan **sedikit lebih dari 10 MON**, karena pemanggilan kontrak menggunakan gas ekstra.
