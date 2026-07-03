---
description: Menambahkan Likuiditas hanya dengan satu klik
---

# Zap

### Apa itu Zap <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap adalah fitur yang memungkinkan Anda menambahkan Likuiditas dengan mudah. Dengan Zap, Anda dapat menyediakan Likuiditas dengan token apa pun yang Anda miliki saldonya, terlepas dari token yang diperlukan dalam pool. Cukup tentukan rentang harga, pilih jumlah yang ingin disediakan, dan jalankan. Token Anda akan secara otomatis diseimbangkan untuk membentuk posisi Likuiditas sambil diperdagangkan dengan cara paling efisien, dengan dampak harga dan Slippage terendah.

### Rantai yang Didukung

* v3 - Semua pool di BNB Chain, pool tertentu di jaringan Ethereum & Arbitrum
* Infinity - Semua pool CLAMM (tanpa hook) di BNB Chain

### Cara Penggunaan <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

Saat ini, Zap mendukung:

* 🆕 Token apa saja!
* Menggunakan token tunggal
* 🆕 Menggunakan dua token
* 🆕 Atau... menggunakan banyak token (ya, dapat digunakan seperti pengumpul debu)

#### Mulai <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Untuk menggunakan Zap, cukup buka halaman Add Liquidity, pilih pasangan Trading yang ingin Anda sediakan Likuiditasnya, tingkatan biaya, dan rentang harga.

Kemudian pilih jumlah token yang ingin Anda sediakan Likuiditasnya.

Opsi Zap akan secara otomatis muncul ketika satu atau lebih token kekurangan saldo.

Klik tautan untuk memunculkan modal Zap.

#### Mulai Zap <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

Di dalam modal "Zap in" yang baru. Anda dapat menemukan kolom-kolom berikut:

1. Pasangan Trading yang Anda Zap (sediakan Likuiditas).
2. Token setoran dan jumlah yang akan disetorkan. Anda dapat dengan bebas menambahkan atau menghapus token untuk Zap.
3. Rentang harga dari posisi baru. Anda juga dapat mengklik panah untuk beralih antara tampilan harga yang berbeda.
4. Rincian lengkap tentang bagaimana fitur Zap akan menangani token setoran Anda.
5. Ringkasan statistik termasuk:
   1. Nilai estimasi dalam USD untuk posisi Likuiditas baru.
   2. Estimasi jumlah token dalam posisi Likuiditas baru.
   3. Estimasi sisa dana dalam USD setelah Zapping. Dalam kebanyakan kasus nilainya adalah 0. Jika Pool Likuiditas atau token memiliki sangat sedikit Likuiditas, nilai ini mungkin meningkat.
   4. Dampak harga untuk Swap dan penyeimbangan token saat Zapping.
   5. Dampak harga untuk penambahan Likuiditas dan pembangunan posisi.
   6. Biaya Zap. Tergantung pada pasangan Likuiditas, tarif biaya mungkin bervariasi.

{% hint style="warning" %}
Perlu diingat bahwa Anda mungkin perlu mengonfigurasi ulang jumlah Zap berdasarkan saldo yang tersedia. Jika Anda tidak memiliki saldo pada salah satu token, harap hapus token tersebut.
{% endhint %}

{% hint style="info" %}
Anda mungkin memperhatikan bahwa pengaturan dari "Add V3 Liquidity" secara otomatis dibawa ke modal Zap. Termasuk pengaturan jumlah setoran dan rentang harga.
{% endhint %}

#### Mulai Zapping <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

Terakhir klik "Approve" dan konfirmasi di pop-up Dompet untuk izin token.

Kemudian, klik "Preview" untuk memunculkan modal konfirmasi akhir. Sebelum melanjutkan, harap tinjau semua statistik dan estimasi yang ditampilkan di modal konfirmasi akhir. Terutama angka dampak dan Slippage maksimum.

Terakhir, klik "Add Liquidity" dan konfirmasi di pop-up Dompet Anda.

Setelah transaksi dikonfirmasi, Anda akan melihat posisi baru Anda yang bersinar di halaman "My Position"

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### Pengaturan Lanjutan <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Jika Anda ingin lebih menyesuaikan pengalaman Zap Anda, cukup klik ikon roda gigi di pojok kanan atas. Dalam pengaturan, Anda dapat mengonfigurasi:

* Slippage maksimum saat Zapping.
* Batas waktu pada deadline transaksi.
* Apakah akan menggunakan Likuiditas agregat KyberSwap untuk melakukan penyeimbangan token. Matikan ini jika Anda hanya ingin berdagang di PancakeSwap Pools.
* Mode Degen dapat digunakan untuk melakukan Zap dengan Slippage sangat tinggi. Tidak disarankan untuk penggunaan normal, gunakan dengan risiko Anda sendiri.

{% hint style="warning" %}
Harap dicatat bahwa pengaturan Slippage dan Deadline bersifat independen dari halaman Swap dan Likuiditas.
{% endhint %}

#### Zap in menggunakan dua token

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Sekarang Anda dapat melakukan Zap in Likuiditas dengan dua token. Ini berguna ketika saldo yang tersedia tidak sesuai dengan pengaturan harga, serta jumlah dan rasio token yang diperlukan. Cukup Zap, dan rasio akan secara otomatis diseimbangkan kembali.

#### Zap in menggunakan banyak token

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Ya, ini bekerja seperti pengumpul token debu. Cocok untuk membersihkan saldo kecil di Dompet Anda, dan memasukkannya ke dalam posisi untuk mulai mendapatkan penghasilan dari biaya Trading.&#x20;
