# 🧙 Page 1

## Cara Menarik NFT Anda dari PancakeSwap NFT Marketplace

Halaman PancakeSwap NFT Marketplace tidak lagi tersedia, tetapi smart contract marketplace masih aktif. Jika Anda mendaftarkan NFT untuk dijual dan NFT tersebut tidak pernah terjual, NFT tersebut masih disimpan oleh kontrak marketplace. Anda dapat mengambilnya kembali sendiri dengan membatalkan listing secara langsung di BscScan.

Proses ini memerlukan beberapa menit per NFT dan hanya membutuhkan sedikit BNB untuk biaya gas.

### Sebelum Anda memulai

Anda memerlukan:

* **Dompet yang sama dengan yang Anda gunakan untuk mendaftarkan NFT.** Hanya dompet yang membuat listing yang dapat membatalkannya.
* **Dompet browser** (misalnya MetaMask, ekstensi Trust Wallet, atau ekstensi Binance Wallet) yang diatur ke **BNB Smart Chain**.
* **Sedikit BNB** untuk membayar gas. Setiap NFT ditarik dalam transaksinya masing-masing.

Siapkan alamat-alamat berikut:

| Item                       | Alamat                                       |
| -------------------------- | -------------------------------------------- |
| Kontrak marketplace        | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Koleksi Pancake Squad      | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Koleksi Pancake Bunnies    | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Tetap aman**
>
> * Hanya berinteraksi dengan kontrak marketplace `0x17539cCa21C7933Df5c980172d22659B8C345C5A`. Selalu periksa alamat pada URL BscScan.
> * Menarik NFT Anda **tidak pernah** memerlukan pengiriman BNB atau token, dan tidak pernah memerlukan penandatanganan persetujuan (`approve` atau `setApprovalForAll`). Jika sebuah situs web atau seseorang meminta Anda melakukannya, itu adalah penipuan.
> * PancakeSwap tidak akan pernah mengirim DM kepada Anda atau menanyakan frasa benih Anda.

### Langkah 1: Temukan NFT yang masih terdaftar

Untuk setiap NFT yang ingin Anda tarik, Anda memerlukan dua informasi: **alamat koleksi** dan **token ID**.

1. Buka [halaman Read Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) dari kontrak marketplace di BscScan.
2. Cari dan buka **`viewAsksByCollectionAndSeller`**.
3. Isi kolom berikut:
   * `collection`: alamat koleksi dari tabel di atas (misalnya, Pancake Squad adalah `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller`: alamat dompet Anda
   * `cursor`: `0`
   * `size`: `100`
4. Klik **Query**.
5. Lihat hasil `tokenIds`. Ini adalah token ID yang masih terdaftar di koleksi tersebut, dan merupakan NFT yang dapat Anda tarik.
6. Jika Anda mendaftarkan NFT di lebih dari satu koleksi, ulangi langkah 3 sampai 5 untuk setiap koleksi.

**Jika `tokenIds` kosong (`[]`)**, Anda tidak memiliki listing aktif di koleksi tersebut. NFT Anda telah terjual (dalam hal ini Anda sudah menerima BNB) atau Anda telah membatalkan listing sebelumnya (dalam hal ini NFT sudah kembali ke dompet Anda).

**Jika Anda memiliki lebih dari 100 listing** dalam satu koleksi, angka terakhir pada hasil adalah cursor berikutnya. Lakukan query lagi dengan angka tersebut sebagai `cursor` untuk melihat sisanya.

**Jika NFT Anda berasal dari koleksi selain Pancake Squad atau Pancake Bunnies**, buka **`viewCollections`** pada halaman yang sama, masukkan `cursor = 0` dan `size = 100`, lalu klik **Query** untuk melihat setiap koleksi yang didukung marketplace.

### Langkah 2: Tarik NFT Anda

1. Buka [halaman Write Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) dari kontrak marketplace di BscScan.
2. Klik **Connect to Web3** dan hubungkan dompet yang sama yang mendaftarkan NFT. Pastikan dompet Anda berada di BNB Smart Chain.
3. Cari dan buka **`cancelAskOrder`**.
4. Isi kolom berikut:
   * `_collection`: alamat koleksi dari Langkah 1
   * `_tokenId`: token ID dari Langkah 1, sebagai angka biasa (misalnya `1234`)
5. Klik **Write** dan konfirmasikan transaksi di dompet Anda. Anda tidak mengirim BNB apa pun; Anda hanya membayar gas.
6. Setelah transaksi berhasil, NFT kembali ke dompet Anda.
7. Ulangi untuk setiap NFT yang ingin Anda tarik.

Untuk memastikan prosesnya berhasil, jalankan Langkah 1 lagi. Token ID tersebut seharusnya tidak lagi muncul dalam daftar.

### Pemecahan masalah

| Masalah                                                   | Artinya dan yang harus dilakukan                                                                                                                                                                                         |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Error: `Order: Token not listed`                          | Dompet yang terhubung tidak mendaftarkan token ID ini di koleksi ini, atau NFT sudah terjual atau ditarik. Pastikan Anda menggunakan dompet asli serta alamat koleksi dan token ID yang benar.                           |
| Tombol Write tidak berfungsi                              | Dompet Anda kemungkinan berada di jaringan yang salah. Beralih ke BNB Smart Chain dan hubungkan kembali.                                                                                                                 |
| Kehabisan gas atau dana tidak mencukupi                   | Tambahkan sedikit BNB ke dompet Anda untuk menutup biaya gas.                                                                                                                                                           |
| Saya tidak lagi memiliki akses ke dompet yang mendaftarkan NFT | Hanya dompet asli yang dapat membatalkan listing. Tidak ada seorang pun, termasuk PancakeSwap, yang dapat menariknya atas nama Anda.                                                                                |
