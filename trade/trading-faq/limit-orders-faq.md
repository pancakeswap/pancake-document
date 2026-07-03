# FAQ

{% hint style="info" %}
Gunakan bilah sisi untuk menemukan jawaban atas pertanyaan Anda dengan cepat!
{% endhint %}

## Limit Order dan TWAP

Silakan merujuk ke FAQ yang disediakan oleh Orbs:

[https://www.orbs.com/dtwap-and-dlimit-faq/](https://www.orbs.com/dtwap-and-dlimit-faq/)

## Limit V2 (Tidak Lagi Didukung)

### Mengapa saya tidak dapat menemukan order saya?

Limit order V2 kini tidak lagi didukung, silakan akses menggunakan tautan ini:

[https://pancakeswap.finance/limit-orders](https://pancakeswap.finance/limit-orders)

### Mengapa order saya tidak dieksekusi?

Limit order dieksekusi ketika mencapai harga yang diinginkan, namun, karena fluktuasi gas, harga eksekusi aktual mungkin berbeda dari harga yang Anda tentukan pada antarmuka. Biasanya, harga eksekusi dan harga yang diinginkan seharusnya hampir identik, namun, jika Anda mengirimkan order yang sangat kecil (\~<$1.000), harga eksekusi mungkin sedikit lebih tinggi untuk memperhitungkan biaya.

Oleh karena itu order Anda mungkin tidak dieksekusi karena:

* Tidak memungkinkan untuk mengisi seluruh order pada harga dan jumlah yang diinginkan karena dampak harga.
* Salah satu token dalam limit order memiliki biaya saat transfer (lihat di bawah).

**Sebelum mengirimkan order, harap periksa UI yang menampilkan harga eksekusi sebenarnya.**

{% hint style="info" %}
Harap diperhatikan: tabel riwayat order mengambil data dari Subgraph dan dapat menampilkan informasi yang sedikit tertunda.
{% endhint %}

### Bisakah saya mengirimkan limit order untuk token dengan biaya saat transfer?

**Tidak.** Token dengan biaya saat transfer tidak boleh digunakan dengan limit order. Lanjutkan dengan risiko Anda sendiri.

### Bagaimana cara mengatur Slippage saat menggunakan limit order?

Slippage tidak relevan dalam limit order. Anda menentukan jumlah input (misalnya 1000 CAKE) dan jumlah output (misalnya 20 BNB). Limit order menjamin bahwa Anda akan menerima tidak kurang dari jumlah output yang ditentukan (20 BNB) untuk jumlah input Anda (1000 CAKE) jika harga pasangan mencapai harga yang diinginkan. **Perhatikan bahwa token dengan biaya saat transfer tidak boleh digunakan dengan limit order** (baca di atas)

### Harga eksekusi sebenarnya menunjukkan "tidak pernah dieksekusi". Apa artinya ini?

Ini pada dasarnya berarti Anda mencoba menukar jumlah token yang sangat kecil sehingga tidak ada cukup token untuk diperhitungkan sebagai biaya gas. Secara umum, Anda perlu meningkatkan jumlah pada kolom "input" untuk menghilangkan kesalahan ini.

### Apakah ada tanggal kedaluwarsa untuk limit order saya?

Order terbuka memiliki tanggal kedaluwarsa 90 hari. Setelah order Anda kedaluwarsa, mungkin tidak akan pernah dieksekusi. Harap batalkan order Anda setelah kedaluwarsa.

Fitur tanggal kedaluwarsa yang dapat dikustomisasi direncanakan untuk waktu dekat.

### Mengapa saya tidak bisa membuat limit order di bawah harga pasar?

Untuk menjual di bawah harga pasar, Anda memerlukan **Stop Limit Order**, bukan limit order. Fitur Stop Limit Order segera hadir.

### Saya membuat order dan tidak ditampilkan di tabel order atau terjebak dalam status "tertunda".

Riwayat order berasal dari subgraph dan oleh karena itu mungkin menampilkan informasi yang sedikit tertunda. Biasanya, keterlambatan tidak lebih dari beberapa menit dalam kondisi terburuk. Silakan merujuk ke indikator subgraph di sudut kanan bawah tabel riwayat order.
