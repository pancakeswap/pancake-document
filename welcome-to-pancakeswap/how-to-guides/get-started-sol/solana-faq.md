# FAQ Solana

### V3 Pools – Pertanyaan yang Sering Diajukan (FAQ)

#### 1. Tingkatan biaya apa saja yang tersedia?

**Tingkatan Biaya yang Didukung:**\
Tingkatan biaya berikut tersedia untuk pool V3 (likuiditas terkonsentrasi):

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**Distribusi Biaya (berlaku untuk semua tingkatan biaya):**

* 84% untuk penyedia Likuiditas (LP)
* 16% untuk protokol
  * 8% dibakar
  * 8% masuk ke kas protokol

#### 2. Apakah siapa saja dapat membuat pool?

Ya. Pembuatan pool bersifat tanpa izin, dengan beberapa pengecualian:

* Hanya satu pool yang dapat ada untuk kombinasi **pasangan token + tingkatan biaya** tertentu (misalnya hanya satu pool SOL<> USDC 0.1% yang dapat ada pada satu waktu)
* Hanya token **SPL** dan token **Token-2022** tertentu yang didukung saat ini.

#### 3. Berapa lama pool yang baru dibuat akan muncul?

* Pool biasanya muncul dalam daftar pool sekitar **5 menit** setelah pembuatan.
* Jika tidak muncul:
  * Gunakan **bilah pencarian** untuk menemukan secara manual.
  * Pool mungkin difilter dari daftar karena **TVL yang rendah**.

#### 4. Mengapa APR atau TVL pool saya masih menampilkan nol?

Ini adalah hal yang wajar terjadi segera setelah pool baru dibuat:

* Data APR dan TVL hanya akan muncul setelah **setidaknya satu Swap** telah terjadi di pool tersebut.
* Setelah Swap terjadi, metrik-metrik ini akan mulai ditampilkan dalam sekitar **15 menit**.

#### 5. Bagaimana cara menambahkan token khusus untuk membuat pool?

Untuk menambahkan token baru:

* Di antarmuka pembuatan pool, buka pemilih token.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* Tempel alamat token ke bilah pencarian.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* Klik **"Add Token"**.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* Token kini dapat dicari dalam daftar.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* Untuk mengelola token:
  * Klik **"View Token List"**.
  *   Aktifkan atau nonaktifkan daftar yang berbeda, termasuk **User Added Token List**, yang mencakup token yang ditambahkan secara manual.

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Mengapa transaksi pertama saya di Solana tampak lebih mahal?

Solana menggunakan **Associated Token Accounts (ATA)** untuk mengelola saldo token setiap Dompet. Saat pertama kali berinteraksi dengan token, Dompet Anda harus membuat ATA, yang menimbulkan biaya awal satu kali (dibayar dalam SOL).

* Biaya pembuatan ATA ini diperlukan oleh protokol Solana dan tidak spesifik untuk PancakeSwap.
* Jika ATA kemudian ditutup, **SOL yang digunakan semula dapat dikembalikan** ke Dompet Anda.
