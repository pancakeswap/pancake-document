# Shared Inventory Hook

Shared Inventory Hook (SIH) resmi PancakeSwap dirancang agar satu pool modal dapat melakukan market-making di setiap pool yang menggunakan token yang sama, alih-alih mengunci likuiditas terpisah di masing-masing pool. Hook ini memberi trader kuotasi yang lebih dalam dan price impact yang lebih rendah, sekaligus memungkinkan penyedia likuiditas menggunakan modal lebih sedikit untuk cakupan yang sama.

Dibangun oleh tim inti PancakeSwap, hook ini dirancang khusus untuk penerbit aset dan market maker yang ingin mengkuotasikan beberapa pasangan di on-chain tanpa memecah inventaris mereka.

#### 🔍 Mengapa Shared Inventory?

Menyediakan likuiditas untuk beberapa pasangan dengan cara konvensional berarti mengunci modal khusus di pool yang terpisah, yang sebagian besar menganggur di antara transaksi. SIH sebaliknya menyimpan satu saldo per token dan menyuntikkannya sebagai likuiditas hanya ketika swap membutuhkannya, sehingga modal yang sama dapat mendukung setiap pool yang menggunakan token tersebut.

#### 📊 Apa Bedanya dengan Model Lain?

Likuiditas terkonsentrasi konvensional mengharuskan seluruh pokok modal ditempatkan di satu pool. Pendekatan lintas pool lainnya, seperti lapisan settlement virtual-balance, umumnya berada di luar AMM itu sendiri, sehingga likuiditasnya mungkin tidak terlihat sebagai kedalaman pool on-chain dan tidak dirutekan langsung oleh aggregator.

Likuiditas SIH masuk dan keluar dari pool PancakeSwap Infinity CLAMM melalui hook pada setiap swap, sehingga muncul sebagai kedalaman pool yang sesungguhnya yang dapat dilihat dan diisi oleh router.

#### ⚙️ Cara Kerjanya

* **Injeksi just-in-time (JIT)**\
  Sebelum setiap swap, hook mencetak posisi likuiditas terkonsentrasi yang dikonfigurasi ke dalam pool; setelah swap dieksekusi, hook membakarnya dan menyelesaikan hasil bersihnya. Posisi tersebut hanya ada selama satu swap, sehingga saldo bebas melayani pool berikutnya yang membutuhkannya.
* **Satu saldo, banyak pool**\
  Inventaris adalah saldo token milik hook itu sendiri, tidak ada setoran per pool. Token apa pun yang digunakan di lebih dari satu pool dibagikan ke semuanya.

{% hint style="success" %}
Hal ini memisahkan kedalaman yang dikuotasikan pool dari modal yang dipegang langsung di dalam pool: hook yang didanai dapat mengkuotasikan likuiditas yang dalam dan rapat di sejumlah pool yang menggunakan token yang sama.
{% endhint %}

* **Hook yang dapat dikonfigurasi**\
  Untuk setiap pool yang dilayaninya, hook memiliki konfigurasi independen yang dapat disesuaikan untuk rentang harga dan kedalaman. Menggeser rentang hanya memerlukan pembaruan konfigurasi, sehingga mudah memusatkan ulang kuotasi di sekitar harga referensi yang bergerak.

#### 📌 Poin Utama

* Satu saldo token bersama mendukung setiap pool yang menggunakan token tersebut. Menambahkan pool baru tidak memerlukan pokok modal baru.
* Sepenuhnya on-chain dan composable: likuiditas SIH adalah kedalaman pool yang nyata, dapat dirutekan oleh PancakeSwap maupun aggregator pihak ketiga.
* Trader mendapatkan kuotasi yang lebih dalam dan price impact yang lebih rendah pada ukuran besar; operator memperoleh trading fee yang sama dengan sebagian kecil dari modal konvensional.
