---
hidden: true
---

# Integrasi Market Maker

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Integrasi Market Maker di Ethereum

PancakeSwap terintegrasi dengan market maker di Ethereum dan Binance Smart Chain untuk membantu trader mengeksekusi transaksi dengan biaya lebih rendah.

Selain AMM, transaksi di PancakeSwap kini dapat diarahkan ke market maker yang telah masuk daftar putih jika mereka menawarkan eksekusi transaksi yang lebih baik dari harga AMM saat ini. Perutean ini dilakukan secara otomatis oleh [Smart Router](smart-router-v2/) sehingga transaksi hanya diarahkan ke market maker ketika mereka secara aktif menawarkan harga yang lebih baik. Jika AMM lebih kompetitif, trader akan diarahkan ke AMM untuk eksekusi.

Ada 2 skenario di mana market maker beroperasi di PancakeSwap.

**Skenario 1: Pool likuiditas AMM yang sudah ada**

Jika PancakeSwap sudah memiliki likuiditas untuk token tertentu (misalnya WETH/USDC) di AMM, PancakeSwap akan meminta penawaran harga kepada market maker untuk transaksi yang sama. Smart router PancakeSwap kemudian akan merutekan permintaan transaksi ke AMM atau market maker tergantung pada sumber likuiditas mana yang memberikan harga terbaik pada waktu tertentu.

**Skenario 2: Tidak ada pool likuiditas AMM yang tersedia**

Dalam skenario ini, smart router akan secara otomatis merutekan transaksi ke market maker. Namun, hal ini tidak menghalangi proyek-proyek untuk kemudian menyiapkan pool likuiditas AMM mereka dan bekerja sama dengan kami untuk mempertahankan likuiditas DEX yang terdesentralisasi.

### Biaya

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap tidak membebankan biaya apa pun kepada trader yang dieksekusi melalui kami oleh market maker. Namun, PancakeSwap menerima **biaya trading sebesar 0,05%** dari market maker yang masuk daftar putih atas volume yang dieksekusi oleh mereka. PancakeSwap menerima **biaya trading yang lebih rendah sebesar 0,01%** jika transaksi yang dieksekusi adalah antara pasangan stablecoin. Silakan lihat rincian biaya di bawah ini:<br>

<table><thead><tr><th width="178">Transaksi</th><th width="138">Biaya Trading</th><th width="182">Biaya PCS dari MM</th><th width="147">Pembakaran Cake</th><th align="center">PancakeSwap Treasury</th></tr></thead><tbody><tr><td>Koin yang di-bridge dari jaringan lain</td><td>N/A</td><td>0,25%</td><td>0,083%</td><td align="center">0,167%</td></tr><tr><td>Non-stablecoin di Ethereum (mis. ETH/USDC)</td><td>N/A</td><td>0,05%</td><td>0,017%</td><td align="center">0,033%</td></tr><tr><td>Non-stablecoin di BSC (mis. BNB/USDT)</td><td>N/A</td><td>0,05%</td><td>0,017% </td><td align="center">0,033%</td></tr><tr><td>Stablecoin ke Stablecoin di Ethereum</td><td>N/A</td><td>0,01%</td><td>0,003%</td><td align="center">0,007%</td></tr></tbody></table>

#### Aset yang saat ini didukung

Aset-aset berikut saat ini didukung dan dapat bertambah/berkurang tergantung pada market maker:

**Di Ethereum**

* **Aset utama:** WETH, WBTC
* **Stablecoin:** USDT, USDC, DAI, BUSD
* **Aset ERC-20 populer lainnya:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**Di Binance Smart Chain:**

* **Aset utama:** BNB, ETH, BTCB
* Token BNB non-asli: ARB, OP

Harap diperhatikan bahwa berbeda dengan AMM, market maker tidak dapat berdagang dalam jumlah berapa pun dan jumlah yang bersedia mereka eksekusi bergantung pada likuiditas mereka sendiri. Tidak jarang terjadi bahwa pesanan yang sangat besar tidak dapat dipenuhi sepenuhnya. Kami menyarankan pengguna untuk meninjau penawaran harga dengan cermat guna memastikan setiap transaksi mencerminkan harga dan jumlah sesuai kebutuhan mereka.

**Waktu henti market maker**

Market maker tidak diharapkan untuk memberikan penawaran harga 24 jam sehari, 7 hari seminggu. Ada beberapa situasi (misalnya peristiwa ekonomi penting, peningkatan sistem) di mana market maker mungkin sementara tidak tersedia untuk memberikan penawaran harga. Harap diperhatikan bahwa selama periode ini, token-token tersebut tidak dapat diperdagangkan, dan kami menyarankan pengguna untuk menunggu beberapa saat sampai market maker kembali online.

#### FAQ

**T.** Apakah market maker akan diintegrasikan di Aptos?

**Jawab:** Kemungkinan ya, kami hanya meluncurkan integrasi market maker di Ethereum dan Binance Smart Chain untuk saat ini guna meningkatkan likuiditas demi pengalaman pengguna yang lebih baik. Kami akan terus memantau jaringan lainnya.

**T.** Bagaimana PancakeSwap menghasilkan pendapatan jika tidak membebankan biaya kepada pengguna?

**Jawab:** PancakeSwap tidak akan membebankan biaya apa pun dari pengguna, tetapi PancakeSwap akan menerima komisi kecil dari market maker dan menggunakannya untuk mendanai pembelian kembali dan pembakaran CAKE.

**T.** Apakah penyedia likuiditas akan terus mendapatkan biaya LP?

**Jawab:** Ya, penyedia likuiditas akan terus mendapatkan hadiah biaya trading sebesar 0,17% (biaya LP) dan hasil dari Farm CAKE.

**T.** Apakah market maker akan menambahkan likuiditas ke AMM? Apakah hal itu akan menyebabkan APR turun?

**Jawab:** Market maker mempertahankan likuiditas terpisah mereka sendiri, sehingga tidak akan mendapatkan APR dari transaksi di AMM. Hanya LP yang akan mendapatkan biaya dan APR dari penyediaan likuiditas ke pool AMM.

**T.** Saya menyediakan likuiditas di PancakeSwap Ethereum. Apakah saya perlu melakukan sesuatu?

**Jawab:** Tidak, Anda tidak perlu melakukan apa pun. Anda akan terus mendapatkan biaya LP untuk transaksi yang dieksekusi melalui AMM dan akan terus mendapatkan hasil dalam CAKE.

**T.** Bagaimana seseorang bisa menjadi market maker?

**Jawab:** Kami menyeleksi dan bekerja sama dengan market maker secara individual. Silakan hubungi kami langsung atau melalui admin kami jika Anda tertarik untuk bekerja sama dengan kami.
