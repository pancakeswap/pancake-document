# FAQ Swap

## Swap

### Apa yang baru di Exchange V3?

* Likuiditas terkonsentrasi - likuiditas akan terkonsentrasi pada rentang harga yang paling aktif diperdagangkan, yang berarti:
  * Slippage trading yang lebih rendah bagi trader
  * Hadiah biaya LP yang berpotensi lebih besar bagi penyedia likuiditas
* Struktur biaya trading yang fleksibel - Penyedia likuiditas dapat memilih di antara beberapa tingkatan biaya trading saat membuat pasangan likuiditas atau menyediakan likuiditas
* Rentang harga yang dapat dikustomisasi - Penyedia likuiditas juga dapat memilih rentang harga mana yang ingin mereka sediakan likuiditas
* Posisi likuiditas non-fungible - Setiap posisi likuiditas akan memiliki ID uniknya sendiri yang sesuai dengan konfigurasinya (seperti rentang harga). Oleh karena itu, Anda akan dapat membuat dan mempertahankan beberapa posisi dengan pasangan trading yang sama tetapi dengan konfigurasi dan jumlah likuiditas yang berbeda
* Kompatibel ke belakang - Exchange v3 juga akan memanfaatkan pasangan likuiditas v2 lama dan stable swap untuk selalu menyediakan rute trading terbaik
* Limit order bawaan - Pengguna pro dapat memanfaatkan rentang harga yang dapat dikustomisasi dalam penyediaan likuiditas untuk secara efektif membuat limit order yang akan mengkonversi semua token ke token yang diinginkan saat harga mencapai target



### Bisakah saya menambahkan token saya sendiri ke Exchange V3?

Semua orang dapat membuat Pool Likuiditas dengan mendepositkan likuiditas di V3.

Namun, token-token berikut saat ini **TIDAK** didukung:

* Token fee-on-transfer
* Token rebase

Untuk token-token ini, harap **JANGAN** menambahkan likuiditas di Exchange V3. Aset Anda mungkin tersangkut dalam posisi likuiditas.



### **Mengapa transaksi saya tidak bisa diproses?**

PancakeSwap adalah aplikasi DeFi yang berinteraksi dengan dompet untuk menyelesaikan transaksi on-chain untuk Swap, membuat LP, Staking di Farm dan pool, dll.

**Biaya Gas**

