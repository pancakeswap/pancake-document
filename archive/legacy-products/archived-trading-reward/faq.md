---
description: FAQ Trading Reward
---

# FAQ

{% hint style="danger" %}
\[Diarsipkan] Trading Reward — Per 23 Agustus 2024
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## Umum

#### Mengapa volume perdagangan saya tidak terlacak?

* Angka volume membutuhkan waktu untuk diperbarui dan tunduk pada penundaan SubGraph. Silakan periksa kembali nanti
* Perdagangan Anda harus dirutekkan melalui pasangan perdagangan yang **tepat** yang disorot di [halaman Trading Reward](https://pancakeswap.finance/trading-reward#rewards-breakdown), termasuk tingkat biaya. Lihat [tutorial ini](https://docs.pancakeswap.finance/products/pancakeswap-exchange/fees-and-routes#check-the-fee-rate-and-fee-amount-that-is-currently-applied) tentang cara melihat rute perdagangan Anda
* Hanya pasangan perdagangan V3 yang memenuhi syarat untuk program ini
* Gunakan alamat dompet yang sama yang memenuhi syarat untuk program Trading Reward di Ethereum maupun BNB Chain
* Jika volume perdagangan Anda dalam suatu pasangan terlalu kecil, Anda mungkin tidak memenuhi syarat untuk mengklaim hadiah apa pun
* Menggunakan agregator perdagangan pihak ketiga dapat mengakibatkan perdagangan dirutekkan melalui penyedia Likuiditas lain dan tidak terlacak

#### Mengapa saya banyak berdagang tetapi hanya menerima hadiah yang sangat sedikit

Jumlah hadiah Trading didasarkan pada biaya Trading yang dibayarkan dalam perdagangan tersebut.

Jika perdagangan Anda dirutekkan melalui pasangan dengan tingkat biaya rendah, misalnya 0,01%, Anda membayar biaya yang sangat kecil untuk perdagangan Anda. Oleh karena itu, jumlah hadiah akan menjadi lebih rendah sesuai.

## Kampanye Top Traders

#### Apakah saya perlu tetap berada dalam peringkat yang diperlukan sepanjang waktu untuk memenangkan kampanye?

Tidak, Anda hanya perlu berperingkat lebih tinggi dari peringkat yang diperlukan **di akhir kampanye**. Namun disarankan untuk berperingkat lebih tinggi dan mempertahankan peringkat. Dan pastikan untuk sering memeriksa kembali untuk memastikan Anda tidak jatuh dari peringkat yang diperlukan.

#### Angka apa yang menjadi dasar peringkat?

Peringkat didasarkan pada jumlah hadiah yang diakumulasikan setiap pengguna melalui perdagangan. Jumlah hadiah sama dengan persentase tetap dari biaya Trading yang mereka bayar dalam perdagangan.

## Kampanye CAKE Stakers

#### Alamat saya memenuhi syarat untuk kampanye sebelumnya. Mengapa tidak memenuhi syarat untuk yang terbaru?

Setiap kampanye memiliki persyaratan kelayakan tersendiri, seperti ambang minimum untuk jumlah veCAKE pada waktu snapshot.

Selain itu, waktu snapshot ditetapkan sebagai waktu akhir setiap kampanye. Dengan veCAKE yang menurun seiring waktu, saldo veCAKE Anda mungkin turun di bawah ambang untuk kampanye mendatang.

Anda mungkin perlu meningkatkan veCAKE. Cukup ikuti instruksi di halaman.

#### Mengapa dikatakan saya memiliki hadiah tambahan yang tidak dapat diklaim?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

Jumlah veCAKE pada waktu snapshot akan menentukan jumlah maksimum hadiah yang dapat Anda peroleh dari kampanye. Lihat catatan kaki dari bagian "Batas Hadiah Maksimum".

Selama kampanye aktif, Anda dapat meningkatkan veCAKE dan menaikkan batas ini kapan saja.

#### Apa itu "veCAKE pada waktu snapshot"

veCAKE secara bertahap menurun seiring waktu seiring berkurangnya sisa waktu kunci. Oleh karena itu, mirip dengan iCAKE IFO, saldo veCAKE snapshot — saldo veCAKE pada waktu tertentu yang bersifat statis — lebih cocok digunakan sebagai metrik kualifikasi.

Dalam Trading Reward, waktu snapshot merujuk pada akhir setiap kampanye. Oleh karena itu, "saldo veCAKE Anda pada waktu snapshot" berarti "saldo veCAKE Anda pada waktu akhir kampanye".

#### Bagaimana "veCAKE pada waktu snapshot" terkait dengan kampanye

* Jumlah saldo veCAKE Anda pada waktu snapshot lebih tinggi dari ambang yang diperlukan
* Jumlah maksimum hadiah yang dapat Anda peroleh terkait dengan y% dari saldo veCAKE Anda pada waktu snapshot

Misalnya:

1. Alice mengunci 300 CAKE selama 2 tahun (104 minggu) pada hari pertama. Pada hari pertama, Alice akan memiliki saldo veCAKE `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149` .
2. Kampanye Trading Reward diluncurkan pada hari pertama, dengan ambang veCAKE 100, dan batas hadiah 1%. Kampanye berakhir dalam 30 hari.
3. Setelah 30 hari, posisi Alice akan memiliki sisa waktu kunci sekitar 99,71 minggu, sehingga saldo veCAKE `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143`.
4. Oleh karena itu, untuk kampanye ini, Alice akan memiliki `143` veCAKE pada waktu snapshot.
5. 143 lebih besar dari 100 sehingga Alice memenuhi syarat untuk kampanye, dia dapat mulai memperdagangkan pasangan yang memenuhi syarat untuk mendapatkan hadiah Trading.
6. Dengan batas hadiah 1%, jumlah maksimum CAKE yang dapat diperoleh Alice dari kampanye ini adalah `143 * 1% = 1.43` CAKE.
7. Alice dapat meningkatkan veCAKE kapan saja sebelum kampanye berakhir, baik dengan mengunci lebih banyak CAKE, atau memperpanjang posisinya.

#### Bagaimana saya dapat memeriksa veCAKE saya pada waktu snapshot selama kampanye?

Anda dapat memeriksa di halaman Trading Reward.

Halaman akan memberi peringatan saat veCAKE Anda pada waktu snapshot lebih rendah dari ambang atau hadiah Anda saat ini dibatasi olehnya.

Dalam kasus tersebut, Anda dapat mengklik tombol "Increase veCAKE" untuk meningkatkan veCAKE tanpa meninggalkan halaman.

#### Dapatkah saya meningkatkan veCAKE selama kampanye?

Ya, Anda dapat meningkatkan veCAKE kapan saja sebelum kampanye berakhir. "veCAKE Anda pada waktu snapshot" akan diperbarui sesuai.
