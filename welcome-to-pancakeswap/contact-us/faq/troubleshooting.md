---
description: Pesan kesalahan umum. Gunakan bilah samping ➡️ untuk melompat ke kesalahan yang Anda lihat.
---

# Pemecahan Masalah Kesalahan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

Terkadang Anda mungkin menghadapi masalah yang tidak memiliki solusi yang jelas. Tips pemecahan masalah ini mungkin dapat membantu Anda menyelesaikan masalah yang Anda hadapi.

## **Masalah pada Pertukaran**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

Anda mencoba melakukan Swap token, tetapi toleransi Slippage Anda terlalu rendah atau Likuiditas terlalu rendah.

{% tabs %}
{% tab title="Solusi" %}
1. Segarkan halaman Anda dan coba lagi nanti.
2. Coba perdagangkan jumlah yang lebih kecil sekaligus.
3. Tingkatkan toleransi Slippage Anda:
   1. Ketuk ikon pengaturan pada halaman Likuiditas.
   2. Tingkatkan toleransi Slippage Anda sedikit dan coba lagi. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. Terakhir, coba masukkan jumlah dengan lebih sedikit tempat desimal.
{% endtab %}

{% tab title="Alasan" %}
**Ini biasanya terjadi saat memperdagangkan token dengan Likuiditas rendah.**

Artinya tidak cukup salah satu token yang ingin Anda tukar di Pool Likuiditas: kemungkinan ini adalah token berkapitalisasi kecil yang sedikit diperdagangkan orang.

Namun, ada juga kemungkinan bahwa Anda mencoba memperdagangkan token penipuan yang tidak dapat dijual. Dalam hal ini, PancakeSwap tidak dapat memblokir token atau mengembalikan dana.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Anda mencoba menambah/menghapus Likuiditas dari Pool Likuiditas (LP), tetapi tidak cukup salah satu dari dua token dalam pasangan tersebut.

{% tabs %}
{% tab title="Solusi" %}
**Segarkan halaman Anda dan coba lagi, atau coba lagi nanti.**

Masih tidak berhasil?

1. Ketuk ikon pengaturan pada halaman Likuiditas.
2. Tingkatkan toleransi Slippage Anda sedikit dan coba lagi.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="Alasan" %}
Kesalahan ini disebabkan oleh upaya menambah atau menghapus Likuiditas untuk Pool Likuiditas (LP) dengan jumlah token A atau token B yang tidak mencukupi (salah satu token dalam pasangan).

Mungkin harga berubah terlalu cepat dan toleransi Slippage Anda terlalu rendah.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solusi untuk pengguna mahir" %}
Oke, jadi Anda benar-benar bertekad untuk memperbaiki ini. Kami benar-benar tidak menyarankan melakukan ini kecuali Anda tahu apa yang Anda lakukan.

Saat ini tidak ada cara sederhana untuk menyelesaikan masalah ini dari situs web PancakeSwap: Anda perlu berinteraksi langsung dengan kontrak. Anda dapat menambahkan Likuiditas langsung melalui kontrak Router, sambil mengatur amountAMin ke jumlah yang kecil, kemudian menarik semua Likuiditas.

**Setujui kontrak LP**

Buka kontrak token LP yang ingin Anda setujui.\
Misalnya, berikut adalah pasangan ETH/WBNB: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Pilih **Write Contract**, kemudian **Connect to Web3** dan hubungkan dompet Anda. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. Di **bagian "1. approve",** setujui token LP untuk router dengan memasukkan
   1. spender (address): masukkan alamat kontrak token LP yang ingin Anda interaksikan
   2. value (uint256): -1

**Kueri "balanceOf"**

1. Beralih ke **Read Contract.**
2. Di **5. balanceOf**, masukkan alamat dompet Anda dan klik **Query**.
3. Catat angka yang ditampilkan. Angka ini menunjukkan saldo Anda dalam LP dalam format uint256, yang akan Anda butuhkan pada langkah berikutnya.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**Tambah atau Hapus Likuiditas**

