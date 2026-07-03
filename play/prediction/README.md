# 🔮 Prediction

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Prediction adalah pasar Prediksi terdesentralisasi yang menyenangkan dan sederhana.

> **Prediksi apakah harga BNB, BTC, atau ETH akan naik atau turun – tebak dengan benar untuk menang!**

### Platform

Anda dapat bermain PancakeSwap Prediction di:

* **Desktop/ dApp**: [Panduan PancakeSwap Prediction](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram Mini App (hanya BNBUSD)**: [Prediction Bot](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Ringkasan: Cara Kerjanya

1. **Pilih aset untuk dipertaruhkan**: Saat ini tersedia di **BNB Chain**, **zkSync Era**, dan **Arbitrum One**.
2. **Pilih NAIK atau TURUN**: Prediksi apakah harga aset akan lebih tinggi atau lebih rendah ketika fase "LIVE" berakhir (setiap putaran = 5 menit).
3. Tempatkan jumlah taruhan Anda: Jumlah BNB berapa pun
4. **Kunci posisi Anda**: Setelah ditempatkan, taruhan Anda tidak dapat diubah.
5. **Menang atau kalah**:
   * Jika Anda memilih **NAIK**, Anda menang jika _Harga Penutupan_ > _Harga Kunci_ di akhir putaran.
   * Jika Anda memilih **TURUN**, Anda menang jika _Harga Penutupan_ < _Harga Kunci_ di akhir putaran.

### Mekanisme & Biaya

* **Rantai yang Didukung: BNB Chain, zkSync Era, Arbitrum One**
* **Frekuensi putaran**: Setiap **5 menit** (putaran bergulir).
* **Biaya partisipasi**: **3%** dari total pool hadiah setiap putaran, sebagian digunakan untuk **buyback CAKE**.
* **Kemenangan**: Klaim kapan saja setelah hasil diselesaikan.
* **Pembayaran** didasarkan pada rasio taruhan di setiap pool:
  * Rasio Pembayaran (Pool NAIK) = _(Total nilai kedua pool ÷ Nilai Pool NAIK)_
  * Rasio Pembayaran (Pool TURUN) = _(Total nilai kedua pool ÷ Nilai Pool TURUN)_
  * Lihat: [FAQ](prediction-faq.md) untuk contoh perhitungan

### Hasil

* **Menang:** Anda berbagi total pot dengan pemenang lainnya (dikurangi biaya 3%)
* **Kalah:** Anda kehilangan seluruh jumlah taruhan Anda

**Kasus Khusus**:

* **Seri** (Harga Kunci = Harga Penutupan): Rumah memenangkan semua taruhan.
* Jika tidak ada taruhan lawan:
  * Jika Anda menang: klaim kembali 97% dari taruhan awal Anda (biaya 3% berlaku).
  * Jika Anda kalah: taruhan penuh Anda masuk ke rumah.
* **Dibatalkan:** misalnya kegagalan Oracle, pengguna mendapat pengembalian dana jumlah taruhan awal mereka

### Sumber Harga (Oracle)

| Rantai    | Pasar                                    | Tujuan                                                                         | Oracle                     |
| --------- | ---------------------------------------- | ------------------------------------------------------------------------------ | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (dijeda) | Menetapkan _Harga Kunci_ dan _Harga Penutupan_ (diperbarui \~ hingga 20 detik). | **Chainlink**              |
| BNB Chain | Semua                                    | Mendukung grafik langsung di antarmuka pengguna (hanya untuk referensi).       | Binance / TradingView Feed |

#### **Oracle ChainLink**

* Digunakan untuk harga Kunci dan harga Akhir setiap putaran pasar Prediksi. Ini diperbarui dalam interval hingga 20 detik.
* Kontrak Prediksi kami menggunakan feed harga Oracle ChainLink di BNB Chain untuk menetapkan harga yang digunakan untuk menentukan apakah pengguna menang atau tidak.
* Digunakan untuk grafik "Chainlink" pada antarmuka.

#### **Binance**

* Digunakan untuk pembaruan harga real-time pada antarmuka pasar Prediksi PancakeSwap.
* Digunakan untuk grafik "TradingView" pada antarmuka.

Karena kami menggunakan dua feed harga yang berbeda, pembaruan harga real-time dari Binance dan harga Oracle ChainLink mungkin berbeda dalam jumlah kecil. Namun, perbedaannya seharusnya tidak signifikan.

### Alamat Kontrak

BNB Chain:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
