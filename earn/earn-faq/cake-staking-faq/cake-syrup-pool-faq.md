---
hidden: true
---

# FAQ CAKE Syrup Pool

## FAQ

### Berapa lama durasi kunci yang dapat kita pilih?

Anda dapat memilih antara 1-52 minggu. Mana yang Anda sukai?

### Variabel apa yang mempengaruhi persentase yield (%) CAKE Syrup Pool baru (opsi Flexible Staking dan Fixed-Term Staking)?

Karena opsi flexible staking dan fixed-term staking adalah bagian dari pool yang sama, variabel berikut mempengaruhi yield% (APR/APY) dari keduanya:

* Total CAKE yang di-stake dalam flexible staking dan fixed-term staking (jumlah keduanya). Semakin banyak CAKE yang di-stake, semakin rendah APR/APY.
* Total CAKE yang terkunci dalam fixed-term staking. Semakin banyak CAKE yang terkunci berarti semakin banyak peningkatan yield, yang menghasilkan lebih sedikit hadiah CAKE untuk orang lain (terutama flexible staking).
* Rata-rata durasi kunci dari semua CAKE yang terkunci dalam fixed-term staking. Jika rata-rata durasi kunci meningkat, APR/APY akan menurun.

### Bisakah saya memanen hadiah selama periode terkunci?

Tidak. Anda hanya dapat memanen hadiah ketika durasi kunci berakhir. Ini didasarkan pada yield/pengembalian yang kami berikan serta implementasi teknisnya.

### Bisakah saya memperpanjang durasi kunci?

Ya. Memperpanjang durasi kunci menambahkan lebih banyak waktu ke **durasi kunci awal** Anda. Saat memilih untuk memperpanjang durasi kunci, perhatikan:

Durasi kunci yang diperpanjang yang baru = durasi kunci awal + durasi yang ditambahkan

### Bisakah saya menghapus CAKE saya dari fixed-term staking melalui kontrak jika saya berubah pikiran?

Tidak. CAKE Anda tidak dapat dihapus atau ditarik dari fixed-term staking kapan pun hingga durasi kunci berakhir dan CAKE Anda terbuka.

### Apa itu jumlah "CAKE Terkunci"?

Jumlah "CAKE Terkunci" adalah saldo CAKE terkunci awal pengguna ditambah hadiah CAKE hingga saat ini.&#x20;

CAKE Terkunci = Saldo CAKE terkunci awal + Hadiah CAKE

Saat menambahkan lebih banyak CAKE ke fixed-term staking, jumlah "CAKE yang akan dikunci" adalah saldo CAKE terkunci awal pengguna, hadiah CAKE hingga saat ini, dan CAKE yang ditambahkan.

### Bisakah APR pool CAKE Fixed-Term Staking berubah setelah saya mengunci CAKE?

Ya, APR pool CAKE fixed-term staking bersifat variabel, sama seperti pool CAKE yang lama. APR pool CAKE fixed-term staking tidak tetap dan bergantung pada:

* Total CAKE yang di-stake di pool CAKE (jumlah Flexible + Fixed-Term Staking).
* Rata-rata durasi kunci dari semua CAKE yang terkunci dalam fixed-term staking.
* Peningkatan yield (mirip pengali) yang dihitung dari durasi kunci awal pengguna. Semakin lama Anda mengunci CAKE, semakin tinggi peningkatan yield.

Misalnya, jika Anda mengunci CAKE selama 52 minggu, peningkatan yield Anda akan lebih besar daripada jika Anda mengunci CAKE selama 26 minggu. Peningkatan yield meningkat secara linier seiring semakin lamanya Anda mengunci CAKE.

### Bisakah saya masih berpartisipasi dalam IFO jika CAKE saya terkunci dalam pool Fixed-Term Staking, atau saya perlu membeli lebih banyak CAKE?

Tidak, diperlukan jumlah CAKE yang terpisah. Namun, locked-staking memberikan masuk untuk penjualan publik IFO. Lihat [iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md).

### Bisakah saya memilih jika CAKE saya terkunci dalam pool Fixed-Term Staking?

Ya! Lihat [vCAKE](../../../welcome-to-pancakeswap/vecake-sunset/archive-vecake/vecake.md).

### Bisakah saya menggunakan pool CAKE Flexible Staking dan pool CAKE Fixed-Term Staking secara bersamaan?

Ya, ketika Anda melakukan fixed-term CAKE staking. Pool sampingan CAKE flexible staking akan otomatis muncul untuk Anda pilih.

### Apakah ada biaya untuk mengubah CAKE Flexible Staked menjadi CAKE Fixed-Term Staked?

Tidak. Tidak ada biaya tambahan untuk memindahkan CAKE dari flexible staking ke fixed-term staking, hanya biaya gas.

### Apa yang terjadi di akhir durasi kunci? Apa itu "After Burning"?

{% hint style="warning" %}
**After Burning akan membakar hadiah CAKE di masa depan dan hadiah CAKE yang sudah diperoleh.** Untuk menghindari kehilangan hadiah CAKE yang sudah Anda peroleh, kami menyarankan untuk memulai periode fixed-term staking baru atau mengubah CAKE Anda ke flexible staking di akhir periode staking terkunci Anda.
{% endhint %}

Ketika periode fixed-term staking Anda berakhir dan CAKE Anda terbuka, Anda memiliki 7 hari untuk menyelesaikan salah satu dari dua opsi:

* Kunci CAKE Anda untuk memulai periode fixed-term staking baru\
  atau
* Ubah CAKE yang di-stake ke flexible staking (tanpa biaya penarikan 72 jam).

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20before%20after%20burning.png)

Selama 7 hari ini, Anda masih akan mendapatkan CAKE.

Setelah 7 hari, jika Anda belum melakukan salah satu dari dua opsi, CAKE yang di-stake Anda akan memasuki apa yang disebut "After Burning". **Dengan "After Burning", hadiah CAKE Anda (termasuk hadiah yang sudah diperoleh) akan mulai dikirim untuk dibakar.** Persentase hadiah CAKE yang dikirim untuk dibakar akan meningkat secara linier dalam periode 90 hari "After Burning" hingga mencapai 100%, yang berarti semua hadiah CAKE dibakar.

Jadi, untuk menghindari kehilangan hadiah CAKE, kami menyarankan untuk memulai periode fixed-term staking baru atau mengubah CAKE Anda ke flexible staking di akhir periode staking terkunci Anda.

Berikut adalah contohnya:

> John melakukan stake 100 CAKE selama 52 minggu, ia memperoleh 50 CAKE selama periode staking-nya, dan sekarang periode staking telah berakhir.&#x20;
>
> Ia kemudian tidak melakukan tindakan apa pun, dan posisinya masuk ke mode "After Burning".
>
> Selama periode 90 hari After Burning, semua 50 CAKE yang ia peroleh akan dibakar secara bertahap bersama dengan CAKE baru yang diperoleh.&#x20;
>
> Setelah 90 hari, hadiah yang sebenarnya ia peroleh akan menjadi 0. Namun, 100 CAKE yang ia depositkan awalnya tidak akan terpengaruh.
>
> Mulailah periode fixed-term staking baru atau ubah ke flexible staking, dan jangan seperti John.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Locked%20-%20lock%20ended%20-%20after%20burning%20started.png)
