# 🍯 \[Diarsipkan] Pottery

{% hint style="danger" %}
\[Diarsipkan] Pottery — Per 3 November 2023
{% endhint %}

Pottery menggabungkan lock-staking CAKE dengan elemen Lotere untuk memberi Anda kesempatan memenangkan hasil yang lebih besar dari setoran CAKE Anda! Ini mudah dan aman karena Anda akan selalu mendapatkan kembali setidaknya semua CAKE yang Anda setorkan.

## Rincian:

* Setorkan CAKE di halaman Pottery dengan minimum 1 CAKE&#x20;
* Setoran ditutup pada Senin pertama setiap bulan untuk kelompok Pottery yang berbeda (23:59 UTC pada Senin tersebut) dan terbuka dari Jumat sebelumnya sekitar pukul 10:00 UTC, kecuali ada pengaturan khusus yang akan diumumkan sebelumnya (Pottery pertama ditutup pada 8 Agustus 2022 23:59 UTC)
* Selama tahap beta produk, ada batas total setoran CAKE untuk setiap kelompok Pottery (batas setoran maksimum adalah 600.000 CAKE)
* CAKE yang disetorkan akan diarahkan ke pool lock-staking dan dikunci selama sepuluh (10) minggu 80% dari total hadiah Staking akan dikirim ke pool Pottery untuk diundi, 20% akan disisihkan untuk penarikan Anda&#x20;
* Untuk setiap kelompok Pottery (satu per bulan), akan ada sepuluh (10) undian mingguan setiap Jumat (pada siang UTC) setelah setoran menghasilkan delapan (8) pemenang per minggu, setiap alamat mungkin memenangkan lebih dari satu dari delapan slot pemenang setiap minggu \*
* Semakin besar setoran Anda relatif terhadap keseluruhan pool, semakin tinggi peluang menang, pemenang dapat mengklaim hadiah langsung setelah setiap undian&#x20;
* Setiap kelompok Pottery melakukan undian secara terpisah&#x20;
* Hanya setelah 10 minggu dari tanggal kunci kelompok Pottery, Anda dapat menarik CAKE Anda&#x20;
* Pottery menggunakan implementasi VRF dari Chainlink untuk keacakan yang benar dan aman

## Kelompok Pottery&#x20;

Pada Jumat sebelum Senin pertama setiap bulan, kelompok Pottery akan dibuka bagi Anda untuk menyetorkan CAKE dan berpartisipasi selama 10 minggu berikutnya. Pengaturan ini menggabungkan setoran untuk diarahkan ke pool staking yang dikunci, sehingga kontrak Pottery dari kelompok tersebut dapat mengoordinasikan hadiah Staking dari setoran dari pool staking yang dikunci.

Setiap tanggal setoran dan kunci akan menjadi kelompok terpisah — satu untuk setiap bulan — misalnya semua setoran pada 5 Sep 2022 akan berada dalam satu kelompok, semua setoran pada 3 Okt 2022 akan berada dalam kelompok lain.

Sementara undian mungkin terjadi secara bersamaan untuk kelompok yang berbeda, pool hadiah untuk setiap kelompok dipisahkan agar adil.

