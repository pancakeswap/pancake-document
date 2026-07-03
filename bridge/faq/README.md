# ❓ FAQ Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Sebelum Melakukan Bridge

1.  **Bisakah saya menggunakan Dompet mobile atau Dompet selain MetaMask untuk mem-bridge CAKE?**

    Saat ini, PancakeSwap CAKE Bridging mendukung Coinbase Wallet, MetaMask, dan Dompet yang kompatibel dengan MetaMask. Dukungan Dompet lainnya akan segera hadir.

    _Tips:_ Untuk menghindari risiko salin-tempel kunci privat atau frasa benih, kami menyarankan untuk membuat Dompet baru melalui ekstensi Dompet desktop untuk bridging.
2.  **Mengapa suatu rute atau token tidak tersedia?**

    Beberapa rute bergantung pada kapasitas bridge, dukungan token, atau Likuiditas. Silakan coba lagi nanti atau gunakan penyedia yang berbeda. Token yang tersedia per rantai ditampilkan langsung di UI Bridge.
3.  **Saya mendapat error saat mengirimkan transaksi bridging.**

    Coba masukkan jumlah secara manual alih-alih menggunakan tombol "MAX", dan hapus desimal dari jumlah jika diperlukan.
4.  **Mengapa kutipan bridging saya menampilkan "Insufficient X to cover native fee"**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    Bridging memerlukan biaya gas yang dibayarkan dalam token asli rantai sumber, misalnya:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    Pastikan Anda memiliki cukup token asli di Dompet sumber Anda untuk menutupi biaya guna menyelesaikan transaksi.
5.  **Mengapa tombol menampilkan "X CAKE Exceeded"?**

    Ada batas kapasitas harian untuk bridging CAKE antara BSC dan Aptos demi keamanan. Coba dengan jumlah yang lebih kecil atau tunggu dan coba lagi nanti. Batas disesuaikan secara dinamis oleh Chef berdasarkan permintaan.
6.  **Mengapa saya tidak dapat menemukan token tertentu?**

    Token tersebut mungkin tidak didukung pada rute yang Anda pilih atau mungkin kekurangan Likuiditas. Coba rantai lain atau jumlah yang berbeda.
7.  **Bisakah saya melakukan bridge dari BNB Chain ke Ethereum tetapi ke alamat yang berbeda?**

    Tidak, demi alasan keamanan, bridging hanya berfungsi antara alamat yang sama di rantai EVM.
8.  **Mengapa saya tidak bisa mem-bridge kurang dari 0,00000001 CAKE?**

    Token Aptos, termasuk CAKE di Aptos, memiliki maksimal 8 tempat desimal. Transaksi di bawah 0,00000001 akan ditolak atau dibulatkan ke bawah. Ini juga berlaku untuk bridging Ethereum. Jumlah sisa tetap ada di Dompet sumber Anda.

***

## Setelah Melakukan Bridge

1.  **Bisakah saya membatalkan transfer bridge setelah mengonfirmasi?**

    Tidak, setelah dimulai, transaksi bridge ditangani oleh penyedia dan tidak dapat dibatalkan. Untuk membalikkan, bridge aset kembali melalui transaksi baru.
2.  **Bagaimana jika transaksi saya terjebak dalam status "pending"?**

    Bridging dapat membutuhkan waktu hingga 30 menit. Periksa status transaksi Anda dengan mencari hash-nya di penjelajah penyedia bridge yang bersangkutan:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    Jika masih pending setelah 60 menit, silakan hubungi admin kami melalui [saluran sosial](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
3. **Saya belum menerima CAKE. Apa yang harus saya lakukan?**
   * Saat melakukan bridge CAKE ke Aptos untuk pertama kalinya, Anda mungkin perlu **mengklaim CAKE secara manual**. Pastikan Dompet Aptos Anda memiliki cukup APT untuk gas. Lihat [panduan bridging Aptos](https://docs.pancakeswap.finance/bridge/bridging/aptos) dan [penjelasan Aptos](https://theaptosbridge.com/faq#registering-claiming-assets).
   * Saat melakukan bridge ke BNB Chain atau Ethereum, beberapa Dompet mengharuskan Anda untuk menambahkan alamat token CAKE secara manual untuk melihat saldo Anda. Sebagai contoh, ikuti [panduan MetaMask](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) ini - Dompet lain seharusnya memiliki alur yang serupa.
   * Jika Anda masih tidak melihat CAKE setelah 60 menit, hubungi admin kami melalui [saluran sosial](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts).
