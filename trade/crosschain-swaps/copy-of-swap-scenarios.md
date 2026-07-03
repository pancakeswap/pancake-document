---
hidden: true
---

# 🔁 Salinan Skenario Swap

Terdapat 4 skenario untuk transaksi Cross-chain.

#### 1️⃣ Bridge Saja

* Contoh: **Bridge ETH di Base ke ETH di Arbitrum**
* Hanya token yang didukung (USDC, USDT, WETH, dll.) yang dapat di-bridge secara langsung. Token-token ini bervariasi berdasarkan jaringan sumber dan tujuan.

**Token yang didukung untuk Bridging oleh Across**

| Jaringan    | USDC | USDT | WETH | ETH | CAKE | DAI | BAL | POOL | WBTC |
| ----------- | :--: | :--: | :--: | :-: | :--: | :-: | :-: | :--: | :--: |
| ARB <> BNB  |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ❌  |  ❌  |   ❌  |   ❌  |
| BASE <> BNB |   ✅  |   ✅  |   ✅  |  ✅  |   ❌  |  ❌  |  ❌  |   ❌  |   ❌  |
| ARB <> BASE |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ❌  |
| ETH <> BNB  |   ✅  |   ✅  |   ✅  |  ✅  |   ✅  |   ❌ |   ❌ |   ❌  |   ❌  |
| ETH <> BASE |   ✅  |   ✅  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ❌  |
| ETH <> ARB  |   ✅  |   ❌  |   ✅  |  ✅  |   ❌  |  ✅  |  ✅  |   ✅  |   ✅  |

#### 2️⃣ Swap → Bridge

* Contoh: **Tukar BNB di BNB Chain ke USDC di Arbitrum**
* Tukar BNB ke token Bridge yang didukung (misalnya USDC) menggunakan pool PancakeSwap di BNB Chain
* Bridge USDC melalui Across ke Arbitrum

#### 3️⃣ Bridge → Swap

* Contoh: **Tukar USDC di BNB Chain ke ARB di Arbitrum**
* Bridge USDC melalui Across
* Tukar USDC ke ARB menggunakan pool PancakeSwap di Arbitrum

#### 4️⃣ Swap → Bridge → Swap

* Contoh: **Tukar BNB di BNB Chain ke ARB di Arbitrum**
* Tukar BNB ke token Bridge (memaksimalkan output pengguna)
* Bridge melalui Across
* Tukar token yang di-bridge ke ARB di Arbitrum menggunakan pool PancakeSwap

***

### ⚠️ Kasus Kegagalan

| Skenario                              | Hasil                                                                                                                                                                                                  |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Kegagalan Swap/Tx di Jaringan Sumber**   | Pengguna langsung menerima kembali token asli di jaringan sumber                                                                                                                                  |
| **Kegagalan Tx Bridge**                 | Across memproses pengembalian dana dalam 90 menit hingga 2 jam, dan pengguna menerima aset yang di-bridge di jaringan sumber. Sementara Relay memproses pengembalian dana dalam satu menit untuk skenario antara SOL <> EVM. |
| **Kegagalan Swap di Jaringan Tujuan** | Pengguna menerima aset yang di-bridge di jaringan tujuan                                                                                                                                              |
