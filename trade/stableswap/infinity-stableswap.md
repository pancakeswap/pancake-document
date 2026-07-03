# Infinity StableSwap

### Ikhtisar

Infinity StableSwap adalah jenis pool dalam [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) yang dioptimalkan untuk menukar aset yang seharusnya diperdagangkan mendekati harga yang sama — seperti stablecoin (misalnya, USDC/USDT) atau aset yang terpeg erat (misalnya, pasangan wrapped token, token liquid staking, dan token liquid restaking).

Produk ini didukung oleh hook StableSwap yang berjalan di atas arsitektur Infinity, terinspirasi dari desain StableSwap NG milik Curve. Saat ini tersedia di BNB Chain, dengan rencana perluasan ke rantai tambahan di masa mendatang.

***

### Cara Kerjanya

Infinity StableSwap menggunakan kurva invariant stabil — hibrida antara constant-sum dan constant-product:

* Mendekati peg → kurva berperilaku mendekati constant-sum, menghasilkan Slippage yang sangat rendah untuk perdagangan di sekitar 1:1.
* Jauh dari peg → kurva secara bertahap beralih ke arah constant-product, yang membantu memulihkan keseimbangan dan melindungi pool selama ketidakseimbangan besar atau kejadian depeg.

Hal ini menjadikannya sangat efektif untuk pasangan stabil di mana penetapan harga yang ketat dan Slippage rendah paling penting.

***

### Fitur Utama

Dioptimalkan untuk Swap mendekati peg: Slippage rendah untuk perdagangan antara aset yang diharapkan diperdagangkan pada harga yang kurang lebih sama.

Penyediaan likuiditas yang sederhana: Penyedia likuiditas (LP) menyetor kedua token secara proporsional tanpa perlu memilih atau mengelola rentang harga — tidak seperti pool CLAMM.

Token LP ERC-20: Posisi LP Anda direpresentasikan sebagai token ERC-20 standar, sehingga mudah digunakan dengan program yield, kampanye poin, dan protokol DeFi lainnya.

Biaya dinamis: Biaya dapat disesuaikan berdasarkan kondisi keseimbangan pool, memberikan penghargaan kepada perdagangan yang membantu memulihkan pool menuju keseimbangan dan mencegah yang memperburuk ketidakseimbangan.

Dukungan routing Infinity: Perdagangan secara otomatis diarahkan melalui pool StableSwap ketika menawarkan harga terbaik — tidak diperlukan langkah tambahan bagi trader.

Parameter Amplifikasi (A) yang dapat disesuaikan: Operator pool dapat menaikkan atau menurunkan parameter A dari waktu ke waktu untuk beradaptasi dengan perubahan kondisi pasar, dengan pengamanan untuk mencegah perubahan mendadak.

***

### Parameter Pool

Perilaku pool StableSwap diatur oleh sekumpulan kecil parameter, yang biasanya ditetapkan saat pembuatan pool.

#### Koefisien Amplifikasi (A)

Parameter A mengontrol seberapa erat pool mengikuti peg harga 1:1.

| Nilai A    | Efek                                                                                        |
| ---------- | ------------------------------------------------------------------------------------------- |
| A lebih tinggi | Kurva lebih ketat di sekitar peg; Slippage lebih rendah mendekati 1:1; lebih sensitif terhadap ketidakseimbangan |
| A lebih rendah | Kurva lebih longgar; berperilaku lebih seperti pool constant-product standar               |

Panduan umum: Gunakan A yang lebih tinggi untuk aset dengan peg yang kuat dan andal (misalnya, USDC/USDT). Gunakan A yang lebih rendah untuk aset dengan peg yang lebih longgar atau lebih volatil (misalnya, beberapa pasangan LST).

Parameter A dapat dinaikkan atau diturunkan secara bertahap oleh operator pool selama periode waktu yang ditentukan. Perubahan diterapkan secara bertahap dengan pengamanan untuk mencegah manipulasi atau pergeseran harga mendadak.

