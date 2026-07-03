# 🌊 Pool Likuiditas

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#id-03e94594-5a75-4687-b260-0dc69574b953" id="id-03e94594-5a75-4687-b260-0dc69574b953"></a>

Di Exchange V3 yang baru, Likuiditas akan dikelola dalam bentuk posisi non-fungible. Anda tetap akan mendapatkan bagian dari biaya selama menyediakan Likuiditas.

Saat Anda menambahkan token ke Pool Likuiditas, Anda akan menerima token NFT Penyedia Likuiditas dan mendapat bagian dari biaya.

### **Posisi likuiditas non-fungible**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28238%29.png" alt=""><figcaption></figcaption></figure>

Di v3, penyedia Likuiditas kini memiliki kontrol lebih besar atas rentang harga yang ingin mereka gunakan untuk menempatkan Likuiditas mereka. Jadi, saat Anda menambahkan token ke Pool Likuiditas di v3, Anda akan membuat posisi likuiditas non-fungible baru dengan pengaturan uniknya sendiri.

Oleh karena itu, di v3, posisi Likuiditas adalah NFT. Harap dicatat bahwa NFT ini dapat dipindahtangankan, dan NFT tersebut mewakili kepemilikan atas aset yang mendasarinya serta biaya Trading yang diperolehnya.

Di v3, biaya Trading tidak lagi secara otomatis digabungkan ke dalam posisi. Anda dapat mengklaimnya secara manual di setiap halaman detail posisi.

Anda dapat menukarkan dana Anda kapan saja dengan menghapus Likuiditas Anda.

### **Likuiditas aktif dan rentang harga**

Di v3, penyedia Likuiditas dapat mengonfigurasi posisi mereka agar hanya menyediakan Likuiditas saat harga berada dalam rentang tertentu. Jika harga Trading bergerak keluar dari rentang tersebut, posisi hanya akan terdiri dari satu jenis token dalam pasangan dan menjadi tidak aktif.

Posisi Likuiditas yang tidak aktif tidak akan berpartisipasi dalam Trading atau mendapatkan biaya Trading apa pun.

### **Likuiditas terkonsentrasi**

Di v3, karena penyedia Likuiditas dapat mengonsentrasikan setoran token mereka untuk menyediakan Likuiditas hanya dalam rentang harga tertentu. Dengan jumlah aset yang sama, v3 dapat mendukung perdagangan yang jauh lebih besar.

Hal ini menghasilkan tingkat Likuiditas relatif yang jauh lebih tinggi dibandingkan dengan v2. Dan penyedia Likuiditas dapat menghasilkan lebih banyak biaya Trading dengan modal yang sama.

Berikut contohnya:

> Baller dan Claire keduanya menyediakan Likuiditas di pool CAKE/USDT dengan aset token senilai $1.000 USD. Harga CAKE saat ini adalah 5 USDT.
>
> Mirip dengan PancakeSwap v2, Baller menyediakan Likuiditasnya di seluruh rentang harga. Oleh karena itu dia menyetorkan semua modalnya, 500 USDT dan 100 CAKE.
>
> Claire memanfaatkan fitur Likuiditas terkonsentrasi baru di PancakeSwap v3 dan membuat posisi dengan rentang harga 2 hingga 12,5 USDT per CAKE. Dia menyetorkan 185 USDT dan 37 CAKE, senilai total $370. Dia sekarang dapat menggunakan sisa $630 di tempat lain, seperti mengunci CAKE di Syrup Pool untuk menikmati hasil CAKE yang tinggi sambil mendapatkan serangkaian manfaat ekosistem PancakeSwap.
>
> Selama CAKE tetap dalam rentang harga 2 hingga 12,5, baik Baller maupun Claire akan mendapatkan jumlah imbalan biaya Trading yang sama sementara Claire menyetorkan jauh lebih sedikit modal ke Pool Likuiditas.

### **Biaya Trading**&#x20;

Menyediakan Likuiditas memberi Anda imbalan dalam bentuk biaya Trading ketika orang menggunakan Pool Likuiditas Anda untuk menyelesaikan Swap.

Setiap kali seseorang melakukan Trading di PancakeSwap, untuk setiap hop (Swap) di setiap Pool Likuiditas Exchange V3, tergantung pada tingkatan biaya Pool Likuiditas, trader membayar biaya mulai dari 0,01% hingga 1%. Tarif biaya dan rincian biaya ditampilkan sebagai berikut:

<details>

<summary>Biaya Trading (EVM)</summary>

| Komponen Biaya / Tingkatan Biaya | 0,01% | 0,05% | 0,25% | 1%  |
| -------------------------------- | ----- | ----- | ----- | --- |
| Penyedia Likuiditas              | 67%   | 66%   | 68%   | 68% |
| Pembakaran CAKE                  | 15%   | 15%   | 23%   | 23% |
| Treasury                         | 18%   | 19%   | 9%    | 9%  |

