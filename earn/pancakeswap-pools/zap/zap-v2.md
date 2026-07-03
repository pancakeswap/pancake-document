---
description: Penyediaan Likuiditas sederhana hanya dengan satu klik
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### Apa itu Zap? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap memungkinkan penyediaan Likuiditas yang sederhana. Tambahkan Likuiditas hanya dengan satu token dan satu klik, tanpa perlu Swap manual atau penyeimbangan token.

* Tambahkan Likuiditas hanya dengan satu token: Anda dapat menambahkan Likuiditas hanya menggunakan satu token dalam pasangan Trading. Zap akan secara otomatis melakukan Swap menggunakan satu token yang Anda sediakan dan secara otomatis menyeimbangkan pasangan Trading ke pembagian 50/50 sebelum menambahkan Likuiditas.
* Tambahkan Likuiditas dengan jumlah token yang tidak seimbang dalam pasangan Trading: Anda dapat menambahkan Likuiditas bahkan jika jumlah token yang Anda sediakan dalam pasangan Trading tidak seimbang sempurna dengan pool saat ini. Misalnya 30:70, yang berbeda dari bobot pool default 50:50. Zap akan secara otomatis menyeimbangkan kembali token ke pembagian 50/50 sebelum menambahkan Likuiditas.
* Hapus Likuiditas dan pilih token yang ingin Anda terima: Saat menghapus Likuiditas, Zap memungkinkan Anda menerima hanya satu token dalam pasangan Trading. Zap akan secara otomatis melakukan Swap sebelum mengembalikan token Anda.

### Aktifkan Zap <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

Secara default, fitur Zap diaktifkan untuk setiap pengguna. Jika Anda tidak melihat UI Zap baru saat menambahkan atau menghapus Likuiditas, harap aktifkan di panel pengaturan. Anda dapat memunculkan panel pengaturan dengan mengklik ikon roda gigi.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
Catatan: Saat ini, fitur Zap masih dalam versi beta. Harap dicatat bahwa fitur ini tidak mendukung beberapa token, seperti token dengan biaya pada transfer. Jika Anda mengalami masalah saat menambahkan atau menghapus Likuiditas, harap nonaktifkan di panel pengaturan.
{% endhint %}

### Zap In (Tambahkan Likuiditas) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

Kunjungi [halaman Likuiditas](https://pancakeswap.finance/liquidity), dan pilih "Add Liquidity".

Pilih pasangan Trading yang ingin Anda sediakan Likuiditasnya dengan memilih dua token input, lihat [panduan Likuiditas](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) untuk mempelajari lebih lanjut.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

Klik tombol "Add Liquidity" untuk melanjutkan.

Jika token dalam pasangan Trading yang Anda tambahkan Likuiditasnya memiliki saldo di Dompet Anda, kotak centang untuk token tersebut akan secara otomatis dicentang. Jika Anda memiliki saldo untuk kedua token di Dompet Anda, kedua kotak centang akan dicentang.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### Zap menggunakan satu token <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

Anda dapat menambahkan Likuiditas hanya menggunakan satu token dalam pasangan Trading. Centang hanya satu kotak centang untuk token yang ingin Anda gunakan. Zap akan secara otomatis menukar setengah dari token yang dicentang ke token lain dalam pasangan Trading sebelum menambahkan Likuiditas. Anda akan melihat pesan peringatan yang menunjukkan token mana yang akan dikonversi.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
Jika dampak harga terlalu tinggi, Zap akan melindungi Anda dengan Slippage. Klik "Reduce TOKEN" untuk menguranginya ke batas yang diinginkan.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### Zap menggunakan dua token dengan jumlah yang tidak seimbang <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Jika kedua token dicentang, jumlah token input tidak sesuai dengan pembagian 50/50. Penyeimbangan Zap akan diperkenalkan. Anda akan melihat pesan "Some of your Token A will be converted to Token B".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
Jika Anda tidak ingin Zap menyeimbangkan jumlah token sebelum menambahkan Likuiditas, cukup klik "Don't Convert". Dalam hal ini, Zap akan menyesuaikan jumlah token input agar sesuai dengan pembagian 50/50 alih-alih mencoba melakukan Swap dan penyeimbangan kembali.
{% endhint %}

### Lanjutkan dengan Zap <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

Ketika Anda mengklik "Supply", detail Zap akan ditampilkan dan menunggu Anda untuk mengonfirmasi.

Anda akan melihat:

1. Berapa banyak token LP yang akan Anda terima.
2. Apa token input, dan jumlah token yang Anda setorkan.
3. Bagaimana token input diperdagangkan agar sesuai dengan pembagian 50/50.
4. Toleransi Slippage yang Anda gunakan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap out (Hapus Likuiditas) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap juga memungkinkan Anda menerima satu token tunggal dalam pasangan Trading saat menghapus Likuiditas.

1. Kunjungi[ ](https://www.google.com/url?q=https://exchange.pancakeswap.finance/%23/pool\&sa=D\&source=editors\&ust=1656322371442758\&usg=AOvVaw2ZJPj_97-YuUMQjQbYbfN4)[halaman Likuiditas](https://pancakeswap.finance/swap#/pool).
2. Klik pada pasangan yang ingin Anda hapus Likuiditasnya di bawah "Your Liquidity".
3. Klik "Remove". Pop-up baru akan muncul.

Di bawah bagian "You Will Receive", Anda dapat menghapus centang pada token yang tidak ingin Anda terima. Zap akan secara otomatis menukar dan mengonversi 100% hasil ke token yang dicentang saat menghapus Likuiditas.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