#### Pengali Biaya Off-Peg

Parameter tambahan yang menyesuaikan biaya efektif saat pool bergerak menjauh dari keseimbangan. Ini membantu mencegah perdagangan yang akan semakin membuat pool tidak seimbang dan membuat pool lebih kuat selama tekanan pasar atau kejadian depeg.

#### Biaya Dinamis

Biaya yang dikenakan pada setiap Swap, dibayarkan kepada penyedia likuiditas. Infinity StableSwap mendukung biaya dinamis — artinya biaya efektif pada suatu perdagangan tertentu dapat bervariasi tergantung pada kondisi pool saat ini (misalnya, apakah perdagangan tersebut meningkatkan atau memperburuk keseimbangan).

***

### Infinity StableSwap vs. Classic StableSwap

Jika Anda pernah menggunakan StableSwap PancakeSwap yang ada sebelumnya, inilah yang berubah — dan apa yang tetap sama.

| <p><br></p>                   | Classic StableSwap                                             | Infinity StableSwap                                                                      |
| ----------------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Kurva penetapan harga         | Invariant stabil (hibrida constant-sum / constant-product)     | Kurva invariant stabil yang sama, Slippage rendah yang sama mendekati peg                |
| Token LP ERC-20               | ✅ Ya                                                           | ✅ Ya                                                                                     |
| Pembuatan pool                | Berat operasional; memerlukan pengaturan manual oleh tim        | Tanpa izin — siapa saja dapat membuat pool                                               |
| Biaya Swap                    | Tetap per pasangan (misalnya 0,01% untuk USDC/USDT)            | Biaya dinamis — menyesuaikan berdasarkan bagaimana perdagangan mempengaruhi keseimbangan pool |
| Parameter Amplifikasi (A)     | Statis — ditetapkan sekali, tidak dapat diubah                  | Dapat disesuaikan — dapat dinaikkan atau diturunkan secara bertahap seiring waktu         |
| Pengali biaya off-peg         | ❌ Tidak didukung                                               | ✅ Didukung — membantu melindungi pool selama kejadian depeg                               |
| Efisiensi gas                 | Standar                                                        | Ditingkatkan — mendapat manfaat dari Singleton dan Flash Accounting milik Infinity        |

#### Yang tetap sama

* Kurva penetapan harga inti dan perilaku Slippage rendah mendekati peg tidak berubah.

#### Yang baru dan lebih baik

* Pembuatan Pool Tanpa Izin: Pool dapat dibuat tanpa izin tanpa memerlukan pengaturan manual oleh tim.
* Biaya dinamis melindungi LP: Alih-alih biaya tetap tunggal, biaya dapat disesuaikan per perdagangan berdasarkan apakah perdagangan membantu atau merusak keseimbangan pool — membuat pool lebih tangguh selama kondisi volatil.
* Parameter A yang dapat disesuaikan: Koefisien amplifikasi dapat disetel seiring waktu sesuai perubahan kondisi pasar, bukan dikunci saat deployment selamanya.

***

### Pertanyaan yang Sering Diajukan

Aset apa yang cocok untuk Infinity StableSwap?

Aset yang diharapkan diperdagangkan mendekati harga yang sama: stablecoin (USDC, USDT, BUSD, dll.), padanan wrapped dari aset yang sama (misalnya, WBTC/cbBTC), dan pasangan token liquid staking / liquid restaking token (LST/LRT) tertentu di mana volatilitas peg rendah.

<br>

Apa perbedaan Infinity StableSwap dengan StableSwap PancakeSwap yang lama?

Infinity StableSwap diimplementasikan sebagai hook pada PancakeSwap Infinity, yang berarti mewarisi semua manfaat infrastruktur Infinity, termasuk biaya gas yang lebih rendah melalui Singleton dan Flash Accounting, serta sistem biaya yang lebih fleksibel. Produk ini juga mendukung kemampuan baru seperti biaya dinamis dan amplifikasi yang dapat disesuaikan yang tidak ditawarkan oleh StableSwap lama.

