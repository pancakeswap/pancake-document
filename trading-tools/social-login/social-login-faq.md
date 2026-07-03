# FAQ Social Login

{% hint style="info" %}
Untuk informasi lebih lanjut lihat: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 Gambaran Umum

**1. Apa itu social login PancakeSwap dan mengapa saya harus menggunakannya?**

Social login memungkinkan Anda mengakses PancakeSwap menggunakan akun **Google**, **X (Twitter)**, **Discord**, atau **Telegram** Anda — tanpa ekstensi dompet atau frasa benih. Dompet self-custodial dibuat di balik layar, sehingga Anda dapat mencoba DeFi secara instan, bahkan dengan jumlah kecil. Ini menurunkan hambatan masuk, terutama dalam momen yang sensitif terhadap waktu.

**2. Rantai apa yang didukung social login?**

Dompet social login Anda berfungsi di semua rantai yang saat ini didukung oleh PancakeSwap:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

Semua dompet **kompatibel dengan EVM** dan dapat digunakan di seluruh jaringan ini secara native melalui PancakeSwap. Jika Anda ingin melihat dukungan untuk rantai lain (termasuk non-EVM), beri tahu kami!

**3. Di mana saya bisa menggunakan dompet social login?**

Anda dapat menggunakannya langsung di **browser** desktop atau mobile mana pun melalui aplikasi web PancakeSwap. Ini **tidak kompatibel** dengan aplikasi dompet eksternal atau browser dApp.



### 🛠️ Pengaturan & Penggunaan Dompet

**4. Bagaimana dompet dibuat dan diamankan?**

Dompet Anda dibuat secara otomatis saat login dan diamankan menggunakan **sistem berbagi kunci 2-dari-2**. Kedua bagian diperlukan untuk merekonstruksi kunci dan menghasilkan tanda tangan.

Untuk informasi lebih lanjut tentang enkripsi berbagi, lihat:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. Berapa banyak dompet yang dapat saya buat?**

Anda mendapatkan **satu dompet per akun sosial per dApp**. Misalnya, jika Anda menggunakan login Google di aplikasi lain yang juga menggunakan Privy, aplikasi tersebut akan membuat dompet terpisah.



### 🔐 Keamanan & Privasi

**6. Bisakah seseorang mengakses dompet saya jika mereka mencuri perangkat saya?**

Tidak. Bahkan jika seseorang mendapatkan akses ke perangkat Anda, mereka masih memerlukan **social login** Anda dan (jika diatur) **kata sandi pemulihan** Anda.

**7. Data apa yang disimpan oleh PancakeSwap atau Privy?**

* PancakeSwap **tidak menyimpan** bagian kunci terkait dompet apa pun.
* Privy menyimpan **Bagian Auth terenkripsi dan Bagian Pemulihan (jika alur pemulihan belum diatur)**.

> Jika Anda belum menyelesaikan pengaturan pemulihan, Bagian Pemulihan Anda tetap tersimpan di Privy secara bawaan. Untuk info lebih lanjut kunjungi: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 Pemulihan & Manajemen Sesi

**8. Bisakah saya menggunakan dompet yang sama di perangkat atau browser yang berbeda?**

Ya! Cukup login dengan akun sosial yang sama. Jika ini perangkat baru, Anda akan melalui proses pemulihan menggunakan kata sandi pemulihan Anda (jika sudah diatur).

**9. Apa yang terjadi jika saya mengganti perangkat?**

Anda akan diminta untuk login ulang dengan akun sosial Anda dan melalui alur pemulihan (pengaturan kata sandi). Jika Anda belum mengatur kata sandi pemulihan, login akun sosial sudah cukup.

**10. Bagaimana jika saya kehilangan akses ke social login dan metode pemulihan saya?**

Jika Anda kehilangan akses ke akun sosial dan metode pemulihan Anda, **dompet Anda tidak dapat dipulihkan**. Tidak ada cadangan frasa benih, dan ekspor kunci privat saat ini tidak didukung.

> ⚠️ Ingat: Mengekspor kunci privat Anda, jika diaktifkan di masa mendatang, akan memberikan kendali penuh atas dompet Anda kepada siapa pun yang memilikinya — perlakukan dengan sangat hati-hati.

**11. Berapa lama sesi aktif berlangsung?**

Sesi berlangsung selama 30 **hari**. Setelah itu, Anda akan diminta untuk **login kembali** dan (jika diperlukan) memasukkan kembali kredensial pemulihan Anda. Selama sesi aktif, Anda dapat bertransaksi tanpa perlu menyetujui setiap tindakan secara manual.



### ⚙️ Kompatibilitas & Keterbatasan

**12. Bisakah saya mengekspor atau mengimpor dompet?**

* **Ekspor**: Tidak didukung secara bawaan, karena alasan keamanan. Ini mungkin berubah dalam pembaruan mendatang.
* **Impor**: Tidak didukung. Anda tidak dapat mengimpor dompet eksternal seperti MetaMask atau Phantom.

**13. Bisakah saya menghubungkan dompet ini ke dApp lain menggunakan WalletConnect?**

Belum saat ini. Dompet tertanam **terbatas hanya untuk PancakeSwap**. Jika Anda tertarik untuk menggunakannya lebih luas, beri tahu kami — ekspansi di masa mendatang memungkinkan.



### 🚀 Fitur Lanjutan

**14. Apakah dompet social login mendukung Account Abstraction?**

Ya. Dompet mendukung **fitur Account Abstraction** seperti penggabungan transaksi dan **sponsorship gas** melalui integrasi seperti Biconomy, dll.

**15. Bagaimana transaksi tanpa tanda tangan diaktifkan?**

* Setelah login, sesi Anda aktif hingga 30 **hari**. Selama waktu ini, PancakeSwap dapat meminta Privy untuk menandatangani transaksi atas nama Anda menggunakan kredensial sesi Anda.&#x20;
* Anda tidak akan melihat popup dompet untuk setiap tindakan — semuanya ditangani di latar belakang. Setelah 30 hari, Anda perlu login kembali untuk terus menggunakan pengalaman tanpa tanda tangan ini.
