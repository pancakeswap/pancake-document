---
hidden: true
---

# Dumb Mode

### Ikhtisar

[**Dumb Mode**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc) pada PancakeSwap Perpetuals menawarkan pengalaman trading yang disederhanakan, ideal bagi trader yang lebih suka berdagang berdasarkan fluktuasi nilai aset dasar dari menit ke menit. Dumb Mode menyederhanakan trading dengan mengurangi kebisingan, memungkinkan pengguna untuk masuk dan keluar posisi jangka pendek dengan mudah.

### Cara Kerjanya

Pengguna diberikan pilihan jendela kedaluwarsa 5 menit, 15 menit, 30 menit, dan 1 jam dengan rasio imbal hasil investasi yang berbeda. Pengguna dapat memilih untuk long atau short pada aset dasar.

Di akhir periode kedaluwarsa, jika aset dasar berada dalam posisi menang (harga lebih tinggi dari harga buka untuk long, harga lebih rendah dari harga buka untuk short), pengguna akan mendapat keuntungan.

Setiap periode kedaluwarsa memiliki imbal hasil investasi (ROI) yang berbeda. Semakin lama periode kedaluwarsa, semakin tinggi ROI-nya. Persentase dan biaya adalah sebagai berikut:<br>

| Periode Kedaluwarsa | ROI Menang (Setelah Biaya)\* | ROI Kalah | Biaya (saat Menang) |
| ----------------- | --------------------------- | ---------- | ----------------- |
| 5 menit         | 50%                         | -100%      | 6% dari jaminan  |
| 15 menit        | 55%                         | -100%      | 6% dari jaminan  |
| 30 menit        | 70%                         | -100%      | 6% dari jaminan  |
| 1 jam            | 83%                         | -100%      | 6% dari jaminan  |

\*ROI Menang dapat disesuaikan sesekali tergantung pada kondisi pasar. Harap periksa halaman ini untuk pembaruan apa pun

Sebagai contoh, dalam skenario berikut:

* Posisi yang Dipilih: Long
* Jaminan yang Ditempatkan: 100 USDT
* Periode Kedaluwarsa: 60 detik
* Harga BTCUSD saat buka: $50.000
* Harga BTCUSD setelah 60 detik: $50.001

Pengguna akan memperoleh keuntungan **100USDT \* 75%= 75USDT**

Untuk informasi lebih lanjut tentang cara membuka posisi Dumb Mode, klik [di sini](dumb-mode-guide.md).

### Pasar dan Aset Margin

Dumb Mode mendukung trading di pasar dan aset margin berikut pada **BNB Chain**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Pasar</td><td>Aset Margin</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

Dumb Mode mendukung trading di pasar dan aset margin berikut pada **Rantai Arbitrum, opBNB, dan Base**:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Pasar</td><td>Aset Margin</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

Dukungan untuk lebih banyak aset/rantai sedang dalam pengembangan.

### Biaya

Biaya sebesar **6%** dari pokok atau jaminan dikenakan dalam hal perdagangan yang menang. Ini sudah dihitung sebelum ROI.

<br>
