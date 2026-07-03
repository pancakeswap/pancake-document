---
description: Gunakan veCAKE Anda untuk memberikan suara dan menentukan cara distribusi emisi CAKE
hidden: true
---

# Gauges Voting

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### Apa itu gauge?

Untuk memahami gauges voting, Anda dapat menganggap produk apa pun yang memerlukan emisi CAKE sebagai serangkaian gauge. Ini mencakup farm, pool hadiah CAKE mingguan, vault position manager, dan lain-lain.

Pemegang veCAKE kini dapat menggunakan veCAKE mereka sebagai suara untuk menentukan berapa % CAKE yang dialokasikan ke produk mana. Semakin banyak veCAKE yang terkumpul oleh gauge melalui Gauges Voting, semakin banyak emisi CAKE yang akan dialokasikan ke pool likuiditas / vault position manager yang mendasarinya.

{% hint style="info" %}
Suara dalam setiap epoch (E-0) menentukan emisi CAKE untuk epoch berikutnya (E+1), dan perubahan ini hanya berlaku setelah epoch saat ini berakhir.
{% endhint %}

#### Jenis Gauge

Ada dua jenis gauge - 'core' dan 'non-core'. Emisi CAKE ke gauge sebelumnya dikendalikan oleh Kitchen, sementara komunitas memengaruhi emisi ke pool 'non-core' dengan memberikan suara menggunakan veCAKE.

1. Gauge 'core' mencakup pasangan dengan token utama dan stablecoin (WBTC, ETH, BNB, USDC, USDT, dll.) - Kitchen akan memastikan pasangan-pasangan ini menerima hadiah CAKE yang memadai karena berkontribusi secara signifikan terhadap pendapatan protokol
2. Gauge 'non-core' mewakili semua gauge lainnya yang tidak diklasifikasikan sebagai gauge 'core'

## Cara Memberikan Suara?

### 1 - Pahami jadwal pemungutan suara

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Pemungutan suara bobot gauge dilakukan setiap dua minggu. Awal epoch, seperti halnya bagi hasil pendapatan, adalah pukul 00:00 UTC setiap hari Kamis genap.

Dalam contoh di atas:

* Epoch 1 dimulai pada pukul 00:00 UTC, hari pertama, Kamis pada Minggu ke-1.
* Epoch 1 berakhir 2 minggu kemudian, pada pukul 00:00 UTC, tanggal 15, Kamis pada Minggu ke-3.
* Pengguna dapat memberikan suara selama pukul 00:00 UTC dari tanggal 1 hingga 14.
* **TIDAK** ada suara yang dapat diberikan selama pukul 00:00 UTC dari tanggal 14 hingga 15 karena suara sedang disesuaikan dan dihitung.
* Hasil pemungutan suara akan di-snapshot pada pukul 00:00 UTC tanggal 15. Akhir Epoch 1.
* Hasil pemungutan suara akan diterapkan dalam 72 jam setelah epoch ditutup.

### 2 - Jadilah memenuhi syarat

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Karena veCAKE secara bertahap berkurang sesuai dengan sisa waktu kunci, hasil pemungutan suara akan diambil melalui snapshot di akhir setiap epoch. Ini mencakup jumlah total veCAKE, dan veCAKE yang dimiliki setiap pengguna.

Dalam contoh di atas:

* Hasil untuk Epoch 1, akan didasarkan pada saldo veCAKE pada pukul 00:00 UTC, tanggal 15.
* Pengguna yang posisi veCAKE-nya membuka kunci sebelum atau pada tanggal 15, akan memiliki saldo veCAKE 0 pada saat snapshot. Oleh karena itu mereka tidak memiliki kekuatan pemungutan suara untuk Epoch 1.

Oleh karena itu, untuk memenuhi syarat, Anda harus mendapatkan posisi veCAKE aktif, yang membuka kunci **LEBIH DARI** waktu akhir/snapshot epoch saat ini.

Dalam contoh di atas:

* Jika Anda ingin memberikan suara di epoch 1, Anda harus memiliki posisi veCAKE yang membuka kunci pada tanggal 21 atau lebih dari tanggal 21, atau hari Kamis pada minggu ke-3.

### 3 - Periksa hasil pemungutan suara saat ini

Buka "CAKE staking", gulir ke bawah dan cari bagian "Gauges Voting", lalu klik "Check Gauges".

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

Di bagian kiri atas. Anda dapat menemukan:

* veCAKE Anda.
* Waktu snapshot dan waktu akhir pemungutan suara untuk epoch saat ini.
* Total jumlah hadiah CAKE yang akan didistribusikan di epoch berikutnya berdasarkan hasil pemungutan suara dari epoch saat ini.
* Total jumlah suara veCAKE yang diberikan.

Di kanan atas, Anda dapat menemukan diagram lingkaran yang mewakili % masing-masing gauge yang diterima.

Di bagian bawah, terdapat daftar lengkap setiap gauge yang dipilih. Dengan jumlah suara yang diterima dan % bobot yang diharapkan, mereka mendapatkan di epoch saat ini. Ada juga kolom "boost" dan "caps", yang merinci dua karakteristik gauge yang penting. Lanjutkan membaca untuk informasi lebih lanjut.

#### Boost Gauge dan Batas Emisi