Buka kontrak router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Pilih **Write Contract** dan **Connect to Web3** seperti di atas.
2. Temukan **addLiquidity** atau **removeLiquidity** (mana yang ingin Anda lakukan)
3. Masukkan alamat token dari kedua token dalam LP.
4. Di **liquidity (uint256),** masukkan angka uint256 yang Anda peroleh dari "balanceOf" di atas.
5. Tetapkan **amountAMin** atau **amountBMin** yang rendah: coba 1 untuk keduanya.
6. Tambahkan alamat dompet Anda di **to (address)**.
7. Deadline harus berupa waktu epoch yang lebih besar dari waktu eksekusi tx.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
Ini dapat menyebabkan Slippage yang sangat tinggi, dan dapat menyebabkan pengguna kehilangan sebagian dana jika di-frontrun
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Coba lagi, tetapi konfirmasi (tanda tangani dan siarkan) transaksi segera setelah Anda membuatnya.

Ini terjadi karena Anda mulai membuat transaksi, tetapi Anda tidak menandatangani dan menyiarkannya hingga melewati batas waktu. Artinya Anda tidak menekan "Konfirmasi" cukup cepat.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

Coba ubah jumlah pada kolom "To". Dengan demikian menempatkan simbol "(estimated)" pada "From". Kemudian segera mulai Swap.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

Ini biasanya terjadi saat Anda mencoba melakukan Swap token dengan biaya sendiri.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

