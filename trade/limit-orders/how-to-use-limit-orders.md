---
hidden: true
---

# Cara Menggunakan Limit Order

## Apa itu Limit Order

Limit order adalah alat untuk memungkinkan pengguna membeli atau menjual aset pada harga yang ditentukan atau lebih baik, alih-alih mengandalkan harga pasar pada saat eksekusi. Dalam limit order, meskipun harga dijamin, order yang dieksekusi tidak — limit order hanya akan dieksekusi jika harga memenuhi kualifikasi order.

## Cara mengatur limit order

1. Buka halaman Swap dan pilih opsi limit order dengan mengklik "LIMIT", atau gunakan tautan ini: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. Pilih token "Dari" dan "Ke" yang ingin Anda perdagangkan. Dalam contoh ini kami memilih USDC dan ETH masing-masing, artinya kami ingin membeli ETH dengan USDC.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. Masukkan jumlah yang ingin Anda perdagangkan. Perhatikan harga limit akan menunjukkan harga pasar saat ini yang kemudian akan memperkirakan jumlah output token tujuan (ETH)
2. Tetapkan harga limit yang diinginkan. Perdagangan HANYA akan dieksekusi ketika harga pasar yang tersedia lebih baik atau sama dengan harga limit. Jumlah output token tujuan akan diperbarui sesuai.

Dalam contoh di bawah, kami ingin membeli ETH ketika harganya $1.900 atau lebih baik. Jumlah ETH yang diterima akan sama atau lebih besar dari 0,037 ETH. Hanya penawaran yang sama atau lebih baik dari jumlah ini yang berhak untuk mengisi order. Jumlah ini memperhitungkan biaya gas dan biaya trading. &#x20;

{% hint style="info" %}
Catatan penting: Karena biaya dibayar dari jumlah token output, harga limit sudah mencakup biaya gas & trading sehingga pengguna harus mempertimbangkan hal ini saat mengatur harga. Misalnya, biaya gas order yang sangat kecil dapat mencapai persentase yang sangat besar dari output order, yang mencerminkan harga limit aktual yang tidak kompetitif dengan harga pasar spot.
{% endhint %}

3.  Tekan "Tempatkan order". Periksa kembali detail order Anda, terima penafian, dan tekan "Konfirmasi order".

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. Setelah transaksi selesai, Anda akan dapat melihat order Anda di bagian riwayat order, di bawah "Open orders". \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. Order terbuka dapat dibatalkan kapan saja dengan memperluas order dan mengklik tombol "Cancel Order".

Hal-hal yang perlu dipertimbangkan:

* Order Anda mungkin tidak dieksekusi jika harga pasar yang tersedia lebih buruk dari harga limit yang telah Anda tetapkan.
* Perdagangan didasarkan pada protokol terdesentralisasi yang memanfaatkan taker off-chain yang bersaing untuk mengisi order. Taker-taker ini berhak meminta biaya, yang protokol hapus untuk taker yang menang dari token output.&#x20;
* Taker mungkin memperhitungkan biaya gas untuk transaksi Anda saat menetapkan biaya mereka, yang dapat mengakibatkan fluktuasi jumlah biaya.
* Saat menentukan harga limit, pengguna akan melihat di UI jumlah minimum token tujuan yang akan mereka terima jika order terisi. Hanya taker yang membuat penawaran sama atau lebih baik dari jumlah ini yang berhak untuk mengisi order. Jumlah ini memperhitungkan biaya gas dan biaya trading.
