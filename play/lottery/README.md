# 🎟️ Lottery

Bermain PancakeSwap Lottery memberi Anda kesempatan untuk memenangkan hadiah CAKE yang besar! Mudah, adil, dan Anda bisa ikut serta sebanyak yang Anda mau selama Anda memiliki CAKE untuk membeli tiket.

[Lihat smart contract](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)

## **Detail:**

* Harga tiket Lottery untuk 1 tiket: \~$5 USD dalam CAKE.
* Batas pembelian tiket per pengguna: Tidak ada batas keseluruhan, tetapi hanya 100 tiket yang dapat dibeli sekaligus.
* Membayar satu tiket akan memberikan kombinasi 6 digit acak kepada pengguna, dengan setiap digit antara 0-9, misalnya "1-9-3-2-0-4". Cocokkan angka dari kiri untuk memenangkan hadiah—semakin banyak angka yang cocok, semakin besar pool hadiah yang akan Anda bagi.
* Lottery menggunakan implementasi VRF dari Chainlink untuk keacakan yang sesungguhnya dan aman.

## Harga tiket dan diskon pembelian massal

Harga tiket Lottery ditetapkan di awal putaran Lottery baru, dan menargetkan $5 USD (mungkin sedikit bervariasi dengan fluktuasi harga yang tiba-tiba).

Membeli beberapa tiket Lottery sekaligus memberikan diskon massal untuk pembelian Anda. Anda dapat membeli hingga 100 tiket dalam satu pembelian, dengan diskon yang dimulai kecil pada 2 tiket, dan meningkat hingga 10% pada 100 tiket.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202024-08-22%20at%209.59.52%20PM.png)

## **Cara menang**

Cocokkan angka, **dari sisi kiri tiket Anda**, dengan angka pemenang yang diundi di akhir putaran Lottery.

* Mencocokkan bahkan hanya angka pertama saja akan memenangkan hadiah kecil.&#x20;
* Cocokkan lebih banyak angka untuk memenangkan bagian dari pool hadiah yang lebih besar.

## **‌**Kelayakan Hadiah

‌Terdapat total enam bola lotere, dari 0 hingga 9, pada setiap tiket. Untuk menang, angka Anda harus cocok dengan angka yang diundi dalam urutan yang sama dengan bola lotere, dimulai dari kiri tiket. Misalnya:

Angka yang diundi

![Drawn Numbers](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28285%29.png)

Angka tiket Anda

![Your Ticket A](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2895%29%20%281%29.png)

Pada contoh di atas, Tiket A, lima angka tiket cocok dengan angka yang diundi, dalam urutan yang persis sama: semua kecuali yang keempat.

Namun, karena digit keempat **tidak** cocok dengan angka yang diundi, hanya tiga digit pertama yang dihitung sebagai cocok berurutan. Ini akan memenangkan hadiah "Cocok 3 pertama".

![Your Ticket B](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28205%29.png)

Contoh Tiket B. Ini adalah tiket yang tidak beruntung. Meskipun lima digit terakhir cocok, digit pertama tidak cocok, sehingga tiket ini tidak memenangkan apa pun.

Anda hanya akan mendapatkan hadiah dari bracket hadiah tertinggi yang Anda penuhi syaratnya. Tiket yang cocok dengan tiga angka pertama hanya akan memenuhi syarat untuk hadiah dari bracket cocok-tiga, dan bukan untuk bracket cocok-satu atau cocok-dua.

**Ingat: Digit harus cocok secara berurutan, dimulai dari kiri ke kanan.**

## Berbagi hadiah antar bracket hadiah

‌Setelah putaran diundi, dan tiket dengan angka yang cocok ditentukan, hadiah diberikan. Jumlah yang dimenangkan oleh setiap tiket akan bergantung pada berapa banyak tiket lain yang menang dalam bracket hadiah yang sama.

‌Misalnya, jika Anda memiliki satu-satunya tiket yang cocok dengan tiga angka berurutan, dan bagian yang telah ditentukan dari pool hadiah untuk bracket Anda adalah 2000 CAKE, Anda akan menerima penuh 2000 CAKE.

‌Namun, jika Anda dan tiga orang lain cocok dengan tiga angka berurutan, 2000 CAKE akan dibagi antara empat tiket pemenang, artinya Anda akan menerima 500 CAKE.

Lihat [FAQ Lottery untuk perincian hadiah](lottery-faq.md#how-are-prizes-broken-down-between-brackets) di setiap bracket.
