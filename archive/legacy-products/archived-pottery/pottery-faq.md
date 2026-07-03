# FAQ Pottery

{% hint style="danger" %}
\[Diarsipkan] Pottery — Per 3 November 2023
{% endhint %}

## Mengapa kita membutuhkan Pottery saat sudah ada Lottery v2?

Pottery adalah produk yang sepenuhnya berbeda dibandingkan Lottery v2. Ini adalah kombinasi dari pool CAKE yang dikunci dan fungsi Lotere yang memanfaatkan implementasi VRF dari Chainlink untuk keacakan yang benar dan aman. Dengan berpartisipasi dalam Pottery, Anda tidak akan kehilangan CAKE yang Anda setorkan, Anda hanya mempertaruhkan hadiah Staking dari CAKE yang Anda setorkan. Produk ini dirancang untuk pengguna CAKE yang lebih menghindari risiko tetapi masih ingin berpartisipasi dalam produk yang sifatnya seperti ini. Ini adalah cara yang mudah, menyenangkan, dan aman untuk mendapatkan kesempatan memenangkan sejumlah CAKE. Pelajari lebih lanjut tentang [struktur produk di sini](https://docs.pancakeswap.finance/products/pottery).

## Apakah Pottery menggantikan Lottery v2 yang asli?

Pottery tidak menggantikan Lottery v2 yang asli. Kedua produk ini beroperasi dan dijalankan secara terpisah. Anda dapat berpartisipasi dalam keduanya!

## Bagaimana Pottery membantu PancakeSwap dan CAKE?

Delapan persen (8%) dari pot hadiah yang didistribusikan setiap minggu akan dikenakan biaya untuk pembakaran, yang meningkatkan nilai CAKE. Kami bertujuan untuk meninjau dan menyesuaikan struktur biaya sesuai setelah tahap beta produk.

## Apa tujuan tahap beta Pottery?

Karena operasi produk baru ini seperti peminjaman dari perbendaharaan, manajemen kelompok, dan pengundian. Produk akan dimulai dalam tahap beta dengan batas total setoran untuk setiap Pottery untuk memastikan semuanya berjalan lancar. Setelah melewati tahap beta, kami dapat meninjau dan menyesuaikan berbagai parameter berdasarkan operasi dan masukan komunitas seperti biaya, frekuensi setiap kelompok, periode kunci, dll.

## Mengapa harus mengunci CAKE saya selama 10 minggu?

Jika Pottery dapat menggunakan pool flexible staking, struktur produknya akan jauh lebih sederhana — mirip dengan produk seperti PoolTogether dan Moonpot. Namun, hasil saat ini dari pool flexible staking tidak cukup bagi kami untuk menghasilkan pool hadiah yang berarti untuk diundi. Oleh karena itu, keputusannya adalah mengunci CAKE untuk durasi sedang guna menyeimbangkan hadiah yang dapat digunakan untuk mendanai pool hadiah. Dengan lebih banyak operasi dan masukan komunitas, kami dapat meninjau dan menyesuaikan durasi kunci ke depannya.

## Mengapa saya tidak bisa menarik?

Perhatikan bahwa tombol penarikan akan menyala dan tersedia hanya setelah 10 minggu dari tanggal kunci. Tanggal penarikan didasarkan pada 10 minggu setelah tanggal dan waktu kunci — 23:59 UTC pada Senin pertama setiap bulan.

## Mengapa saya tidak bisa melihat setoran saya?

Terkadang mungkin ada sedikit keterlambatan karena pembacaan Subgraph, akan ada sinyal ketika ada penundaan — biasanya akan menampilkan jumlah yang benar jika Anda memeriksa kembali dalam 15 menit.

## Bagaimana saya tahu jika saya menang dalam undian mingguan?

Setelah setiap undian pada Jumat sekitar siang UTC, Anda dapat melihat hasil dan pemenang di panel Ronde Selesai. Cara lain untuk memeriksa apakah Anda menang dalam undian mingguan mana pun adalah dengan memeriksa di panel Klaim untuk melihat apakah ada hadiah yang dapat diklaim. Lihat [halaman ini tentang cara berpartisipasi](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery)!

## Apa sumber pendanaan hadiah?

Pool hadiah didanai oleh hadiah Staking dari setoran. Namun, karena hadiah Staking dari pool CAKE locked staking hanya didistribusikan setelah durasi kunci — 10 minggu dalam kasus ini, untuk pengalaman produk yang lebih baik dan untuk memfasilitasi undian mingguan tepat setelah tanggal setoran, kontrak meminjam 80% dari perkiraan total hadiah Staking dari kelompok tersebut dari perbendaharaan CAKE berdasarkan APR pada saat penguncian. CAKE yang dipinjam digunakan untuk pembayaran setiap undian mingguan. Pelajari lebih lanjut tentang [struktur produk di sini](https://docs.pancakeswap.finance/products/pottery)!

## Jika saya menang, apakah saya perlu mengklaim hadiah secara manual?

Ya, Anda perlu mengklik tombol Klaim di bawah panel Klaim di halaman Pottery.

## Seberapa sering Pottery diadakan?

Setiap kelompok Pottery terbuka untuk setoran pada Jumat sebelumnya sekitar pukul 10:00 UTC dan ditutup pada Senin pertama setiap bulan pada 23:59 UTC, kecuali ada pengaturan dan pemberitahuan khusus sebelumnya. Setiap kelompok akan memiliki 10 undian mingguan pada 10 Jumat berikutnya pada siang UTC.

Pottery pertama akan membuka setoran pada 5 Agustus 2022 dan dikunci pada 8 Agustus 2022 pada 23:59 UTC.

## Mengapa setoran Pottery hanya dibuka sekali sebulan?

Pengaturan ini menggabungkan setoran untuk diarahkan ke pool locked staking, sehingga kontrak Pottery dari kelompok tersebut dapat mengoordinasikan hadiah Staking dari setoran dari pool locked staking. Dengan lebih banyak operasi dan masukan komunitas, kami dapat meninjau dan menyesuaikan frekuensinya ke depannya.

## Berapa batas untuk menyetorkan?

Ada setoran minimum 1 CAKE. Pada tahap beta produk, juga akan ada batas setoran maksimum untuk setiap kelompok yang dapat Anda lihat di panel Setoran saat melakukan setoran. Ini untuk memastikan semuanya di sisi operasional termasuk peminjaman dari perbendaharaan, locked staking, dan pengundian berjalan lancar. Sementara maksimum yang dapat Anda setorkan adalah batas setoran maksimum kelompok tersebut (jika tidak ada orang lain yang menyetorkan CAKE), Anda akan memenangkan semua hadiah, namun itu juga berarti keuntungan akhir yang akan Anda dapatkan sama dengan menempatkan CAKE Anda ke pool locked staking selama 10 minggu, tetapi Anda juga akan membayar biaya Pottery.

## Mengapa kita membutuhkan sistem kelompok? Mengapa kita tidak menggabungkan semuanya?

Karena Pottery berinteraksi dengan fixed-term staking CAKE, setiap setoran hanya dapat ditarik setelah durasi kunci. Jika kita ingin menggabungkan semua setoran, meskipun kita dapat menambahkan lebih banyak setoran setelah kunci awal dan juga menguncinya selama 10 minggu (dari waktu setoran baru), penyetor awal tidak akan dapat menarik tepat waktu.

## Apa itu token SHARE?

Token SHARE dibuat dan didistribusikan ketika Anda menyetorkan di pottery. Ini mewakili dan berfungsi sebagai bukti kepemilikan Anda terhadap pool setoran.

Saat penarikan, token SHARE akan ditransfer kembali ke kontrak pottery dan dibakar.

## Di mana saya dapat memberikan masukan untuk produk ini?

Silakan hubungi kami di [Telegram](https://t.me/pancakeswap) atau [Discord](https://discord.gg/pancakeswap) jika Anda masih tidak yakin tentang formatnya atau jika Anda memiliki masukan bagi kami untuk meningkatkan ini lebih lanjut!
