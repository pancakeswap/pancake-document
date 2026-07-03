# Biaya dan Rute

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

Di Exchange V3, secara default PancakeSwap Smart Router akan memanfaatkan likuiditas dari V3, V2, StableSwap (BNB Chain), serta AMM dan market maker (BNB Chain & Ethereum), untuk mengeksekusi transaksi dan menemukan harga terbaik bagi para trader.

Namun, pengguna selalu dapat menyesuaikan trading mereka dengan memilih sumber likuiditas mana yang akan digunakan oleh router, serta mengaktifkan atau menonaktifkan multihop dan split routing.

### **Memeriksa tingkat biaya dan jumlah biaya yang saat ini diterapkan**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

Untuk mengetahui berapa banyak biaya yang akan dikenakan pada Swap Anda saat ini, lihat bagian "Fee" di detail Swap.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

Untuk mengetahui jenis pool dan tingkatan biaya yang digunakan oleh transaksi Anda saat ini, lihat bagian "Route".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

Untuk melihat detail lebih lanjut, klik ikon kaca pembesar untuk menampilkan tampilan rute trading lengkap.



### **Menyesuaikan sumber likuiditas**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

Di bagian atas antarmuka "Customize Routing", Anda dapat memilih sumber likuiditas mana yang akan digunakan router saat merutekan transaksi Anda. Untuk membuka antarmuka ini, Anda dapat:

* Klik "Customize Routing" di bagian bawah tampilan rute trading.
* Klik ikon roda gigi di antarmuka Swap, lalu klik "Customize Routing" di bagian bawah.

Secara default, semua sumber likuiditas diaktifkan dan Smart Router akan memanfaatkan sepenuhnya semua likuiditas yang tersedia di PancakeSwap.

Harap diperhatikan bahwa router TIDAK akan merutekan transaksi antara pool likuiditas AMM dan market maker MM. Ketika transaksi Anda dieksekusi oleh market maker MM, tidak akan melalui pool likuiditas AMM mana pun.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

Anda dapat mengklik tombol "Reset" di sudut kanan atas untuk mereset konfigurasi ke pengaturan default.



### **Menyesuaikan preferensi perutean**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

Di bagian bawah antarmuka "Customize Routing", Anda dapat menyesuaikan preferensi perutean dengan mengaktifkan atau menonaktifkan multihop dan split routing.

Multihop memungkinkan token untuk ditukar melalui beberapa hop di antara beberapa pool likuiditas demi mendapatkan penawaran terbaik. Menonaktifkannya akan membatasi transaksi hanya pada Swap langsung, yang dapat menyebabkan Slippage lebih tinggi atau bahkan kerugian dana.

Split routing memungkinkan Swap token dipecah menjadi beberapa rute untuk mendapatkan penawaran terbaik. Menonaktifkannya akan membatasi transaksi agar hanya dieksekusi dengan satu rute, yang dapat mengakibatkan efisiensi rendah atau Slippage lebih tinggi.

{% hint style="warning" %}
Ketika transaksi Anda tidak dapat dieksekusi karena konfigurasi trading yang disesuaikan, sebuah peringatan akan muncul. Anda dapat mengklik "Check your settings" untuk langsung membuka antarmuka "Customize Routing". Atau pilih "Reset to default" untuk segera mereset konfigurasi Anda kembali ke default.
{% endhint %}