Oleh karena itu, hal pertama adalah **memastikan Anda memiliki cukup BNB untuk membayar biaya gas** transaksi on-chain. Biasanya, biaya gas berfluktuasi tergantung pada jumlah transaksi dalam antrean, jika ada lebih banyak transaksi, biaya gas yang lebih tinggi mungkin diperlukan untuk memproses transaksi. Di BNB Smart Chain, biaya gas biasanya berkisar dari sen hingga satu dolar USD dalam BNB. Pelajari lebih lanjut tentang [biaya gas di sini](https://academy.binance.com/en/glossary/gas).

**Biaya Transaksi**

Jika tindakan Swap Anda masih tidak berhasil dan menampilkan kesalahan untuk merevisi Slippage -- Anda mungkin ingin memeriksa apakah token yang coba Anda Swap memiliki **biaya dan pembatasan pada transaksi**.

Tidak jarang token di BNB Smart Chain menyertakan **biaya transaksi** dalam kontrak mereka, biasanya biaya ini dapat digunakan untuk pembakaran, mendanai treasury proyek yang adil — misalnya, [token APX ini memiliki pajak 1% pada setiap transaksi](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) untuk dikirim ke alamat pembakaran, sehingga lebih banyak transaksi berarti lebih banyak pembakaran, mengumpulkan nilai bagi pemegang token APX.

Dengan biaya transaksi, baik itu inklusif (sebagian dari jumlah Swap dikirim ke tempat lain selain alamat Anda sehingga output lebih kecil dari yang diperkirakan untuk input yang diperkirakan) atau eksklusif (memerlukan transfer tambahan dari alamat Anda untuk mengirim token tambahan sehingga input lebih besar dari yang diperkirakan untuk output yang diperkirakan), itu mempengaruhi jumlah input dan output yang Anda setujui untuk menandatangani transaksi. Dalam banyak kasus, transaksi tidak dapat memenuhi persyaratan input dan output karena pajak.

**Swap dengan Biaya Transaksi**

Sebelum Anda menukar token apa pun, pastikan Anda telah mengunjungi situs web mereka untuk memahami apakah mereka memiliki mekanisme biaya transaksi (atau _pajak_ seperti yang dikatakan banyak proyek). Jika ada, pastikan Anda menetapkan Slippage yang cukup untuk mengakomodasi biaya transaksi -- misalnya, jika ada biaya transaksi sebesar 5%, Slippage Anda harus ditetapkan setidaknya 5% ditambah Slippage trading normal tergantung pada jumlah trading dan likuiditas token, katakanlah 5,5%-6%.

Dalam beberapa kasus ekstrem termasuk beberapa penipuan, beberapa token bahkan memiliki pemblokiran pada sebagian besar atau semua transfer on-chain, atau hanya mengizinkan alamat tertentu untuk menjual, dalam kasus seperti itu tidak mungkin menukar token dengan sukses. Pelajari tentang token yang coba Anda Swap dan waspadai biaya dan pembatasan apa pun!



### Apakah antarmuka Swap baru menggunakan likuiditas v2 atau stable swap?

Ya. Swap v3 baru menggunakan likuiditas dari PancakeSwap v3, v2 dan stable swap untuk mendapatkan rute trading terbaik.



### Apa itu split routing?

Di Swap v3, perdagangan Anda mungkin dipecah menjadi beberapa rute untuk mengeksekusi perdagangan dengan nilai terbaik.

Untuk melihat detail lebih lanjut tentang bagaimana perdagangan Anda diarahkan, ketuk tombol "v" pada bagian "Route" untuk memperluas dan melihat detailnya.

Pelajari lebih lanjut [di sini](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences).



### Bagaimana cara mengkustomisasi atau menonaktifkan sumber likuiditas tertentu?

Swap v3 baru menggunakan likuiditas dari PancakeSwap v3, v2 dan stable swap untuk mendapatkan rute trading terbaik. Namun, Anda dapat mengkustomisasi atau menonaktifkan sumber likuiditas tertentu jika Anda tidak ingin perdagangan Anda diarahkan melalui mereka.

Saat melihat rute trading, klik tombol "Customize Routing". Atau klik tombol ⚙️ di sudut kanan atas antarmuka Swap dan pilih "Customize Routing".

Dalam pop-up "Customize Routing", Anda dapat memilih sumber likuiditas mana yang ingin Anda gunakan. Atau nonaktifkan multihop sepenuhnya.

Catatan: menonaktifkan multihop dapat menyebabkan peningkatan Slippage atau nilai trading yang lebih buruk pada pasangan trading tertentu. Lanjutkan dengan hati-hati.

Pelajari lebih lanjut [di sini](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources).



## Likuiditas

### Apa itu tingkatan biaya dan bagaimana cara memilih yang tepat?

Di Exchange v3, saat Anda menyediakan likuiditas, Anda dapat memilih di antara beberapa biaya trading yang berbeda (0,01%, 0,05%, 0,25%, dan 1%) untuk pasangan token yang sama.

Misalnya, untuk CAKE-BNB, mungkin ada pasangan 0,25%, yang berarti biaya trading sebesar 0,25% berlaku untuk setiap perdagangan. Namun, beberapa penyedia likuiditas mungkin memilih untuk menyediakan likuiditas ke pasangan trading CAKE-BNB dengan tingkat biaya 0,05%, menawarkan penawaran yang lebih baik dan menarik lebih banyak volume trading.

Tidak ada jawaban "benar" untuk konfigurasi biaya trading mana yang dipilih. Ini tergantung pada token dalam pasangan trading. Biasanya, token volatil harus memiliki biaya trading yang lebih tinggi untuk lebih baik mengkompensasi impermanent loss yang disebabkan oleh volatilitas. Di sisi lain, token seperti stablecoin memiliki pergerakan harga yang lebih kecil dan impermanent loss yang lebih rendah, oleh karena itu biaya trading mereka harus lebih rendah.

Saat memilih pasangan token, antarmuka "Tambah Likuiditas" akan secara otomatis memilih tingkatan biaya yang paling populer untuk Anda.



### Mengapa dua token setoran saya tidak sama nilainya dalam USD?

Di Exchange V3, aset dasar dalam posisi likuiditas tidak selalu memiliki nilai yang sama dalam USD. Ini akan tergantung pada pengaturan rentang harga suatu posisi dan harga pasangan saat ini.

Bahkan, jika posisi Anda keluar dari rentang, semua token akan dikonversi ke satu aset tunggal. Selain itu, Anda dapat menyediakan likuiditas ke rentang harga yang tidak mencakup harga saat ini dan hanya menyetor satu aset tunggal. Lanjutkan membaca untuk mempelajari lebih lanjut ⬇️



### Apa yang terjadi jika posisi likuiditas saya keluar dari rentang?

Anda tidak akan mendapatkan hadiah biaya trading jika harga saat ini keluar dari rentang harga yang ditentukan dalam posisi Anda.

Selain itu, semua token akan dikonversi ke satu aset tunggal tergantung pada arah kondisi harga.

Misalnya, jika posisi CAKE/BUSD dikonfigurasi dengan rentang harga 3 BUSD per CAKE hingga 5 BUSD per CAKE. Dan semua aset dalam posisi akan dikonversi ke BUSD jika harga CAKE lebih tinggi atau sama dengan 5 BUSD per CAKE, dan sebaliknya.

Harap diperhatikan bahwa jika harga bergerak kembali ke dalam rentang, Anda akan mulai menerima hadiah biaya trading lagi. Tidak diperlukan tindakan tambahan.



### Apakah lebih baik selalu menyediakan likuiditas dengan rentang yang lebih kecil?

Menyediakan likuiditas ke rentang harga yang lebih kecil akan membantu memusatkan likuiditas Anda ke rentang harga tertentu, meningkatkan pangsa relatif Anda terhadap total likuiditas dalam rentang harga tersebut, yang berpotensi menghasilkan lebih banyak hadiah biaya trading.

Namun, harap diingat bahwa hanya posisi likuiditas aktif yang akan mendapatkan hadiah biaya trading dari perdagangan. Ini berarti Anda hanya akan mendapatkan hadiah ketika harga trading saat ini berada dalam rentang harga yang ditentukan dalam posisi likuiditas.



### Apakah ada cara untuk menyesuaikan posisi saya secara otomatis agar selalu berada dalam rentang dan mendapatkan hadiah biaya?

PancakeSwap v3 mendukung deposit likuiditas satu klik melalui Zap, tersedia di BNB Chain dan Ethereum.



### Apa yang akan menjadi rincian biaya trading untuk Exchange v3?

|                    | 0,01% | 0,05% | 0,25% | 1%  |
| ------------------ | ----- | ----- | ----- | --- |
| Penyedia Likuiditas | 67%   | 66%   | 68%   | 68% |
| Pembakaran CAKE    | 15%   | 15%   | 23%   | 23% |
| Treasury           | 18%   | 19%   | 9%    | 9%  |

### Apakah hadiah biaya LP secara otomatis di-compound seperti Exchange v2?

Tidak.

Di Exchange v3 Anda perlu mengklaim hadiah biaya trading secara manual. Anda dapat melakukannya di halaman detail posisi. Anda dapat menemukan semua posisi likuiditas v3 Anda di halaman likuiditas.



### Apa yang mempengaruhi APR LP?

Di Exchange v3, APR hadiah biaya LP dapat bervariasi antara posisi likuiditas. Ini didasarkan pada faktor-faktor berikut:

* Volume trading\
  \- lebih banyak volume menghasilkan lebih banyak hadiah biaya
* Tingkatan biaya pasangan likuiditas\
  \- tingkatan biaya yang lebih tinggi menghasilkan lebih banyak hadiah biaya dari perdagangan individual
* Jumlah token yang didepositkan\
  \- lebih banyak token dalam posisi berarti pangsa relatif yang lebih besar terhadap total likuiditas aktif, yang mendapatkan lebih banyak hadiah biaya trading dari perdagangan
* Rentang harga yang dipilih\
  \- rentang harga yang lebih kecil memungkinkan konsentrasi yang lebih tinggi untuk jumlah token yang sama yang didepositkan, yang berarti pangsa relatif yang lebih besar terhadap total likuiditas aktif, dan mendapatkan lebih banyak hadiah biaya trading dari perdagangan
* Jumlah likuiditas yang saat ini aktif\
  \- jika ada lebih banyak pengguna yang mendepositkan dan memusatkan likuiditas mereka dengan rentang yang sama seperti Anda, Anda akan mendapatkan lebih sedikit biaya trading karena pangsa relatif yang lebih kecil terhadap total
* Apakah posisi likuiditas aktif\
  \- hanya posisi likuiditas aktif yang akan mendapatkan hadiah biaya trading



### Bisakah saya menyediakan likuiditas v2?

Menyediakan likuiditas v2 tidak lagi disarankan. Kami merekomendasikan penggunaan likuiditas v3 untuk memanfaatkan fitur baru guna meningkatkan efisiensi.

Jika Anda ingin melanjutkan menambah likuiditas v2:

* Jika pasangan token tidak memiliki pool v3, atau memiliki lebih banyak likuiditas di v2 daripada pool terbesar di v3. "Tambah Likuiditas V2" akan muncul. Cukup klik untuk beralih ke penambahan likuiditas v2
* Sebagai alternatif, gunakan `/v2` di URL untuk selalu menggunakan penyediaan likuiditas v2



### Mengapa saya tidak bisa menambahkan likuiditas ke pasangan yang baru saya buat?

Karena bug dari Exchange V2 lama (ada di setiap fork UniSwap V2), Anda tidak akan dapat menambahkan likuiditas ke pasangan menggunakan UI likuiditas PancakeSwap normal dan panggilan kontraknya jika pasangan:

* Dibuat dengan memanggil `createPair` pada FactoryV2 tanpa mendepositkan likuiditas awal dan mencetak token LP awal
* Kemudian, salah satu token dalam pasangan telah ditransfer secara manual ke dalam kontrak pool sementara memanggil `sync`

{% hint style="info" %}
Baru-baru ini, jumlah serangan semacam itu yang meningkat terdeteksi di PancakeSwap Exchange V2 di BNB Chain.

Kami sangat merekomendasikan menggunakan UI kami untuk membuat pasangan trading untuk token Anda dengan menambahkan likuiditas awal saat pembuatan pasangan.
{% endhint %}

Sementara Tim sedang bekerja keras untuk menyelesaikan masalah ini, berikut adalah panduan langkah demi langkah untuk menyelesaikannya menggunakan BscScan:

#### Temukan alamat pool dan halaman BscScan-nya

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

Jika pasangan Anda terpengaruh, Anda akan melihat tautan ke halaman BscScan untuk pasangan/pool trading dalam prompt kesalahan.

Sebagai alternatif, Anda dapat menuju ke Factory V2 ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)), pergi ke "Read Contract", "6. getPair", masukkan alamat dua token dalam pasangan trading Anda, dan klik "Query". Anda seharusnya melihat alamat pasangan di kolom return.

