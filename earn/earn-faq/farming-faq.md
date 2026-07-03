---
hidden: true
---

# FAQ Farming

### Mengapa ada beberapa APR?

Dalam V3, Anda dapat mengkonsentrasikan aset saat menyediakan likuiditas untuk meningkatkan bagian Anda terhadap total likuiditas yang tersedia, sehingga mendapatkan % hadiah yang lebih tinggi.&#x20;

Oleh karena itu, tergantung pada pengaturan rentang harga posisi, setiap posisi likuiditas akan memiliki APR biaya LP-nya sendiri dan APR farming-nya sendiri.

APR global dihitung dengan total jumlah hadiah CAKE dalam USD, dibagi dengan total jumlah aset dalam posisi aktif yang saat ini di-stake di farm. Jadi APR farming global hanyalah referensi umum, dan tidak mewakili APR individual untuk setiap posisi.

Untuk melihat APR farming Anda, periksa posisi Anda yang terdaftar di bawah setiap farm.

###

### Apa yang terjadi jika posisi likuiditas saya keluar dari rentang saat staking di Farm?

Dalam V3, hanya posisi likuiditas aktif (dalam rentang) yang akan mendapatkan CAKE dari farm.

Posisi akan berhenti menerima hadiah CAKE ketika harga keluar dari rentang.

Jika harga kembali masuk ke dalam rentang, posisi akan mulai menerima hadiah CAKE lagi. Tidak diperlukan tindakan tambahan dari peserta staking.



### Apakah ada cara untuk menyesuaikan posisi saya secara otomatis agar selalu dalam rentang dan mendapatkan hadiah biaya?

PancakeSwap v3 mendukung deposit likuiditas satu klik melalui Zap, tersedia di BNB Chain dan Ethereum.



### Apakah lebih baik selalu farming dengan posisi likuiditas dalam rentang yang lebih kecil?

Menyediakan likuiditas ke rentang harga yang lebih kecil akan membantu mengkonsentrasikan likuiditas Anda, meningkatkan bagian relatif Anda terhadap total likuiditas dalam rentang harga, yang berpotensi mendapatkan lebih banyak hadiah CAKE.

Namun, perlu diingat bahwa hanya posisi likuiditas aktif yang akan mendapatkan hadiah CAKE. Ini berarti Anda hanya akan mendapatkan hadiah ketika harga perdagangan saat ini berada dalam rentang harga yang ditentukan dalam posisi likuiditas.

Jika Anda perlu menyesuaikan rentang harga posisi, Anda perlu melakukan unstake, menghapus likuiditas, dan membuat posisi baru dengan rentang harga yang diperbarui. Perlu diingat bahwa penyesuaian yang sering tidak selalu merupakan strategi yang paling optimal karena merealisasikan impermanent loss dan memerlukan biaya gas tertentu untuk menyelesaikan beberapa transaksi.



### Berapa banyak posisi yang dapat saya stake dalam satu farm?

Tidak ada batas maksimum posisi yang dapat Anda stake dalam satu farm.

Namun perlu diingat bahwa Anda perlu mengeluarkan biaya gas untuk memanen secara manual dari masing-masing posisi. Selalu pertimbangkan biaya gas dalam operasi yield.



### Seberapa sering saya harus memanen hadiah?

Seberapa sering Anda memanen hadiah terserah Anda, tetapi perlu diingat bahwa ada biaya kecil yang terlibat dalam pemanenan. Anda dapat melihat biaya ini di dompet Anda saat mengonfirmasi setelah mengklik "Harvest"**.**

Ini menunjukkan biaya pemanenan seperti yang terlihat di dompet MetaMask. Dompet yang berbeda akan menampilkan informasi dengan cara yang sedikit berbeda. Pertimbangkan untuk membiarkan hadiah Anda tumbuh terlebih dahulu sehingga Anda lebih jarang membayar biaya.



### Bagaimana jika saya ingin menyesuaikan posisi saat staking di farm?

