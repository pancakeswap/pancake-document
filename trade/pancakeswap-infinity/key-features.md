# Fitur Utama

### 1️⃣ Singleton

Di PancakeSwap v3, setiap pool likuiditas memiliki kontraknya sendiri, yang membuat pembuatan pool dan Swap di beberapa pool menjadi lebih mahal.

Infinity memperbaiki hal ini dengan mengimplementasikan model Singleton. Kini, semua pool berada dalam satu kontrak tunggal yang disebut PoolManager. Perubahan ini memangkas biaya gas pembuatan pool hingga 99% dan membuat Swap multi-hop (Swap yang melewati beberapa pool) menjadi jauh lebih murah dengan menghindari transfer token yang tidak perlu.

#### ⚙️ **Cara kerjanya:**

* Data setiap pool disimpan dalam kontrak bersama menggunakan ID pool yang unik.
* Membuat pool baru kini hanya merupakan pembaruan state, bukan deployment kontrak penuh.
* Swap antar pool lebih cepat dan menggunakan lebih sedikit gas.<br>

Pendekatan Singleton ini, bersama dengan optimisasi lain seperti Flash Accounting dan ERC-6909, membantu menjadikan PancakeSwap Infinity sebagai salah satu platform DEX yang paling hemat gas saat ini.

***

### ⚡️ Flash Accounting

Flash Accounting adalah optimisasi powerful dalam PancakeSwap Infinity yang membantu mengurangi biaya gas selama transaksi kompleks seperti Swap multi-hop dan perubahan likuiditas.

Pada versi lama (seperti v3), token dipindahkan masuk dan keluar dari setiap pool pada setiap langkah transaksi. Hal ini menyebabkan biaya gas tinggi, terutama untuk Swap multi-hop.

Dengan Flash Accounting, hal tersebut tidak lagi diperlukan. Alih-alih memindahkan token setelah setiap langkah, PancakeSwap Infinity melacak semua pergerakan token secara internal dan hanya melakukan satu transfer akhir di akhir seluruh transaksi. Ini menghemat banyak gas.

#### ⚙️ **Cara Kerjanya:**

* Ketika Anda berinteraksi dengan Infinity (misalnya, melakukan Swap atau menambah likuiditas), sistem menghitung saldo bersih token yang Anda hutang atau terima.
* Saldo token bersih ini disimpan sementara menggunakan Transient Storage, fitur baru yang diperkenalkan dengan peningkatan Cancun Ethereum (EIP-1153).
* Transient Storage lebih murah dari penyimpanan tradisional karena hanya berlaku selama durasi transaksi—tidak diperlukan penulisan atau pembacaan permanen.

***

### 🪙 Dukungan Token Native

Dengan pengenalan arsitektur Singleton dan Flash Accounting, PancakeSwap Infinity kini mendukung token gas native (misalnya BNB, ETH) secara langsung di pool likuiditas—tidak perlu lagi wrapping dan unwrapping.

#### ✅ Sorotan Utama

* **Pool Token Native Langsung:** Anda kini dapat membuat pool seperti ETH/USDC, BNB/CAKE tanpa memerlukan WETH atau WBNB.
* **Hemat Gas:** Transfer token native \~50% lebih murah dibandingkan transfer token ERC-20, menghasilkan biaya gas lebih rendah untuk Swap dan tindakan likuiditas.<br>

**Sebelumnya Dihapus, Kini Diaktifkan Kembali:** Dukungan token native tidak ada di versi sebelumnya karena kompleksitas implementasi dan fragmentasi likuiditas.

***

### 📈 Kurva Penetapan Harga Kustom

PancakeSwap Infinity memberikan pengembang kemampuan untuk membuat model penetapan harga kustom untuk pool—melampaui model tradisional yang digunakan di sebagian besar AMM.

{% hint style="success" %}
**Pengembang dapat membangun perilaku Swap dan model likuiditas yang sepenuhnya baru yang disesuaikan dengan jenis aset atau strategi trading tertentu.**
{% endhint %}

#### 🔧 Apa Itu Kurva Penetapan Harga Kustom?

Kurva penetapan harga kustom memungkinkan pengembang untuk:

* Melewati logika pool manager native, membuat pool dengan perilaku Swap yang didefinisikan secara kustom.
* Mengubah cara jumlah token dihitung untuk Swap atau modifikasi likuiditas.
* Menggabungkan mekanisme biaya kustom, seperti:
  * Biaya penarikan likuiditas
  * Rabat atau penalti berdasarkan strategi

Semua ini dimungkinkan melalui callback hook before/after swap, yang dapat mencegat dan memodifikasi parameter Swap secara dinamis.

#### 🛠 Contoh Kasus Penggunaan

* **Kurva StableSwap:** Merancang kurva yang lebih datar di sekitar rasio harga 1:1, mengurangi dampak harga antara aset seperti USDC dan USDT.
* **RWA:** Membuat perilaku kustom untuk berbagai jenis aset dengan pasokan dinamis.
* **Biaya di Tingkat Hook:** Membebankan biaya unik yang berbeda dari biaya tingkat pool, seperti biaya pengembang.
* **Model Risiko Kustom:** Menyesuaikan penetapan harga untuk mencerminkan volatilitas, data oracle, atau metrik eksternal.

