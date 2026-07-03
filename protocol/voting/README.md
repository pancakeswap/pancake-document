# 📔 Tata Kelola

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Sebagai bagian dari [peningkatan Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3), halaman ini telah diperbarui pada 15 Mei 2025
{% endhint %}

Pemungutan suara memberikan suara kepada komunitas PancakeSwap, memungkinkan komunitas untuk turut menentukan arah perkembangan PancakeSwap di masa depan.

Kunjungi [portal pemungutan suara asli PancakeSwap](https://pancakeswap.finance/voting) dan halaman [Forum](https://forum.pancakeswap.finance/) kami.

## Mekanisme Pemungutan Suara

:notebook\_with\_decorative\_cover:Ringkasan - Apa yang Berubah (setelah [Pembaruan Tokenomics 3.0](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3))

<table><thead><tr><th width="200.6015625">Komponen Tata Kelola</th><th width="218.01953125">Sebelum Tokenomics 3.0</th><th width="205.1796875">Setelah Tokenomics 3.0</th><th>Status<select><option value="q1dVFsCri7zA" label="✅ Berubah" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Tidak Berubah" color="blue"></option></select></th></tr></thead><tbody><tr><td>Kekuatan Suara</td><td>1 veCAKE = 1 kekuatan suara</td><td>1 CAKE = 1 kekuatan suara</td><td><span data-option="q1dVFsCri7zA">✅ Berubah</span></td></tr><tr><td>Delegasi</td><td>Diizinkan (melalui mekanisme veCAKE)</td><td>Delegasi tidak diizinkan</td><td><span data-option="q1dVFsCri7zA">✅ Berubah</span></td></tr><tr><td>Ambang Pengajuan Proposal</td><td>Diperlukan 100K veCAKE untuk Snapshot</td><td>Diperlukan 100K CAKE untuk Snapshot</td><td><span data-option="q1dVFsCri7zA">✅ Berubah</span></td></tr><tr><td>Proposal Inti vs Komunitas</td><td>Peran dan tujuan yang jelas untuk setiap jenis proposal</td><td>Tidak ada perubahan</td><td><span data-option="4AGl26rwjYcI">🔁 Tidak Berubah</span></td></tr><tr><td>Periode Pemungutan Suara</td><td>Komunitas: Tetap<br>Inti: Variabel</td><td>Tidak ada perubahan</td><td><span data-option="4AGl26rwjYcI">🔁 Tidak Berubah</span></td></tr><tr><td>Waktu Snapshot</td><td>Pada blok saat proposal diposting</td><td>Tidak ada perubahan</td><td><span data-option="4AGl26rwjYcI">🔁 Tidak Berubah</span></td></tr><tr><td>Kuorum</td><td>Tidak ada kuorum minimum</td><td>Tidak ada perubahan</td><td><span data-option="4AGl26rwjYcI">🔁 Tidak Berubah</span></td></tr></tbody></table>

### 1. **Kekuatan Suara (Berubah)**

* **Semua pemegang CAKE memiliki hak suara langsung.**
* **Kekuatan suara berbanding lurus dengan jumlah CAKE yang dipegang di alamat dompet saat snapshot**
  * **1 CAKE = 1 kekuatan suara**
  * **CAKE yang di-staking di Syrup Pools tidak dihitung** terhadap kekuatan suara Anda, karena tidak merupakan bagian dari saldo dompet Anda saat snapshot
  * Saldo snapshot = Blok yang sama saat proposal diposting
* **Delegasi tidak lagi didukung.** Setiap pemegang CAKE harus memilih secara individual.

### 2. **Pengajuan Proposal (Tidak Berubah)**

* **Cara Mengajukan Proposal**
  * Ajukan di [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create)
  * Harus mencakup:
    * Judul
    * Konten
    * Deskripsi
    * Tindakan on-chain (jika diperlukan)
    * Durasi Pemungutan Suara
* Jenis Proposal
  1.  Proposal Inti

      * Hanya dapat diajukan oleh **Tim Inti PancakeSwap**.
      * Memerlukan suara dari pemegang CAKE.
      * Jika disahkan, akan diimplementasikan oleh tim PancakeSwap.

      Contoh

      1. Penyesuaian protokol (perubahan produk, perubahan biaya)
      2. Penggunaan signifikan dana Pertumbuhan Ekosistem yang tidak tercakup oleh proposal sebelumnya
  2. Proposal Komunitas
     * Proposal **Komunitas** diposting oleh komunitas PancakeSwap. Proposal ini digunakan untuk mengajukan ide dan mengekspresikan sudut pandang komunitas. Ini adalah **saran tidak mengikat** dari komunitas.
     * Siapa pun dengan **100.000 CAKE (saldo snapshot)** dapat mengajukan.
     * Tim PancakeSwap dapat mengadopsi proposal yang kuat ke dalam Proposal Inti di masa mendatang
     * Anggota komunitas juga dapat menggunakan [Forum](https://forum.pancakeswap.finance/) kami untuk memberikan masukan dan saran kepada protokol.

### **3. Durasi Pemungutan Suara (Tidak Berubah)**

* Semua pemegang CAKE dapat memberikan suara **selama jendela pemungutan suara** untuk setiap proposal.
  * Proposal komunitas: Tetap selama 3 hari
  * Proposal Inti: Variabel, ditetapkan oleh PancakeSwap
* Kekuatan suara Anda ditentukan oleh **snapshot saldo CAKE Anda pada blok saat proposal diposting**.
* **Menambahkan lebih banyak CAKE setelah proposal diposting tidak akan meningkatkan kekuatan suara Anda** untuk pemungutan suara tersebut.

Untuk detail lengkap, lihat [Panduan Pemungutan Suara](https://docs.pancakeswap.finance/protocol/voting/voting-guide).

### **4. Hasil Pemungutan Suara (Tidak Berubah)**

* Hasil didasarkan pada **total suara yang diberikan** (total CAKE yang digunakan untuk memilih)
* **Saat ini tidak ada kuorum minimum yang diperlukan** agar proposal bisa lolos.

## Catatan: Hak Veto

Untuk melindungi protokol, **Tim Inti PancakeSwap berhak untuk campur tangan dalam situasi kritis** — seperti ancaman keamanan atau masalah yang mempengaruhi operasi platform yang stabil — **tanpa memerlukan pemungutan suara komunitas atau polling Snapshot**.

Dalam setiap kasus di mana tindakan veto diambil, Tim Inti akan **secara publik berbagi penjelasan yang jelas** tentang keputusan tersebut.

**Kemungkinan tindakan veto meliputi:**

1. **Menghentikan sementara smart contract** untuk memperbaiki bug atau kerentanan mendesak.
