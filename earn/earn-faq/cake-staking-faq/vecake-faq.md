---
hidden: true
---

# FAQ veCAKE

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### Apa perbedaan antara CAKE terkunci dan veCAKE? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE adalah versi baru dari fixed-term CAKE staking dengan lebih banyak manfaat dan kekuatan bagi pemegang CAKE terkunci. Termasuk pemungutan suara bobot gauge, insentif ekstra, peningkatan yield, dan lainnya.

#### Apa yang terjadi pada hadiah pool CAKE ketika veCAKE baru diterapkan <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

Emisi hadiah pool CAKE akan dialihkan untuk memberi hadiah kepada semua pemegang veCAKE berdasarkan saldo veCAKE mereka terhadap total pasokan.

Hadiah CAKE dan hadiah berbagi pendapatan mingguan sekarang dapat diklaim setiap Kamis.

Harap diperhatikan bahwa untuk terus menerima hadiah, pengguna perlu bermigrasi ke staking veCAKE yang baru.

#### Berapa durasi maksimum yang dapat saya kunci CAKE saya <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

Durasi maksimum untuk mengunci CAKE kini telah diperpanjang menjadi 4 tahun.

#### Apakah veCAKE token baru? Bisakah dipindahkan? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE adalah angka yang dihasilkan secara langsung berdasarkan jumlah CAKE yang dikunci dan sisa waktu kunci. Ini bukan token standar dan tidak dapat dipindahkan.

#### Mengapa saldo veCAKE saya berubah? Bagaimana menghitung saldonya? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

Saldo veCAKE berkurang secara linier menjadi 0 berdasarkan sisa durasi kunci. Oleh karena itu ketika kita mendekati waktu unlock, saldo Anda berkurang.

Saldo veCAKE dapat dihitung dengan:

