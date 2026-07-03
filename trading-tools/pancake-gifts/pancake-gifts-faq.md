# FAQ Pancake Gifts

FAQ ini membahas cara kerja Pancake Gifts di balik layar, apa yang diharapkan dalam berbagai skenario, dan mengapa pilihan desain tertentu dibuat.

***

## 1. 🔐 Perilaku & Akses Kode Hadiah

### **1.1 Mengapa kode hadiah tidak disimpan?**

Kami **sengaja tidak menyimpan** kode hadiah di:

* Penyimpanan lokal frontend
* Basis data backend

Ini melindungi:

* Privasi pengguna
* Keamanan terhadap kompromi perangkat
* Klaim hadiah yang tidak disengaja atau berbahaya

### **1.2 Bisakah saya meregenerasi atau mengambil kembali kode hadiah nanti?**

Tidak. Kode hadiah:

* Ditampilkan **hanya sekali** selama pembuatan
* Tertanam dalam **tautan** atau **kode QR** yang dihasilkan
* **Tidak akan ditampilkan lagi** di antarmuka pengguna atau riwayat

{% hint style="warning" %}
Jika kode hilang dan Anda tidak menyimpan tautan atau kode QR, hadiah tidak dapat diklaim secara manual. Sebagai gantinya, untuk mengambil kembali jumlah hadiah Anda, Anda dapat membatalkannya secara manual.
{% endhint %}

### **1.3 Apakah kode hadiah masih akan tertanam dalam tautan berbagi atau kode QR?**

Ya:

* Tautan berbagi menyertakan kode hadiah (misalnya `pancakeswap.finance/gift#code=xxxx`)
* Kode QR juga menyematkan kode hadiah, tetapi **tidak dapat diregenerasi nanti.**&#x20;

{% hint style="success" %}
**Tip Pro:**  Unduh gambar setelah dihasilkan
{% endhint %}

* Klaim manual memerlukan kode hadiah aktual — tidak ada cadangan jika tautan/kode QR hilang

## 2. 🎁 Status & Kedaluwarsa Hadiah

### **2.1 Bisakah saya melihat apakah hadiah telah diklaim, dibatalkan, atau kedaluwarsa?**

Ya. Bagian **Riwayat Hadiah** menampilkan:

* Status: Menunggu / Diklaim / Dibatalkan / Kedaluwarsa / Tidak Dapat Diklaim
* Detail hadiah (token, jumlah, jenis, rantai, cap waktu)

### **2.2 Apa yang terjadi ketika hadiah kedaluwarsa?**

Jika hadiah tidak diklaim dalam **jendela bawaan 7 hari**:

* **Seluruh jumlah hadiah dikembalikan** ke dompet pembuat
* **Biaya gas klaim tetap (\~$0,05) tidak dikembalikan**

## 3. 🧠 Logika & Keterbatasan Klaim

### **3.1 Bisakah pengguna mengklaim hadiah di rantai yang berbeda dari tempat hadiah dibuat?**

Tidak. Hadiah **terikat pada rantai**:

* Hadiah yang dibuat di **BSC** harus diklaim di **BSC**
* Pemberian hadiah lintas rantai saat ini tidak didukung

## 4. ⛽ Biaya Gas & Desain

### **4.1 Bagaimana jumlah gas tetap untuk pembuatan hadiah ditentukan?**

Kami menetapkan harga gas tetap berdasarkan kondisi rantai BNB saat ini (\~5 kali jumlah Gas yang direkomendasikan saat ini).

Buffer ini:

* Melindungi terhadap lonjakan gas yang tiba-tiba
* Memastikan hadiah tetap dapat diklaim dalam kondisi volatilitas normal

\
Contoh

* **Saat ini yang direkomendasikan: 0,1 Gwei** (lihat: [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Oleh karena itu, Biaya gas klaim tetap = 0,1 Gwei x 5 = 0,5 Gwei**