Pastikan Anda memiliki 30% lebih banyak token di dompet Anda daripada yang ingin Anda perdagangkan, atau coba perdagangkan jumlah yang lebih kecil. Jika Anda ingin menjual semaksimal mungkin, coba 70% atau 69% alih-alih 100%.\
Disebabkan oleh desain token Restorative Rebase seperti tDoge atau tBTC.\
[Pahami cara kerja token restorative rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Kemungkinan lain dari masalah ini adalah penerbit token jahat baru saja menangguhkan perdagangan untuk token mereka. Atau mereka membuat tindakan penjualan hanya tersedia untuk alamat dompet tertentu. Selalu lakukan riset sendiri untuk menghindari potensi penipuan. Jika token yang Anda coba Swap tetapi gagal dengan kode kesalahan ini berasal dari airdrop, kemungkinan besar itu adalah penipuan. Harap jangan melakukan persetujuan token apa pun atau mengikuti tautan apa pun, dana Anda mungkin berisiko jika Anda mencoba melakukannya.

### Transaksi tidak dapat berhasil

Coba perdagangkan jumlah yang lebih kecil, atau tingkatkan toleransi Slippage melalui ikon pengaturan dan coba lagi. Ini disebabkan oleh Likuiditas yang rendah.

### **Dampak Harga Terlalu Tinggi**

Coba perdagangkan jumlah yang lebih kecil, atau tingkatkan toleransi Slippage melalui ikon pengaturan dan coba lagi. Ini disebabkan oleh Likuiditas yang rendah.

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Solusi" %}
**Jika Anda mendapatkan error ini saat menghapus Likuiditas dari pasangan BNB:**

Pilih "Receive WBNB" dan coba lagi.

**Jika Anda mendapatkan error ini saat mencoba melakukan Swap:**

Harap hubungi tim proyek token yang ingin Anda Swap. \*\*\*\* Masalah ini harus diselesaikan oleh tim proyek.
{% endtab %}

{% tab title="Alasan" %}
**Masalah ini (saat melakukan Swap) disebabkan oleh token yang telah mengkodekan router PancakeSwap V1 secara keras ke dalam kontrak mereka.**

Meskipun praktik ini tidak disarankan, alasan proyek-proyek ini melakukannya tampaknya terkait dengan tokenomics mereka, di mana setiap pembelian mengirimkan % token ke LP.

Proyek-proyek yang terpengaruh kemungkinan tidak akan berfungsi dengan router V2: mereka kemungkinan besar perlu membuat versi baru token mereka yang mengarah ke alamat router baru kami, dan memigrasikan pemegang token yang ada ke token baru mereka.

Kami menyarankan agar proyek apa pun yang membuat token semacam itu juga berupaya mencegah pengguna mereka menambahkannya ke V2 LP.

Alamat router terbaru adalah [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

Saat mencoba melakukan Swap token, transaksi gagal dan pesan kesalahan ini ditampilkan. Kesalahan ini dilaporkan pada perangkat seluler yang menggunakan Trust Wallet.

{% tabs %}
{% tab title="Solusi" %}
1. Coba ulangi transaksi dengan peningkatan batas Slippage.
2. Jika langkah 1 tidak menyelesaikan masalah Anda, pertimbangkan untuk menggunakan dompet lain seperti SafePal untuk transaksi Anda.
{% endtab %}

{% tab title="Alasan" %}
**Ini biasanya terjadi saat memperdagangkan token dengan batas Slippage yang tidak memadai di Trust Wallet.**

Detail tepat dari masalah ini masih sedang diselidiki.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Saat mencoba melakukan Swap token, transaksi gagal dan pesan kesalahan ini ditampilkan. Kesalahan ini dilaporkan di berbagai platform.

{% tabs %}
{% tab title="Solusi" %}
1. Periksa untuk memastikan Anda memiliki dana yang cukup tersedia.
2. Pastikan Anda telah memberikan izin kontrak untuk membelanjakan jumlah dana yang Anda coba perdagangkan.
{% endtab %}

{% tab title="Alasan" %}
Kesalahan ini terjadi saat memperdagangkan token dengan batas yang tidak memadai, atau saat dompet memiliki dana yang tidak mencukupi.\
Jika Anda memperdagangkan token dengan Restorative Rebase seperti aset tau tDoge atau tBTC, pastikan Anda memahami cara kerjanya terlebih dahulu dengan [panduan tentang token Rebase](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c) ini.
{% endtab %}
{% endtabs %}

## **Masalah dengan Farm**

### Fail with error 'ds-math-sub-underflow'

Anda telah kehabisan batas izin LP token Anda ke kontrak MasterChef.

**Gunakan manajer persetujuan token seperti unrekt atau BscScan untuk**

## **Masalah dengan Syrup Pools**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

Anda tidak memiliki cukup SYRUP di dompet Anda untuk melakukan unstake dari pool CAKE-CAKE.

**Dapatkan setidaknya SYRUP sebanyak jumlah CAKE yang ingin Anda unstake.**

1. Beli SYRUP di pertukaran. Jika Anda ingin melakukan unstake 100 CAKE, Anda memerlukan setidaknya 100 SYRUP.
2. Coba unstake lagi.

Jika masih gagal, Anda dapat melakukan "emergencyWithdraw" dari kontrak secara langsung untuk melakukan unstake token yang di-stake.

1. Buka: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Klik **"Connect to Web3"** dan hubungkan dompet Anda. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. Di bagian **"4. emergencyWithdraw"**, masukkan "0" dan klik "Write".

Ini akan melakukan unstake token yang di-stake Anda dan kehilangan hasil CAKE yang belum dikumpulkan.

{% hint style="warning" %}
**Ini akan menghilangkan hasil yang belum Anda panen.**
{% endhint %}

Untuk mencegah hal ini terjadi lagi, **jangan jual SYRUP Anda.** Anda masih membutuhkannya untuk melakukan unstake dari pool "Stake CAKE Earn CAKE".

Kesalahan ini terjadi karena Anda telah menjual atau mentransfer token SYRUP. SYRUP dicetak dengan rasio 1:1 terhadap CAKE saat Anda melakukan stake di CAKE-CAKE Syrup Pool. SYRUP harus dibakar dengan rasio 1:1 terhadap CAKE saat memanggil leaveStaking (unstake CAKE dari pool), sehingga jika Anda tidak memiliki cukup, Anda tidak dapat melakukan unstake dari pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Kesalahan Kehabisan Gas

> Warning! Error encountered during contract execution \[out of gas]

Anda telah menetapkan batas gas yang rendah saat mencoba melakukan transaksi.

{% tabs %}
{% tab title="Solusi" %}
Coba tingkatkan **batas gas** (bukan harga gas!) secara manual di dompet Anda sebelum menandatangani transaksi.

Batas 200000 biasanya sudah cukup.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

Contoh di atas berasal dari MetaMask; periksa dokumentasi dompet Anda jika Anda tidak yakin cara menyesuaikan batas gas.
{% endtab %}

{% tab title="Alasan" %}
Pada dasarnya, dompet Anda (MetaMask, Trust Wallet, dll.) tidak dapat menyelesaikan apa yang sedang dicoba.

Dompet Anda memperkirakan bahwa batas gas terlalu rendah, sehingga panggilan fungsi kehabisan gas sebelum panggilan fungsi selesai.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Solusi" %}
1. Gunakan Unrekt.net untuk mencabut persetujuan untuk smart contract yang ingin Anda interaksikan
2. Setujui kontrak lagi, tanpa menetapkan batas pada batas pembelanjaan
3. Coba berinteraksi dengan kontrak lagi.
{% endtab %}

{% tab title="Alasan" %}
Ini terjadi ketika Anda menetapkan batas pada batas pembelanjaan saat pertama kali menyetujui kontrak, kemudian mencoba melakukan Swap melebihi batas tersebut.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

Anda mungkin mencoba melakukan unstake dari Syrup Pool dengan imbalan yang rendah di dalamnya. Solusi di bawah ini.

Jika tidak, Anda mungkin mencoba mengirim token yang tidak ada di dompet Anda (misalnya, mencoba mengirim token yang sudah ditetapkan untuk transaksi yang tertunda). Dalam hal ini, pastikan saja Anda memiliki token yang ingin Anda gunakan.

{% tabs %}
{% tab title="Solusi" %}
Pertama, [beri tahu tim](../social-accounts.md) pool mana yang Anda coba unstake, agar mereka dapat mengisi ulang imbalan. Jika Anda terburu-buru untuk unstake dan tidak keberatan kehilangan hasil yang tertunda, coba lakukan emergencyWithdraw:

Anda dapat melakukan "emergencyWithdraw" dari kontrak secara langsung untuk melakukan unstake token yang di-stake.

1. Temukan alamat kontrak Syrup Pool yang ingin Anda unstake. Anda dapat menemukannya di log transaksi dompet Anda.
2. Buka [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) dan di bilah pencarian, masukkan alamat kontrak.
3. Pilih **Write Contract.**
4. Klik **"Connect to Web3"** dan hubungkan dompet Anda.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. Di bagian **"3. emergencyWithdraw",** dan klik "Write".

Ini akan melakukan unstake token yang di-stake Anda dan kehilangan hasil yang belum dikumpulkan.

{% hint style="warning" %}
**Ini akan menghilangkan hasil yang belum Anda panen.**
{% endhint %}
{% endtab %}

{% tab title="Alasan" %}
Kesalahan ini cenderung muncul saat Anda mencoba melakukan unstake dari Syrup Pool lama, tetapi tidak cukup imbalan yang tersisa di pool untuk Anda panen saat menarik. Ini menyebabkan transaksi gagal.
{% endtab %}
{% endtabs %}

## **Masalah dengan Prediksi**

Periksa [Broken link](/broken/pages/8zN9xzaYD1DvxZvzLzug "mention")

## **Masalah lainnya**

### Kesalahan Provider

> Provider Error\
> No provider was found

Ini terjadi ketika Anda mencoba terhubung melalui ekstensi browser seperti MetaMask atau Binance Chain Wallet, tetapi Anda belum memasang ekstensi tersebut.

{% tabs %}
{% tab title="Solusi" %}
Pasang ekstensi browser resmi untuk terhubung, atau baca panduan kami tentang [cara menghubungkan dompet ke PancakeSwap](https://docs.pancakeswap.finance/get-started/connection-guide).
{% endtab %}
{% endtabs %}

### ID Chain Tidak Didukung

Alihkan chain Anda ke BNB Smart Chain. Periksa dokumentasi dompet Anda untuk panduan jika Anda membutuhkan bantuan.

### Already processing eth\_requestAccounts. Please wait.

Pastikan Anda masuk ke aplikasi dompet Anda dan terhubung ke BNB Smart Chain.

### Masalah membeli SAFEMOON dan token serupa

Untuk memperdagangkan SAFEMOON, Anda harus mengklik ikon pengaturan dan **mengatur toleransi Slippage ke 12% atau lebih.**\
Ini karena **SafeMoon mengenakan biaya 10% pada setiap transaksi**:

* 5% biaya = didistribusikan ulang ke semua pemegang yang ada
* 5% biaya = digunakan untuk menambah Likuiditas

Inilah juga mengapa Anda mungkin tidak menerima token sebanyak yang Anda harapkan saat membeli.\
Baca lebih lanjut tentang [Cara Membeli Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Kesalahan Internal JSON-RPC

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Terjadi saat mencoba menghapus Likuiditas pada beberapa token melalui MetaMask. Penyebab utamanya masih belum diketahui. Coba gunakan dompet alternatif.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

Anda tidak memiliki cukup BNB untuk membayar biaya transaksi. Anda memerlukan lebih banyak BNB jaringan BEP-20 di dompet Anda.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Tingkatkan batas gas untuk transaksi di dompet Anda. Periksa dokumentasi dompet Anda untuk mempelajari cara meningkatkan batas gas.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Penyebabnya tidak jelas. Coba langkah-langkah ini sebelum mencoba lagi:

1. Tingkatkan batas gas
2. Tingkatkan Slippage
3. Bersihkan cache

## **Masalah dengan Profil**

### Ups! Kami tidak dapat menemukan Pancake Collectibles apa pun di dompet Anda.

Kami sedang menyelidiki logika di balik masalah ini. Sementara itu, coba solusi berikut.

{% tabs %}
{% tab title="Solusi 1" %}
1. Buka halaman "Collectible", kemudian kembali ke halaman profil.\
   Jika Anda tidak dapat menemukan tautannya, buka [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles) secara langsung.
2. Coba buat profil lagi.
{% endtab %}

{% tab title="Solusi 2" %}
Ubah lingkungan.

* Bersihkan cache dan coba lagi.
* Coba lagi di browser yang berbeda.
* Coba lagi di aplikasi dompet yang berbeda.
* Coba lagi di jaringan yang berbeda (beralih antara Wi-Fi dan seluler)
{% endtab %}
{% endtabs %}

### Pemeriksaan nama pengguna terus berputar

Ada dua kemungkinan penyebab.

1. Anda memiliki beberapa dompet yang terpasang di browser.
2. Masalah jaringan.

{% tabs %}
{% tab title="Solusi 1" %}
Penyebab utama: Anda memiliki beberapa dompet yang terpasang di browser.\
\
Ini mungkin menyebabkan konflik antar dompet. Hal ini di luar kendali PancakeSwap dan kami tidak dapat berbuat apa-apa.

1. Hanya pasang satu dompet di browser, hapus yang lain.
2. Hubungkan kembali dompet dan coba atur nama pengguna lagi.
{% endtab %}

{% tab title="Solusi 2" %}
Penyebab utama: Jaringan tidak stabil.

Anda harus mencoba lagi.

1. Hapus apa pun yang telah dimasukkan di kolom teks secara lengkap.
2. Ketik ulang nama pengguna, kemudian tunggu beberapa detik.
3. Jika tidak berhasil, muat ulang halaman dan coba lagi.
{% endtab %}
{% endtabs %}
