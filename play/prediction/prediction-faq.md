# FAQ Prediction

{% hint style="info" %}
Gunakan bilah samping untuk menemukan jawaban atas pertanyaan Anda dengan cepat!
{% endhint %}

## A) Pertanyaan Umum

### **1. Berapa biayanya?**

3% dari total pot setiap putaran akan masuk ke perbendaharaan, yang 100%-nya akan digunakan untuk buyback dan membakar CAKE.

### 2. Bagaimana pembayaran dihitung?

* Rasio Pembayaran untuk Pool NAIK = Total Nilai Kedua Pool ÷ Nilai Pool NAIK
* Rasio Pembayaran untuk Pool TURUN = Total Nilai Kedua Pool ÷ Nilai Pool TURUN

**Contoh - Taruhan 2 BNB "TURUN", hasil = "TURUN":**

* Sisi TURUN = 15 BNB, total pool hadiah = 150 BNB&#x20;
* Rasio pembayaran TURUN = 150 BNB / 15 BNB = 10x
* Jumlah Pembayaran = Rasio Pembayaran × Posisi × (1 - Biaya Perbendaharaan)
  * Jika Anda bertaruh 2 BNB pada TURUN, pembayaran = (2 × 10) × (1 − 0,03) = 19,4 BNB
* Keuntungan = 19,4 − 2 = 17,4 BNB

### 3. Apakah ada batas waktu sebelum saya dapat mengumpulkan kemenangan saya?

Tidak, Anda akan dapat mengumpulkan kemenangan Anda kapan saja di masa mendatang.

### 4. Berapa alamat kontrak PancakeSwap Prediction?

**BNB Chain**

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Posisi & Hasil

### 1. **Bisakah saya mengubah atau menghapus posisi saya?**

Tidak. Setelah Anda memasuki posisi, Anda TIDAK DAPAT mengubah arah, menambah, atau menghapus posisi Anda. Posisi sudah terkunci, jadi pastikan Anda 100% puas dengan arah posisi sebelum mengonfirmasi. &#x20;

### 2. Kapan pasar akan dibatalkan? Apa yang terjadi kemudian?

* **Kapan:** Kegagalan Oracle atau layanan backend, atau keadaan luar biasa lainnya.
* **Hasil:** Pengguna dapat mengklaim 100% dari jumlah taruhan awal mereka (tanpa biaya).

### 3. Hasil putaran berubah setelah putaran berakhir! Mengapa?

Terkadang, setelah putaran ditutup, hasil akhir mungkin berbeda dari hasil terakhir yang ditampilkan selama putaran berlangsung. Jika Anda menyaksikan putaran berakhir pada "TURUN", mungkin tampak berubah menjadi "NAIK" beberapa detik kemudian.

Ini karena kami menggunakan feed harga Oracle untuk menentukan hasil akhir putaran. Periode antara akhir satu putaran dan awal putaran berikutnya adalah 30 detik, tetapi Oracle diperbarui setiap 20 detik. Ada kemungkinan bahwa selama periode singkat ini, Oracle mungkin mengirimkan pembaruan sementara transaksi untuk memicu putaran berikutnya sedang ditambang. Ini dapat tampak "membalik" hasil putaran sebelumnya.

### 4. Apa itu Harga Kunci & Harga Penutupan?

* **Harga Kunci:** Harga pada awal fase LIVE.
* **Harga Penutupan:** Harga di akhir putaran, digunakan untuk menentukan pemenang.

**Contoh – Putaran 400 (BNB Prediction):**

1. **12:00–12:05:** Tempatkan Taruhan → Pengguna bertaruh 0,1 BNB pada "NAIK"
2. **12:05–12:10:** Fase Kunci → Harga Kunci = $850
3. **12:10:** Fase Tutup → Harga Penutupan = $860
4. **Hasil: Taruhan "NAIK"** menang

**Catatan:**

* Harga Oracle mungkin membutuhkan waktu hingga 20 detik untuk diperbarui.
* Kemenangan rumah: Semua taruhan masuk ke Rumah

### 5. Situasi apa yang dianggap sebagai KEMENANGAN RUMAH?

**Skenario:**

1. Tidak ada taruhan lawan dan pengguna kalah (misalnya, hanya satu pengguna bertaruh NAIK dan hasilnya = TURUN)
2. Harga Kunci = Harga Penutupan

**Yang terjadi:**

* PancakeSwap mengambil 100% pool; semua dana digunakan untuk membakar CAKE.
* Pengguna di kedua sisi kehilangan jumlah taruhan awal mereka.

**Contoh - Tidak ada taruhan lawan:**

* Pengguna A bertaruh NAIK, tidak ada taruhan TURUN, hasil = TURUN → Pengguna A kalah; 100% dana masuk ke perbendaharaan.
* Pengguna B bertaruh NAIK, tidak ada taruhan TURUN, hasil = NAIK → Pengguna B mendapatkan kembali 97% dari deposito.



## C) Jeda Pasar

### 1. Apa artinya ketika pasar dijeda?

Pasar dijeda ketika ada kondisi yang memengaruhi keandalan kontrak. Pasar yang dijeda berarti tidak ada taruhan yang akan berlangsung untuk putaran apa pun.

### 2. Apa yang menyebabkan pasar PancakeSwap Prediction dijeda?

