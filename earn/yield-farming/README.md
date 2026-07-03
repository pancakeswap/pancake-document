# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

Yield Farms memungkinkan pengguna untuk mendapatkan CAKE sambil mendukung PancakeSwap dengan melakukan Staking pada LP Token.

Lihat [panduan Cara Menggunakan Farm](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) kami untuk mulai farming.

Pelajari [cara menemukan smart contract Farm](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
Yield farming dapat memberikan hadiah yang lebih baik daripada Syrup Pools, tetapi mengandung risiko **Impermanent Loss**. Ini tidak semenakutkan kedengarannya, namun tetap penting untuk memahami konsep ini sebelum Anda mulai.

Lihat [artikel tentang Impermanent Loss ](https://academy.binance.com/en/articles/impermanent-loss-explained)dari Binance Academy untuk mengetahui lebih lanjut.
{% endhint %}

## Perhitungan Hadiah

Perhitungan APR Yield Farm mencakup keduanya:

* **APR hadiah LP** yang diperoleh melalui penyediaan likuiditas; dan
* **APR hadiah dasar Farm** yang diperoleh dengan melakukan Staking LP Token di Farm.

Mengapa? Karena ketika Anda melakukan Staking LP token di sebuah farm untuk mendapatkan CAKE, Anda tetap menyediakan likuiditas ke pool likuiditas, sehingga Anda juga mendapatkan hadiah LP!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

Lalu bagaimana cara menghitung angka-angka tersebut?

### Menghitung APR Hadiah Dasar Farm

**APR Dasar Farm** dihitung berdasarkan pengali farm dan total jumlah likuiditas di farm -- ini adalah jumlah CAKE yang didistribusikan ke farm tersebut.

### Menghitung APR Hadiah LP

Selain itu, petani juga menerima **hadiah LP** atas penyediaan likuiditas. Berikut contoh perhitungan **hadiah LP**:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

Pada pasangan WBNB/BUSD di atas, kita melihat nilai-nilai berikut:

**Likuiditas:** $387,42 Juta\
**Volume 24J:** $96,97 Juta\
**Volume 7H:** $709,73 Juta

* Hitung biaya tahunan
  * Gunakan volume 24J untuk menghitung **bagian biaya** penyedia likuiditas di pool (berdasarkan struktur biaya perdagangan 0,17%):\
    $96.970.000\*0,17/100 = **$164.849**
  * Selanjutnya, gunakan **bagian biaya** tersebut untuk memperkirakan **biaya tahunan** yang diproyeksikan yang diperoleh oleh pool (berdasarkan volume 24J saat ini):\
    $164.849\*365 = **$60.169.885**
* Kita sekarang dapat menggunakan biaya tahunan untuk menghitung **APR hadiah LP:** Yaitu **biaya tahunan** dibagi **likuiditas:**\
  ($60.169.885/$387.420.000)\*100 = **15,53% APR hadiah LP**