#### Periksa token mana yang telah didepositkan dan transfer token lainnya ke pasangan secara manual

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png)

Dari kolom saldo token di BscScan, Anda dapat memeriksa token mana yang telah didepositkan ke pool. Biasanya, itu harus token yang dipasangkan. (Seperti WBNB, USDT, dll...)

Setelah dikonfirmasi, Anda harus mentransfer aset lainnya secara manual ke dalam kontrak pool. Anda dapat melakukannya di aplikasi dompet yang Anda pilih dengan memasukkan alamat pool sebagai penerima.

Anda dapat mentransfer jumlah berapa pun tetapi karena ini secara efektif "menyumbangkan" aset ke pool. Anda akan mentransfer aset Anda ke likuiditas tanpa mencetak token likuiditas. Jadi kami merekomendasikan untuk meminimalkan jumlah ini.

{% hint style="warning" %}
PENTING: Setelah mentransfer token, Anda harus segera memanggil `sync()` pada pool.
{% endhint %}

Anda dapat melakukannya dengan menuju ke halaman BscScan untuk pasangan trading, pergi ke "Write Contract", "8. Sync", dan mengklik tombol "Write". Anda perlu menghubungkan dompet sebelum melakukan transaksi.

Setelah transaksi dikonfirmasi, Anda dapat menambahkan likuiditas berikutnya di UI PancakeSwap.

