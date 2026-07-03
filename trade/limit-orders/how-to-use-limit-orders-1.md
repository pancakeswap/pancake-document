# Cara Menggunakan Limit Order

Limit order penghasil biaya di PancakeSwap bekerja secara berbeda dari limit order tradisional. Saat pengguna menempatkan limit order, mereka secara efektif menyediakan **likuiditas satu sisi** ke pool PancakeSwap Infinity.

Seiring pergerakan harga pasar, Swap di pool dapat menggunakan likuiditas pengguna. Ketika ini terjadi, token yang disetor sepenuhnya dikonversi menjadi token output, dan pengguna menerima:

* Token output, dan
* Biaya trading yang diperoleh dari Swap yang dieksekusi terhadap likuiditas mereka.

***

**Contoh: Menjual BNB untuk USDT**

* **Harga saat ini di pool BNB/USDT:** 600 USDT per BNB
* **Harga target / limit pengguna:** 700 USDT per BNB

Proses:

1. Pengguna mengatur limit order untuk menjual BNB seharga 700 USDT.
2. BNB mereka disetor ke tick yang paling dekat dengan harga 700 USDT per BNB di pool.
3. Ketika harga pasar eksternal mencapai 700 USDT, harga pool menyesuaikan untuk cocok (karena peluang arbitrase / harga yang lebih baik).
4. Pada saat itu, BNB pengguna ditukar menjadi USDT.
5. Selama proses ini, pengguna mendapatkan biaya dari setiap Swap yang menggunakan likuiditas mereka.
6. Setelah likuiditas sepenuhnya dikonsumsi, USDT yang telah dikonversi (ditambah biaya) secara otomatis ditarik dan dikirim ke dompet pengguna.

***

### Panduan langkah demi langkah

Pilih pasangan token (misalnya, BNB/CAKE) dan jumlah yang ingin Anda jual / beli

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Tetapkan harga target / limit Anda

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Tempatkan limit order dan "Konfirmasi". Likuiditas ditempatkan atas nama Anda di tick yang paling dekat dengan harga limit

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Setelah harga pool mencapai target Anda, order Anda dieksekusi. Token output yang diinginkan beserta biaya secara otomatis ditarik dan dikirim ke dompet Anda.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Status Order

Anda dapat melihat status order Anda dengan mengklik di sini

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Order Anda dapat berada dalam salah satu kondisi berikut:**

| Status           | Deskripsi                                                                              |
| ---------------- | ---------------------------------------------------------------------------------------- |
| Pending          | Menunggu harga mencapai target Anda                                                   |
| Filled           | Order dieksekusi dan dana dikirim ke dompet Anda                                             |
| Partially Filled | Hanya sebagian order yang dieksekusi. Anda akan memegang kedua token (misalnya, sebagian BNB, sebagian USDT) |
| Cancelled        | Anda membatalkan order. Semua dana Anda dikembalikan kepada Anda                              |

### FAQ

**T: Apakah saya perlu membayar biaya untuk menempatkan limit order?**

J: Tidak. Sebaliknya, Anda mendapatkan 0,1% biaya trading saat order Anda dieksekusi.

**T: Apakah saya bisa menempatkan order untuk pasangan apa pun?**

J: Saat peluncuran, hanya pasangan tertentu yang didukung. Lebih banyak pasangan akan ditambahkan kemudian.

**T: Berapa ukuran order minimum?**

J: $50. Ini mencegah order kecil yang dapat mengakibatkan gas berlebih.&#x20;

**T: Apa yang terjadi jika hanya sebagian order saya yang terisi?**

J: Anda akan memegang kedua token. Anda dapat membatalkan kapan saja dan menarik kedua token beserta biaya yang diperoleh.

**T: Order saya terisi tetapi saya belum menerima dana di dompet saya?**

J: Dalam skenario yang sangat jarang, ini bisa terjadi tetapi dana Anda selalu aman. Cukup gunakan tombol "Withdraw" di UI detail order untuk mengklaim dana secara manual.
