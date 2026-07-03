# Arbitrum

Pada 31 Agustus 2023, PancakeSwap Perpetuals akan meluncurkan Program Hadiah Trading V2 di Arbitrum. Pengguna yang melakukan Staking [ALP di CAKE Syrup Pool](https://pancakeswap.finance/pools?chain=arb) di Arbitrum dapat menikmati pengganda boosting. Selain itu, tidak ada periode vesting untuk hadiah yang diperoleh dalam program ini. Pengguna dapat mengklaim hadiah USDC mereka kapan saja. Detailnya adalah sebagai berikut:

Waktu mulai: 31 Agustus 2023, 08:00 (UTC)

Periode Aktivitas (Epoch): Setiap Kamis 08:00:00 UTC hingga Kamis berikutnya 07:59:59, berlangsung 1 minggu

Waktu Distribusi Hadiah: Setiap siklus adalah 00:00 (UTC) hingga 23:59 (UTC) setiap hari. Hadiah diterbitkan setiap Kamis sekitar pukul 08:00 (UTC). Setelah tingkat pengguna diperbarui, hadiah akan dihitung dan didistribusikan. Pengguna harus mengklaim hadiah mereka dalam 30 hari setelah hadiah diterbitkan. Jika tidak, platform akan mencabut hadiah tersebut.&#x20;

Jumlah hadiah: Untuk 5 minggu pertama, 25% dari biaya trading (dalam USDC). Kumpulan hadiah ini kemudian akan didistribusikan sesuai tingkatan.

Aturan aktivitas: Pengguna yang berdagang di PancakeSwap Perpetuals V2 di Arbitrum akan memenuhi syarat untuk kumpulan hadiah

### Rincian Tingkatan

Setiap Kamis pada pukul 08:00:00 UTC, kami menghitung data trading dari Kamis lalu 08:00:00 UTC hingga Kamis ini pukul 07:59:59 dan kemudian memperbarui Tingkatan pengguna sesuai aturan Tingkatan. Aturan Tingkatan adalah sebagai berikut (konfigurasi didukung):

<table><thead><tr><th width="161">Tingkatan</th><th width="249.33333333333331">Deskripsi</th><th>Bobot</th></tr></thead><tbody><tr><td>Diamond</td><td>Volume trading epoch >=1 Juta USD</td><td>5</td></tr><tr><td>Gold</td><td>Volume trading epoch >=500 Ribu USD</td><td>3</td></tr><tr><td>Silver</td><td>Volume trading epoch >=250 Ribu USD</td><td>1</td></tr></tbody></table>

**Catatan: Kriteria tingkatan dan bobot dapat berubah berdasarkan likuiditas pool dan aktivitas trading keseluruhan di platform**

Hadiah akan didistribusikan secara merata ke semua pengguna yang memenuhi syarat untuk tingkatan tertentu

### Rumus perhitungan Hadiah Trading:&#x20;

Di akhir setiap siklus hadiah trading, volume trading efektif pengguna dalam siklus tersebut akan dihitung untuk menentukan bobot dan jumlah hadiah USDC.

Rumus untuk jumlah hadiah spesifik adalah: r = min{R \* W/Sum(Wi), R \* 20%\}, parameternya adalah sebagai berikut:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Jumlah hadiah USDC yang akan ditambang oleh pengguna untuk epoch saat ini</td></tr><tr><td>R</td><td>Hadiah epoch saat ini R=(nilai USDC dari biaya ETH + nilai USDC dari biaya DAI + nilai USDC dari biaya BTC + biaya USDC)*0,25, di mana 1% biaya Swap perlu dikurangkan saat penyelesaian, misalnya: ketika biaya ETH mingguan adalah 1 dan Harga ETH adalah 2.000, biaya ETH untuk nilai USDC = 1 * 2000 * 0,99</td></tr><tr><td>W</td><td>Bobot yang sesuai dengan level Tingkatan pengguna</td></tr><tr><td>Sum(Wi)</td><td>Total skor bobot semua pengguna. Wi mewakili bobot pengguna mana pun, dan sum(Wi) mewakili total skor bobot dari semua pengguna.</td></tr></tbody></table>

* Bagian pendapatan maksimum per pengguna dibatasi sebesar 20% dari pendapatan yang dicadangkan untuk program

Syarat dan Ketentuan

* Karena perbedaan biaya trading untuk setiap pasangan trading di V2, hadiah yang diterima pengguna dapat bervariasi meskipun volume trading efektif mereka sama.
* Hadiah yang akan didistribusikan untuk setiap siklus akan disimpan di alamat kontrak berikut:&#x20;
* PancakeSwap/ApolloX berhak atas interpretasi akhir untuk aktivitas ini.



Peringatan Risiko: Trading crypto futures membawa risiko yang substansial. Semua aktivitas trading dilakukan atas kebijaksanaan dan risiko Anda sendiri. Informasi di sini tidak boleh dianggap sebagai saran keuangan atau investasi dari PancakeSwap/ApolloX. PancakeSwap/ApolloX tidak akan bertanggung jawab atas kerugian apa pun yang mungkin timbul dari penggunaan PancakeSwap/ApolloX oleh Anda.

<br>