<br>

Apakah saya perlu mengelola posisi saya dari waktu ke waktu?

Tidak. Tidak seperti CLAMM, Anda tidak perlu mengatur atau menyesuaikan rentang harga. Likuiditas Anda selalu aktif di seluruh kurva, sehingga tidak ada risiko posisi Anda menjadi "di luar rentang."

<br>

Bisakah saya menyediakan likuiditas hanya dengan satu token?

Ya, setoran satu token didukung.

<br>

Bagaimana cara kerja biaya dinamis?

Dalam Infinity StableSwap, biaya Swap dapat bervariasi per perdagangan berdasarkan bagaimana perdagangan tersebut mempengaruhi keseimbangan pool. Perdagangan yang membantu membawa pool kembali ke keseimbangan dapat membayar biaya efektif yang lebih rendah, sementara perdagangan yang memperburuk ketidakseimbangan dapat membayar biaya yang lebih tinggi. Ini dirancang untuk melindungi LP dan menjaga kondisi pool yang lebih sehat.



***



## Membuat Pool Infinity StableSwap



Pool Infinity StableSwap bersifat tanpa izin — siapa saja dapat membuatnya tanpa memerlukan persetujuan dari tim PancakeSwap.

<br>

### Langkah demi langkah

1\. Buka halaman Farm/Liquidity dan klik Buat Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Pilih Pool StableSwap dari opsi jenis pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Pilih pasangan token untuk pool Anda (misalnya USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Parameter Pool

| Parameter                  | Fungsinya                                                                                                                   |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Biaya Swap                 | Biaya yang dikenakan pada setiap Swap, dibayarkan kepada LP. Default adalah 0,01% untuk pasangan stabil yang ketat.         |
| A (Amplifikasi)            | Mengontrol seberapa erat kurva mengikuti peg. Lebih tinggi = Slippage lebih rendah mendekati 1:1, tetapi lebih sensitif terhadap ketidakseimbangan. |
| Pengali Biaya Offpeg       | Menaikkan biaya saat pool bergerak menjauh dari keseimbangan, mencegah perdagangan yang memperburuk ketidakseimbangan.      |
| Waktu Moving Average       | Jendela waktu yang digunakan untuk menghitung harga rata-rata bergerak untuk penyesuaian biaya dinamis.                     |

⚠️ Tetapkan parameter dengan hati-hati. Parameter yang salah — terutama A yang sangat tinggi pada aset dengan peg yang longgar — dapat meningkatkan risiko bagi LP. Jika tidak yakin, gunakan preset untuk jenis aset Anda dan hindari mengubah pengaturan Lanjutan.

<br>

Pilih Preset Parameter Pool — ini secara otomatis menetapkan parameter yang direkomendasikan untuk jenis aset Anda. Anda masih dapat menyesuaikannya secara manual melalui tombol Lanjutan.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Preset                                      | A    | Pengali Biaya Offpeg | Waktu Moving Average (detik) |
| ------------------------------------------- | ---- | -------------------- | ----------------------------- |
| Stablecoin yang Dapat Ditebus Fiat          | 1000 | 10                   | 600                           |
| Stablecoin Beragunan Kripto                 | 100  | 12,5                 | 600                           |
| Token Liquid Restaking                      | 500  | 10                   | 600                           |

<br>

&#x20; Tidak yakin mana yang dipilih?

* Gunakan Stablecoin yang Dapat Ditebus Fiat untuk pasangan seperti USDC/USDT
* Gunakan Stablecoin Beragunan Kripto untuk stablecoin algoritmik atau berbasis kripto
* Gunakan Token Liquid Restaking untuk pasangan LRT seperti stkBNB/WBNB.

<br>

5\. Masukkan jumlah setoran untuk menyemai likuiditas awal. Kedua jumlah token harus sama (misalnya 1 USDC dan 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Klik Pratinjau Pool, tinjau pengaturan Anda, centang kotak konfirmasi, lalu klik Buat Pool.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
