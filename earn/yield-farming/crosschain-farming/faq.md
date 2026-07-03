# FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### Apa yang harus saya lakukan di PancakeSwap pada blockchain lain?

Sediakan likuiditas, lakukan perdagangan, dan farming seperti biasa. Jika Anda sudah menjadi pengguna multichain, ingat untuk menyediakan likuiditas di PancakeSwap pada blockchain lain yang telah kami terapkan (seperti Ethereum), karena kami memiliki hadiah CAKE di BNB Smart Chain untuk Anda, yang memungkinkan Anda mendapatkan lebih banyak CAKE tanpa harus melakukan bridging aset tersebut!

### **Apakah akan ada lebih banyak pasangan?**

Ya, tetapi kami akan melakukan penerapan secara bertahap untuk memastikan keamanan dana pengguna dan inflasi CAKE tetap menjadi prioritas. Sampaikan kepada kami di obrolan komunitas apa yang menurut Anda harus ditambahkan ke PancakeSwap di blockchain lain, serta blockchain lain apa yang sebaiknya kami terapkan PancakeSwap.

### **Mengapa biaya gas untuk staking LP token tinggi?**

Sejumlah kecil token native (misalnya, ETH di Ethereum) diperlukan untuk pengaturan pertama kali. Sehingga transaksi pertama akan sedikit lebih mahal.