#### Bagaimana jika saya ingin menentukan harga peluncuran?

Anda harus menyesuaikan pool ke harga peluncuran saat mentransfer token dan memperbaiki pool.

Jumlah yang akan ditransfer dapat dihitung menggunakan:

* `tokenInside`: token yang sudah ditransfer ke dalam pool. Biasanya itu harus token yang dipasangkan. (Seperti WBNB, USDT, dll...)
* `tokenToSend`: token yang akan dikirim ke pool. Biasanya itu harus token proyek Anda
* `tokenInside.price`: harga USD dari tokenInside
* `tokenToSend.price`: harga USD dari tokenToSend (harga peluncuran)
* `pool`: pool V2

Dengan rumus berikut:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

Jika hasilnya lebih kecil dari 0 (biasanya terjadi ketika harga peluncuran sangat besar. Anda mungkin perlu terlebih dahulu mendepositkan lebih banyak `tokenInside` ke dalam pool)



### Bagaimana cara mengelola stable LP, dan LP v2 lama?

Anda dapat mengelolanya seperti biasa dengan membuka halaman [Liquidity](https://pancakeswap.finance/liquidity).



### Mengapa saya perlu mengatur ulang persetujuan pada USDT sebelum mengaktifkan/menyetujui?

Saat beroperasi di mainnet Ethereum, token USDT mengikuti logika berbeda untuk mengelola persetujuan dan kelonggaran token.

Oleh karena itu, ketika batas pengeluaran terlalu rendah. Diperlukan pengaturan ulang persetujuan sebelum menetapkan yang baru.
