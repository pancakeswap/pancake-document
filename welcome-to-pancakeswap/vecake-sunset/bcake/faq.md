# FAQ

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### Bagaimana pengganda bCAKE dihitung?

Anda mungkin menyadari bahwa Anda mendapatkan pengganda boost bCAKE yang berbeda saat melakukan staking di farm yang berbeda.

Hal tersebut karena pengganda bCAKE - Farm Booster dihitung menggunakan metrik berikut saat aktivasi atau penyegaran:

* `userLpBalanceInFarm` : Jumlah likuiditas yang Anda stake di farm.&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm` : Total jumlah likuiditas yang di-stake di farm atau jumlah likuiditas aktif saat ini di V3 LP pool. bCAKE akan memilih angka yang lebih kecil di antara keduanya.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)` : Jumlah veCAKE yang Anda miliki secara real-time
* `veCAKE.totalSupply` : Total pasokan veCAKE secara real-time

Pengganda dihitung menggunakan metode berikut:

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` dan `constantB` ditetapkan oleh kitchen dan dapat disesuaikan di masa mendatang berdasarkan umpan balik komunitas dan kondisi pasar. `constantB` bervariasi antara farm yang berbeda untuk mengkompensasi perbedaan harga LP.

`constantA` dan `constantB` dapat diambil melalui:

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

Tetapi:

{% hint style="info" %}
**TL;DR**

Semakin banyak LP (likuiditas) yang ingin Anda tingkatkan

Semakin banyak CAKE yang perlu Anda kunci untuk durasi yang lebih lama
{% endhint %}

### Mengapa pengganda saya berubah bahkan setelah aktivasi?

Harap diperhatikan bahwa **setiap tindakan pengguna pada posisi farming atau CAKE staking pool akan secara otomatis memperbarui pengganda boost Anda** berdasarkan data dan statistik terbaru dari farm dan CAKE staking pool, termasuk namun tidak terbatas pada:

* Stake/Unstake posisi ke/dari farm
* Panen hadiah CAKE dari farm
* Perpanjang durasi Staking CAKE Anda
* Tambahkan lebih banyak CAKE ke posisi staking jangka tetap Anda
* Konversi posisi CAKE staking Anda ke fleksibel

{% hint style="warning" %}
Harap diperhatikan:&#x20;

Untuk memastikan keadilan dan mencegah potensi penyalahgunaan menggunakan data yang kedaluwarsa. Farm booster dirancang untuk bersifat tanpa izin dan tata kelola komunitas. Oleh karena itu, **siapa pun** dapat memanggil fungsi `updateLiquidity(address _tokenId)` pada kontrak MasterChef V3 untuk menyegarkan pengganda boost siapa pun menggunakan data terbaru.

Selain itu, kitchen juga akan memantau semua posisi farming yang diaktifkan bCAKE dan akan menyegarkan posisi mana pun dengan pengganda yang sudah kedaluwarsa.
{% endhint %}

### Mengapa saya tidak dapat meningkatkan sebuah posisi

1. Farm booster hanya tersedia untuk farm tertentu. Lebih banyak farm akan tersedia di masa mendatang. Untuk saat ini, **cari angka APR berwarna hijau dengan ikon roket hijau.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. Karena melibatkan beberapa kontrak, beberapa interaksi kontrak memerlukan sedikit lebih banyak token gas (BNB). Pastikan Anda memiliki cukup BNB di dompet Anda. Jika kesalahan terus berlanjut, coba tingkatkan batas gas transaksi secara manual.

### Berapa Pengganda Boost bCAKE maksimum yang dapat saya dapatkan?

Saat ini, boost maksimum yang dapat diperoleh pengguna untuk farm booster adalah 2,5x, yang memberikan mereka 2,5x APR asli.

Harap diperhatikan bahwa boost maksimum yang dapat Anda dapatkan bervariasi antara jenis likuiditas yang Anda coba stake:

* V3: maks 2x
* V2, StableSwap: maks 2,5x
* Position Manager: maks 2,5x

### Bagaimana cara meningkatkan Pengganda Boost bCAKE saya?

* Tambahkan lebih banyak CAKE ke posisi Staking veCAKE
* Perpanjang atau perbarui durasi posisi Staking veCAKE Anda

Secara sederhana:

**Stake lebih banyak CAKE, stake lebih lama**

[Pelajari lebih lanjut tentang cara pengganda boost bCAKE dihitung](faq.md#how-are-the-bcake-multipliers-calculated).

### Dari mana hadiah CAKE yang ditingkatkan berasal?

**Tenang, tidak ada emisi tambahan yang dialokasikan untuk membuat bCAKE dapat berfungsi.**

Mirip dengan veCAKE CAKE staking. bCAKE meningkatkan bagian individu pengguna terhadap pengguna lain.

Meskipun APR dasar mungkin turun setelah penerapan bCAKE. Tim Chefs percaya ini adalah pertukaran yang baik karena menguntungkan pecinta CAKE yang setia dengan meningkatkan hasil farming mereka, menciptakan lebih banyak permintaan untuk CAKE, dan berfungsi sebagai insentif yang bagus untuk Staking CAKE.

### Mengapa pengganda yang saya terima rendah?&#x20;

bCAKE - farm booster bekerja dengan mengevaluasi posisi Staking veCAKE Anda dan posisi liquidity farming Anda terhadap pengguna lain. Secara sederhana:

> Jika pengguna ingin meningkatkan lebih banyak likuiditas di farm, mereka harus mengunci lebih banyak CAKE untuk durasi yang lebih lama di pool.

Desain ini memastikan manfaatnya tidak hanya ditawarkan kepada pemegang besar, tetapi kepada pengguna mana pun yang memiliki posisi Staking CAKE yang cukup besar dibandingkan dengan posisi farmingnya.

Pelajari lebih lanjut tentang cara pengganda dihitung [di sini](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated).

### Mengapa hanya ada x jumlah farm yang tersedia untuk booster?

Karena bCAKE melibatkan pembaruan salah satu produk inti PancakeSwap, yaitu liquidity farming. Tim Chefs ingin mengambil pendekatan yang lebih lambat dan lebih stabil dalam peluncuran.

Oleh karena itu, pada fase rilis produk awal. Banyak parameter yang sangat konservatif. Termasuk jumlah farm yang dapat di-boost pengguna, farm mana yang dapat di-boost pengguna, serta parameter kesulitan dalam menerima pengganda boost.

**Tim Chefs akan menyesuaikan parameter berdasarkan umpan balik komunitas.**

### **Apakah bCAKE V3 telah diaudit?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE telah diaudit oleh auditor internal maupun eksternal.

Lihat laporan audit di sini: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
