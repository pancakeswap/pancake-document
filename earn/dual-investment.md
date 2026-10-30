# 🍩 Dual Investment

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201%20%282%29.png" alt=""><figcaption></figcaption></figure>

Dual Investment memungkinkan Anda menempatkan dana pada harga target dan memperoleh reward tetap, ke arah mana pun pasar bergerak. Pilih aset, tentukan apakah Anda ingin **Buy Low** atau **Sell High**, lalu pilih harga target dan tanggal settlement. Pada saat settlement, Anda menerima pokok dana beserta reward, baik dalam aset yang Anda setorkan maupun yang dikonversi pada harga target Anda.

Dual Investment tersedia di BNB Chain dengan **BTCB** dan **BNB**, yang dipasangkan dengan **USDT**.

{% hint style="info" %}
Dual Investment bukan produk tabungan. Bergantung pada harga settlement, dana Anda dapat dikonversi menjadi aset lain pada harga target Anda, dan aset tersebut dapat bernilai lebih rendah daripada yang Anda setorkan.
{% endhint %}

***

## Apa itu Dual Investment?

#### **Dua kemungkinan hasil, satu reward tetap**

Setiap produk Dual Investment memiliki harga target dan tanggal settlement. Saat Anda berlangganan, reward Anda dikunci pada APR yang ditampilkan. Pada saat settlement, harga pasar menentukan salah satu dari dua hasil yang Anda peroleh:

* **Harga tidak mencapai target Anda.** Anda menerima kembali aset asli Anda beserta reward.
* **Harga mencapai target Anda.** Pokok dana dan reward Anda dikonversi menjadi aset lainnya pada harga target Anda.

Anda memperoleh reward pada kedua kasus. Satu-satunya perbedaan adalah aset yang Anda terima.

#### **Buy Low**

Gunakan Buy Low jika Anda bersedia membeli BTCB atau BNB di bawah harga saat ini. Anda menyetorkan **USDT** dan memilih harga target yang lebih rendah daripada harga saat ini.

| Harga settlement             | Yang Anda terima                                                    |
| ---------------------------- | ------------------------------------------------------------------- |
| Sama dengan atau di atas target | USDT (pokok + reward)                                            |
| Di bawah target Anda         | BTCB atau BNB, dibeli pada harga target Anda beserta reward Anda    |

#### **Sell High**

Gunakan Sell High jika Anda bersedia menjual BTCB atau BNB di atas harga saat ini. Anda menyetorkan **BTCB atau BNB** dan memilih harga target yang lebih tinggi daripada harga saat ini.

| Harga settlement                | Yang Anda terima                                          |
| ------------------------------- | --------------------------------------------------------- |
| Sama dengan atau di bawah target | BTCB atau BNB (pokok + reward)                           |
| Di atas target Anda             | USDT, dijual pada harga target Anda beserta reward Anda   |

#### **Cara kerja APR**

APR bergantung pada seberapa dekat harga target dengan harga saat ini dan berapa lama produk berjalan. Target yang lebih dekat dengan harga saat ini membayar APR lebih tinggi karena lebih besar kemungkinannya untuk dikonversi. Target yang lebih jauh membayar lebih rendah tetapi lebih besar kemungkinannya mengembalikan aset asli Anda.

Reward Anda dihitung sebagai berikut:

`Reward = Subscription amount × APR × (Days to settlement ÷ 365)`

#### **Contoh: Buy Low**

BTCB diperdagangkan pada $83,467. Anda berlangganan 1.000 USDT pada produk Buy Low 1 hari dengan target $82,000 pada APR 14,68%. Reward Anda sekitar 0,40 USDT.

| Harga settlement | Yang Anda terima                      |
| ---------------- | ------------------------------------- |
| $82,000 atau lebih | 1.000,40 USDT                       |
| Di bawah $82,000 | 0,0122 BTCB (1.000,40 USDT ÷ $82,000) |

Jika BTCB di-settle pada $78,000, Anda tetap membeli pada $82,000. Anda akan memegang 0,0122 BTCB senilai sekitar 951,60 USDT, yang lebih rendah daripada yang Anda setorkan.

#### **Contoh: Sell High**

BTCB diperdagangkan pada $83,467. Anda berlangganan 0,01 BTCB pada produk Sell High 1 hari dengan target $84,500 pada APR 89,28%. Reward Anda sekitar 0,0000245 BTCB.

| Harga settlement | Yang Anda terima                       |
| ---------------- | -------------------------------------- |
| $84,500 atau kurang | 0,0100245 BTCB                      |
| Di atas $84,500  | 847,07 USDT (0,0100245 BTCB × $84,500) |

Jika BTCB di-settle pada $88,000, Anda tetap menjual pada $84,500. Anda akan menerima 847,07 USDT untuk BTCB yang seharusnya bernilai sekitar 882 USDT.

#### **Siapa pihak lawannya?**

Setiap produk dikuotasikan oleh market maker, yang mengambil sisi berlawanan dari posisi Anda. Market maker menyetorkan jaminan (bond) yang mengamankan pembayaran Anda. Jika market maker gagal bayar, klaim Anda dijamin oleh bond mereka.

***

## Cara menggunakan Dual Investment

