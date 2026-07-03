# Farm

Farming PancakeSwap Infinity adalah cara yang sederhana dan hemat gas bagi pengguna untuk mendapatkan hadiah likuiditas tanpa perlu melakukan Staking LP token mereka. Setelah likuiditas ditambahkan ke pool yang memenuhi syarat, hadiah mulai bertambah secara otomatis.

#### ⚙️ Cara Kerjanya

Berikut penjelasan singkat tentang bagaimana sistem melacak dan mendistribusikan hadiah:<br>

**✅ Tidak Perlu Staking**

* Cukup pegang posisi LP Anda di dompet.
* Tidak perlu mengunci aset Anda atau berinteraksi dengan smart contract tambahan.
* Anda mulai mendapatkan hadiah secara otomatis ketika menambahkan likuiditas.

#### 📈 Distribusi Hadiah

* Hanya posisi yang berada dalam rentang (yang menyediakan likuiditas aktif) yang menerima hadiah.
* Hadiah sebanding dengan biaya yang diperoleh oleh posisi Anda selama setiap periode, yang disebut epoch.

#### ⏳ Apa Itu Epoch?

* Epoch adalah jendela waktu tetap — saat ini ditetapkan pada 8 jam.
* Hadiah dihitung dan didistribusikan setelah setiap epoch.
* Epoch saat ini dijadwalkan pada pukul 00:00, 08:00, dan 16:00 UTC.

***

#### 🔄 Proses Farming & Klaim

1. **Pelacakan Posisi:** Sistem backend memantau posisi LP Anda di semua Farm.
2. **Perhitungan Hadiah:** Di akhir setiap epoch,
   1. Sistem menghitung hadiah Anda berdasarkan likuiditas dan biaya yang dihasilkan.
   2. Sistem memproses hadiah ke dalam Merkle tree dan mengirimkan Merkle root ke smart contract.
3. **Periode Sengketa:**
   1. Setelah Merkle root dipublikasikan, periode sengketa 1 jam dimulai.
   2. Selama periode sengketa:
      1. Hadiah yang baru dihitung tidak dapat diklaim.
      2. Hadiah dari epoch sebelumnya tetap tersedia untuk diklaim.
      3. Alat verifikasi otomatis dan yang dioperasikan komunitas memeriksa keakuratan data yang dipublikasikan. Jika ditemukan ketidaksesuaian, sengketa dapat diajukan untuk mencegah distribusi yang tidak benar.
4. **Mengklaim Hadiah:**
   1. Setelah periode sengketa berakhir, Anda dapat mengklaim hadiah untuk epoch terbaru.
   2. Semua hadiah yang belum diklaim di semua Farm dapat diklaim dalam satu transaksi yang hemat gas.
5. **Hadiah yang Belum Diklaim Akan Dilanjutkan:**
   1. Hadiah yang belum diklaim akan dilanjutkan ke epoch berikutnya. Setiap pembaruan mencakup hadiah sebelumnya, memastikan tidak ada penghasilan yang hilang atau kedaluwarsa.

{% hint style="info" %}
Rentang likuiditas yang lebih sempit umumnya menghasilkan penghasilan lebih tinggi, tetapi meningkatkan kemungkinan posisi bergerak keluar dari rentang dan tidak memenuhi syarat untuk mendapatkan hadiah.
{% endhint %}

#### 🌱 Ringkasan

✅ Tidak ada Staking\
✅ Klaim yang hemat gas\
✅ Pembaruan hadiah rutin\
✅ Proses sengketa yang adil dan transparan\
✅ Hadiah terakumulasi hingga Anda siap untuk mengklaim
