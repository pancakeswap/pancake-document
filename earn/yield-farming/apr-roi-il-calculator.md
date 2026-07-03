# Kalkulator APR/ROI/IL

Dalam V3 Liquidity dan Farm, dengan likuiditas non-fungible yang baru dan kemampuan rentang harga yang dapat disesuaikan. Setiap posisi LP akan memiliki APR biaya LP dan APR farming CAKE-nya sendiri.

Untuk membuat penyediaan likuiditas lebih lancar dan tidak terlalu rumit, tampilan APR otomatis baru dengan kalkulator ROI yang sepenuhnya baru tersedia untuk digunakan kapan pun Anda menyediakan likuiditas atau melakukan farming.

## Tampilan dan perhitungan APR otomatis <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

Ketika Anda menyediakan likuiditas, tampilan APR otomatis bereaksi terhadap perubahan konfigurasi Anda dan menghitung APR berdasarkan pengaturan Anda.

Sebagai contoh, dalam kebanyakan kasus, jika Anda mempersempit pengaturan rentang harga, APR akan naik.

Harap diperhatikan untuk APR biaya LP:

* Perkiraan jumlah hadiah biaya LP bervariasi berdasarkan tingkatan biaya yang dipilih; hadiah biaya memerlukan klaim dan compounding secara manual.
* Angka APR dihitung menggunakan volume perdagangan historis, yang bergantung pada Subgraph dan mungkin mengalami keterlambatan pengindeksan.

Untuk APR farming:

* Perkiraan jumlah hadiah CAKE didasarkan pada emisi CAKE langsung ke farm. Angka tersebut dapat berubah berdasarkan penyesuaian emisi di masa mendatang.

{% hint style="info" %}
Angka-angka dihitung pada tingkat dan kondisi pool saat ini dan dapat berubah berdasarkan berbagai variabel eksternal. Angka-angka tersebut adalah estimasi yang disediakan hanya untuk kemudahan Anda, dan sama sekali tidak mewakili pengembalian yang dijamin.
{% endhint %}

Anda dapat menemukan tampilan APR ini di:

* Halaman "Add Liquidity" - menampilkan APR biaya LP
* Halaman detail setiap posisi likuiditas yang ada - menampilkan APR biaya LP\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* Halaman Farm, dalam posisi di bawah setiap farm - menampilkan APR gabungan dengan biaya LP dan hadiah CAKE\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## Kalkulator ROI yang disempurnakan <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

Setiap kali Anda melihat tampilan APR otomatis, Anda dapat mengkliknya untuk membuka kalkulator ROI yang baru. Kalkulator ROI baru telah dirancang ulang dengan beberapa fitur tambahan untuk memenuhi kebutuhan penyediaan likuiditas terkonsentrasi V3 dan farming.

Mari kita bahas setiap bagian bersama-sama:

### Jumlah Deposit, "Staked For" dan "Compounding Every" <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Ketiganya adalah input dasar, yang juga terdapat di kalkulator ROI sebelumnya. Fungsinya untuk menentukan:

1. Berapa banyak aset yang disediakan ke posisi likuiditas, dalam USD.
2. Berapa lama aset tersebut akan di-stake di posisi tersebut.
3. Seberapa sering Anda akan melakukan compounding hadiah kembali ke posisi.



⓵ **Jumlah Deposit**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

Anda dapat memasukkan jumlah dalam USD secara manual, atau menggunakan tombol tindakan cepat untuk mengisi $100, $1.000, atau jumlah maksimum yang diizinkan berdasarkan saldo token di dompet Anda.



⓶ **Durasi Stake**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

Anda dapat memilih berapa lama aset di-stake dalam posisi likuiditas dengan memilih antara: 1 hari, 7 hari, 30 hari, 1 tahun, dan 5 tahun.

Jumlah pengembalian akan dihitung berdasarkan durasi staking Anda.



⓷ **Compounding**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

Anda dapat memilih seberapa sering Anda akan melakukan panen hadiah yang dihasilkan oleh posisi, dan melakukan compounding kembali ke posisi. Anda dapat memilih antara: 12 jam, 1 hari, 7 hari, dan 30 hari.

