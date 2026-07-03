# FAQ Solana Farming

### 1. Bagaimana cara kerja SOL Farming?

* V3 Farming bersifat **berbasis kampanye**, artinya farm aktif hanya untuk durasi tertentu.
* Selama kampanye berlangsung:
  * Token hadiah didistribusikan **setiap detik** ke **posisi likuiditas aktif**.
  * APR farming akan ditampilkan di halaman daftar pool dan halaman posisi saya
* Setelah kampanye berakhir:
  1. **Tidak ada lagi hadiah** yang akan didistribusikan.
  2. **APR farming tidak akan lagi ditampilkan** di halaman daftar pool dan halaman posisi saya
  3. Farm menjadi **tidak aktif**, tetapi dapat dimulai ulang oleh pembuatnya dengan menambahkan lebih banyak hadiah.

### 2. Apakah saya perlu melakukan stake LP NFT untuk mendapatkan hadiah farming?

* **Tidak diperlukan staking**.
* Selama posisi likuiditas Anda **aktif (dalam rentang)** di pool dengan farm aktif, Anda akan mendapatkan hadiah secara otomatis.

### 3. Apakah ada farm booster?

* **Tidak**, farm V3 **tidak** mendukung mekanisme boosting apa pun.
* Hadiah hanya didasarkan pada bagian likuiditas aktif Anda di pool.

### 4. Bisakah beberapa farm dibuat untuk pool yang sama?

* **Tidak**, hanya **satu farm per pasangan token dan tingkatan biaya** yang dapat ada.

### 5. Bagaimana farm SOL dikonfigurasi?

#### A. Token Hadiah

* Hingga **3 token hadiah berbeda** dapat ditetapkan per farm.
* Setelah ditetapkan, jenis token hadiah **tidak dapat diubah**.
* Pembuat farm dapat:
  * **Mengisi ulang** token hadiah yang dialokasikan.
  * **Memperpanjang durasi farming** setelah kampanye berakhir.

#### B. Durasi Kampanye

* Kampanye harus berlangsung minimal **7 hari** dan maksimal **90 hari**.

### 6. Bisakah farm diedit setelah dibuat?

Pembuat farm dapat mengedit parameter berikut **setelah farm dibuat**:

1. Tingkat distribusi hadiah (per detik)
2. Tanggal berakhir kampanye
3. Menambah token hadiah dan jumlah hadiah yang sesuai (hanya jika kurang dari 3 token yang awalnya ditetapkan)
