# FAQ

### Saya telah mengunci CAKE atau memigrasikan posisi CAKE pool saya. Mengapa saya masih memiliki 0 bagian? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Bagian diperbarui pada setiap distribusi mingguan pukul 00:00 UTC setiap hari Kamis.

Hadiah terakumulasi setiap kali Anda telah selesai melakukan staking selama satu epoch penuh.&#x20;

Epoch adalah periode 7 hari, dimulai setiap hari Kamis, pukul 00:00 UTC. Misalnya, jika Anda melakukan staking pada hari Selasa. Epoch pertama Anda akan dimulai pada hari Kamis. Setelah Anda selesai melakukan staking hingga Kamis berikutnya. Anda akan dapat mengklaim hadiah dari hari Kamis ini hingga Kamis berikutnya, yaitu epoch ke-1.

Periksa kembali setiap hari Kamis untuk melihat pembaruan jumlah hadiah.

### Mengapa bagian/hadiah saya menjadi 0 meskipun memiliki posisi staking yang aktif? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Saat menghitung hadiah, sisa durasi kunci dibulatkan ke bawah ke minggu. Oleh karena itu, untuk menerima bagian, Anda harus memastikan posisi staking Anda membuka kunci tidak lebih awal dari hari Kamis berikutnya pukul 00:00 UTC.

Misalnya, minggu ke-1 dimulai pada pukul 00:00 UTC, Kamis, 1 Jan. Untuk menerima hadiah untuk distribusi minggu ke-1. Anda harus:

* Bergabung sebelum pukul 00:00 UTC, 1 Jan.
* Memiliki posisi Staking veCAKE yang aktif, yang membuka kunci pada atau setelah pukul 00:00 UTC, 15 Jan. (Kamis di minggu ke-3)

Harap diperhatikan bahwa jika posisi staking Anda membuka kunci pada pukul 00:00 UTC, 8 Jan (Kamis di minggu ke-2). Anda tetap akan menerima 0 hadiah untuk minggu ke-1 karena saldo veCAKE Anda berubah pada pukul 00:00 UTC, 8 Jan.

### Bisakah saya bergabung dengan periode distribusi di pertengahan minggu? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Tidak, seperti yang telah disebutkan, hadiah hanya dapat mulai terakumulasi ketika Anda sudah melakukan staking pada awal epoch. Yaitu setiap minggu pada pukul 00:00 UTC, hari Kamis.&#x20;

### Bagaimana cara menerima lebih banyak hadiah? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Karena bagian Anda di pool dihitung berdasarkan saldo veCAKE pada waktu distribusi, yaitu pukul 00:00 UTC Kamis berikutnya yang akan datang. Untuk menerima lebih banyak hadiah, cukup tingkatkan saldo veCAKE Anda dengan:

* Mengunci lebih banyak CAKE di posisi staking veCAKE
* Memperpanjang posisi staking Anda

Harap diperhatikan bahwa setelah menambahkan CAKE atau memperpanjang, bagian Anda hanya akan diperbarui setelah awal epoch berikutnya, yaitu pukul 00:00 UTC, hari Kamis yang akan datang.

### Mengapa hadiah mingguan yang disuntikkan tidak 100% cocok dengan volume yang ditampilkan di berbagai pelacak (seperti halaman Info)? Mengapa hadiah pool CAKE mingguan tidak 100% cocok dengan hasil pemungutan suara gauge?

Jumlah hadiah CAKE yang disuntikkan setiap minggu mungkin tidak 100% cocok dengan angka yang dihitung dari volume yang ditampilkan di berbagai pelacak. Beberapa faktor eksternal dapat memengaruhi jumlah hadiah CAKE yang dapat dikonversi:

* Harga token CAKE saat biaya perdagangan sedang dikonversi dan diproses
* Harga aset dasar saat biaya perdagangan sedang dikonversi dan diproses
* Untuk menghemat gas dan biaya operasional. Pendapatan dari blockchain selain BNB Chain diproses setiap bulan. Pendapatan tersebut akan disuntikkan dengan penundaan satu bulan dengan rata-rata mingguan.
* Beberapa pasangan perdagangan mungkin memiliki likuiditas yang tidak mencukupi saat memproses biaya perdagangan.
* Beberapa pasangan perdagangan mungkin mengandung token dengan logika khusus yang mencegah biayanya diproses.
* Penundaan transaksi akibat performa infrastruktur dan sistem pendukung.

Tim Chefs bekerja keras untuk menerapkan alat dan praktik guna memastikan lebih banyak biaya perdagangan yang dihasilkan dapat diproses dan dikonversi menjadi CAKE.
