# 🔀 Crosschain Swaps

Crosschain Swap memungkinkan pengguna untuk menukar token antar jaringan dengan mulus—semuanya dalam satu transaksi yang efisien.

Crosschain Swap didukung antara:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**Transaksi berlangsung sangat cepat — biasanya selesai dalam hitungan detik hingga kurang dari satu menit.**
{% endhint %}

***

### 🔍 Cara Kerjanya

1. Pengguna memilih jaringan Asal / Tujuan dan token Asal / Tujuan
2. Router PancakeSwap menghitung rute paling efisien
3. Swap dieksekusi menggunakan pool likuiditas PancakeSwap (v2, v3, Infinity, StableSwap) di jaringan sumber dan tujuan
4. Bridging ditangani melalui protokol mitra kami: [Across](https://across.to/) (untuk EVM <> EVM), [Relay](https://relay.link/bridge) (untuk SOL <> EVM)

{% hint style="success" %}
**Crosschain Swap tersedia untuk token apa pun dengan likuiditas yang memadai di jaringan sumber dan tujuan.**
{% endhint %}

***

### 💸 Biaya

* **PancakeSwap tidak membebankan biaya apa pun untuk transaksi Cross-chain.**
* Biaya terdiri dari:
  1. **Biaya Trading:** Dikenakan untuk Swap di dalam pool likuiditas di jaringan sumber dan tujuan
  2. **Biaya Bridge:** Dibayarkan kepada relayer untuk bridging aset

***

### 🎯 Apa Itu Intents?

Intents memungkinkan pengguna untuk menentukan hasil yang diinginkan tanpa perlu khawatir tentang bagaimana hal itu dicapai.

Contoh Intents:

* "Tukar 1 ETH di Base untuk setidaknya 3000 USDC di Arbitrum"

Tanpa intents, pengguna perlu melakukan secara manual:

* Bridge ETH ke Arbitrum
* Menemukan DEX dengan harga ETH → USDC terbaik

{% hint style="success" %}
**Dengan intents — sistem menangani semuanya secara otomatis.**
{% endhint %}

**Manfaat desain berbasis intent:**

* UX yang mulus
* Waktu transaksi lebih cepat
* Transaksi satu klik, satu langkah

***

### 🔐 Audit

Kami telah melakukan beberapa putaran audit dengan nama-nama terkemuka di bidang keamanan cross-chain:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