Saat staking di farm, Anda dapat menambah atau menghapus likuiditas tanpa melakukan unstake. Cukup temukan posisi likuiditas yang ingin Anda sesuaikan, dan klik judul/id-nya, maka Anda akan diarahkan ke halaman detail posisi di mana Anda dapat menggunakan tombol "Add" dan "Remove".

Jika Anda ingin menyesuaikan konfigurasi rentang harga posisi likuiditas, Anda perlu melakukan unstake dari farm, menghapus semua likuiditas, dan membuat ulang posisi baru dengan menambahkan likuiditas.



### Apa yang mempengaruhi APR Farming?

Dalam Farm v3, APR hadiah CAKE dapat bervariasi antara posisi likuiditas. Ini didasarkan pada faktor-faktor berikut:

* Tingkat emisi CAKE ke Farm\
  \- lebih banyak CAKE akan menghasilkan yield yang lebih tinggi untuk semua farm. Baca lebih lanjut di [halaman tokenomics kami](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics)
* Pengali farm\
  \- farm dengan pengali yang lebih tinggi akan mendapatkan lebih banyak CAKE secara proporsional terhadap semua farm. Harap diperhatikan bahwa farm v3 dan v2 + stable swap menggunakan dua kumpulan pengali yang terpisah. Dan farm di Ethereum dan BNB Chain juga menggunakan dua kumpulan pengali yang terpisah.
* Jumlah token yang didepositkan dalam posisi\
  \- lebih banyak token dalam posisi berarti bagian relatif yang lebih besar terhadap total likuiditas aktif di farm pool dan mendapatkan lebih banyak hadiah CAKE
* Rentang harga yang dipilih\
  \- rentang harga yang lebih kecil memungkinkan konsentrasi yang lebih tinggi untuk jumlah token yang sama yang didepositkan, yang berarti bagian relatif yang lebih besar terhadap total likuiditas aktif di farm pool, dan mendapatkan lebih banyak hadiah CAKE
* Jumlah likuiditas yang saat ini aktif\
  \- jika ada lebih banyak pengguna yang mendepositkan dan mengkonsentrasikan likuiditas mereka dengan rentang yang sama seperti Anda, Anda akan mendapatkan hadiah CAKE yang lebih sedikit karena bagian relatif yang lebih kecil terhadap total
* Apakah posisi likuiditas aktif\
  \- hanya posisi likuiditas aktif yang akan mendapatkan hadiah CAKE dari farm



### Mengapa saya melihat popup "Update Positions"?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28321%29.png)

Tidak lama setelah peluncuran V3, Chefs menerapkan pembaruan pada Farm untuk membuat perhitungan hadiah lebih akurat dan andal. Jika Anda melihat popup ini, itu berarti beberapa posisi Anda memerlukan pembaruan.

Cukup klik "Update All", dan konfirmasi di popup dompet Anda.

Harap diperhatikan bahwa Chefs juga menerapkan pembaruan ini pada data staking historis antara peluncuran Farm V3 dan saat pembaruan ini diterapkan. Jika ada hadiah CAKE tambahan, mereka akan di-airdrop ke dompet Anda sebelum 1 Mei 2023.



### Mengapa farm 2x di V3 memiliki APR lebih rendah daripada farm 1x di V2?

Pertama, ketika membandingkan APR, Anda perlu memastikan total likuiditas yang di-stake antara dua farm adalah sama.

Selain itu, kami sekarang memiliki beberapa kelompok farm yang memiliki aliran emisi CAKE masing-masing. Dan setiap kelompok farm berbagi kumpulan pengali yang terpisah.

Setiap farm individu akan menerima emisi CAKE berdasarkan:

* A = Total CAKE per detik/blok untuk kelompok farm yang dimilikinya
* B = Total jumlah pengali dalam kelompok yang dimilikinya
* C = Pengali yang dimilikinya

`CAKE per blok/detik = C / B * A`

Angka-angka di atas dapat ditemukan di masing-masing kontrak [MasterChef](/broken/pages/-MeTWzQOSmb1ej51HT0I).



### Bisakah saya menggunakan bCAKE di farm v3?

Ya

bCAKE untuk Farm V3 akan segera hadir setelah penerapan Farm V3 PancakeSwap. Nantikan pembaruannya.
