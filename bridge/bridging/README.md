---
description: Bridge CAKE antara Ethereum, BNB Chain, Aptos, dan banyak lagi
---

# 🌉 Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Bridging ke/dari EVM (Situs Baru): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Bridging ke/dari Aptos (V1 Bridge): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## Apa itu bridging dalam kripto?

* Bridging dalam kripto mengacu pada proses pemindahan aset antara jaringan blockchain yang berbeda.
* Ini meningkatkan interoperabilitas, memungkinkan transfer data dan aset di berbagai jaringan.

\
Berikut beberapa alasan mengapa Anda mungkin ingin melakukan bridge:

* Membeli token kripto yang berbeda
* Mencetak NFT yang hanya tersedia di jaringan tertentu
* Menghemat biaya dengan transaksi yang lebih murah
* Menggunakan dapp yang hanya tersedia di jaringan lain

***

## CAKE, sebuah token multichain

Dengan ekspansi dan penerapan multichain kami, CAKE kini menjadi token multichain yang asli di BNB Chain, tetapi juga tersedia di Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB, dan Aptos.

CAKE di rantai mana pun setara dengan CAKE di BNB Smart Chain. CAKE selalu dapat di-bridge antar rantai dengan rasio 1:1 dan tanpa biaya apa pun dalam bentuk CAKE.

**Harap diingat bahwa hanya ada satu CAKE.** Tidak ada versi CAKE yang berbeda di rantai yang berbeda. Total pasokan CAKE di semua blockchain dibatasi pada 400 juta, sebagaimana diuraikan dalam [proposal pemungutan suara](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5) ini.

***

## Apa itu PancakeSwap Bridge?

PancakeSwap Bridge adalah alat dalam aplikasi yang praktis yang memungkinkan Anda memindahkan aset antara blockchain yang berbeda langsung melalui antarmuka PancakeSwap. Alih-alih mengunjungi situs bridge eksternal, Anda dapat mem-bridge token yang didukung antar rantai seperti BNB Chain, Ethereum, Base, Arbitrum, dan lainnya—semuanya dari satu tempat.

PancakeSwap Bridge didukung oleh penyedia pihak ketiga terpercaya dan berfungsi sebagai **agregator**—memilih rute terbaik berdasarkan harga, kecepatan, dan keandalan.

Untuk mempelajari cara mem-bridge CAKE, lihat tutorial dan FAQ di bagian berikut.

***

## 🔗 Cara Kerjanya

### Bridging melalui Agregator

PancakeSwap Bridge bertindak sebagai lapisan cerdas di atas protokol bridge pihak ketiga yang terpercaya. Saat Anda memulai transfer bridge, PancakeSwap akan:

* Memeriksa beberapa bridge yang terintegrasi untuk menemukan rute optimal
* Mengirim transaksi Anda ke penyedia yang dipilih

Bridging bersifat non-custodial—aset Anda tidak menyentuh penjagaan PancakeSwap. Transfer ditangani langsung oleh penyedia bridge.

### Penyedia Bridge yang Didukung

Saat ini kami berintegrasi dengan:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Catatan: Setiap penyedia memiliki mekanisme bridging, rantai yang didukung, biaya, dan batas yang berbeda.

***

### Rantai dan Token yang Didukung

#### Rantai yang Saat Ini Didukung

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (Situs V1)

#### Token yang Tersedia untuk Bridging

Token yang tersedia bervariasi berdasarkan rantai dan rute. Token yang umum didukung meliputi (namun tidak terbatas pada):

* CAKE
* USDT
* USDC
* ETH

***

#### Keterbatasan & Pengecualian

Beberapa token mungkin tidak didukung karena keterbatasan bridge atau kendala Likuiditas. Token-token ini telah disaring untuk pengalaman pengguna terbaik. Sebagai contoh:

**Untuk cBridge:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**Untuk deBridge:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_Di atas hanya contoh. Token yang benar-benar tersedia per rantai ditampilkan langsung di UI Bridge._

***

### 💸 Biaya dan Pengeluaran

#### Biaya Bridge

* Dikenakan oleh penyedia bridge yang mendasarinya
* Biasanya mencakup biaya kecil per transfer
* Ditampilkan dengan jelas sebelum Anda mengonfirmasi bridge Anda

***

#### Biaya Gas

* Anda membayar biaya gas di **rantai sumber** untuk memulai transaksi
* Beberapa penyedia mungkin juga memerlukan gas di **rantai tujuan**
* **Tips:** Selalu simpan token asli (misalnya, ETH, BNB) di kedua sisi bridge

***

#### Jumlah Minimum & Batasan

Beberapa rute bridge memberlakukan:

* **Jumlah minimum/maksimum bridge** (misalnya, minimum 10 USDC)
* **Desimal atau format token yang didukung** (misalnya, hanya token ERC-20)

UI akan secara otomatis mendeteksi dan menampilkan transfer yang tidak valid.

***

### ⏳ Waktu Transaksi & Pelacakan

#### Berapa Lama Waktu yang Dibutuhkan untuk Bridging?

Transfer bridge biasanya selesai dalam beberapa **menit**, tergantung pada:

* Rantai sumber dan tujuan
* Kemacetan jaringan
* Efisiensi penyedia bridge

#### Melacak Transfer Anda

Setelah dikirimkan, Anda dapat melihat status transaksi melalui penjelajah khusus penyedia:

* [deBridge Explorer](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Explorer](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

Jika transaksi macet dalam waktu lama, periksa penjelajah yang relevan atau hubungi admin kami melalui [saluran sosial](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) untuk mendapatkan [bantuan](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help).

***

### 🧠 Tips Sebelum Melakukan Bridge

* **Simpan token gas di kedua rantai** (misalnya, ETH + BNB)
* **Mulai dengan jumlah kecil** jika ini pertama kali Anda melakukan bridge
* Hindari bridging selama periode aktivitas rantai yang tinggi (dapat mengakibatkan biaya gas yang lebih tinggi)
* Konfirmasi kompatibilitas token di kedua rantai
* Selalu periksa kembali jaringan sumber dan tujuan

***

### Tambahan: Alamat CAKE Omni-chain Fungible Token (OFT)

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
