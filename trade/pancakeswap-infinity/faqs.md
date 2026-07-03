# FAQ

1. **Apa perbedaan Infinity dengan PancakeSwap V3?**\
   Infinity menambahkan fitur-fitur baru seperti hooks yang dapat diprogram, lebih banyak [jenis pool](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) (seperti LBAMM dan CLAMM), dan penghematan gas. Namun, mekanisme inti Swap dan penyediaan likuiditas secara umum serupa dengan v3, kecuali beberapa perbedaan kecil pada pool LBAMM untuk penyediaan likuiditas.\
   <br>
2.  **Apa perbedaan antara LBAMM dan CLAMM?**

    1. **LBAMM (Liquidity Book AMM):** Menggunakan bin likuiditas, masing-masing menampung likuiditas pada tingkat harga yang berbeda. LP dapat menyediakan likuiditas di berbagai bin, Swap dieksekusi pada satu tingkat harga dalam sebuah bin.
    2. **CLAMM (Concentrated Liquidity AMM):** Memungkinkan pengguna menyediakan likuiditas dalam rentang harga kustom seperti di PancakeSwap V3.

    \
    Untuk detail lebih lanjut, kunjungi [di sini](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types). \
    <br>
3. **Bagaimana cara mengklaim hadiah Farm saya, dan mengapa dibatasi setiap 8 jam?**\
   Anda dapat mengklaim hadiah Farm dari posisi likuiditas Anda dengan mengklik tombol "Harvest". Infinity memungkinkan klaim sekaligus di semua posisi Farm yang aktif, menghemat biaya gas. Hadiah dihitung dan diproses setiap 8 jam untuk mengoptimalkan biaya gas dan komputasi. \
   \
   Untuk detail lebih lanjut tentang mekanisme farming, kunjungi [di sini](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms). \
   <br>
4.  **Bagaimana cara kerja Infinity hooks?**\
    Hooks adalah ekstensi smart contract yang dapat dikustomisasi dan menambahkan fungsionalitas ekstra ke sebuah pool. Hooks dapat memicu tindakan tambahan selama Swap atau peristiwa likuiditas — misalnya, menyesuaikan biaya, memberikan diskon, atau menerapkan logika lain.<br>

    Hooks dilampirkan ke sebuah pool saat pool tersebut dibuat. Dalam kebanyakan kasus, **pengguna tidak perlu mengambil langkah tambahan apa pun**. Selama Anda melakukan Swap atau menyediakan likuiditas seperti biasa, Anda akan secara otomatis mendapat manfaat dari logika hook jika berlaku untuk pool tersebut.<br>

    👉 **Anda dapat melihat hooks yang aktif dan detailnya di halaman setiap pool di bagian "Pool Features".**\
    <br>
5.  **Mengapa saya tidak menerima biaya apa pun saat menarik posisi dari pool LBAMM?**\
    Dalam pool LBAMM (Liquidity Book AMM), biaya secara otomatis ditambahkan ke bin likuiditas aktif Anda. Ini berarti:

    1. Ketika Anda menarik posisi, biaya yang diperoleh sudah termasuk dalam jumlah token total yang Anda tarik.
    2. Tidak seperti AMM tradisional, tidak ada saldo "biaya yang perlu dikumpulkan" secara terpisah — semuanya sudah tergabung dalam nilai posisi Anda.

    \
    Jika Anda tidak menyadari adanya token tambahan saat penarikan, kemungkinan disebabkan oleh:

    1. Posisi Anda mungkin telah mengalami impermanent loss lebih besar dari biaya yang dikumpulkan akibat pergerakan harga selama durasi posisi Anda.
    2. Likuiditas Anda tidak berada di bin aktif tempat transaksi terjadi.
