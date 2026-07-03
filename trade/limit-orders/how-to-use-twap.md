# Cara Menggunakan TWAP

## Apa itu TWAP?

TWAP (Time-weighted Average Price) adalah jenis order umum yang digunakan di CeFi yang membagi order menjadi ukuran perdagangan yang lebih kecil dan mengeksekusinya pada interval teratur. Tujuan utama order TWAP adalah untuk mengurangi dampak harga order. Ini juga dapat berguna jika pengguna ingin menerapkan strategi dollar-cost averaging (DCA) dan membeli token tertentu secara konsisten (yaitu sekali sebulan).

Oleh karena itu, TWAP paling baik digunakan ketika ukuran order besar dibandingkan dengan likuiditas yang tersedia, atau ketika pengguna mengantisipasi periode volatilitas harga yang tinggi tanpa tren naik atau turun yang jelas.

## Cara mengatur order TWAP?

1. Buka halaman Swap dan pilih opsi order TWAP dengan mengklik TWAP
2. Pilih token "Dari" dan "Ke" dan masukkan jumlah yang ingin Anda perdagangkan.
3. UI memungkinkan baik order dTWAP-market, yang mengeksekusi semua perdagangan pada harga pasar yang tersedia, maupun order dTWAP-limit, yang hanya mengeksekusi perdagangan individual jika berada dalam batas harga yang ditetapkan oleh pengguna. \
   Dalam contoh ini kami memilih untuk mengeksekusi order TWAP pada harga pasar.
4. Selanjutnya, kami menentukan parameter TWAP. Ada 3 parameter utama yang mengontrol efektivitas order dTWAP:
   1. Total perdagangan: Memungkinkan pengguna untuk menentukan jumlah perdagangan individual yang akan dibagi ordernya. Slider UI dimulai dengan 1 perdagangan dan memungkinkan pengguna meningkatkan jumlah perdagangan individual, atau memungkinkan pengguna memasukkan total perdagangan secara manual di kolom input langsung.\
      Pengguna harus memperhatikan bahwa ada tradeoff tertentu saat menentukan parameter ini: lebih banyak perdagangan berarti ukuran perdagangan individual yang lebih kecil, yang berarti dampak harga yang lebih kecil. Namun, lebih banyak perdagangan juga berarti lebih banyak transaksi dan biaya gas keseluruhan yang lebih tinggi.&#x20;
   2. Interval Perdagangan: Mengatur jarak waktu antara setiap perdagangan individual. UI dimulai dengan minimum yang diizinkan (2 menit), yang menyisakan waktu minimum untuk perang penawaran taker dan penyelesaian blok antara setiap bagian. Pengguna dapat mengaturnya ke durasi apa pun yang diinginkan. Perdagangan tidak akan pernah dieksekusi sebelum waktu ini berlalu setelah perdagangan sebelumnya.\
      Sekali lagi pengguna harus berhati-hati saat mengatur parameter ini: interval yang lebih panjang akan memberi arbitrageur jendela yang lebih lama untuk menutup perbedaan harga pada pool yang terpengaruh dan membawa cadangan kembali ke keseimbangan (setara dengan harga spot). Namun, diperlukan lebih lama untuk order terisi dan menambah ketidakpastian pada harga pengisian akhir, terutama di saat volatilitas yang meningkat
   3. Durasi Maksimum: Waktu maksimum di mana jumlah total semua perdagangan individual yang membentuk order dTWAP penuh dapat dieksekusi. Setelah batas waktu ini, perdagangan kedaluwarsa, terlepas dari jumlah aktual yang telah di-Swap.\
      Perhatikan bahwa semua bagian mungkin tidak dieksekusi dalam limit order, tergantung pada apakah harga tetap dalam parameter yang ditetapkan. \
      Durasi rekomendasi default dihitung dengan mengalikan jumlah interval dengan interval perdagangan, dan kemudian menggandakan jumlah ini sebagai buffer untuk memberikan cukup waktu bagi aktivitas on-chain. (perhatikan bahwa menetapkan durasi yang lebih pendek dari default di atas dapat mengakibatkan order yang terisi sebagian).

Seperti yang terlihat, parameter-parameter ini memberikan fleksibilitas yang signifikan dalam mengkustomisasi setiap order, dengan mempertimbangkan faktor-faktor seperti kondisi pasar, biaya gas saat ini, dll.

8. Tekan "Tempatkan order". Periksa kembali detail order Anda, terima penafian, dan tekan "Konfirmasi order".
9. Setelah transaksi diproses, Anda akan dapat melihat status order Anda di bagian riwayat order, di bawah "Open orders".
10. Order terbuka dapat dibatalkan kapan saja dengan memperluas order dan mengklik tombol "Cancel Order".

Hal-hal yang perlu dipertimbangkan

* Order dieksekusi dalam perdagangan yang lebih kecil selama periode waktu tertentu dan tunduk pada kondisi pasar dan risiko lainnya.
* Perdagangan Anda mungkin dieksekusi pada harga yang jauh berbeda dari harga pasar saat ini (meskipun tidak lebih buruk dari harga limit Anda, jika Anda menetapkan satu), yang dapat mengakibatkan kerugian yang signifikan. Jika harga pasar yang tersedia lebih buruk dari harga limit yang Anda tetapkan, beberapa perdagangan dari order Anda mungkin tidak dieksekusi, mengakibatkan order yang terisi sebagian.
* Perdagangan didasarkan pada protokol terdesentralisasi yang memanfaatkan taker off-chain yang bersaing untuk mengisi order. Taker-taker ini berhak meminta biaya, yang protokol hapus untuk taker yang menang dari token output.&#x20;
* Taker mungkin memperhitungkan biaya gas untuk transaksi Anda saat menetapkan biaya mereka, yang dapat mengakibatkan fluktuasi jumlah biaya.

<br>
