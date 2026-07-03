# Glosarium Perpetuals V1

**Di sini Anda akan menemukan definisi semua istilah yang terkait dengan trading berjangka**

### **Trading Perpetual**

&#x20;Perpetuals, perpetual swaps, atau perps adalah jenis kontrak berjangka khusus tanpa tanggal kedaluwarsa.



### **Leverage**

Leverage adalah mekanisme trading. Trader dapat menggunakannya untuk meningkatkan eksposur mereka ke pasar dengan memungkinkan mereka membayar kurang dari jumlah penuh investasi. Dengan kata sederhana, Anda meminjam uang untuk meng-leverage investasi Anda.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **Margin**

adalah jaminan yang Anda berikan untuk posisi Leverage Anda. Ada dua Mode untuk menggunakannya:

* Mode Cross Margin: Semua posisi cross di bawah aset margin yang sama berbagi saldo cross margin aset yang sama. Dalam kejadian Likuidasi, saldo margin penuh aset Anda beserta posisi terbuka yang tersisa di bawah aset tersebut dapat disita.
* Mode Isolated Margin: Kelola risiko Anda pada posisi individual dengan membatasi jumlah margin yang dialokasikan untuk masing-masing. Jika rasio margin suatu posisi mencapai 100%, posisi akan dilikuidasi. Margin dapat ditambahkan atau dikurangi dari posisi menggunakan mode ini.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Rasio Margin**: Rasio Margin = Margin Pemeliharaan / Saldo Margin. Posisi Anda akan dilikuidasi setelah Rasio Margin mencapai 100%.

**Rasio Pemeliharaan**: Jumlah minimum saldo margin yang diperlukan untuk menjaga posisi terbuka Anda.

**Saldo Margin** = Saldo Dompet + PNL Belum Terealisasi. Posisi Anda akan dilikuidasi setelah Saldo Margin <= Margin Pemeliharaan.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Aset:

**Setoran**: Setorkan dana Anda ke akun berjangka Anda

**Penarikan**: Tarik dana Anda dari akun berjangka Anda ke dompet Anda

**Saldo**: Saldo Dompet = Total Transfer Bersih + Total Keuntungan Terealisasi + Total Biaya Pendanaan Bersih - Total Komisi.

**PNL Belum Terealisasi**: Keuntungan dan kerugian yang belum terealisasi pada posisi ini dihitung berdasarkan Harga Mark, dan persentase imbal hasil ekuitas.

**Mode:**&#x20;

* Mode Aset Tunggal: Mendukung trading USDⓈ-M Futures hanya menggunakan aset margin tunggal dari simbol tersebut. PNL dari posisi aset margin yang sama dapat di-offset. Mendukung Mode Cross Margin dan Mode Isolated Margin.
* Mode Multi-Aset: Trading USDⓈ-M Futures di berbagai aset margin. PNL dapat di-offset di antara posisi aset margin yang berbeda. Hanya mendukung Mode Cross Margin.

{% hint style="info" %}
Catatan: Jika ada posisi terbuka atau order terbuka dalam USDⓈ-M Futures, Mode Multi-Aset tidak dapat diaktifkan. Mode Multi-Aset hanya berlaku untuk USDⓈ-M Futures. Sebelum mengaktifkan Mode Multi-Aset, harap baca panduan secara mendetail untuk mengelola risiko akun USDⓈ-M Futures dengan lebih baik saat menggunakan Mode Multi-Aset.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Order

**Beli/Long:** Buka order Long. Dalam order ini Anda membeli aset dan menunggu untuk menjual ketika harganya naik. "Beli" dan "long" digunakan secara bergantian.

**Jual/Short:** Buka order Short. Dalam order ini, Anda meminjam aset, menjualnya, dan berharap dapat membelinya kembali ketika harganya turun. "Jual" dan "short" digunakan secara bergantian.

**Limit Order:** Limit order adalah order untuk membeli atau menjual pada harga tertentu atau lebih baik. Limit order tidak dijamin untuk dieksekusi.

**Market Order:** Market order adalah order untuk membeli atau menjual pada harga terbaik yang tersedia saat ini. Dieksekusi terhadap limit order yang sebelumnya ditempatkan di order book. Saat menempatkan market order, Anda akan membayar biaya sebagai market taker.

**Stop Limit Order:** Cara termudah untuk memahami stop-limit order adalah dengan memecahnya menjadi harga stop, dan harga limit. Harga stop adalah harga yang memicu limit order, dan harga limit adalah harga limit order yang dipicu. Ini berarti bahwa begitu harga stop Anda tercapai, limit order Anda akan segera ditempatkan di order book.

**Stop Market Order:** Mirip dengan stop-limit order, stop market order menggunakan harga stop sebagai pemicu. Namun, ketika harga stop tercapai, ini memicu market order.

**Trailing Stop:** Trailing stop adalah jenis order yang dirancang untuk mengunci keuntungan atau membatasi kerugian saat perdagangan bergerak menguntungkan. Trailing stop hanya bergerak jika harga bergerak menguntungkan. Begitu bergerak untuk mengunci keuntungan atau mengurangi kerugian, ia tidak bergerak kembali ke arah lain.

**Post Only:** Mode Post-Only berarti Trader hanya dapat menempatkan Order jika akan diposting ke Order Book sebagai Maker Order. Order yang akan diposting sebagai Taker Order akan ditolak. Tidak ada Market Order yang dapat ditempatkan dan tidak ada Order yang akan terisi. Order yang menunggu dapat dibatalkan dalam mode post-only.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**Reduce Only:** Order Reduce-Only hanya akan mengurangi posisi Anda, tidak meningkatkannya.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**Instruksi TIF** memungkinkan Anda menentukan jumlah waktu order Anda akan tetap aktif sebelum dieksekusi atau kedaluwarsa. Anda dapat memilih salah satu dari opsi ini untuk instruksi TIF:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (Good Till Cancel): Order akan tetap aktif hingga terisi atau dibatalkan.&#x20;
* **IOC** (Immediate Or Cancel): Order akan dieksekusi segera (baik sepenuhnya atau sebagian). Jika hanya dieksekusi sebagian, porsi order yang tidak terisi akan dibatalkan.&#x20;
* **FOK** (Fill Or Kill): Order harus diisi sepenuhnya segera. Jika tidak, order tidak akan dieksekusi sama sekali.

