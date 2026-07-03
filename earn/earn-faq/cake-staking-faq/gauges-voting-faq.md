---
hidden: true
---

# FAQ Pemungutan Suara Gauges

### Saya memiliki posisi aktif, mengapa saya tidak bisa memilih? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Pastikan waktu unlock Anda sama dengan atau lebih lambat dari 1 minggu setelah waktu snapshot epoch saat ini.&#x20;

Jika posisi Anda membuka kunci pada waktu snapshot, itu berarti Anda memiliki 0 veCAKE pada waktu snapshot. Oleh karena itu Anda tidak dapat memilih.



### Bisakah langsung memilih setelah saya menyiapkan posisi veCAKE?

Ya.

Setelah posisi Anda siap, Anda dapat langsung menggunakan CAKE untuk memilih.

Namun:

* Tidak ada suara yang dapat diberikan dalam 24 jam terakhir sebuah epoch.
* Anda tidak dapat memperbarui keputusan pemungutan suara pada gauge tertentu lebih sering dari 10 hari.
* Pastikan posisi Anda tidak membuka kunci lebih awal dari atau pada waktu snapshot.



### Bisakah saya mendapatkan lebih banyak veCAKE atau suara?

Ya, cukup tambahkan lebih banyak CAKE atau perpanjang posisi kunci Anda.

Harap diperhatikan bahwa setelah mendapatkan lebih banyak veCAKE dengan menambahkan CAKE atau memperpanjang waktu kunci. Anda perlu memperbarui setiap gauge secara manual dengan mengirimkan ulang permintaan pemungutan suara.



### Mengapa hasil pemungutan suara berubah setelah periode penghitungan?

Selama periode penghitungan, PancakeSwap Kitchen akan memberikan suaranya berdasarkan berbagai metrik dari semua gauge.&#x20;

Tujuannya adalah untuk:

* Memastikan pool likuiditas inti mendapatkan pengembalian yang kompetitif pada posisi LP mereka
* Memastikan pengaturan mitra Syrup Pool yang ada terpenuhi sebelum sepenuhnya memigrasikannya ke sistem pemungutan suara gauge veCAKE
* Memastikan bahwa farm-farm yang lebih kecil yang tidak menerima suara apa pun setelah peluncuran veCAKE akan mendapatkan setidaknya sebagian alokasi dalam peluncuran awal, dibatasi pada tingkat emisi mereka saat ini.

Lihat proposal ini untuk lebih detail: [https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c](https://pancakeswap.finance/voting/proposal/0x9602c8f56d01f239b88ecf914ee263cc9cdd75b8d10ae4d9536fc27b2680849c)



### Mengapa jumlah suara saya berkurang?

Karena ketika kita memilih pada gauge, kita memilih menggunakan veCAKE kita. Dan saldo veCAKE secara bertahap berkurang seiring sisa waktu kunci.&#x20;

Suara Anda akan berkurang hingga 0 ketika posisi veCAKE Anda membuka kunci.

Untuk mendapatkan lebih banyak suara, dapatkan lebih banyak veCAKE dengan menambahkan lebih banyak CAKE ke kunci, atau memperpanjang kunci.



### Setelah mendapatkan lebih banyak veCAKE, mengapa saya tidak bisa memilih lebih banyak gauge?

Ketika memilih pada gauge, kita memberikan suara dengan mendefinisikan berapa % dari veCAKE kita yang pergi ke setiap gauge.

Oleh karena itu, meskipun Anda mendapatkan lebih banyak veCAKE. Jika Anda telah mengalokasikan 100% veCAKE Anda dalam 10 hari sebelumnya, Anda tidak dapat mengubah keputusan hingga akhir periode cooldown 10 hari.



### Hasil pemungutan suara telah dihitung, mengapa tingkat emisi tidak berubah?

Dibutuhkan sekitar 72 jam untuk menerapkan hasil pemungutan suara ke berbagai produk emisi di PancakeSwap. Chefs terus mengotomatiskan proses ini untuk memperpendek jeda serta meningkatkan akurasi.



### Mengapa gauge yang saya pilih tidak menerima emisi CAKE apa pun di epoch berikutnya?

Gauge yang masuk daftar putih perlu menerima suara yang setara minimal 1 CAKE per hari dalam emisi, sebelum mereka dapat menerima CAKE apa pun.
