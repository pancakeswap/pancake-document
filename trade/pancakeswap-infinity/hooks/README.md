# Hooks

{% hint style="info" %}
Jika Anda seorang pengembang atau mencari dokumentasi teknis terperinci tentang pengembangan hook, silakan kunjungi [di sini](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook).
{% endhint %}

Hooks adalah add-on powerful yang memungkinkan pengembang memperluas dan menyesuaikan perilaku pool likuiditas di PancakeSwap Infinity. Anggap saja sebagai "plugin" atau "widget" yang menambahkan fitur baru ke pool likuiditas.

#### 🔍 Apa Itu Hooks?

* Hooks adalah smart contract eksternal yang dibuat oleh siapa saja—pengembang, protokol, atau anggota komunitas—dan dilampirkan ke pool likuiditas untuk meningkatkan atau memodifikasi perilakunya.
* Setiap pool hanya dapat memiliki satu hook yang dilampirkan, tetapi satu hook dapat melayani banyak pool.
* Hooks dapat menjalankan kode kustom sebelum atau setelah tindakan kunci seperti:
  * Menginisialisasi pool
  * Swap
  * Menambah/menghapus likuiditas
  * Donasi<br>

**⛓️ Cara Kerja Hooks:**

* Sebuah hook dipilih saat pembuatan pool dan tidak dapat diubah setelahnya.
* Kontrak hook memicu tindakan tertentu (Swap, tambah likuiditas, dll.) dan mengeksekusi logika sebelum atau setelah tindakan tersebut sebagaimana didefinisikan dalam kontrak.
* Misalnya, sebuah hook dapat:
  * Menawarkan diskon biaya Swap kepada pemegang CAKE
  * Membebankan biaya kustom dan mendistribusikan hadiah
  * Mengaktifkan logika Swap baru seperti StableSwap atau pesanan bergaya TWAMM<br>

#### ⚙️ Callback Hook

Hooks dapat dipicu selama sepuluh momen tertentu. Pengembang dapat memilih mana yang ingin mereka implementasikan:

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

Ini memungkinkan implementasi perilaku yang sangat dapat dikustomisasi dan modular melalui hooks.

#### 🔧 Dua Jenis Hooks

**Tipe 1: Tidak Memerlukan Otorisasi**

Hooks ini berjalan secara otomatis dan tidak memerlukan izin pengguna. Mereka dipicu oleh tindakan seperti Swap atau perubahan likuiditas.



Contoh:

* Biaya Dinamis: Menyesuaikan biaya Swap berdasarkan volatilitas pasar
* Rabat Biaya: Memberikan diskon kepada pengguna yang memegang CAKE atau melakukan trading dalam volume tinggi



Contoh Alur (Diskon Biaya CAKE):

1. Seorang pengguna memulai Swap.
2. Hook memeriksa saldo CAKE mereka melalui callback hook `beforeSwap`.
3. Jika pengguna memegang cukup CAKE sesuai ambang batas yang ditentukan, mereka mendapat diskon 50% untuk biaya pool.
4. Sisa transaksi berjalan seperti biasa.<br>

{% hint style="success" %}
Hooks ini tidak memerlukan antarmuka khusus atau interaksi tambahan. Manfaatnya diterapkan secara otomatis.
{% endhint %}

**Tipe 2: Memerlukan Otorisasi Pengguna**

Hooks ini memerlukan pengguna untuk berinteraksi langsung dengan hook tersebut, memberikan otorisasi, dan mungkin perlu mentransfer dana, sering kali untuk membuat atau mengelola posisi.



Contoh:

* Limit Order: Mengeksekusi Swap hanya ketika harga target tercapai.
* TWAP: Memecah pesanan besar menjadi bagian-bagian lebih kecil untuk eksekusi yang lebih baik.
* Manajemen Likuiditas Aktif: Secara otomatis mengelola posisi LP untuk imbal hasil optimal.



Contoh Alur (Hook Limit Order):

1. Pengguna berinteraksi langsung dengan kontrak hook (bukan antarmuka Swap biasa).
2. Mereka memasukkan detail seperti harga limit, pasangan token, jumlah.
3. Hook menerbitkan token tanda terima yang mewakili pesanan.
4. Kemudian, ketika harga pool mencapai target, hook mengeksekusi pesanan menggunakan afterSwap.
5. Pengguna dapat mengembalikan token tanda terima untuk mengklaim aset yang ditukar.

{% hint style="info" %}
Hooks ini sering kali memerlukan antarmuka kustom dan pengguna harus mempercayai serta menyetujui kontrak hook untuk menyimpan dana mereka.
{% endhint %}

#### 🚀 Kasus Penggunaan & Inovasi

Hooks membuka kemungkinan tanpa batas, termasuk:

* AMM kustom (misalnya, kurva stablecoin)
* Hadiah liquidity mining
* Strategi trading otomatis, manajemen likuiditas
* Limit order on-chain, jenis pesanan lainnya
* Penetapan harga dinamis dan penyesuaian biaya
* Strategi LP penghasil yield<br>

Dengan hooks, pengembang dapat membangun pengalaman DeFi yang sepenuhnya baru menggunakan infrastruktur PancakeSwap Infinity yang sudah ada—mempercepat pengembangan dan mengurangi biaya.
