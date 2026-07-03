# CAKE Tokenomics v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Tingkat emisi** <a href="#emission-rate" id="emission-rate"></a>

### **Per blok**

| **Metrik**                                                                        | **Emisi/blok (CAKE)** | **Emisi/hari (CAKE)** |
| --------------------------------------------------------------------------------- | --------------------: | --------------------: |
| Emisi                                                                             |                    40 |             1.152.000 |
| Dibakar Mingguan [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual)   |                -25,75 |              -787.600 |
| **Emisi Efektif**                                                                 |          **<14,25\*** |          **364.400\*** |

\*Emisi Efektif sebenarnya sedikit di bawah jumlah ini: tambahan 45.000 CAKE per hari dialihkan dari jumlah yang dialokasikan untuk lotere, dan dibakar (PID 137 - Detail di bawah).

Selain hal di atas, sejumlah CAKE dinamis juga [dicetak ke alamat Dev](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) dengan tingkat 9,09%. Ini berarti jika 100 CAKE dipanen, maka 9,09 CAKE dicetak tambahan dan dikirim ke Alamat Dev.

{% hint style="info" %}
Semua CAKE yang dicetak ke alamat Dev dibakar dalam pembakaran mingguan dan tidak pernah masuk ke peredaran.

Oleh karena itu, kami tidak memasukkannya dalam tingkat emisi di atas.
{% endhint %}

## Distribusi <a href="#distribution" id="distribution"></a>

| Didistribusikan ke               | Hadiah/blok (% dari emisi) | Hadiah/blok (total CAKE) |              Hadiah/hari |
| -------------------------------- | -------------------------: | -----------------------: | -----------------------: |
| Farm dan Lotere                  |                     10,62% |                     4,25 |       122.400 (perkiraan) |
| di antaranya dialihkan dan dibakar |                          |                          |                  -46.000 |
| Syrup Pools                      |                        25% |                       10 |       288.000 (perkiraan) |
| **Total Emisi CAKE Harian**      |                            |                          | **364.400 (perkiraan)**  |

## **Mekanisme Deflasioner Lainnya** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
Proses pembakaran saat ini dilakukan secara manual. [Lihat transaksi pembakaran di sini](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

Selain hal di atas, CAKE juga dibakar dengan cara-cara berikut:

* **0,05%** dari setiap perdagangan yang dilakukan di PancakeSwap V2
* **100%** dari CAKE yang dikirim ke alamat Dev
* **100%** dari biaya performa CAKE dari IFO
* **100%** dari CAKE yang digunakan untuk Pembuatan Profil dan pencetakan NFT
* **100%** dari CAKE yang ditawarkan selama Farm Auctions
* **20%** dari CAKE yang digunakan untuk tiket lotere
* **45.000** CAKE per hari (secara historis dialokasikan untuk lotere) _(CAKE untuk ini dihasilkan oleh sebuah farm - PID 137)_
* **3%** dari setiap putaran pasar Prediksi digunakan untuk membeli CAKE dan dibakar
* **2%** dari setiap panen hasil di Auto CAKE Pool
* **2%** dari setiap penjualan NFT di NFT Market digunakan untuk membeli CAKE dan dibakar

## Mengapa pembakaran CAKE dilakukan secara manual?

Untuk dapat beroperasi dengan cepat, PancakeSwap diluncurkan sebagai MVP (produk minimum yang layak) dengan kontrak MasterChef yang memancarkan 40 CAKE per blok. Oleh karena itu, tim awal tidak menambahkan fungsi tambahan seperti kemampuan untuk menyesuaikan logika pencetakan CAKE. Karena migrasi ke MasterChef baru akan membutuhkan banyak waktu dan tenaga, tim memilih untuk mengurangi emisi CAKE melalui proses pembakaran manual dengan membuat dua pool:

* Legacy Lottery Pool (PID - 137) - membakar CAKE dari lotere
* Burn Pool (PID - 138) - membakar CAKE per blok

Pool-pool ini bekerja mirip dengan Farm, di mana para Chef dapat menyesuaikan persentase dari 40 CAKE per blok yang dialokasikan ke sana setelah setiap pemungutan suara pengurangan emisi CAKE.

{% hint style="warning" %}
Pada hari pembakaran, pasokan yang ditampilkan di beranda mungkin tiba-tiba melonjak beberapa juta CAKE.

Jangan khawatir - **CAKE INI TIDAK PERNAH BENAR-BENAR MASUK KE PEREDARAN:**
{% endhint %}

Lonjakan yang tampak ini hanyalah karena cara semua CAKE yang dialokasikan untuk pembakaran disimpan selama seminggu.

CAKE yang dikirim ke kedua pool PID-137 dan PID-138 dipanen sebelum menyelesaikan pembakaran token mingguan, dan ini membuat Total Pasokan yang ditampilkan di situs melonjak sekitar ~6 juta. Hal ini karena CAKE yang tertunda tidak terdaftar dalam Total Pasokan hingga dipanen pada hari pembakaran. Setelah transaksi pembakaran token selesai, ~6 juta tersebut ditampilkan dalam Jumlah yang Dibakar.

## Cara Mengonfirmasi Pasokan CAKE Sendiri

Untuk mengonfirmasi bahwa pasokan CAKE yang beredar yang ditampilkan di beranda PancakeSwap sudah benar,

1. Kunjungi kontrak token CAKE di BscScan dan [lihat berapa banyak CAKE yang dipegang oleh Alamat Pembakaran.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) Itulah total jumlah CAKE yang telah dibakar (dihapus dari peredaran SELAMANYA, dan tidak mungkin pernah diambil kembali).
2. Kemudian, kurangi jumlah yang dibakar ini dari "Total Pasokan" yang ditampilkan BscScan.
3. Ini memberi Anda pasokan CAKE yang sebenarnya.



#### **Baca lebih lanjut tentang mekanisme deflasioner CAKE di halaman berikutnya.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