Selain itu, ada biaya lain (sebagian besar biaya gas) yang terlibat dalam crosschain farming. Lihat [bagian khusus ini](faq.md#are-there-any-fees-when-i-do-crosschain-farming) untuk mengetahui lebih lanjut.

### **Mengapa staking dan unstaking memerlukan waktu 30 menit untuk selesai?**

Semua transaksi cross-chain akan memerlukan waktu sekitar 30 menit untuk selesai. Hal ini karena:

* Transaksi harus dieksekusi di blockchain farming (seperti Ethereum) dan di BNB Chain.
* Pengiriman pesan cross-chain memerlukan waktu.
* Untuk memastikan keamanan dan semua data tersinkronisasi serta konsisten antara berbagai blockchain.

### **Di mana hadiah CAKE yang saya panen?**

CAKE yang Anda panen akan didistribusikan di BNB Smart Chain. Silakan beralih jaringan blockchain di dompet Anda untuk memeriksa saldo CAKE.

### **Saya tidak dapat memanen karena dompet saya tidak mendukung perpindahan antara blockchain yang berbeda!**

Silakan coba menggunakan aplikasi dompet lain yang mendukung multichain dan perpindahan jaringan.

Harap diperhatikan bahwa staking dan unstaking LP token juga akan memanen semua CAKE yang telah diperoleh ke dompet Anda di BNB Smart Chain. Oleh karena itu, jika Anda tidak ingin menggunakan aplikasi dompet lain, cukup stake lebih banyak, atau unstake sejumlah kecil LP token untuk memanen CAKE yang telah Anda peroleh.

### Apakah ada biaya saat melakukan crosschain farming?

Tidak seperti farming secara native di BNB Chain, farming di blockchain lain memerlukan aktivitas cross-chain. Berikut adalah biaya yang terlibat:

**1 - Biaya gas untuk membuat kontrak proxy**

Kontrak proxy harus dibuat di BNB Chain untuk crosschain farming. Biaya gas untuk pembuatan kontrak proxy disertakan dalam transaksi.

Biaya ini hanya dikenakan sekali pada transaksi "stake" pertama.

**2 - Biaya gas untuk panggilan di BNB Chain**

Ketika pengguna mendepositkan atau menarik LP token. Sebuah eksekutor akan melakukan transaksi yang memanggil atas nama pengguna di BNB Chain. Biaya gas untuk panggilan ini disertakan dalam transaksi.

Biaya ini dikenakan pada setiap transaksi deposit atau penarikan.

**3 - Biaya gas untuk panggilan di blockchain lain**

Ketika pengguna menarik LP token. Sebuah eksekutor akan melakukan transaksi akhir yang memanggil untuk melepaskan LP token di blockchain lain (seperti Ethereum). Biaya gas untuk panggilan ini disertakan dalam transaksi.

Biaya ini hanya dikenakan pada transaksi penarikan.

**4 - Biaya pesan cross-chain**

Kami memanfaatkan bus pesan yang didukung oleh Celer untuk merutekan pesan cross-chain kami. Oleh karena itu biaya pesan disertakan berdasarkan panjang byte pesan tersebut.

Biaya ini dikenakan pada setiap transaksi stake. Dalam transaksi unstake, biaya ini dikenakan dua kali karena komunikasi dua arah antara BNB Chain dan blockchain lain diperlukan untuk keamanan.

```
messagingFee = feeBase + message.length * feePerByte;
```

Anda dapat menemukan variabel dalam rumus tersebut di dalam kontrak bus pesan:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - Dana awal**

Ini sebenarnya bukan "biaya".&#x20;

Untuk setiap pengguna baru yang mulai melakukan crosschain farming di PancakeSwap. Pada transaksi "stake" pertama, kami akan mendepositkan 0,005 BNB ke dompet BNB Chain mereka. Jumlah token native yang sesuai di chain farming (seperti ETH di Ethereum) akan dibebankan dari transaksi deposit, menggunakan nilai pasar yang disediakan oleh oracle harga.

Ini bertujuan untuk membantu pengguna memulai perjalanan BNB Chain mereka dengan mudah. Kami memahami betapa tidak nyamannya memiliki semua CAKE yang dipanen tetapi tidak dapat menjelajahi ekosistem PancakeSwap yang dinamis tanpa menemukan cara lain untuk mendapatkan BNB sebagai gas.

Biaya ini hanya dikenakan sekali pada transaksi "stake" pertama.

### Dari mana emisi berasal?&#x20;

_diperbarui pada 10 Oktober 2022_

Saat ini, Chefs telah mengalihkan 0,0189 CAKE per blok dari pool CAKE ke semua crosschain farm.&#x20;

Berikut adalah rincian emisi:

<table><thead><tr><th width="249"></th><th>Pengali</th><th>CAKE per blok</th></tr></thead><tbody><tr><td><strong>CAKE Pool</strong></td><td>-</td><td><strong>8,9811</strong></td></tr><tr><td><strong>Semua Crosschain Farm</strong></td><td>-</td><td><strong>0,0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0,5x</td><td>0,0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0,2x</td><td>0,0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0,2x</td><td>0,0042</td></tr></tbody></table>

### Apa yang terjadi selama deposit, panen, dan penarikan?

Crosschain farming PancakeSwap seperti menggunakan LP token "pengganti" untuk farming di BNB Chain, dengan MasterChef PancakeSwap yang sama. Hadiah CAKE dihitung dan didistribusikan di BNB Chain, dikontrol dan dijaga oleh kontrak MasterChef yang sama.

#### Saat Deposit:

1. Pengguna meminta deposit LP token di blockchain farming (seperti Ethereum).
2. LP token dipindahkan ke kontrak vault farming.
3. Bus pesan Celer dimanfaatkan untuk mengirimkan pesan "deposit" ke BNB Chain.
4. Eksekutor di BNB Chain mencetak jumlah token farming yang sama sebagai "pengganti", kemudian mendepositkannya ke dalam farm.

#### Saat Panen:

Karena hadiah CAKE dihitung dan didistribusikan di BNB Chain. Pengguna dapat mengklaim hadiah CAKE mereka dengan satu transaksi BNB Chain tanpa perlu operasi cross-chain.

#### Saat Penarikan:

1. Pengguna meminta penarikan LP token di blockchain farming (seperti Ethereum).
2. Bus pesan Celer dimanfaatkan untuk mengirimkan pesan "withdraw" ke BNB Chain.
3. Eksekutor di BNB Chain menarik token farming dari farm, membakar token tersebut, mentransfer CAKE yang diperoleh ke pengguna, dan memanfaatkan bus pesan Celer untuk mengirimkan pesan konfirmasi kembali ke blockchain farming asal.
4. Eksekutor di blockchain farming mengonfirmasi semuanya kemudian melepaskan LP token dari kontrak vault.
