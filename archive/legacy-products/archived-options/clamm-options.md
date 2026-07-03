# CLAMM Options

{% hint style="danger" %}
\[DIARSIPKAN] Options — Per 11 Maret 2025\
Jika Anda masih memiliki Likuiditas untuk ditarik, harap lakukan segera dengan mengunjungi https://www.stryke.xyz/en/trade.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options menghadirkan pendekatan baru untuk perdagangan options on-chain, menawarkan penyedia Likuiditas platform untuk memanfaatkan Likuiditas v3 di PancakeSwap. Ini memungkinkan mereka untuk menggunakan Likuiditas baik untuk Pool Likuiditas v3 maupun untuk menjual options, mendapatkan biaya Trading AMM standar, premi options, dan hadiah tambahan, sementara pedagang dapat memanfaatkan Likuiditas ini untuk membeli American-style options pada berbagai token.

Dibuat oleh tim Stryke (sebelumnya Dopex), protokol CLAMM options memperkenalkan sistem penyediaan Likuiditas ganda yang efisien untuk pedagang options (pembeli) dan Pool PancakeSwap v3.

Berikut adalah rincian terstruktur tentang cara kerja CLAMM Options:

1. LP yang menambahkan Likuiditas ke CLAMM options secara bersamaan berkontribusi ke Pool PancakeSwap v3 yang ditunjuk dalam rentang harga yang mereka pilih.
2. Ketika pedagang options (pembeli) memulai posisi, Likuiditas diekstraksi dari Pool v3 untuk memfasilitasi penjualan options. LP yang bersangkutan dengan demikian menjadi penjual options dan menerima premi.
3. Likuiditas yang tidak digunakan oleh pembeli options berada di Pool PancakeSwap v3, berpotensi mendapatkan biaya Trading.
4. Hasil dari menjual options dan menyediakan Likuiditas dalam Pool v3 mencerminkan kerugian tidak permanen (impermanent loss) yang sama, memastikan pengguna tidak menghadapi peningkatan risiko dibandingkan dengan metode konvensional penambahan Likuiditas ke Pool v3.
5. LP menghadapi beberapa risiko, karena Likuiditas mungkin tidak terpakai karena permintaan pembelian options yang lebih rendah. Selain itu, karena Likuiditas ditambahkan ke pool dalam rentang yang tidak aktif, mungkin tidak menghasilkan biaya apa pun.

American-style CLAMM options PancakeSwap akan mulai diluncurkan di rantai Arbitrum, menawarkan fleksibilitas dengan berbagai durasi kedaluwarsa mulai dari 1 jam hingga 24 jam.

| **Pasar**              | ARB/USDC, ETH/USDC, dan wBTC/USDC |
| ---------------------- | --------------------------------- |
| **Jenis Options**      | Call & Put                        |
| **Harga Strike**       | Berdasarkan tick Pool v3          |
| **Durasi Kedaluwarsa** | 1J, 2J, 6J, 12J, dan 24J          |

**Kondisi Eksekusi:** Pengguna dapat mengeksekusi posisi sebelum penutupan untuk menghindari options in-the-money yang kedaluwarsa tidak bernilai. Auto-exercise dapat diaktifkan untuk merealisasikan keuntungan secara otomatis saat kedaluwarsa, tanpa tindakan lebih lanjut.

### Panduan langkah demi langkah

Berikut adalah panduan langkah demi langkah tentang cara menggunakan PancakeSwap CLAMM Options.

**Untuk Pedagang:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**Untuk LP:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