```javascript
lockedAmount // jumlah CAKE yang dikunci
currentTime // waktu saat ini
lockEndTime // waktu unlock
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // waktu kunci maksimum (4 tahun)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### Bagaimana cara meningkatkan veCAKE saya? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Setelah Anda memiliki posisi veCAKE aktif, Anda dapat menambahkan lebih banyak CAKE atau memperbarui/memperpanjang durasi kunci untuk meningkatkan saldo veCAKE Anda.

#### Apa yang terjadi ketika posisi membuka kunci? Bisakah langsung diperbaharui? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

Ketika posisi staking veCAKE membuka kunci, Anda dapat menarik semua CAKE yang di-stake.

Untuk memperbaharui posisi, Anda perlu menarik semua CAKE dan menyiapkan posisi staking baru dengan memilih jumlah yang akan dikunci dan durasi kunci.

#### Saya mengunci selama 1 minggu, mengapa sisa waktu kunci kurang dari 1 minggu? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

Ketika Anda mengunci dengan veCAKE baru, waktu unlock dibulatkan ke depan ke Kamis terdekat dengan waktu UTC. Misalnya, ketika Anda mengunci selama 1 minggu pada hari Selasa, waktu unlock aktual Anda akan menjadi Kamis berikutnya, yang 2 hari kemudian.

Anda dapat melihat pratinjau waktu unlock aktual Anda di bagian bawah.

#### Bisakah saya mengunci lebih banyak CAKE di pool CAKE? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

Tidak.

Setelah veCAKE diterapkan, pool staking CAKE akan dihentikan dan tidak lagi menerima perpanjangan atau deposit CAKE apa pun.

Untuk mengunci CAKE dan menikmati manfaatnya, buka halaman veCAKE.

#### Mengapa saya tidak bisa bermigrasi? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

Migrasi dari pool CAKE ke veCAKE mengharuskan Anda memiliki posisi aktif. Jika posisi staking pool CAKE Anda sudah membuka kunci, cukup tarik CAKE tersebut dan buat posisi staking veCAKE native.

Dalam beberapa kasus, migrasi tidak dapat dilakukan ketika sisa waktu kunci pool CAKE Anda kurang dari 7 hari. Dalam kasus tersebut, cukup tunggu hingga unlock, tarik CAKE tersebut dan buat posisi staking veCAKE native.

#### Bisakah saya menarik lebih awal CAKE yang terkunci? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

Tidak.

Setelah dikunci, CAKE akan di-stake dalam kontrak veCAKE hingga waktu unlock.

#### Bisakah saya bermigrasi sebagian CAKE saya? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

Tidak.

Anda hanya dapat bermigrasi seluruh posisi pool CAKE Anda sekaligus.

#### Apa yang akan terjadi pada iCAKE, bCAKE, vCAKE, dan rCAKE? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**Untuk iCAKE:**

IFO iCAKE kini telah ditingkatkan untuk mendukung veCAKE. Lihat:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**Untuk bCAKE:**

Farm boosting bCAKE kini telah ditingkatkan untuk mendukung veCAKE. Lihat:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**Untuk vCAKE:**

Pemungutan suara vCAKE kini telah ditingkatkan untuk mendukung veCAKE. Lihat:

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**Untuk rCAKE:**

Semua pemegang veCAKE (baik native maupun yang telah bermigrasi) akan secara otomatis terdaftar dalam pool berbagi pendapatan baru. Bagian pendapatan didistribusikan sesuai jadwal yang ada. Pool berbagi pendapatan lama akan dihentikan, pengguna dapat mengklaim hadiah tertunda mereka dengan membuka kartu manfaat. Lihat:

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Broken link](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### Bisakah dompet multisig digunakan untuk berinteraksi dengan veCAKE?

Ya

Namun, ada modifier `noContract` yang diterapkan dalam kontrak staking veCAKE untuk alamat yang tidak masuk daftar putih. Untuk mengaktifkan staking atau migrasi dari pool staking CAKE fixed-term. Semua dompet multisig berbasis kontrak harus melakukan tindakan self-whitelisting satu kali.

Untuk memasukkan ke daftar putih, kunjungi salah satu halaman berikut:

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

Sebuah prompt seharusnya muncul. Klik "Whitelist" dan lanjutkan dengan tx di dompet multisig Anda.

Sebuah tx akan dikirimkan ke pemilik veCAKE, yang merupakan kontrak dengan fungsi penulisan tanpa izin untuk memungkinkan kontrak apa pun melakukan self-whitelisting.

Jika prompt tidak muncul, ikuti instruksi ini untuk mengeksekusi tx dari [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11):

```
// panggil:
VECakeOwner.setWhitelist(bool _status = true)

// Alamat VECakeOwner:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### Mengapa ada beberapa APR?

Mengunci CAKE untuk mendapatkan veCAKE memberikan sejumlah manfaat yang bagus di seluruh rangkaian produk yang dibangun oleh PancakeSwap. Manfaat dan insentif hadir dalam berbagai bentuk dan dari berbagai sumber. Oleh karena itu, ada beberapa APR.

Anda dapat memperoleh semuanya secara bersamaan sehingga APR gabungan akan menjadi jumlah dari semua APR.

Harap diperhatikan bahwa banyak manfaat lain dari veCAKE tidak dapat dikuantifikasi dalam format APR, seperti [Farm Yield Booster bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/), atau [IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md). Pastikan untuk memeriksa hal-hal tersebut juga.

#### Apa itu APR Pool veCAKE?

Ini adalah insentif yang berasal dari emisi CAKE, dengan tingkatnya dikontrol oleh gauge pemungutan suara Pool veCAKE.

Untuk meningkatkan emisi ke gauge ini, lihat [Gauge Voting](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/).

#### Apa itu APR Berbagi Pendapatan?

Ini adalah insentif yang berasal dari berbagi pendapatan protokol, yang berasal dari biaya swap yang dikumpulkan dalam produk DEX.

Lihat [Berbagi Pendapatan](/broken/pages/wQegezs7c6A2HzQjPEjh) untuk info lebih lanjut.
