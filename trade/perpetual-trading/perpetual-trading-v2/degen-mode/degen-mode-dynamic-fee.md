# Biaya Dinamis Degen Mode

PancakeSwap Perpetuals Degen Mode menggunakan model biaya dinamis. Biaya ini dirancang untuk membebankan biaya berdasarkan PnL dan melindungi pengguna dari kerugian.\
**Bagaimana cara kerjanya?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

di mana:

* Pnl adalah keuntungan atau kerugian pada posisi
* shareRate adalah tingkat bagi hasil, yaitu persentase dari nosional yang dibayarkan sebagai biaya (15% sebagai default)
* Notional adalah jumlah uang yang digunakan untuk membuka posisi
* closeMinRate adalah tingkat biaya penutupan minimum, yaitu jumlah minimum yang dapat Anda bayar untuk menutup posisi (0,03% sebagai default)

\
**Contoh:**

Jika Anda memiliki posisi dengan keuntungan $100, tingkat bagi hasil 15%, dan nosional $600, maka tingkat biaya penutupan adalah:

Tingkat biaya penutupan = Max(100 \* 15% / 600, 0,03%) = 0,03%

Dalam hal ini, tingkat biaya penutupan adalah 0,03%, yaitu tingkat biaya penutupan minimum.<br>

Catatan:

Biaya eksekusi hanya akan dikenakan saat posisi dibuka. Biaya ditetapkan sebesar 0,3 USD (BNB Chain)/ 0,2 USD (Arbitrum)/ 0,01 USD (opBNB)/ 0,3 USD (Base), serupa dengan yang dikenakan saat trading pasangan Trading Perpetual klasik. Tidak ada biaya pembukaan posisi.

Dalam kejadian Likuidasi, tingkat kerugian likuid 90% sudah mencakup biaya penutupan.
