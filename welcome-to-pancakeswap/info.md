# 📈 Analitik (Halaman Info)

## Halaman Info&#x20;

Lihat situs analitik asli PancakeSwap di sini: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Semua data metrik inti bersumber dari Pengindeks internal PCS, yang pada gilirannya mengumpulkan data dari peristiwa yang dipicu saat kontrak dipanggil.&#x20;

Untuk dimensi tanggal dalam pengindeks internal PancakeSwap, kami menggunakan waktu standar internasional (UTC) untuk statistik harian. Oleh karena itu, ketika sumbu horizontal pada Dasbor menampilkan tanggal, itu merepresentasikan tanggal dalam waktu standar internasional (UTC).<br>

## Metrik Inti

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volume (Volume Trading):** Kami memantau data harian untuk setiap pasangan perdagangan dan data perdagangan harian untuk setiap token. Volume perdagangan harian ditentukan dengan mengalikan volume perdagangan setiap token untuk hari tersebut dengan harganya.

**Total Value Locked:** Dapatkan semua pool dari Pengindeks internal dan baca reserve\_usd atau total\_value\_locked\_usd dari setiap pool.&#x20;

**Harga:** Dalam Pengindeks Internal PCS, kami menggunakan beberapa pool dasar untuk menghitung harga terkait USD. Pool utama adalah pool perdagangan stablecoin, di mana kami menggunakan pool perdagangan dengan volume tertinggi sebagai pool dasar dan menghitung harga USD stablecoin berdasarkan bobot volume perdagangan. Selain itu, pool perdagangan token dasar ke stablecoin chain juga dianggap sebagai pool dasar untuk menyediakan harga USD.

_Token yang tidak masuk daftar putih atau tidak dipasangkan dengan token yang masuk daftar putih dikecualikan dari perhitungan ini._

<br>