Pasar Prediksi akan dijeda dalam kondisi berikut:

1. Kontrak Prediksi tidak dapat memperoleh harga dari oracle ChainLink karena oracle belum memposting harga pada saat putaran berakhir.
2. Kontrak Prediksi tidak dapat mengeksekusi tindakan (mengakhiri putaran atau mendapatkan harga dari oracle) karena transaksi terjebak dalam mempool lebih dari 15 blok.
3. PancakeSwap telah memutuskan untuk menghentikan Prediksi untuk pasar/aset tersebut.

### 3. Apa yang terjadi pada posisi saya jika pasar dijeda?

Jika pasar dijeda sementara Anda memiliki posisi live, dana Anda akan tersedia untuk diklaim kembali, dengan cara yang sama seperti Anda biasanya mengklaim kemenangan.

Untuk mengklaim kembali dana, Anda perlu membayar beberapa biaya gas. Kami tidak dapat mengompensasi Anda untuk biaya gas, jadi harap pertimbangkan risiko kecil ini sebelum berpartisipasi.

### 4. Kapan pasar akan dilanjutkan setelah dijeda?

Pasar akan dilanjutkan ketika seorang admin (salah satu chef) secara manual melanjutkan pasar.



## D) Pemecahan Masalah & Klaim

### 1. Bagaimana cara mengklaim kemenangan lama dari pasar CAKEUSD di BNB Chain?&#x20;

* Buka [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc)
* Periksa tab riwayat untuk kemenangan putaran historis

### 2. Mengapa saya tidak dapat melihat kemenangan saya di dompet?

Ketika Anda mengumpulkan kemenangan, kemenangan tersebut mungkin tidak muncul di log transaksi dompet Anda seperti biasa.\
Ini karena menggunakan jenis transaksi yang berbeda: Transaksi Internal.\
Masukkan alamat dompet Anda di BscScan, lalu periksa tab "Internal Txns" untuk mengonfirmasi bahwa kemenangan telah tiba.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. Mengapa hasil putaran saya tidak ditampilkan?

Ada buffer 15 blok pada setiap putaran, yang dapat menyebabkan penundaan hingga 45 detik setelah akhir putaran.\
Buffer ini untuk mengakomodasi fakta bahwa kami mungkin tidak dapat mengambil harga secara andal dan mengakhiri putaran segera: berbagai faktor blockchain memengaruhi kecepatan konfirmasi transaksi di jaringan.

### 4. Saya tidak dapat mengumpulkan kemenangan, apa yang harus saya lakukan?

Pastikan Anda memiliki cukup BNB di dompet untuk membayar biaya gas. Anda memerlukan sedikit BNB untuk memicu smart contract.

### **5. Bagaimana jika saya tidak dapat mengklaim kemenangan dari situs web?**

Anda mungkin dapat mengklaim kemenangan langsung dari kontrak. Ikuti langkah-langkah di 3 tab di bawah ini.

{% tabs %}
{% tab title="Periksa putaran yang Anda mainkan" %}
Cara memeriksa riwayat putaran yang Anda mainkan

1. Buka halaman BscScan dari [kontrak Prediction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (misalnya BNBUSD).
2. Gulir ke bawah ke "8. getUserRounds".
3. Ketikkan alamat dompet Anda di bawah "user(address)".
4. Atur "cursor(uint256)" ke 0 dan "size(uint256)" ke 1000.
5. Ketuk "Query"
6. Putaran yang Anda masuki akan ditampilkan di bawah di baris pertama. (setelah "uint256\[]:")
{% endtab %}

{% tab title="Periksa apakah Anda dapat mengklaim" %}
Pertama, periksa apakah Anda seharusnya benar-benar dapat mengklaim dari putaran yang Anda mainkan.

1. Buka halaman BscScan dari [kontrak Prediction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (misalnya BNBUSD), dan buka tab Read
2. Gulir ke bawah ke "4. claimable".
3. Ketikkan id putaran yang ingin Anda periksa di bawah "epoch(uint256)".
4. Ketikkan alamat dompet Anda di bawah "user(address)".
5. Ketuk "Query"
6. Jika putaran dapat diklaim, akan ditampilkan "true".
7. Jika hasilnya "false". Harap ulangi langkah-langkah di atas dan coba dengan "19. refundable".&#x20;
8. Catatan: ⬆️ Jika Anda melihat putaran mengembalikan "false" pada "4. claimable" dan "19. refundable", tetapi ditampilkan di situs web, kemungkinan sudah diklaim dan situs web masih tertinggal.
{% endtab %}

{% tab title="Klaim dari putaran" %}
Cara mengklaim

1. Buka halaman BscScan dari [kontrak Prediction](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) (misalnya BNBUSD), dan buka tab Write
2. Ketuk "🔴 Connect to Web3"
3. Gunakan MetaMask atau WalletConnect untuk terhubung.
4. Gulir ke bawah ke "3. claim"
5.  Ketikkan nomor putaran yang ingin Anda klaim dalam format ini, termasuk tanda kurung \[]: `[12345]`&#x20;

    Jika Anda ingin mengklaim dari beberapa putaran sekaligus, pisahkan putaran dengan koma seperti ini: `[12345,12346,12347]`
6. Ketuk "Write"
7. Konfirmasi di dompet&#x20;
{% endtab %}
{% endtabs %}
