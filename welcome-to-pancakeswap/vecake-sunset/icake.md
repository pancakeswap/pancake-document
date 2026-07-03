---
description: Staking veCAKE dan Alokasi IFO
hidden: true
---

# iCAKE

### **Apa itu iCAKE yang baru?**

Setelah beralih ke veCAKE, iCAKE yang baru akan didasarkan pada saldo veCAKE

* Sama seperti iCAKE lama, ini menentukan batas komitmen CAKE maksimum dalam penjualan publik IFO PancakeSwap. Misalnya, jika Anda memiliki 200 iCAKE, Anda dapat mengkomitkan 200 CAKE dalam penjualan publik IFO.
* Jumlah iCAKE baru dihitung menggunakan saldo veCAKE di akhir setiap IFO. Oleh karena itu, Anda akan memiliki jumlah iCAKE yang berbeda untuk setiap IFO.
* Karena saldo veCAKE secara bertahap berkurang seiring sisa waktu kunci. Oleh karena itu, iCAKE Anda di IFO mendatang akan berkurang seiring saldo veCAKE. Untuk mempertahankan jumlah iCAKE, tambahkan lebih banyak CAKE ke staking, atau perbarui/perpanjang kunci Anda.

**iCAKE BUKAN token baru, melainkan metrik numerik yang digunakan oleh sistem IFO PancakeSwap.**

### Bagaimana iCAKE dihitung?

Jumlah iCAKE yang Anda miliki didasarkan pada saldo veCAKE di akhir setiap IFO, dikalikan dengan rasio yang telah ditentukan sebelumnya.

veCAKE adalah nilai yang dihitung secara dinamis berdasarkan berapa banyak CAKE yang Anda kunci dan berapa banyak waktu yang tersisa dalam kunci. Untuk mempelajari lebih lanjut tentang cara veCAKE dihitung, lihat [di sini](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef).

Rasio tambahan diterapkan di atas saldo veCAKE, yang disesuaikan oleh Kitchen untuk setiap IFO. Misalnya, jika rasionya adalah 2x, dan Anda memiliki 1 veCAKE di akhir IFO berikutnya, Anda dapat mengkomitkan hingga 2 CAKE.

Contoh:

* Anda mengunci 100 CAKE selama 2 tahun.
  * Sisa waktu kunci Anda adalah: `2 * 52 * 7 * 24 * 60 * 60 = 62899200`  (detik)
  * Waktu kunci maksimum adalah: `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (detik)
  * Pada saat ini, Anda memiliki: `100 * (62899200 / 126403199) ~= 49,76` veCAKE
* IFO berikutnya dijadwalkan; waktu berakhirnya tepat 1 minggu kemudian, yaitu `604800` detik setelah saat ini.
  * Pada saat itu, sisa waktu kunci Anda adalah: `62899200 - 604800 = 62294400` (detik)
  * Pada saat itu, Anda memiliki: `100 * (62294400 / 126403199) ~= 49,28` veCAKE
* Untuk IFO ini, rasio ditetapkan sebesar `3x`
* Oleh karena itu, untuk IFO ini, Anda memiliki: `49,28 * 3 = 147,84` iCAKE, yang berarti Anda dapat mengkomitkan hingga 147,84 CAKE dalam penjualan publik.

### Cara memeriksa jumlah iCAKE yang saya miliki?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

Anda dapat memeriksa jumlah iCAKE yang Anda miliki di halaman IFO [di sini](https://pancakeswap.finance/ifo).

Harap diingat bahwa ketika tidak ada IFO yang akan datang, iCAKE Anda akan dihitung menggunakan saldo veCAKE secara real-time, yang berkurang secara bertahap detik demi detik.

Ketika ada IFO yang akan datang, iCAKE Anda akan dihitung menggunakan saldo veCAKE pada waktu snapshot, yaitu akhir IFO. iCAKE Anda tidak akan berkurang atau berubah hingga IFO berakhir.

### **Bagaimana cara meningkatkan jumlah iCAKE yang saya miliki?**

Anda dapat meningkatkan jumlah iCAKE kapan saja dengan:

* Menambahkan lebih banyak CAKE ke posisi Staking veCAKE Anda.
* Memperpanjang posisi Staking veCAKE Anda.

di [Halaman CAKE Staking](https://pancakeswap.finance/cake-staking)

### Apa itu "Rasio" dalam perhitungan iCAKE?

Rasio adalah faktor kontrol tambahan yang diterapkan di atas saldo veCAKE saat menghitung iCAKE.

Misalnya, jika rasionya adalah 2x, dan Anda memiliki 1 veCAKE di akhir IFO berikutnya, Anda dapat mengkomitkan hingga 2 CAKE.

Di antara setiap IFO, kitchen akan mengoptimalkan "Rasio" berdasarkan berbagai metrik. Penyesuaian akan dipublikasikan di semua saluran media sosial.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

Anda dapat memeriksa angka "Rasio" saat ini untuk perhitungan iCAKE dengan membuka [halaman IFO](https://pancakeswap.finance/ifo).
