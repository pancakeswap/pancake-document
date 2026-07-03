# Pengantar Options



{% hint style="danger" %}
\[DIARSIPKAN] Options — Per 11 Maret 2025\
Jika Anda masih memiliki Likuiditas untuk ditarik, harap lakukan segera dengan mengunjungi https://www.stryke.xyz/en/trade.
{% endhint %}



## Apa itu Options?

Options adalah kontrak derivatif yang memberi pembeli hak, tetapi bukan kewajiban, untuk membeli (call option) atau menjual (put option) aset yang mendasarinya pada harga yang telah ditentukan (harga strike) dalam periode yang ditentukan (tanggal kedaluwarsa).

## Jenis-jenis Options?

### Call Options

Call option memberi pemegang hak untuk membeli aset yang mendasarinya pada harga strike yang disepakati pada atau sebelum tanggal kedaluwarsa. Pedagang membeli call option ketika mereka memperkirakan harga aset yang mendasarinya akan naik. Ini memungkinkan mereka untuk mendapatkan keuntungan dari potensi kenaikan harga tanpa harus memiliki aset yang mendasarinya secara langsung.

> Seorang pedagang membeli call option pada Bitcoin dengan harga strike $50.000 yang kedaluwarsa dalam satu bulan. Jika harga Bitcoin naik di atas $50.000 dalam bulan itu, investor dapat mengeksekusi option untuk membeli Bitcoin seharga $50.000, berpotensi mendapatkan keuntungan dari selisih harga.

### Put Options

Put option memberi pemegang hak untuk menjual aset yang mendasarinya pada harga strike yang disepakati pada atau sebelum tanggal kedaluwarsa. Pedagang membeli put option ketika mereka memperkirakan harga aset yang mendasarinya akan turun. Ini memungkinkan mereka untuk mendapatkan keuntungan dari potensi penurunan harga tanpa harus short sell aset yang mendasarinya. Biasanya put option juga digunakan untuk lindung nilai terhadap risiko penurunan portofolio investasi.

> Seorang pedagang membeli put option pada Ethereum dengan harga strike $3.000 yang kedaluwarsa dalam dua minggu. Jika harga Ethereum turun di bawah $3.000 dalam kerangka waktu itu, pedagang dapat mengeksekusi option untuk menjual Ethereum seharga $3.000, sehingga mengurangi potensi kerugian.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Posisi Options

Untuk setiap jenis option, terdapat dua posisi potensial:

### **Long Option (Pembeli Option)**&#x20;

Posisi ini melibatkan pembayaran premi di muka untuk mendapatkan option. Jika option berakhir dalam keuntungan, pemegang menerima penyelesaian.

### **Short Option (Penulis/Penjual Option)**

Dalam posisi ini, penjual menerima premi di muka untuk menerbitkan option. Namun, jika option berakhir dalam keuntungan (untuk pembeli; berdasarkan harga yang mendasari, harga strike, dan jenis option), penjual berkewajiban untuk membayar penyelesaian.

## American vs. European Options

* **American Options:** Dapat dieksekusi kapan saja sebelum tanggal kedaluwarsa. Fleksibilitas ini membuatnya lebih berharga daripada European options.
* **European Options:** Hanya dapat dieksekusi pada tanggal kedaluwarsa. Umumnya lebih murah daripada American options karena kurangnya fleksibilitas.

## Kapan menggunakan Options?

Berikut adalah beberapa contoh kasus penggunaan:

1. **Spekulasi:** Seorang investor percaya bahwa harga Bitcoin akan meningkat selama sebulan ke depan. Mereka membeli call option pada Bitcoin untuk mendapatkan keuntungan dari kenaikan harga yang diantisipasi.
2. **Lindung Nilai:** Seorang validator mata uang kripto ingin melindungi diri dari potensi penurunan harga Ethereum. Mereka membeli put option pada Ethereum untuk melindungi dari kerugian jika harga turun di bawah tingkat tertentu.
3. **Menghasilkan Pendapatan:** Seorang investor kripto yang memegang sejumlah besar Ether memutuskan untuk menulis call option pada kepemilikan mereka, mendapatkan premi sambil tetap berpartisipasi dalam potensi gerakan harga ke atas.

## Penetapan Harga Options

Penetapan harga options bersifat kompleks dan melibatkan berbagai faktor, dengan model Black-Scholes sebagai yang paling umum digunakan.&#x20;

Faktor-faktor utama yang mempengaruhi penetapan harga options meliputi:

* **Harga Aset yang Mendasari:** Harga pasar saat ini dari aset yang mendasarinya.
* **Harga Strike:** Harga di mana pemegang option dapat membeli atau menjual aset yang mendasarinya.
* **Volatilitas:** Tingkat fluktuasi harga dalam aset yang mendasarinya.&#x20;
* **Waktu Menuju Kedaluwarsa:** Waktu tersisa hingga option kedaluwarsa.
* **Suku Bunga:** Tingkat pengembalian bebas risiko.

Penetapan harga options menentukan premi/biaya yang diterima penulis ketika pedagang options membeli option mereka. Penulis option terekspos pada risiko membayar penyelesaian jika option mereka kedaluwarsa In-The-Money atau ITM (menguntungkan bagi pembeli). Oleh karena itu, premi yang mereka terima dari pembeli harus mencerminkan secara wajar probabilitas peristiwa ITM.

Premi CLAMM options PancakeSwap diturunkan dari model Black-Scholes dengan asumsi berikut:

* Tingkat bebas risiko diasumsikan nol.
* Volatilitas berdasarkan volatilitas historis 30 hari dari yang mendasari \[digunakan sebagai proksi untuk implied volatility (IV)].

Beberapa pengecualian meliputi:

* IV $ETH dan $BTC diambil langsung dari Deribit jika harga strike cocok. Jika harga strike tidak cocok, strike atas dan bawah terdekat dari Deribit diberi bobot berdasarkan tingkat offset untuk menetapkan IV.
* $ARB menggunakan volatilitas historis berbasis beta 30 hari dengan menghitung harga strike efektif dari aset dasar terhadap $ETH untuk mengekstrapolasi IV yang kemudian dikalikan dengan beta aset dasar terhadap $ETH

Aset dengan volatilitas tinggi akan memiliki premi yang lebih mahal daripada aset dengan volatilitas lebih rendah karena ada risiko yang lebih besar bagi penulis option yang kedaluwarsa ITM.

## Penyelesaian Options

### Kondisi Penyelesaian

* Penyelesaian ditentukan berdasarkan moneyness option pada saat kedaluwarsa.
* Penyelesaian hanya dihitung jika option berada In-The-Money (ITM) saat eksekusi.

### Kondisi ITM

* **Call Option:** Jika Harga Spot Saat Penyelesaian > Harga Strike
* **Put Option:** Jika Harga Spot Saat Penyelesaian < Harga Strike

### Perhitungan Penyelesaian

* **Call Option:** #Options \* (Harga Spot Saat Penyelesaian - Harga Strike)
* **Put Option:** #Options \* (Harga Strike - Harga Spot Saat Penyelesaian)

### Moneyness

Moneyness merujuk pada nilai intrinsik suatu option, ditentukan dengan membandingkan harga strikenya dengan harga spotnya pada saat eksekusi.

### Klasifikasi

1. Out-of-The-Money (OTM):
   1. Suatu option adalah OTM jika harga spot saat penyelesaian berbeda dari harga strike dan tidak ada nilai yang akan dipertukarkan jika penyelesaian terjadi segera.
   2. Kondisi:
      1. Call Option: Harga Spot < Harga Strike
      2. Put Option: Harga Spot > Harga Strike

{% hint style="info" %}
Call option $ETH dengan harga strike $2.000 akan OTM jika harga spot adalah $1.800 ($1.800 < $2.000 yaitu OTM).
{% endhint %}

2. At-The-Money (ATM):
   1. Suatu option adalah ATM jika harga spot saat penyelesaian sama dengan harga strike dan tidak ada nilai yang akan dipertukarkan jika penyelesaian terjadi segera.
   2. Kondisi: Baik Call maupun Put Options: Harga Spot = Harga Strike

{% hint style="info" %}
Baik call option maupun put option $ETH dengan harga strike $1.800 akan ATM jika harga spotnya juga $1.800 ($1.800 = $1.800 yaitu ATM).
{% endhint %}

3. In-The-Money (ITM):
   1. Suatu option adalah ITM jika harga spot saat penyelesaian berbeda dari harga strike dan ada nilai yang akan dipertukarkan jika penyelesaian terjadi segera.
   2. Kondisi:
      1. Call Option: Harga Spot > Harga Strike
      2. Put Option: Harga Spot < Harga Strike

{% hint style="info" %}
Call option $ETH dengan harga strike $1.600 akan ITM jika harga spot adalah $1.800 ($1.800 > $1.600 yaitu ITM).
{% endhint %}

Penyelesaian yang diperoleh oleh pembeli option sama dengan agunan yang hilang oleh penulis option. Penyelesaian tidak termasuk premi options yang dibayarkan, yang diperhitungkan saat menghitung keuntungan atau kerugian bagi pembeli dan penulis option.