![(Hanya untuk tujuan ilustrasi, tanggal kunci kelompok aktual untuk Pottery pertama telah ditetapkan pada 8 Agustus 2022)](https://lh5.googleusercontent.com/KamNAZK7s2N454cI_cvnjHJpuAH8HfgWlmEXZevzDVW_uxiw_pymKZCp97L9hSjcGGzjjQeGuSt7oOIOXECq_xoU47zEC4rhJp2IA37ROeUOUSqXKgqKjNqcJnHOopC8mi5IeqR9UAprhNF5zM4PLjc)

Misalnya, ada 2 undian terpisah pada 9 Sep 2022, satu untuk kelompok Agustus 1 sebagai undian mingguan keenam dan yang lainnya untuk kelompok Sep 5 sebagai undian mingguan pertama. Jika kelompok Agustus 1 memiliki total 100.000 CAKE yang disetorkan dan kelompok Sep 5 memiliki total 300.000 CAKE yang disetorkan, hadiah mingguan untuk kelompok Agustus 1 hanya akan berasal dari hadiah Staking dari 100.000 CAKE tersebut, sementara hadiah mingguan untuk kelompok Sep 5 hanya akan berasal dari hadiah Staking dari 300.000 CAKE tersebut. Jika Anda hanya menyetorkan CAKE di kelompok Agustus 1, Anda berkesempatan memenangkan hadiah mingguan pada 9 Sep berdasarkan hadiah Staking dari 100.000 CAKE. Jika Anda menyetorkan CAKE di kelompok Agustus 1 dan Sep 5, Anda berkesempatan memenangkan kedua hadiah mingguan pada 9 Sep.

#### Mengapa kita membutuhkan sistem kelompok? Mengapa kita tidak menggabungkan semuanya?

Karena Pottery berinteraksi dengan fixed-term staking CAKE, setiap setoran hanya dapat ditarik setelah durasi kunci. Jika kita ingin menggabungkan semua setoran, meskipun kita dapat menambahkan lebih banyak setoran setelah kunci awal dan juga menguncinya selama 10 minggu, penyetor awal tidak akan dapat menarik tepat waktu.

## **Pendanaan Hadiah & Alokasi Hadiah Staking**

Setoran dikelompokkan ke dalam kelompok bulanan untuk pengaturan hadiah Staking yang lebih efisien yang juga dikelompokkan bersama untuk setiap kelompok. Hadiah Staking digunakan untuk mendanai pool hadiah dan beberapa hadiah Staking untuk setoran ke Pottery.

80% dari hadiah Staking akan diarahkan untuk mendanai pool hadiah untuk 10 undian mingguan dan sisanya 20% akan disisihkan sebagai hadiah Staking ketika Anda menarik setoran CAKE setelah 10 minggu.

Namun, karena hadiah Staking dari pool CAKE locked staking hanya didistribusikan setelah durasi kunci — 10 minggu dalam kasus ini, untuk pengalaman produk yang lebih baik dan untuk memfasilitasi undian mingguan tepat setelah tanggal setoran, kontrak meminjam 80% dari perkiraan total hadiah Staking dari kelompok tersebut dari perbendaharaan CAKE berdasarkan APR pada saat penguncian. CAKE yang dipinjam digunakan untuk pembayaran setiap undian mingguan.

Di akhir 10 minggu, ketika hadiah didistribusikan dari pool staking, perbendaharaan CAKE akan dibayar kembali terlebih dahulu, kemudian sisanya akan diarahkan kembali ke vault bagi pengguna untuk ditarik bersama dengan setoran awal mereka di kelompok tersebut.

![](https://lh5.googleusercontent.com/7AEqm_m542SHUGbc69uu8v_7Xfa_hKym8De3fBscEF6IySHEmy1P1k5S3W_PvnFSMBSOZOUFpPNDKhEp3sHOB8jCuLfjA8QJxsurqK-hZ0umrw0w8bIRPvMZKuQ4TnNTfKRdU8s3UXO1n0Smnp8_6sAg)

Misalnya, jika kelompok Pottery pada 1 Agustus 2022 telah menarik total 100.000 CAKE sebagai setoran, estimasi keuntungan untuk 10 minggu locked staking adalah sekitar 3.674 CAKE. Kontrak akan meminjam 80% darinya, atau sekitar 2.940 CAKE, untuk pool hadiah untuk 10 undian mingguan, yaitu total 294 CAKE sebagai hadiah untuk setiap undian mingguan sebelum biaya.

Penting untuk dicatat bahwa hadiah dan APR di akhir durasi dari setoran mungkin berubah selama durasi 10 minggu berdasarkan setoran lain dan periode kunci mereka di pool CAKE yang dikunci, mungkin ada sedikit penyimpangan dari persentase yang ditentukan (+/- 10%).

Semua hadiah Staking bersih dari biaya akan dikembalikan kepada penyetor melalui pool hadiah atau hadiah. Jika APR aktual lebih rendah dari APR yang diperkirakan pada saat penguncian, itu berarti lebih banyak hadiah yang didistribusikan kepada penyetor selama undian mingguan, dan lebih sedikit untuk bagian hadiah Staking. Jika APR aktual lebih tinggi dari APR yang diperkirakan pada saat penguncian, lebih sedikit hadiah yang didistribusikan melalui undian mingguan dan lebih banyak yang disisihkan untuk hadiah Staking yang tersedia untuk ditarik. Pada akhirnya, nilai yang diharapkan adalah sama.

## **Cara Menang — Perhitungan Peluang**

Peluang dihitung berdasarkan porsi jumlah setoran relatif terhadap total ukuran setoran kelompok. Sederhananya, semakin banyak CAKE yang Anda setorkan, semakin tinggi peluang menang setiap undian mingguan. Misalnya, jika Anda telah menyetorkan 10.000 CAKE dan total setoran kelompok adalah 100.000 CAKE, ada peluang 10% bahwa Anda akan menang di setiap undian mingguan.

Setiap alamat dapat memenangkan lebih dari 1 dari 8 slot pemenang setiap minggu.

Dalam kasus ekstrem, jika semua 100.000 CAKE kelompok disetorkan oleh Anda, Anda akan memenangkan semua hadiah dari setiap undian mingguan. Namun, itu berarti keuntungan akhir yang akan Anda dapatkan sama dengan menempatkan 100.000 CAKE ke pool locked staking selama 10 minggu, tetapi Anda juga akan membayar biaya Pottery.

## **Risiko — Penting!**

Anda dijamin mendapatkan kembali 100% dari apa yang Anda setorkan dalam 10 minggu. Namun, Anda _hanya_ dapat menarik setoran CAKE setelah 10 minggu penguncian, tanpa cara lain untuk menarik lebih awal.

Dengan berpartisipasi dalam Pottery, Anda akan mempertaruhkan hadiah Staking, beserta utilitas locked-CAKE lainnya seperti iCAKE dan vCAKE. Jika Anda tidak memenangkan apa pun dari 10 undian mingguan, Anda akan kehilangan 80% dari hadiah Staking yang seharusnya Anda dapatkan jika Anda mengunci CAKE di pool staking selama 10 minggu.

Silakan berpartisipasi berdasarkan preferensi risiko Anda, setelah CAKE disetorkan, tidak ada yang dapat dilakukan untuk membantu Anda menarik lebih awal.

## **Biaya**

Delapan persen (8%) dari pot hadiah yang didistribusikan setiap minggu akan dikenakan biaya untuk pembakaran. Kami bertujuan untuk meninjau dan menyesuaikan struktur biaya sesuai setelah tahap beta produk.

## **Siap Berpartisipasi?**

Jika Anda sudah paham tentang struktur produk, risiko, dan biaya — lihat halaman ini tentang [cara berpartisipasi](https://docs.pancakeswap.finance/products/pottery/how-to-play-pottery) dari UI web PancakeSwap dan [FAQ Pottery](https://docs.pancakeswap.finance/products/pottery/pottery-faq) lainnya!


