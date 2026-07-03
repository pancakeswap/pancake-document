# FAQ Lottery

## Bagaimana jika tidak ada pemenang?

Jika CAKE dalam pool hadiah tidak dimenangkan, itu tidak terbuang! CAKE yang tidak diklaim bergulir ke putaran Lottery berikutnya.

## Tiket saya cocok dengan beberapa angka tetapi saya tidak dapat mengklaim hadiah

Tiket hanya memenuhi syarat untuk hadiah jika angka yang cocok dari kiri ke kanan. Lihat [dokumentasi Lottery v2](./) untuk penjelasan menyeluruh.

## Apa perbedaan Lottery v2 dengan Lottery v1?

Lottery v2 mendistribusikan hadiah lebih luas dibandingkan Lottery v1. Ini memberikan setiap tiket peluang 1 dari 10 untuk cocok dengan angka pertama, yang berarti lebih banyak tiket setidaknya akan memenangkan hadiah kecil. Ini juga memiliki 6 (meningkat dari 4) angka yang perlu dicocokkan secara berurutan untuk memenangkan hadiah terbesar.

Secara keseluruhan ini berarti lebih banyak tiket dapat memenangkan hadiah, tetapi jackpot hadiah terbesar akan dimenangkan lebih jarang, sehingga menghasilkan pool hadiah utama yang sangat besar!

**Lottery v2 memperkenalkan:**

* harga tiket yang lebih murah (\~$5 USD dalam CAKE per tiket) yang tidak berfluktuasi liar dengan harga CAKE
* diskon pembelian massal
* bracket pool hadiah 6 tingkat dengan pool hadiah yang meningkat seiring lebih banyak angka yang dicocokkan
* pemilihan angka manual (opsional), sehingga pengguna dapat menggunakan angka keberuntungan mereka
* [implementasi VRF dari Chainlink](https://docs.chain.link/docs/chainlink-vrf/) untuk keacakan yang sesungguhnya dan aman
* biaya keseluruhan yang lebih rendah (lihat [bagian bawah halaman ini](lottery-faq.md#what-transaction-fee-will-i-pay-for-buying-tickets) untuk informasi lebih lanjut)

[Pelajari lebih lanjut tentang fitur, cara bermain, dan hadiah Lottery v2](./)

## Bagaimana hadiah dibagi antar bracket?

Pool hadiah setiap bracket merupakan bagian dari total CAKE dalam setiap putaran Lottery.

* | Bracket (angka yang cocok berurutan) | Alokasi CAKE |
  | ------------------------------------ | ------------ |
  | 1 angka pertama                      | 2%           |
  | 2 angka pertama                      | 3%           |
  | 3 angka pertama                      | 5%           |
  | 4 angka pertama                      | 10%          |
  | 5 angka pertama                      | 20%          |
  | 6 angka pertama                      | 40%          |
  | Bakar                                | 20%          |

## Bisakah saya menukar tiket saya kembali ke CAKE?

Tidak, setelah dibeli Anda tidak akan dapat mengonversi tiket Anda kembali ke CAKE.

## Jika saya menang, apakah saya perlu mengklaim hadiah secara manual?

Ya, Anda perlu mengklik tombol **Check Now** di bawah "Are you a winner?" pada halaman Lottery.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2868%29.png)

## Seberapa sering lotere diadakan?

Undian lotere dilakukan setiap 12 atau 36 jam. Satu undian lotere terjadi setiap hari bergantian antara pukul 0 AM UTC dan 12 PM UTC, putaran berikutnya setelah putaran 0 AM UTC akan setelah 36 jam, putaran berikutnya setelah putaran 12 PM UTC akan setelah 12 jam.

![Lottery injection schedule](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Lottery%20Schedule%20Update%20Feb%204.png)

## Biaya transaksi apa yang akan saya bayar untuk membeli tiket?

Setiap pembelian tiket yang Anda lakukan akan menjadi satu transaksi. Membeli satu tiket dalam satu pembelian Lottery akan dikenakan biaya transaksi normal.

Namun, membeli lebih banyak tiket dalam pembelian tersebut akan meningkatkan biaya. Membeli 100 tiket daripada 1 tidak akan mengalikan biaya sebesar 100 kali, tetapi mungkin meningkatkan jumlah biaya sebesar 5-6 kali (meskipun ini bervariasi).

## Bagaimana cara kerja diskon massal?

Diskon massal memberikan hadiah kepada pembelian tiket dalam jumlah besar dengan diskon bertingkat. Jika Anda hanya membeli 2 tiket, diskonnya tidak signifikan, tetapi akan bertambah dengan cepat seiring Anda meningkatkan jumlah tiket yang dibeli dalam satu transaksi.

Diskon hanya berlaku untuk setiap transaksi hingga 100 tiket. Diskon tidak berlaku untuk transaksi berikutnya atau putaran berikutnya.

## Mengapa saya hanya bisa membeli 100 tiket?

Anda hanya dapat membeli maksimum 100 tiket dalam satu pembelian, tetapi Anda dapat melakukan beberapa pembelian. Tidak ada yang menghalangi Anda membeli lebih banyak tiket setelah 100 tiket pertama Anda.

## Jika saya membuat dua atau lebih tiket dengan angka yang sama secara manual dan menang, apakah saya berhak atas hadiah untuk setiap tiket?

Ya, setiap tiket diperlakukan sebagai entri terpisah dalam Lottery. Perlu diingat bahwa hadiah tidak akan 1:1, karena setiap tiket pemenang yang Anda miliki akan mengencerkan setiap bagian dari total hadiah bracket tersebut.

## Jadwal injeksi: Kapan CAKE ditambahkan ke lotere?

Ketika orang membeli tiket, CAKE yang mereka belanjakan ditambahkan ke pot lotere. Selain itu, 8.000 CAKE juga ditambahkan (diinjeksikan) ke pot lotere setiap putaran lainnya secara terjadwal reguler selama tujuh putaran per minggu seperti yang ditunjukkan di atas dalam gambar jadwal lotere.
