---
description: '2026-08-21'
---

# Memperkenalkan Shared Inventory Hook

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

Mengutip lima pasangan seharusnya tidak membutuhkan modal lima kali lipat. Namun onchain, begitulah kesepakatan yang diterima setiap penerbit aset: likuiditas terikat pada setiap pasangan, sehingga setiap pasangan baru berarti menyediakan modal tambahan - sebagian besar hanya diam tanpa menghasilkan apa pun sampai pasangan tersebut diperdagangkan dalam rentang harga yang tepat. Setiap kali Anda ingin mengutip pasangan baru, Anda menyediakan modal LP baru ke dalamnya — modal yang kemudian terkunci pada satu pasangan itu dan tidak dapat digunakan di tempat lain.

Shared Inventory Hook (SIH) memutus keterkaitan itu. Ini adalah hook terbaru di PancakeSwap Infinity — dan yang pertama dibangun untuk efisiensi modal.

_💡 Ringkasan: Hook adalah smart contract (seperti add-on) yang terhubung ke pool Infinity dan menjalankan logika kustom di tengah swap — tanpa perlu membuat venue baru._

Jadi bagaimana cara kerjanya?

Alih-alih mengunci tumpukan terpisah di setiap pool, penerbit aset RWA mendanai **satu inventaris bersama**, dan shared inventory hook mengutip kedalaman dari inventaris itu ke pasangan mana pun yang sedang diperdagangkan — just-in-time, tepat saat swap terjadi. Bayangkan satu gudang bahan yang memasok setiap hidangan di dapur, alih-alih gudang bahan terpisah untuk masing-masing hidangan. Satu saldo melakukan pekerjaan banyak saldo.

Perubahan tunggal itulah yang membuat SIH efisien secara modal, dan tampak dalam tiga cara:

* **Modal tetap aktif dan bekerja.** Likuiditas dari inventaris hook disuntikkan secara just-in-time saat swap, sehingga aktif bekerja dan menghasilkan biaya bagi Anda alih-alih menganggur.
* **Peluang biaya dari satu saldo, di berbagai pasangan.** Satu inventaris menghasilkan di semua pasangan yang dilayaninya, sehingga Anda menangkap arus biaya dengan modal yang jauh lebih sedikit.
* **Price impact lebih rendah.** Karena likuiditas yang dikutip saat swap lebih dalam, trade besar mengalami price impact lebih rendah setiap kali SIH mengutip harga terbaik.
* **Efisiensi modal meningkat.** Danai sekali; modal yang sama mendukung kedalaman di setiap pasangan yang mengaktifkan SIH. Selain itu, Anda dapat mengaktifkan SIH untuk pasangan baru tanpa menambah modal.

> \*\*Sudah yakin? Bawa aset Anda ke onchain dengan cara yang efisien secara modal — isi formulir ini → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**Buktinya ada onchain**

SIH diluncurkan bersama bStocks pada bulan Agustus ini, dan angka yang paling penting adalah seberapa keras modal tersebut bekerja. Pada snapshot hook terbaru (21 Agu 2026), 75% inventaris bersama aktif dikerahkan di tiga pasangan (inventaris hook \~$297K, aktif \~$224K). Pada dua pasangan yang sudah matang, CRCLB dan MUB, utilisasinya \~99% (98.96% / 98.95%). Modal yang akan menganggur di pool V3 CLAMM tradisional berada dalam rentang dan mengutip di sini.

Pada minggu-minggu pertamanya (hingga 21 Agu), ketiga pasangan memperdagangkan \~$710K dalam 5,713 swap — dilayani dari inventaris bersama sebesar \~$297K, menghasilkan biaya LP pada tier 0.25%.

_**Sumber:** Dasbor Dune Internal_ **Pool aktif:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**Ke mana arah ini**

Model ini dibangun untuk berskala — lebih banyak pasangan, satu saldo bersama yang membentang di ribuan pasar yang diperdagangkan 24/7. Ini adalah jalur tercepat yang pernah kami lihat untuk menghadirkan seluruh jajaran pasangan sebuah token ke onchain tanpa melipatgandakan modal di baliknya.

Pool SIH aktif berada di [halaman Earn PancakeSwap](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001) — buka **Infinity** dan cari **Shared Inventory** di bawah fitur pool. SIH saat ini diaktifkan pada CRCLB / USDT, MUB / USDT, dan GMEB / USDT.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_Catatan: LP ritel sudah dapat menambahkan likuiditas ke pool ini dari Earn — setoran tersebut menjadi likuiditas pool residen, yang disimpan terpisah dari inventaris bersama._

_**Penting:**_

_SIH kurang terpapar pada pergeseran harga dibandingkan posisi LP standar karena inventaris hanya dikerjakan pada saat swap. Ini bukan tanpa risiko. Operator tetap memegang inventaris yang bergerak mengikuti pasar. Seperti strategi onchain lainnya, hasilnya bergantung pada volume, inventaris, lindung nilai, dan kondisi pasar._

Siap memaksimalkan efisiensi modal? Aktifkan SIH untuk pasangan token Anda sekarang → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, The Chefs 🥞

***

_Penafian: Konten ini hanya untuk informasi umum dan tujuan edukasi. Konten ini tidak boleh dianggap sebagai nasihat keuangan, hukum, atau profesional lainnya. Harga aset digital dapat berfluktuasi. Nilai investasi Anda dapat turun maupun naik._
