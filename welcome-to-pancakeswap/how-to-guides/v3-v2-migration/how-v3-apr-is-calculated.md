# Cara Menghitung APR v3

{% hint style="info" %}
Di Likuiditas dan Farm v3, dengan Likuiditas non-fungible baru dan kemampuan rentang harga yang dapat dikustomisasi, setiap posisi LP akan memiliki biaya LP dan APR farming CAKE tersendiri.
{% endhint %}

Total APR merupakan gabungan dari APR biaya LP dan APR hadiah CAKE

### Biaya LP

Secara teoritis, dengan rentang harga dan Likuiditas yang akan ditambahkan pengguna, kita dapat memperkirakan ekspektasi biaya 7 hari ke depan sebagai berikut&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Jumlah biaya yang terkumpul dalam rentang harga yang ditentukan pengguna selama 7 hari terakhir
* $$L_{in}$$: Likuiditas saat ini dalam rentang harga yang ditentukan pengguna
* $$\Delta{L}$$: Likuiditas yang ingin ditambahkan pengguna ke rentang harga

#### Biaya dalam rentang

Untuk $$fee_{in}$$, kami menggunakan data volume Trading historis, tingkat biaya, dan data harga historis untuk memperkirakan harga dalam rentang

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Tingkat biaya
* $$V_{7d}$$: Total volume Trading selama 7 hari terakhir
* $$T_{in}$$: Durasi, diukur dalam detik, harga berada dalam rentang harga selama 7 hari terakhir
* $$T_{7d}$$: 7 hari diukur dalam detik

### APR Cake

#### Alokasi Pool

Total hadiah cake per detik di MC v3 menggunakan upkeep dan dapat diturunkan dari `latestPeriodCakePerSecond`&#x20;

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

Pada setiap pool, kita dapat menggunakan `poolInfo` untuk mendapatkan `poolWeight` dengan membagi `poolInfo.allocPoint / totalAllocPoint`

#### APR Cake Global

APR global dihitung menggunakan total jumlah Likuiditas aktif & yang di-stake dengan emisi hadiah CAKE pool.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD` mewakili Likuiditas aktif yang di-stake pada pool saat ini dalam USD, yang terdiri dari semua tick posisi dalam rentang yang di-stake di MasterChef v3.

#### APR Cake Posisi

APR untuk posisi individual dapat bervariasi tergantung pada pengaturan rentang harga mereka.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: Hadiah CAKE yang diperoleh dalam USD per tahun di pool
* $$USD_p$$: Total nilai USD dalam posisi
* $$L_{p}$$: Likuiditas posisi
* $$L_{lm}$$: Total Likuiditas staking yang dilacak oleh LMPool