#### **Buka halaman Dual Investment**

Kunjungi [pancakeswap.finance/dual-investment](https://pancakeswap.finance/dual-investment?chain=bsc) atau klik **Dual Investment** pada bilah navigasi utama PancakeSwap.

#### **1. Pilih aset target**

Pilih **BTCB** atau **BNB**. Setiap kartu menampilkan harga saat ini dan rentang APR yang tersedia di semua produk untuk aset tersebut.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28407%29.png" alt=""><figcaption></figcaption></figure>

#### **2. Pilih arah**

Pilih **Buy Low** untuk menyetorkan USDT dan membeli aset pada harga yang lebih rendah, atau **Sell High** untuk menyetorkan aset dan menjualnya pada harga yang lebih tinggi.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28430%29.png" alt=""><figcaption></figcaption></figure>

#### **3. Pilih tanggal settlement dan harga target**

Gunakan filter durasi (**1 Day**, **< 3 Days**, **< 7 Days**, dan lebih lama) untuk mempersempit daftar. Produk dikelompokkan berdasarkan tanggal settlement. Setiap baris menampilkan harga target, jaraknya dari harga saat ini, dan APR.

Hitung mundur di samping setiap tanggal settlement menunjukkan sisa waktu Anda untuk berlangganan. Langganan ditutup sebelum settlement.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28475%29.png" alt=""><figcaption></figcaption></figure>

#### **4. Masukkan jumlah langganan Anda**

Klik **Subscribe** pada target yang Anda inginkan, lalu masukkan jumlah atau ketuk **MAX**. Setiap produk memiliki minimum dan maksimum per langganan, serta total kapasitas tetap. Setelah suatu target terisi penuh, target tersebut tidak dapat dibuka kembali, sehingga Anda perlu memilih harga target lain.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28476%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### **5. Tinjau dan konfirmasi**

Tinjau arah, harga target, tanggal settlement, dan kedua kemungkinan hasil.&#x20;

Rate ditahan untuk waktu singkat saat Anda mengonfirmasi. Jika kedaluwarsa atau berubah, halaman akan mengambil rate baru dan meminta Anda menerimanya sebelum melanjutkan.

#### **6. Klaim pembayaran Anda**

Setelah settlement, klik **Claim** pada suatu posisi, atau **Claim all** untuk mengklaim semua posisi yang telah di-settle sekaligus. Pembayaran Anda dikirim ke dompet Anda dalam aset yang ditentukan oleh hasil settlement.

***

## FAQ Dual Investment

#### **Apa itu Dual Investment?**

Dual Investment adalah produk yang memungkinkan Anda menempatkan dana pada harga target dan memperoleh reward tetap. Pada saat settlement, Anda menerima pokok dana beserta reward, baik dalam aset asli Anda maupun yang dikonversi menjadi aset lainnya pada harga target Anda.

#### **Aset apa saja yang didukung?**

BTCB dan BNB, yang dipasangkan dengan USDT, di BNB Chain.

#### **Apa perbedaan antara Buy Low dan Sell High?**

Buy Low memungkinkan Anda menyetorkan USDT dan membeli BTCB atau BNB pada harga target di bawah harga saat ini. Sell High memungkinkan Anda menyetorkan BTCB atau BNB dan menjualnya pada harga target di atas harga saat ini.

#### **Apakah saya memperoleh reward pada kedua hasil?**

Ya. Reward ditetapkan saat Anda berlangganan dan dibayarkan pada kedua hasil. Reward dibayarkan bersama pokok dana Anda, dalam aset apa pun yang Anda terima saat settlement.

#### **Dapatkah saya menarik dana sebelum tanggal settlement?**

Tidak. Setelah Anda berlangganan, dana Anda dikunci hingga settlement dan langganan tidak dapat dibatalkan.

#### **Mengapa APR berbeda antarproduk?**

Target yang lebih dekat dengan harga saat ini, dan tanggal settlement yang lebih singkat, umumnya membayar APR lebih tinggi karena memiliki peluang konversi yang lebih besar. Rate dikuotasikan secara langsung dan dapat berubah antara saat Anda membuka suatu produk dan saat Anda mengonfirmasi.

#### **Mengapa rate berubah saat saya berlangganan?**

Rate dikuotasikan secara langsung oleh market maker dan hanya ditahan untuk waktu singkat. Jika rate kedaluwarsa, berubah, atau pengguna lain lebih dahulu mengisi harga tersebut, halaman akan mengambil rate baru dan meminta Anda menerimanya sebelum melanjutkan.

#### **Apakah saya perlu mengklaim pembayaran saya?**

Ya. Setelah settlement, klaim pembayaran Anda dari **Your Holdings**. Anda dapat mengklaim posisi satu per satu atau menggunakan **Claim all**.

#### **Siapa yang mengambil sisi berlawanan dari posisi saya?**

Market maker mengkuotasikan setiap produk dan mengambil sisi berlawanan dari posisi Anda. Mereka menyetorkan bond yang mengamankan pembayaran Anda, dan jika market maker gagal bayar, klaim Anda dijamin oleh bond tersebut.

#### **Biaya apa saja yang dikenakan?**

Gratis.