Untuk memastikan hadiah CAKE diberikan ke gauge yang paling produktif. Setiap gauge dapat diterapkan dengan boost dan/atau batas emisi. Dua karakteristik tersebut dapat ada secara bersamaan.

Boost Gauge adalah pengganda yang diterapkan pada jumlah suara yang diterima gauge, berkisar dari 1x hingga 2,5x (gauge untuk pool V3 dibatasi pada 2x). Ini untuk mendorong suara dan likuiditas untuk pasangan perdagangan yang penting.

Batas emisi adalah batas maksimum pada % bobot yang dapat diterima gauge, berkisar dari 2% hingga 20%. Ini untuk mendorong keadilan dalam alokasi dan mencegah penyalahgunaan sistem gauge.

Misalnya:

* Sebuah gauge memiliki 10 suara, boost 2x dan batas 15%. Total suara adalah 100.
* Setelah menerapkan boost, gauge ini akan memiliki 20 suara, bobot 20% terhadap total (100).
* Namun, karena memiliki batas 15%, % akhir hadiah CAKE yang diterima gauge ini di epoch berikutnya akan disesuaikan menjadi 15%.

#### Bagaimana Boost Gauge dan Batas Emisi ditentukan?

Selama proses pendaftaran gauge, kami meminta pemohon untuk mengusulkan nilai pengganda boost dan % batas emisi yang ingin mereka tetapkan pada gauge. Ini harus dipilih oleh pemegang veCAKE, bersama dengan seluruh pendaftaran gauge.

Opsi default untuk semua gauge adalah pengganda 1,00x dan batas emisi 5%. Ini dapat diubah dengan proposal di masa mendatang.

{% hint style="info" %}
Harap diperhatikan bahwa hasil pemungutan suara diperbarui setiap minggu. Angka-angka dihitung berdasarkan saldo veCAKE pada pukul 00:00 UTC, hari Kamis berikutnya yang akan datang.
{% endhint %}

### 4 - Tambahkan gauge untuk dipilih

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Untuk memberikan suara pada gauge, gulir ke bawah dan cari bagian "My Votes". Klik "Add Gauge".

Di jendela pop-up, Anda dapat menambahkan gauge ke daftar suara Anda dengan mengklik ikon biru "+". Anda dapat menemukan hasil pemungutan suara saat ini di daftar, beserta boost dan batas.

Untuk menemukan gauge dengan cepat, Anda dapat menggunakan filter untuk memfilter gauge berdasarkan blockchain, tier biaya, dan jenis likuiditas. Atau ketikkan ticker token ke dalam kolom pencarian.

### 5 - Pilih berapa % veCAKE yang akan digunakan untuk setiap gauge

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Setelah menambahkan gauge, Anda dapat memilih berapa % veCAKE Anda yang dialokasikan ke masing-masing gauge.

Hal ini karena:

* veCAKE secara bertahap berkurang seiring dengan sisa waktu kunci. Tidak praktis untuk memperkirakan dan menghitung berapa banyak veCAKE yang tepat untuk dipilih.
* Sangat menyulitkan untuk melakukan re-vote di setiap epoch berikutnya. Oleh karena itu, gauges voting dirancang untuk membawa keputusan pemungutan suara Anda di seluruh epoch berikutnya hingga Anda memberikan suara baru.

Dalam contoh di atas:

* Saat ini, saya memiliki 2,62 veCAKE.
* Saya memutuskan untuk mengalokasikan 80% ke CAKE-BNB, yaitu 2,10 veCAKE saat ini.
* 20% ke USDC-ETH, yaitu 0,52 veCAKE, sekali lagi saat ini.
* Total veCAKE saya akan secara bertahap berkurang seiring sisa waktu kunci. Pada saat snapshot, saya mungkin memiliki lebih sedikit veCAKE, tetapi keputusan pembagian 80% - 20% saya akan tetap diterapkan pada hasil akhir.
* Selain itu, keputusan 80% - 20% ini akan diterapkan pada setiap epoch berikutnya hingga saya memperbaruinya dengan mengajukan permintaan suara baru. Atau hingga veCAKE saya menjadi 0 karena membuka kunci.

Setelah Anda mengonfirmasi keputusan, klik "Submit vote" dan konfirmasi di dompet Anda.

### 6 - Perbarui suara Anda

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Setelah suara Anda diajukan, Anda dapat melihat suara Anda diperbarui ke "Current Votes". Dan sisa veCAKE diperbarui.

Harap diperhatikan bahwa keputusan pemungutan suara untuk setiap gauge hanya dapat diperbarui setiap 10 hari. Setelah Anda mengajukan permintaan suara, semua gauge yang dipilih akan dikenakan periode pendinginan 10 hari sebelum Anda dapat mengajukan permintaan pembaruan lainnya.

Untuk memperbarui keputusan suara Anda, ubah persentasenya dan ajukan kembali.

{% hint style="info" %}
Harap diperhatikan bahwa setelah mendapatkan lebih banyak veCAKE dengan menambahkan CAKE atau memperpanjang waktu kunci. Anda perlu memperbarui semua gauge secara manual dengan mengajukan ulang permintaan suara.

Periode pendinginan 10 hari tetap berlaku terlepas dari apakah Anda mengubah keputusan % Anda.
{% endhint %}
