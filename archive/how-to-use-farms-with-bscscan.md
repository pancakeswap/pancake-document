# Cara Menggunakan Farm dengan BscScan

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Karena memerlukan beberapa langkah, menggunakan Farm dengan PancakeSwap mungkin terasa mengintimidasi pada awalnya. Panduan ini akan memandu Anda menggunakan kontrak Farm secara langsung melalui BscScan.

{% hint style="warning" %}
Harap dipahami bahwa menggunakan BscScan untuk berinteraksi dengan kontrak tidak disarankan bagi pemula. Jika Anda tidak merasa percaya diri, kami sarankan menggunakan panduan [Cara Menggunakan Farm](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) sebagai gantinya.
{% endhint %}

## Menemukan pengidentifikasi proses Farm

Untuk berinteraksi dengan benar dengan smart contract farming, Anda memerlukan pengidentifikasi proses (PID) yang sesuai untuk pasangan LP Anda. Untuk saat ini, cara termudah untuk menemukan ini adalah dengan memeriksa GitHub.

1\. Buka [kode Farm situs web PancakeSwap di GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Control**/**command** + **F** dan cari pasangan Anda berdasarkan ticker (bukan nama proyek). Misalnya, 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. Catat atau salin nomor PID — dalam hal ini 389 — di tempat yang mudah Anda akses. Anda akan membutuhkannya nanti.

## Menyetorkan Token LP melalui BscScan

Ada beberapa hal yang terlibat dalam menyetorkan Token LP menggunakan BscScan. Kami telah membaginya menjadi beberapa langkah agar lebih mudah diikuti.

### Mendapatkan alamat Kontrak Staking Utama

Alamat untuk kontrak staking utama adalah: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Namun, dengan asumsi Anda ingin mengkonfirmasinya, kunjungi [halaman BscScan Kontrak Staking Utama PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). Anda akan melihat alamat di kiri atas. Klik **ikon halaman** untuk menyalinnya ke clipboard. Anda akan membutuhkannya segera.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### Buka kontrak untuk Token LP Anda

Anda perlu menyetujui smart contract untuk Token LP yang ingin Anda masukkan ke farm sebelum dapat menggunakannya.

### Dari kode sumber

1\. Pertama, buka [farms.ts di GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Control**/**command** + **F** dan cari pasangan Anda berdasarkan ticker (bukan nama proyek). Misalnya, 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Ketika Anda menemukan kode untuk pasangan LP yang Anda cari, temukan alamat setelah "56:". Ini akan menjadi alamat kontrak Anda.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### Dari UI

1\. Pertama, kunjungi [halaman Farm PancakeSwap](https://pancakeswap.finance/farms) dan cari pasangan yang Anda pilih menggunakan kolom "SEARCH" di kanan atas. Kami menggunakan CAKE-BUSD untuk contoh ini.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Klik **Details** untuk memperluas baris dan menampilkan informasi lebih lanjut.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Klik **View Contract** untuk membuka smart contract di BscScan.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### Memberikan izin ke kontrak Token LP

Setelah kontrak Token LP Anda terbuka di BscScan, Anda akan menyetujui pengeluaran Token LP Anda ke dalam Farm.

1\. Di halaman kontrak Token LP, buka **Contract**, kemudian **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Klik **Connect to Web3** untuk menghubungkan MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Konfirmasi koneksi.

3\. Di bawah fungsi 1, "approve", Anda akan melihat "spender:address". Tempel alamat kontrak Kontrak Staking Utama yang sebelumnya Anda salin ke clipboard.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. Anda juga perlu menyetujui jumlah Token LP yang dapat digunakan oleh kontrak. Di kolom nilai, Anda perlu memasukkan jumlah dalam Wei. Anda dapat menggunakan [BscScan Unit Converter](https://www.bscscan.com/unitconverter) untuk mengubah jumlah Anda dengan mudah ke Wei. Di sini kami akan menggunakan 5 Token LP CAKE-BUSD.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
Anda juga dapat menggunakan `-1` sebagai nilai untuk memberikan persetujuan pengeluaran tanpa batas. Ini tidak berarti Anda akan menghabiskan segalanya secara default, tetapi hanya bahwa transaksi dengan ukuran berapa pun yang menggunakan kontrak ini akan diizinkan oleh dompet Anda.
{% endhint %}

6\. Klik **Write** dan terima tindakan di dompet MetaMask Anda. Anda sekarang dapat memasukkan Token LP ke Farm hingga jumlah yang telah Anda setujui.

### Setorkan Token LP dengan smart contract Kontrak Staking Utama

Dengan Kontrak Staking Utama yang sekarang disetujui untuk menggunakan Token LP Anda, saatnya untuk melakukan setoran.

1\. Kembali di [halaman BscScan Kontrak Staking Utama PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), buka **Contract**, kemudian **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Klik **Connect to Web3** untuk menghubungkan MetaMask.

3\. Gulir ke fungsi 2, "deposit", dan ketik PID Anda ke kolom "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

Jika Anda tidak mencatat PID sebelumnya, Anda dapat mempelajari cara mendapatkannya di bagian **Menemukan pengidentifikasi proses Farm** di atas halaman ini.

4\. Di bawah \_pid Anda akan melihat "\_amount". Masukkan jumlah yang disetujui kontrak LP untuk digunakan sebelumnya.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Periksa informasinya dan klik **Write**. Konfirmasi tindakan Anda di MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Anda dapat mengkonfirmasi bahwa setoran berhasil dengan mengklik **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Menarik dari Pool

Menarik Token LP dari Pool sangat mirip dengan melakukan setoran. Perbedaannya adalah fungsi mana yang akan Anda gunakan.

1\. Kembali di [halaman BscScan Kontrak Staking Utama PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), buka **Contract**, kemudian **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Klik **Connect to Web3** untuk menghubungkan MetaMask.

3\. Gulir ke bawah ke fungsi 15, "withdraw", dan ketik PID Anda ke kolom "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

Jika Anda tidak mencatat PID sebelumnya, Anda dapat mempelajari cara mendapatkannya di bagian **Menemukan pengidentifikasi proses Farm** di atas halaman ini.

4\. Di bawah \_pid Anda akan melihat "\_amount". Masukkan jumlah LP yang ingin Anda tarik dari Pool.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Periksa informasinya dan klik **Write**. Konfirmasi tindakan Anda di MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Anda dapat mengkonfirmasi bahwa penarikan berhasil dengan mengklik **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Melakukan penarikan darurat**

‌Menggunakan fungsi penarikan darurat memungkinkan Anda menarik semua dana dari pool ketika tidak ada cara lain yang berhasil.

{% hint style="danger" %}
**Menggunakan fungsi penarikan darurat akan mengorbankan hadiah CAKE Anda!**

Tim PancakeSwap sangat menyarankan untuk menghindari fungsi ini kecuali diarahkan secara resmi oleh tim PancakeSwap, atau jika Anda sangat nyaman berinteraksi dengan smart contract dan memahami kode yang mendasarinya.
{% endhint %}

‌1. Di [halaman BscScan Kontrak Staking Utama PancakeSwap](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), buka **Contract**, kemudian **Write Contract**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. Klik **Connect to Web3** untuk menghubungkan MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Gulir ke bawah ke fungsi 4, "emergencyWithdraw", dan ketik PID Anda ke kolom "\_pid".

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

Jika Anda tidak mencatat PID sebelumnya, Anda dapat mempelajari cara mendapatkannya di bagian **Menemukan pengidentifikasi proses Farm** di atas halaman ini.

5\. Periksa informasinya dan klik **Write**. Konfirmasi tindakan Anda di MetaMask.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. Anda dapat mengkonfirmasi bahwa penarikan berhasil dengan mengklik **View your transaction**.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
