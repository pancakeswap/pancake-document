# FAQ & Pemecahan Masalah Syrup Pool

## Pemecahan Masalah

### **Saya tidak dapat menemukan Syrup Pool tempat saya melakukan staking!**

Anda seharusnya dapat menemukan Syrup Pool di bawah tab "Finished" pada halaman Syrup Pools.&#x20;

Dengan memilih "Staked Only", akan lebih mudah untuk menemukan aset Anda.

### **Mengapa saya tidak bisa melakukan unstake token dari Syrup Pool?**

Jika Anda tidak dapat melakukan unstake dari pool Stake Cake, Earn CAKE, pastikan Anda belum menjual token SYRUP di dompet Anda. Token ini berfungsi sebagai \`bukti kepemilikan\` atas CAKE Anda di pool CAKE Manual.&#x20;

### **Mengapa token yang diperoleh menjadi nol setelah staking/unstaking?**

Jangan khawatir! Token tersebut sudah ada di dompet Anda.

Setiap kali Anda melakukan stake atau unstake dari Syrup Pool atau farm, token yang diperoleh akan dipanen dan dikirim ke dompet Anda secara bersamaan.

## **Pertanyaan Umum**

### Bagaimana APR untuk Syrup Pools dihitung?

> APR Syrup Pool = Hadiah yang dianualisasikan (USD) / Dana pengguna yang di-stake di Syrup Pool (USD) \* 100

Sebagai contoh dasar, mari kita ambil pool 60 hari dengan hadiah senilai 300.000 USD, dan CAKE senilai 3.000.000 USD yang di-stake di dalamnya.

APR berfluktuasi seiring lebih banyak CAKE yang di-stake oleh pengguna, dan seiring perubahan harga CAKE dan token hadiah.

|                                                       | **Perhitungan**                   | Jumlah                                     |
| ----------------------------------------------------- | --------------------------------- | ------------------------------------------ |
| Total hadiah yang akan didistribusikan (nilai USD)    |                                   | 300.000 USD                                |
| Periode distribusi                                    |                                   | 60 hari                                    |
| Distribusi harian                                     | 300.000 / 60 =                    | 5.000 USD per hari                         |
| **Hadiah yang dianualisasikan (nilai USD)**           | 5.000 \* 365 =                    | **1.825.000 USD**                          |
| **Nilai CAKE yang di-stake pengguna di pool (USD)**   |                                   | **3.000.000 USD**                          |
| **APR**                                               | (1.825.000 / 3.000.000) \* 100 =  | <p></p><p><strong>60,833% APR</strong></p> |

### **Apa yang dimaksud dengan angka "End" pada Syrup Pool saya?**

Ini menunjukkan jumlah blok yang tersisa hingga hadiah untuk pool tersebut berhenti didistribusikan. Setelah pool mencapai blok tersebut, Anda harus melakukan unstake token Anda, karena Anda tidak akan menerima hadiah apa pun setelah itu.

### **Dari mana hadiah Syrup Pools berasal?**

Ada tiga jenis utama Syrup Pools.

1. Stake CAKE, dapatkan CAKE
2. Stake CAKE, dapatkan token lainnya.&#x20;
3. Stake token lain, dapatkan CAKE

Hadiah untuk Syrup Pools "Stake CAKE, dapatkan CAKE" berasal dari [emisi CAKE](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics). Setiap blok, sejumlah token CAKE dialokasikan sebagai hadiah untuk pool-pool ini.

Hadiah untuk jenis "Stake CAKE, dapatkan token lain" disediakan oleh tim proyek yang mensponsori Syrup Pool.

Untuk jenis "Stake token lain, dapatkan CAKE", treasury PancakeSwap membeli kembali CAKE dari pasar untuk didistribusikan sebagai hadiah. Pool-pool ini didanai oleh PancakeSwap, bukan oleh proyek itu sendiri.

### Apa itu Token SYRUP?

Token SYRUP PancakeSwap didepositkan ke dompet Anda saat Anda berinteraksi dengan Syrup Pool **Manual** "Stake CAKE, Earn CAKE". Token ini tidak di-stake untuk&#x20;

Ini pada dasarnya adalah IOU yang menunjukkan berapa banyak CAKE yang Anda stake di pool.

Token ini akan dikembalikan secara otomatis saat Anda melakukan unstake CAKE dari pool tersebut.

{% hint style="warning" %}
Jangan menjual token SYRUP Anda! Anda perlu mengembalikan SYRUP untuk melakukan unstake CAKE dari pool CAKE Manual. Jumlah SYRUP yang Anda kembalikan harus sama dengan jumlah CAKE yang Anda unstake.
{% endhint %}
