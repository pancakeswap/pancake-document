# 🎯 PancakeSwap Auto Slippage

PancakeSwap telah memperkenalkan Auto Slippage untuk membuat Trading lebih mudah dan lebih efisien. Auto Slippage secara otomatis menyesuaikan Slippage untuk Anda berdasarkan kondisi pasar saat ini, membantu mencegah perdagangan yang gagal dan mengurangi risiko kehilangan uang akibat kesalahan Slippage.

## Apa itu Slippage?

**Slippage** terjadi ketika harga yang Anda harapkan untuk suatu perdagangan berbeda dari harga di mana perdagangan sebenarnya diselesaikan. Ini dapat terjadi karena beberapa alasan:

* Volatilitas pasar – Harga dapat bergerak cepat antara saat Anda menempatkan dan mengonfirmasi
* Likuiditas rendah – tidak cukup token tersedia pada harga yang Anda harapkan
* Penundaan blockchain – waktu konfirmasi dapat menyebabkan harga berubah sebelum perdagangan selesai

{% hint style="info" %}
Contoh:

Anda mencoba menukar 100 CAKE untuk BNB, mengharapkan 1 CAKE = 0,01 BNB. Namun pada saat perdagangan Anda diproses, harga telah berubah dan Anda hanya mendapatkan 0,0098 BNB per CAKE. Perbedaan kecil ini yang kami sebut Slippage.
{% endhint %}

## Apa itu Toleransi Slippage?

**Toleransi Slippage** adalah perbedaan harga maksimum yang bersedia Anda terima sebelum perdagangan Anda dibatalkan. Jika harga bergerak melebihi toleransi yang Anda tetapkan, transaksi Anda akan gagal untuk mencegah kerugian yang tidak terduga.

{% hint style="info" %}
Contoh:

Jika Anda menetapkan toleransi Slippage 1% dan harga berubah lebih dari 1% sebelum perdagangan selesai, perdagangan tidak akan berjalan.
{% endhint %}

## Apa yang terjadi jika Toleransi Slippage saya terlalu rendah?

Jika toleransi Slippage Anda **terlalu rendah**, ada kemungkinan lebih tinggi transaksi Anda akan gagal — terutama ketika:

* Pasar sedang volatile
* Anda menukar token dengan Likuiditas rendah
* Menggunakan token dengan pajak atau mekanisme kompleks

{% hint style="warning" %}
Penting: Meskipun transaksi gagal, Anda tetap akan mengonsumsi biaya gas untuk mencoba.
{% endhint %}

## Memperkenalkan Auto Slippage - Mengapa Auto Slippage Membantu?

Auto Slippage secara otomatis menyesuaikan Slippage Anda berdasarkan kondisi pasar saat ini, menghemat waktu Anda dan mengurangi risiko perdagangan yang gagal.&#x20;

Dengan **Auto Slippage**, tidak perlu lagi menyesuaikan toleransi Slippage secara manual. Ini membantu mencegah masalah umum seperti:

* **Menetapkan Slippage terlalu rendah**, yang dapat menyebabkan transaksi gagal akibat perubahan harga kecil selama eksekusi.
* **Menetapkan Slippage terlalu tinggi**, yang dapat mengakibatkan menerima lebih sedikit token dari yang diharapkan karena menerima rentang harga yang lebih lebar.

{% hint style="info" %}
Untuk memastikan pengalaman Trading terbaik, auto slippage telah **diaktifkan secara otomatis**. Jika toleransi Slippage manual telah ditetapkan, pengaturan Slippage baru akan diterapkan.
{% endhint %}



## Bagaimana cara kerja Auto Slippage?

<pre class="language-html"><code class="lang-html"><strong>Auto Slippage (%) = (Biaya Gas dalam USD / Nilai Token Output dalam USD) * 100%
</strong></code></pre>

* Jika biaya gas tinggi dibandingkan nilai token output, Auto Slippage akan menetapkan Slippage yang lebih tinggi untuk memastikan perdagangan berhasil.
* Jika gas murah dan nilai token output besar, Slippage yang lebih kecil akan digunakan.

Auto Slippage akan memilih nilai antara **0,5%** dan **5,0%**, tergantung pada kondisi token dan jaringan.



## Apakah Auto Slippage tersedia di semua jaringan?

Tidak — Auto Slippage hanya didukung di rantai Layer 1 (L1) seperti BNB Chain, Ethereum, dll.

Ini tidak didukung di rantai Layer 2 (L2), karena:

* Formula auto slippage mengandalkan nilai biaya gas yang bermakna untuk menghitung pengaturan Slippage yang berguna
* Karena biaya gas L2 sangat rendah, penerapan auto slippage di L2 tidak akan meningkatkan tingkat keberhasilan perdagangan

{% hint style="success" %}
&#x20;Jika Auto Slippage **tidak didukung** di suatu jaringan:

* Pengaturan Slippage yang sebelumnya Anda gunakan akan diterapkan
* Jika Anda belum pernah menetapkan sebelumnya, akan bawaan ke 0,5%
{% endhint %}