{% hint style="info" %}
Pada versi AMM sebelumnya (misalnya, PancakeSwap v2/v3), logika penetapan harga bersifat hardcoded dan kaku. Arsitektur PancakeSwap Infinity membuka kemampuan untuk membangun pool yang lebih efisien secara modal dan lebih disesuaikan.
{% endhint %}

#### 🔍 Fleksibilitas Pengembang

* Pengembang dapat men-deploy kontrak hook kustom untuk mengganti logika penetapan harga.
* Callback hook seperti beforeSwap dan afterSwap memungkinkan kendali penuh atas bagaimana delta token dihitung dan diterapkan.

***

### 🧮 ERC-6909: Akuntansi Multi-Token yang Efisien

PancakeSwap Infinity mengadopsi [ERC-6909](https://eips.ethereum.org/EIPS/eip-6909), standar token ringan dan hemat gas yang dirancang untuk akuntansi internal beberapa token dalam satu kontrak. Standar ini menggantikan banyak operasi ERC-20 tradisional dengan primitif mint dan burn—menghasilkan penghematan gas yang signifikan dan alur transaksi yang lebih sederhana.

#### ⚙️ Cara Kerjanya

Alih-alih memindahkan token masuk dan keluar dari protokol pada setiap interaksi, token ERC-6909 merepresentasikan saldo internal:

* Mint: Ketika pengguna menyetorkan token atau melakukan trading, mereka dapat memilih untuk menerima token ERC-6909 sebagai klaim.
* Burn: Kemudian, alih-alih mentransfer token ERC-20 lagi, pengguna cukup membakar token ERC-6909 ini untuk menyelesaikan saldo atau mendanai operasi baru.

Model ini secara drastis mengurangi kebutuhan transfer token eksternal, yang biasanya menimbulkan biaya gas lebih tinggi dan berinteraksi dengan logika pihak ketiga (misalnya, pemeriksaan daftar hitam USDC).

#### 🪙 Manfaat ERC-6909

<table><thead><tr><th width="262.9921875">Fitur</th><th width="497.7421875">Manfaat</th></tr></thead><tbody><tr><td>✅ Klaim Saldo Internal</td><td>Tidak perlu berulang kali mentransfer token antara pengguna dan kontrak</td></tr><tr><td>✅ Mint/Burn Hemat Gas</td><td>Overhead konstan terlepas dari token, tidak ada panggilan kontrak eksternal</td></tr><tr><td>✅ Lebih Sederhana dari ERC-1155</td><td>Ukuran kode lebih kecil, tidak ada callback, tidak ada persyaratan transfer batch</td></tr><tr><td>✅ Dukungan Multi-Token</td><td>Satu kontrak dapat melacak beberapa jenis token dengan saldo yang terisolasi</td></tr><tr><td>✅ Terintegrasi dengan PoolManager</td><td>Menghilangkan persetujuan dan transfer ERC-20 yang berlebihan</td></tr></tbody></table>

#### 🚀 Kasus Penggunaan

* **Trader frekuensi tinggi:** Hindari transfer yang boros gas dan berinteraksi langsung menggunakan saldo internal.
* **Manajer likuiditas:** Buka dan tutup posisi dengan lebih efisien tanpa pergerakan token yang berlebihan.

#### 💡 Catatan Penting

* Pengguna memilih untuk menggunakan alur ERC-6909 ketika mereka tidak perlu segera menyelesaikan transfer token.
* Saldo internal dapat dikonsolidasi dan diselesaikan secara bersih nanti, memberikan pengguna tingkat lanjut kendali dan fleksibilitas yang lebih besar.

***

### 💸 Metode Donate

Metode `donate()` memungkinkan pengguna untuk langsung memberi insentif kepada penyedia likuiditas dalam rentang di dalam sebuah pool dengan mendonasikan token. Metode ini mengandalkan sistem akuntansi biaya pool untuk memfasilitasi pembayaran, memastikan hanya token pool yang didukung.

#### 🔹 Fitur Utama:

* **Pembayaran Langsung ke LP:** Donasi dibuat langsung kepada penyedia likuiditas, memberikan hadiah kepada mereka yang mempertahankan likuiditas dalam rentang aktif pool.
* **Hanya Mendukung Token Pool:** Metode `donate()` hanya mendukung donasi dalam token pool, karena memanfaatkan sistem akuntansi biaya untuk memastikan distribusi yang tepat.
* **Terbuka untuk Semua Pengguna:** Pengguna mana pun dapat memanggil metode `donate()`, memungkinkan siapa saja untuk memberi insentif pada penyediaan likuiditas aktif.

Meskipun metode `donate()` adalah alat yang powerful untuk memberi insentif kepada LP, para donatur harus menyadari bahwa donasi mereka mungkin di-frontrun oleh pengguna lain. Hal ini dapat terjadi ketika seorang pengguna dengan cepat menambahkan likuiditas ke pool tepat sebelum donasi dilakukan, menerima sebagian dari dana yang didonasikan.

Untuk mencegah frontrunning, donatur mungkin perlu mempertimbangkan strategi tambahan saat merancang mekanisme donasi mereka, seperti:

* Memastikan donasi terjadi dengan cara yang meminimalkan kemampuan frontrunning yang oportunistik.
* Menambahkan penundaan waktu atau kondisi tertentu (menggunakan callback hook before/after donate) yang memastikan donasi tidak dieksploitasi dengan cara ini.
