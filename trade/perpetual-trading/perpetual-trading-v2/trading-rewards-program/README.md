---
description: ApolloX akan meluncurkan Program Hadiah Trading di V2
hidden: true
---

# Program Hadiah Trading

### Ikhtisar Program Hadiah

Detailnya adalah sebagai berikut:

Periode aktivitas: Tanggal bervariasi dari siklus ke siklus dan untuk rantai yang berbeda

Waktu Distribusi Hadiah: Setiap siklus adalah 00:00 (UTC) hingga 23:59 (UTC) setiap hari. Hadiah diterbitkan pada hari berikutnya sekitar pukul 03:00 (UTC). Pengguna harus mengklaim hadiah mereka dalam 30 hari setelah hadiah diterbitkan. Jika tidak, platform akan mencabut hadiah tersebut.&#x20;

Jumlah hadiah: Dibatasi sebesar $15.000 USD senilai APX per hari

Aturan aktivitas: Pengguna yang berdagang di V2 mendapatkan dari kumpulan hadiah. Mereka yang melakukan Staking APX di DAO untuk mendapatkan veNFT akan menikmati pengganda boosting yang sesuai dengan nilai Power yang dihitung dari veNFT tersebut.&#x20;

| Nilai Power               | Pengganda Boosting  |
| ------------------------- | -------------------- |
| 50.000 < Power =<100.000  | 1,5                  |
| 100.000 < Power =<300.000 | 2                    |
| Power > 300.000           | 2,5                  |

Rumus perhitungan Hadiah Trading:&#x20;

Di akhir setiap siklus hadiah trading, biaya trading efektif pengguna dan jumlah Staking dalam siklus tersebut akan dihitung untuk menentukan bobot dan jumlah hadiah APX. Rumusnya adalah sebagai berikut:

r = R\*W / sum(Wi)



Parameter:

| r       | Hadiah APX pengguna untuk siklus ini                                                                                                                                                                                                                                                                                        |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Ditentukan oleh kontribusi biaya trading V2 pengguna pada hari sebelumnya dan harga token APX terbaru                                                                                                                                                                                                                     |
| W       | <p>Skor bobot total individual W=f*w, di mana;</p><p>f mengacu pada biaya trading efektif yang dikontribusikan oleh pengguna dalam siklus ini, yang akan dikonversi ke USD.</p><p>w adalah Pengganda Boosting yang diperoleh pengguna dalam siklus ini dari Staking APX di DAO. (Lihat tabel di atas untuk informasi lebih lanjut)</p> |
| sum(Wi) | Total skor semua pengguna. Wi mewakili skor pengguna individual mana pun, dan sum(Wi) mewakili jumlah semua skor pengguna                                                                                                                                                                                              |

&#x20;

Rumus perhitungan R adalah sebagai berikut:

R=Min(Pengganda nilai dolar \* Biaya Trading, Batas nilai dolar)/ Max(Harga Terakhir APX, Lantai Harga APX)

* Pengganda nilai dolar: 0,70 epoch ini
* Biaya Trading: Nilai pendapatan biaya V2 hari sebelumnya yang dikonversi ke USD
* Batas nilai dolar: 15.000 berdasarkan konfigurasi sistem
* Harga Terakhir APX: Berdasarkan harga token APX terbaru
* Lantai Harga APX: 0,04 epoch ini

Syarat dan Ketentuan

* Setelah akhir setiap siklus, ApolloX dapat menyesuaikan aturan program sesuai masukan pengguna dan kondisi pasar. Hadiah akan diterbitkan secara non-linier.
* Selama aktivitas, platform akan mengurangi persentase pendapatan biaya trading V2 yang disuntikkan ke pool ALP dari 50% menjadi 20%. Sisa 30% akan digunakan untuk membeli kembali APX.
* Karena perbedaan biaya trading untuk setiap pasangan trading di V2, hadiah yang diterima pengguna dapat bervariasi meskipun volume trading efektif mereka sama.
* Hadiah yang akan didistribusikan untuk setiap siklus akan disimpan di alamat kontrak berikut: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX berhak atas interpretasi akhir untuk aktivitas ini.

Peringatan Risiko: Trading crypto futures membawa risiko yang substansial. Semua aktivitas trading dilakukan atas kebijaksanaan dan risiko Anda sendiri. Informasi di sini tidak boleh dianggap sebagai saran keuangan atau investasi dari ApolloX. ApolloX tidak akan bertanggung jawab atas kerugian apa pun yang mungkin timbul dari penggunaan ApolloX oleh Anda.

### Mengklaim Hadiah

Karena program hadiah trading diselenggarakan oleh mitra kami di ApolloX, harap lanjutkan dengan langkah-langkah berikut untuk mengklaim hadiah Anda:\
\
Langkah 1: Buka [Halaman Perpetuals PancakeSwap](https://perp.pancakeswap.finance/en/futures/v2/)

Langkah 2: Klik tab Trading Reward (V2) di bagian atas halaman

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

Langkah 3: Anda akan dialihkan ke halaman klaim hadiah ApolloX untuk memeriksa status hadiah Anda saat ini. Klik "Claim" untuk mengklaim hadiah Anda selama periode aktivitas.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
