---
hidden: true
---

# FAQ Berbagi Pendapatan

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### Bagaimana cara menghitung bagian (rCAKE)? <a href="#id-50b7c683-feb0-47f6-809f-39c1a0976bb5" id="id-50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

Pada setiap distribusi mingguan, bagian setiap pengguna dihitung ulang berdasarkan:

1. Jumlah CAKE terkunci yang mereka miliki
2. Sisa durasi kunci dari CAKE terkunci mereka yang dibulatkan ke bawah ke minggu, dan waktu kunci maksimum yang diizinkan (saat ini 52 minggu)

Misalnya:

Jika pengguna memiliki 50 CAKE terkunci dan sisa waktu kunci adalah 10,3 minggu, maka pengguna memiliki `50 * (10 / 52 ) ~= 9,61` bagian.

### Saya telah memperbarui posisi saya; mengapa saya masih memiliki 0 bagian? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Bagian (rCAKE) diperbarui pada setiap distribusi mingguan pada pukul 23:59 UTC setiap Rabu. Kembali lagi setelah distribusi mingguan berikutnya untuk melihat bagian Anda yang telah diperbarui.

### Mengapa bagian saya 0 meskipun memiliki posisi staking aktif? <a href="#id-9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="id-9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Saat menghitung bagian (rCAKE), sisa durasi kunci dibulatkan ke bawah ke minggu. Oleh karena itu untuk menerima bagian, Anda harus memastikan posisi staking Anda membuka kunci tidak lebih awal dari distribusi berikutnya.

Misalnya, untuk menerima bagian untuk distribusi minggu 1. Anda harus:

* Bergabung sebelum 23:59 UTC, 2 Agustus.
* Memiliki posisi fixed-term CAKE staking aktif yang membuka kunci lebih lambat dari 23:59 UTC, 9 Agustus.

Jika posisi staking Anda membuka kunci lebih awal dari 23:59 UTC, 9 Agustus, Anda akan menerima 0 bagian untuk minggu 1.

### Bisakah saya bergabung dengan periode distribusi di tengah minggu? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Tidak, seperti yang disebutkan bagian dihitung pada awal periode distribusi pada pukul 23:59 UTC setiap Rabu. Oleh karena itu Anda akan menerima bagian mulai dari distribusi berikutnya dan mulai mengakumulasikan hadiah sejak saat itu.

### Bagaimana cara mendapatkan lebih banyak bagian? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Karena bagian dihitung berdasarkan jumlah CAKE dan sisa durasi kunci, untuk menerima lebih banyak bagian, Anda dapat:

* Mengunci lebih banyak CAKE
* Memperpanjang posisi staking Anda

Harap diperhatikan bahwa setelah menambahkan CAKE atau memperpanjang, bagian TIDAK diperbarui secara real time dan hanya diperbarui pada distribusi mingguan setiap minggunya.

### Apakah saya perlu memperbarui posisi staking saat menambahkan lebih banyak CAKE atau memperpanjang staking? <a href="#id-71d1d397-ac1c-454b-abd9-15492860f05c" id="id-71d1d397-ac1c-454b-abd9-15492860f05c"></a>

Tidak, Anda hanya perlu mendaftar sekali. Semua operasi pool staking CAKE berikutnya akan secara otomatis memberi tahu pool berbagi pendapatan dan memperbarui bagian Anda pada distribusi mingguan berikutnya.

### Mengapa hadiah yang diinjeksikan mingguan tidak 100% sesuai dengan volume yang ditampilkan di berbagai pelacak (seperti halaman Info)?

Jumlah hadiah CAKE yang diinjeksikan setiap minggu mungkin tidak 100% sesuai dengan angka yang dihitung dari volume yang ditampilkan di berbagai pelacak. Beberapa faktor eksternal dapat mempengaruhi jumlah hadiah CAKE yang dapat dikonversi:

* Harga token CAKE saat biaya perdagangan sedang dikonversi dan diproses
* Harga aset dasar saat biaya perdagangan sedang dikonversi dan diproses
* Untuk menghemat gas dan biaya operasional. Pendapatan dari blockchain selain BNB Chain diproses secara bulanan. Mereka akan diinjeksikan dengan penundaan satu bulan dengan rata-rata mingguan.
* Beberapa pasangan perdagangan mungkin memiliki likuiditas yang tidak memadai saat memproses biaya perdagangan.
* Beberapa pasangan perdagangan mungkin mengandung token dengan logika kustom yang mencegah biaya mereka untuk diproses.

Chefs bekerja keras untuk menerapkan alat dan praktik guna memastikan lebih banyak biaya perdagangan yang dihasilkan dapat diproses dan dikonversi menjadi CAKE.
