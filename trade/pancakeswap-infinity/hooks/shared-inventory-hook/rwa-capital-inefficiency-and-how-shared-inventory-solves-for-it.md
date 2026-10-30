---
description: '2026-09-04'
---

# Inefisiensi Modal RWA — dan Cara Shared Inventory Mengatasinya

Sebuah eksperimen studi kasus PancakeSwap (Bagian 1: Latar Belakang)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

Ini adalah bagian pertama dari studi kasus dua bagian. Pada bagian ini, kami menguraikan masalah efisiensi modal nyata yang dihadapi penerbit aset RWA, memperkenalkan bagaimana Shared Inventory Hook (SIH) dari PancakeSwap dirancang untuk mengatasinya, serta memperkenalkan eksperimen studi kasus langsung untuk mengujinya dengan data onchain.

Dalam beberapa minggu ke depan, kami akan menerbitkan Bagian 2: Hasil.

***

### 🧩 Apa Itu Masalah Efisiensi Modal?

Industri RWA menyukai satu angka: **berapa banyak yang telah ditokenisasi.** Angka ini menjadi judul utama di hampir setiap laporan - kelas aset baru hadir, miliaran diterbitkan, pertumbuhan ratusan persen.

Namun ada angka kedua yang terkubur, yang mungkin merupakan sinyal yang lebih penting: **berapa banyak yang benar-benar dapat diperdagangkan?**

