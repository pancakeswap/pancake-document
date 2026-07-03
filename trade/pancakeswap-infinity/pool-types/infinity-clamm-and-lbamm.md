# Infinity CLAMM & LBAMM

#### 🔷 CLAMM (Concentrated Liquidity AMM)

CLAMM memungkinkan penyedia likuiditas untuk mengalokasikan modal mereka dalam **rentang harga tertentu**. Hal ini menghasilkan:

* **Efisiensi modal yang lebih tinggi**: Lebih banyak likuiditas pada harga trading aktif.
* **Likuiditas yang lebih dalam**: Eksekusi yang lebih baik bagi para trader.
* **Manajemen LP aktif**: LP perlu menyesuaikan posisi seiring pergerakan harga.
* **Potensi impermanent loss yang lebih tinggi** untuk posisi di luar rentang.

{% hint style="info" %}
CLAMM beroperasi pada formula constant product (X \* Y = K). Setiap posisi likuiditas bersifat non-fungible dan direpresentasikan sebagai NFT.
{% endhint %}

#### 🔷 LBAMM (Liquidity Book AMM atau "Bin Pool")

LBAMM mengimplementasikan **bin harga diskrit**, masing-masing menampung likuiditas pada tingkat harga tertentu. LBAMM mengikuti **formula constant sum (X + Y = K).**



**Karakteristik utama:**

* Perdagangan dengan **dampak harga 0** dalam sebuah bin.
* **Likuiditas fungible** (likuiditas dalam setiap bin adalah token ERC-20).
* **Biaya gas lebih rendah** untuk menyesuaikan posisi LP.
* **Dukungan untuk berbagai bentuk likuiditas** (misalnya, miring, seragam).
* Lebih cocok untuk pasangan **volatilitas rendah** karena kurva penetapan harga yang datar per bin.

> 🥞 **PancakeSwap adalah protokol pertama yang menawarkan pool LBAMM dengan hooks.**

{% hint style="success" %}
Pool CLAMM dan LBAMM keduanya mendukung **hooks**, yang memungkinkan pengembang untuk menyesuaikan perilaku pool. Jenis pool dapat diperluas melalui Pool Manager baru, yang dapat ditambahkan tanpa redeployment protokol.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Fitur</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Kurva Penetapan Harga</strong></td><td>Constant Product (X * Y = K)</td><td>Constant Sum (X + Y = K)</td></tr><tr><td><strong>Token Likuiditas</strong></td><td>Non-fungible (NFT)</td><td>Fungible (ERC-20 per bin)</td></tr><tr><td><strong>Terbaik Untuk</strong></td><td>Pasangan volatilitas tinggi/rendah</td><td>Pasangan volatilitas rendah</td></tr><tr><td><strong>Keunggulan</strong></td><td><ol><li>Efisiensi modal</li><li>Hemat gas dalam rentang lebar/penuh</li><li>Diadopsi secara luas</li></ol></td><td><ol><li>Dampak harga 0 dalam bin</li><li>Manajemen LP lebih murah</li><li>Bentuk likuiditas fleksibel</li></ol></td></tr><tr><td><strong>Dukungan Hook</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Biaya

PancakeSwap Infinity mendukung sistem biaya yang fleksibel dan dapat diperluas melalui pengaturan biaya Statis dan Dinamis. Pengaturan ini memberikan alat yang powerful kepada pembuat pool dan LP untuk mengoptimalkan berbagai strategi trading dan profil risiko.

#### 🔁 Biaya Dinamis

* Biaya Dinamis ditentukan secara real-time melalui kontrak hook.
* Biaya ini dapat berfluktuasi berdasarkan faktor eksternal seperti volatilitas, volume trading, status pengguna (misalnya, kepemilikan CAKE), atau logika kustom apa pun yang dikodekan ke dalam hook.
* Pool dengan biaya dinamis harus mengaktifkan pengaturan ini pada saat pembuatan pool dan melampirkan hook yang mampu memodifikasi biaya melalui `beforeSwap`.
* Setelah pool diinisialisasi, jenis biaya (dinamis atau statis) tidak dapat diubah.

Biaya dinamis menawarkan fleksibilitas maksimum dan mengoptimalkan struktur biaya untuk LP maupun pengguna Swap berdasarkan kondisi pasar.

#### 📌 Biaya Statis

* Pool Biaya Statis memiliki biaya tetap yang ditetapkan saat pembuatan pool.
* Biaya ini tidak dapat diubah setelah pool diinisialisasi.
* Cocok untuk kasus penggunaan yang lebih sederhana atau di mana prediktabilitas struktur biaya penting.<br>

**🔒 Batas Biaya Maksimum:**

* Pool CLAMM: Hingga 100% (terutama untuk kasus penggunaan yang terspesialisasi atau eksperimental)
* Pool LBAMM: Dibatasi hingga 10%<br>

**🏛 Biaya Protokol (untuk pool biaya statis):**

* PancakeSwap menerapkan biaya protokol pada pool Infinity
* 33% dari biaya LP, dibatasi hingga 0,4%

| **Biaya LP**       | **Biaya Protokol** |
| ------------------ | ------------------ |
| 1%                 | 0,33%              |
| 2%                 | 0,4% (dibatasi)    |
| Pool Biaya Dinamis | 0%                 |

#### 🛠️ Catatan Pengaturan untuk Pembuat Pool

* Saat menginisialisasi pool melalui PoolManager, pembuat harus memilih:
  * Apakah pool menggunakan biaya statis atau dinamis
  * Apakah kontrak hook dilampirkan (diperlukan untuk biaya dinamis)

Pengaturan ini bersifat permanen dan menentukan bagaimana pool berperilaku sepanjang masa hidupnya.