Jumlah pengembalian dan APY akan dihitung berdasarkan pilihan Anda. Jika Anda tidak berencana untuk melakukan compounding posisi Anda, hilangkan centang pada kotak di sebelah kiri.

{% hint style="info" %}
Dalam V3, biaya LP dan CAKE yang diperoleh harus dipanen dan di-compound secara manual.
{% endhint %}

### &#x20;⓸ Harga Historis <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

Ini adalah bagian hanya-tampilan untuk merujuk pergerakan harga historis dari pasangan yang dipilih.

Anda dapat merujuk pergerakan harga historis dalam berbagai rentang waktu, seperti seberapa besar harga biasanya berfluktuasi, lalu menemukan pengaturan rentang harga yang cocok untuk menyeimbangkan antara APR yang lebih tinggi dan risiko impermanent loss yang lebih rendah.

* MIN - harga minimum
* MAX - harga maksimum
* AVG - harga rata-rata
* CURRENT - harga saat ini

{% hint style="info" %}
Grafik harga hanya menggunakan data dari pasangan V3 aktual. Oleh karena itu data harga sebelum penerapan V3 tidak tersedia. Empat metrik harga mewakili rentang waktu yang dipilih saat ini dan akan berubah berdasarkan pilihan.
{% endhint %}

### ⓹ Rentang Harga <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

Menggunakan bagian ini, Anda dapat memeriksa berapa banyak likuiditas yang telah didepositkan ke berbagai rentang harga, dan menentukan serta mengatur rentang harga yang Anda sediakan likuiditas.

Anda dapat menemukan grafik distribusi di bawah judul. Semakin besar jumlah likuiditas, semakin tinggi grafik tersebut.

Anda dapat mengubah pengaturan rentang harga Anda dengan:

* Menyeret dua pengendali pada grafik untuk meningkatkan atau mengurangi batas harga minimum dan maksimum.
* Menggunakan ruang di antara dua pengendali untuk menggeser rentang yang dipilih.
* Mengklik tombol + dan - pada kolom harga min dan maks.
* Mengklik angka di kolom harga dan memasukkannya secara manual.

Jika Anda ingin menavigasi grafik distribusi:

1. Gunakan tombol pembesar plus dan minus untuk memperbesar dan memperkecil tampilan
2. Seret sumbu X (bawah) untuk menggeser ke kiri dan ke kanan

Jika Anda ingin menyediakan likuiditas ke seluruh rentang harga, klik "Full Range"

### ⓺ Balik arah harga untuk melihat harga dengan basis berbeda <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

Untuk beberapa pasangan token, lebih mudah dan lebih intuitif untuk melihat harga dengan token basis tertentu. Misalnya, untuk pasangan BNB/USDT, kebanyakan orang lebih suka melihat harga dalam "berapa USDT per BNB" daripada sebaliknya.

Anda dapat dengan mudah membalik tampilan harga. Cukup klik tombol setelah "View prices in:" untuk beralih basis antara dua token dalam pasangan tersebut.

### ⓻ Impor dan ekspor (terapkan) pengaturan Anda <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

Ketika Anda membuka kalkulator ROI di jendela "Add Liquidity", atau dengan melihat posisi yang sudah ada, pengaturan berikut akan diimpor secara otomatis sehingga Anda tidak perlu mengaturnya lagi:

1. Jumlah aset yang Anda depositkan
2. Rentang harga
3. Tingkatan biaya yang dipilih

Setelah selesai mengonfigurasi di kalkulator ROI, Anda dapat mengklik "Apply Settings" untuk langsung menerapkan pengaturan dari kalkulator ke jendela "Add Liquidity" sehingga Anda tidak perlu menyesuaikannya secara manual.

### ⓼ Hitung hadiah farming dan APR <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

Hadiah farming akan disertakan dalam perhitungan jika Anda membuka kalkulator ROI di halaman "Farm".

Anda dapat memperluas bagian detail untuk melihat rincian hadiah.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