Sebagai contoh, di pool dengan tingkatan biaya 0,25%:

* Di antara semua posisi Likuiditas aktif (dalam rentang), terdapat total 10 CAKE dan 10 BNB token.
* Seseorang menukar 1 CAKE dengan 1 BNB.
* Orang lain menukar 1 BNB dengan 1 CAKE.
* Penyedia Likuiditas yang berada dalam rentang dan menyediakan Likuiditas aktif mendapatkan total 0,0017 CAKE dan 0,0017 BNB dari perdagangan tersebut.
* Posisi dengan rentang harga yang tidak mencakup harga saat ini, sehingga tidak aktif, tidak akan berkontribusi pada Trading atau mendapatkan biaya apa pun.

</details>

<details>

<summary><strong>Biaya Trading (Solana)</strong></summary>

**Tingkatan Biaya Pool CLMM V3 yang Tersedia:**\
0,01%, 0,02%, 0,03%, 0,04%, 0,05%, 0,1%, 0,15%, 0,16%, 0,18%, 0,2%, 0,25%, 0,4%, 0,6%, 0,8%, 1%, 2%, 3%, 4%

**Catatan:** **Distribusi biaya tetap sama** di semua tingkatan biaya.

| Komponen Biaya                        | % dari Total Biaya Swap | Deskripsi                                                                    |
| ------------------------------------- | ----------------------- | ---------------------------------------------------------------------------- |
| **LP (Penyedia Likuiditas)**          | 84%                     | Diperoleh oleh LP yang menyediakan Likuiditas dalam rentang harga aktif      |
| **Pembakaran**                        | 8%                      | Dihapus secara permanen untuk mengurangi pasokan CAKE                        |
| **Treasury**                          | 8%                      | Dialokasikan ke treasury protokol PancakeSwap                                |

**Contoh: Distribusi Biaya di Pool CAKE/SOL 0,25%**

1. **Pengaturan Pool:** Total Likuiditas aktif: 10 CAKE dan 10 SOL (posisi dalam rentang).
2. **Swap Terjadi:**
   * Pengguna A menukar 1 CAKE → 1 SOL.
   * Pengguna B menukar 1 SOL → 1 CAKE.
3. **Total Biaya yang Dikumpulkan:**
   * 0,25% per perdagangan × 2 perdagangan = **0,005 CAKE + 0,005 SOL**.
4. **Distribusi Biaya:**
   * **84% ke LP:** 0,0042 CAKE + 0,0042 SOL
   * **8% untuk Pembakaran:** 0,0004 CAKE + 0,0004 SOL
   * **8% ke Treasury:** 0,0004 CAKE + 0,0004 SOL
5. **Pendapatan LP:**
   * Hanya **LP dalam rentang** yang mendapatkan biaya. Biaya didistribusikan secara proporsional berdasarkan bagian masing-masing LP.
   * **LP di luar rentang** **tidak mendapatkan biaya**.

</details>

### **Mendapatkan CAKE**

Untuk membuat menjadi penyedia Likuiditas semakin menguntungkan, Anda juga dapat menempatkan posisi Likuiditas Anda untuk menghasilkan hasil segar di [CAKE Farms](https://pancakeswap.finance/liquidity/pools), sambil tetap mendapatkan imbalan biaya Trading.

***

## Exchange V2

### Token LP

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28142%29.png" alt=""><figcaption></figcaption></figure>

Sebagai contoh, jika Anda menyetorkan **CAKE** dan **BNB** ke dalam sebuah Pool Likuiditas, Anda akan menerima token **CAKE-BNB LP**.

Jumlah token LP yang Anda terima mewakili bagian Anda dari Pool Likuiditas CAKE-BNB.

Anda juga dapat menukarkan dana Anda kapan saja dengan menghapus Likuiditas Anda.

### **Mendapatkan biaya Trading**

Setiap kali seseorang melakukan Trading di PancakeSwap, untuk setiap hop (Swap) di setiap Pool Likuiditas Exchange V2, trader membayar biaya tetap sebesar 0,25%, **di mana 0,17%** ditambahkan kembali ke Pool Likuiditas dalam bentuk biaya Trading.

### **Mendapatkan CAKE**

Exchange V2 lama akan berjalan secara paralel dengan Exchange V3 baru. Jadi, beberapa pasangan Trading akan tetap berada di PancakeSwap Exchange V2 dan memiliki V2 Farm yang sesuai. Silakan periksa tag untuk mengidentifikasi versi exchange.



## Impermanent Loss

Menyediakan Likuiditas tidak tanpa risiko, karena Anda mungkin terkena impermanent loss.

["Sederhananya, impermanent loss adalah perbedaan antara memegang token di AMM dan memegang token di Dompet Anda." - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