Kesenjangan di antara kedua angka itulah intinya. Pada pelacak kanonis, [rwa.xyz](http://rwa.xyz), nilai yang _direpresentasikan_ onchain jauh melampaui nilai yang dapat _ditransaksikan_ pada waktu tertentu — data menunjukkan nilai yang terkunci, referensi, dan terdistribusi **lebih dari satu orde besaran lebih besar daripada yang berada di buku order yang dapat diperdagangkan.**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_Sumber: app.rwa.xyz/stocks_

Bagi penerbit RWA, inilah jebakannya. Menokenisasi saham, ETF, atau obligasi treasuri adalah bagian yang mudah - membuatnya dapat diperdagangkan dengan spread ketat dan andal adalah tantangannya, dan di sinilah efisiensi modal ditentukan. Tujuan utamanya adalah memungkinkan trader _benar-benar mem&#x70;erdagangkan_ aset yang ditokenisasi dengan mudah dan murah - di situlah volume dan biaya pada akhirnya berasal.

Dan inilah alasan mengapa ini secara khusus merupakan masalah _efisiensi modal_, bukan sekadar masalah likuiditas.

#### Setiap pool yang dikutip menuntut tumpukan USDT eksklusifnya sendiri

Untuk membuat satu pasangan RWA dapat diperdagangkan dalam pool likuiditas terkonsentrasi (CLAMM) tradisional, penerbit membutuhkan aset kuotasi — USDT — yang disiapkan khusus agar pembeli dapat menjual ke dalamnya. Jika mendaftarkan sepuluh pasangan, model CLAMM memerlukan pendanaan **sepuluh tumpukan USDT terpisah**, satu tumpukan per pasangan, tanpa ada yang dapat saling membantu. Dengan demikian, modal kuotasi terpecah menjadi silo-silo eksklusif.

Kami mengukurnya pada buku kami sendiri. Kami mengambil **7 pool ekuitas tokenisasi yang aktif di PancakeSwap** (masing-masing menjalankan pool V3 CLAMM tradisional) dan menarik data USDT eksklusifnya.

Snapshot: **2 September 2026.**

<table data-search="false"><thead><tr><th>Pasangan</th><th>USDT eksklusif di pool</th><th>TVL Pool</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Total</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

Itu berarti **\~$745k USDT dialokasikan secara eksklusif.**

Dan ini hanya untuk nama-nama yang memiliki buku order.

SNXXB, KORUB, SOXSB, dan DJTB sama sekali tidak memiliki buku USDT CLAMM — sudah ditokenisasi, tetapi sulit diperdagangkan.

***

### 🎯 Apa yang Harus Dioptimalkan oleh Penerbit?

Dengan mengesampingkan mekanismenya, penerbit RWA pada intinya harus menyelesaikan tiga hal:

1. **Aset mereka benar-benar dan efisien dapat diperdagangkan** — kuotasi yang ketat untuk setiap aset, bukan hanya token unggulan.
2. **Modal sesedikit mungkin** yang terikat untuk itu — aset kuotasi itu mahal; mendanai sepuluh tumpukan USDT secara eksklusif tidak terlalu efisien.
3. **Tidak perlu menjalankan meja trading —** Menerbitkan aset tanpa harus mengoperasikan infrastruktur likuiditas setiap hari.

Jadi pertanyaannya adalah apakah likuiditas dapat distrukturkan secara berbeda — dan itulah yang dirancang untuk diselesaikan oleh Shared Inventory Hook dari PancakeSwap.

***

### 🥞 Shared Inventory Hook (SIH)

**SIH adalah hook PancakeSwap Infinity yang memungkinkan penerbit RWA mendukung banyak pasangan dari satu pot USDT bersama, alih-alih satu tumpukan eksklusif per pasangan.**

SIH melakukannya dengan menyediakan likuiditas secara just-in-time, sehingga memungkinkan:

* Kuotasi yang lebih dalam pada pasangan
* Price impact yang lebih rendah, terutama pada trade bernilai besar
* Modal penerbit RWA yang lebih bebas karena modal yang dikerahkan lebih sedikit dapat mengutip lebih banyak pasangan

Mari kita lihat klaim ini dalam praktik.

Per snapshot **2 September 2026** yang sama, SIH menyimpan **$635,028** inventaris dalam satu hook, mengutip **11 pasangan** dari **$180,467** USDT bersama, dengan tingkat utilisasi **87.7%**. Dengan ini, SIH telah memproses **$3.56M dalam 17,299 transaksi.**

Jadi itu adalah **satu saldo USDT bersama sekitar \~$700k yang mengutip sekitar \~11 pasangan dibandingkan \~$745k yang hanya mengutip 7 pasangan**.

Pekerjaan yang sama, hanya dirancang untuk menghentikan duplikasi modal.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

Dipetakan kembali ke hal-hal yang menjadi perhatian penerbit:

* N saldo USDT eksklusif secara tradisional → ✅ satu pot bersama dengan SIH
* Diterbitkan tetapi tidak dapat diperdagangkan → ✅ dapat diperdagangkan\
  Inventaris bersama yang disuntikkan secara just-in-time di sekitar harga langsung berarti token yang tidak memiliki buku USDT V3 tetap dapat dikutip, bukan hanya dicetak.
* Mengoperasikan meja trading → ✅ operator berizin\
  Penerbit menyediakan inventaris; hook dan operatornya menangani penguntipan.

***

### 🔬 Coba Shared Inventory Simulator

Bangun pemahaman tentang cara kerja SIH dengan alat perbandingan interaktif kami **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

Ini adalah perbandingan **tingkat tinggi yang dinormalisasi** antara SIH dan buku CLAMM tradisional — sejumlah faktor dunia nyata dibuat konstan di kedua sisi agar mekanisme efisiensi modal dapat diisolasi dengan jelas. Ini adalah model untuk pemahaman, bukan laporan laba rugi.

Tiga tab:

* **Tab Simulator** - bermain dengan inventaris, lebar band, dan arus transaksi untuk melihat bagaimana SIH _akan_ berkinerja dibandingkan pool CLAMM yang sebanding dalam berbagai kondisi.
* **Tab Comparison** - SIH dibandingkan langsung dengan buku **PancakeSwap V3 CLAMM** pada pool yang sama, sehingga Anda dapat melihat perbedaan pot USDT bersama vs USDT eksklusif dalam modal yang dikomitmenkan dan cakupan secara berdampingan.
* **Tab Live data** — ukur bagaimana SIH _sebenarnya_ berkinerja saat ini, diambil dari kueri onchain yang menggerakkan studi ini.

Simulator ini bertujuan membantu mendemonstrasikan cara kerja Shared Inventory Hook. Cobalah, lalu ukur dengan hasil nyata yang akan kami terbitkan dalam beberapa minggu ke depan.

***

### 🧪 Eksperimen

Selama **beberapa minggu ke depan** kami menjalankan SIH secara langsung dan mengukurnya terhadap klaim efisiensi modal di atas, menggunakan sumber onchain. Setiap minggu kami akan merilis informasi singkat baru tentang kinerja dan arsitektur SIH.

**Pasangan RWA aktif dalam studi:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Catatan: SNXXB, KORUB, SOXSB, dan DJTB sama sekali tidak memiliki buku CLAMM tradisional._

**Kami akan menerbitkan hasilnya dalam beberapa minggu ke depan di** [**Twitter**](https://x.com/PancakeSwap) **PancakeSwap.**

Hasil yang diterbitkan akan mencakup:

* **Dataset kinerja lengkap -** Seluruh data SIH selama beberapa minggu ke depan, digabungkan menjadi satu gambaran.
* **Pertanyaan alokasi modal -** Berapa banyak modal yang sebenarnya dihemat SIH bagi penerbit RWA.
* **Berhasil / gagal -** Di mana SIH melampaui ekspektasi, dan di mana masih perlu perbaikan.
* **Kesimpulan -** Kesimpulan yang beralasan tentang seberapa efektif SIH sebenarnya untuk efisiensi modal RWA.

_Catatan tentang data: Angka di sini diambil dari kueri onchain langsung dan data pasangan publik, dengan kutipan sumber di dalam teks. Beberapa perbandingan menggunakan jangka waktu yang berbeda dan telah kami tandai — studi ini dirancang untuk mengukur perbandingan yang setara, sedangkan pengantar ini hanya dapat membingkai pertanyaannya._

***

### Ingin mengaktifkan SIH pada aset Anda?

Jika Anda penerbit RWA dan lelah mendanai tumpukan USDT terpisah untuk setiap pool yang Anda kutip, ini untuk Anda.

Kami sedang melakukan onboarding penerbit RWA sekarang. Isi formulir Google ini dan kami akan memandu Anda agar aset Anda dikutip di SIH - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Terima kasih telah membaca! Ikuti kami di [X](https://x.com/PancakeSwap) untuk pembaruan terbaru, dan bergabunglah dalam percakapan di [Telegram](https://t.me/PancakeSwap) dan [Discord](https://discord.gg/pancakeswap).

Mari kita membangun,\
The Chefs 🥞

***

_Penafian: Konten ini hanya untuk informasi umum dan tujuan edukasi. Konten ini tidak boleh dianggap sebagai nasihat keuangan, hukum, atau profesional lainnya. Harga aset digital dapat berfluktuasi. Nilai investasi Anda dapat turun maupun naik._
