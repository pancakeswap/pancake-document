---
description: Bridge CAKE antara rantai EVM dan Aptos
---

# Cara Melakukan Bridge - EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Panduan berikut menggunakan BNB Chain sebagai contoh rantai EVM. Proses yang sama dapat diterapkan pada Ethereum.
{% endhint %}

## Bridge CAKE dari BNB Smart Chain ke Aptos

1 - Pastikan Dompet Anda mendukung BNB Smart Chain dan Aptos Mainnet. Atau Anda memiliki kedua Dompet yang terpasang di browser Anda.

Kemudian buka [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Pertama, kita perlu menghubungkan Dompet BNB Smart Chain kita.

Klik "Connect" dan pilih Dompet yang Anda inginkan di bawah bagian "EVM". Kemudian konfirmasi dan setujui di pop-up Dompet Anda.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Kemudian, kita perlu menghubungkan Dompet Aptos kita.

Di modal koneksi Dompet, pilih Dompet yang Anda inginkan di bawah bagian "Aptos". Kemudian konfirmasi dan setujui di pop-up Dompet Anda.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Klik "v" di kolom pemilihan token atas dan pilih "CAKE".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - Masukkan jumlah CAKE yang ingin Anda bridge ke Aptos.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Jika Dompet Aptos Anda baru dibuat dan tidak memiliki saldo APT (Aptos Coin). Kami menyarankan untuk membiarkan opsi "gas on destination" pada pengaturan defaultnya. Bridge akan menyetorkan sejumlah kecil APT ke Dompet Anda, tidak hanya untuk membantu Anda memulai perjalanan di Aptos, tetapi Anda juga membutuhkan APT untuk gas guna mendaftarkan dan mengklaim CAKE yang telah di-bridge.

Mengubah opsi ini dapat menyebabkan bridging gagal.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - Klik "Transfer" untuk memulai transaksi bridging dan konfirmasi melalui pop-up konfirmasi Dompet.

Harap dicatat bahwa tergantung pada kondisi Dompet BNB Smart Chain dan Dompet Aptos Anda, Anda mungkin perlu menyetujui **beberapa** konfirmasi Dompet. Misalnya, jika Anda melakukan bridge CAKE ke Aptos untuk pertama kalinya, Anda perlu:

* Menyetujui pengeluaran CAKE pada kontrak bridging (dari Dompet BNB Smart Chain Anda)
* Mendaftarkan CAKE (dari Dompet Aptos Anda)

Untuk detail lebih lanjut, silakan lihat [perincian ini](aptos.md#bridging-cake-to-aptos-for-the-first-time).

8 - Santai dan tunggu sebentar. Proses ini seharusnya hanya membutuhkan beberapa menit. Setelah bridging selesai, CAKE akan disimpan ke Dompet Aptos Anda. Anda dapat melacak kemajuannya melalui bilah kemajuan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## Bridge CAKE ke Aptos untuk Pertama Kalinya

Melakukan bridge CAKE ke Dompet Aptos memerlukan transaksi registrasi dan klaim. Ini dilakukan untuk meningkatkan keamanan pengguna dan merupakan fitur unik Aptos.

### **Jika Anda sudah memiliki APT (Aptos Coin) di Dompet Anda:**

Anda akan diminta untuk mendaftarkan CAKE di Dompet Aptos Anda jika belum terdaftar. Tidak diperlukan transaksi klaim tambahan dalam kasus ini.

### **Jika Anda tidak memiliki APT (Aptos Coin) di Dompet Anda:**

Setelah transaksi bridge selesai, Anda perlu mengklaim CAKE Anda secara manual. Untuk menutupi biaya gas pengklaiman, token APT akan dikirim ke Dompet Aptos Anda dari Dompet sumber Anda.

Langkah-langkah registrasi dan klaim ini hanya berlaku pertama kali Anda berinteraksi dengan token di Aptos. Transfer token yang sama berikutnya tidak memerlukan tindakan ini.

Sebelum melakukan bridge CAKE ke Aptos untuk pertama kalinya, pastikan alamat Aptos Anda memiliki cukup APT untuk biaya gas. Untuk detail lebih lanjut, lihat penjelasan Aptos di sini: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Bridge CAKE dari Aptos ke BNB Smart Chain

1 - Pastikan Dompet Anda mendukung BNB Smart Chain dan Aptos Mainnet. Atau Anda memiliki kedua Dompet yang terpasang di browser Anda.

Kemudian buka [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/)

2 - Pertama, kita perlu menghubungkan Dompet BNB Smart Chain kita.

Klik "Connect" dan pilih Dompet yang Anda inginkan di bawah bagian "EVM". Kemudian konfirmasi dan setujui di pop-up Dompet Anda.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Kemudian, kita perlu menghubungkan Dompet Aptos kita.

Di modal koneksi Dompet, pilih Dompet yang Anda inginkan di bawah bagian "Aptos". Kemudian konfirmasi dan setujui di pop-up Dompet Anda.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Klik "v" di kolom pemilihan token atas dan pilih "CAKE". Kemudian klik tombol panah ganda di tengah halaman untuk membalik arah bridging.

Pastikan jaringan "Aptos" berada di kolom atas.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - Masukkan jumlah CAKE yang ingin Anda bridge ke BNB Smart Chain.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - Jika Dompet BNB Smart Chain Anda baru dibuat dan tidak memiliki saldo BNB (token gas). Kami menyarankan untuk membiarkan opsi "gas on destination" pada pengaturan defaultnya. Bridge akan menyetorkan sejumlah kecil BNB ke Dompet Anda. Ini akan membantu Anda memulai perjalanan di BNB Smart Chain dan menjelajahi ekosistem PancakeSwap yang dinamis.

7 - Klik "Transfer" dan setujui transaksi dari pop-up Dompet Anda.

8 - Santai dan tunggu sebentar. Proses ini seharusnya hanya membutuhkan beberapa menit. Setelah bridging selesai, CAKE akan disimpan ke Dompet BNB Smart Chain Anda. Anda dapat melacak kemajuannya melalui bilah kemajuan.
