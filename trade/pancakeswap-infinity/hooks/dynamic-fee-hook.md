# Dynamic Fee Hook

Dynamic Fee Hook resmi PancakeSwap dirancang untuk menciptakan pertukaran nilai yang lebih adil antara Penyedia Likuiditas dan Trader. Hook ini melindungi LP dari impermanent loss (IL) yang berlebihan sambil menjaga pasar tetap efisien bagi para trader.

Dibangun oleh tim inti PancakeSwap, hook ini dirancang khusus untuk menawarkan alternatif yang cerdas dan adaptif terhadap model biaya tetap konvensional.

#### 🔍 Mengapa Biaya Dinamis?

Perdagangan Arbitrase besar menyebabkan divergensi harga yang lebih besar di pool, meningkatkan IL bagi LP. Model biaya dinamis kami membebankan biaya yang lebih tinggi secara proporsional pada perdagangan arbitrase yang lebih besar untuk mengimbangi risiko ini—sambil tetap menyisakan cukup ruang bagi para arbitrageur untuk mendapat keuntungan dan menjaga harga tetap selaras.

#### 📊 Apa Bedanya dengan Model Lain?

Model-model lain di masa lalu menggunakan data historis untuk memperkirakan volatilitas dan faktor lain untuk menyesuaikan biaya. Namun:

* Data historis adalah indikator tertinggal dan mungkin tidak secara akurat memprediksi volatilitas masa depan.
* Peristiwa pasar eksternal (seperti perubahan regulasi atau pergeseran ekonomi) dapat membuat tren masa lalu menjadi tidak dapat diandalkan.
* Model yang kompleks dan banyak parameter berisiko overfitting—berkinerja baik pada data masa lalu tetapi buruk pada kondisi baru yang belum pernah ada sebelumnya.

Pendekatan kami lebih sederhana, adaptif, dan didasarkan pada perilaku trading secara real-time.

#### ⚙️ Cara Kerjanya

* **Kami tidak memprediksi volatilitas atau faktor makro lainnya**\
  Sebagai gantinya, model kami secara inheren mendapat manfaat dari perilaku para arbitrageur dalam berbagai kondisi pasar:
  * **Volatilitas tinggi:** Lebih banyak perdagangan arbitrase dalam ukuran yang lebih besar → Biaya lebih tinggi untuk LP, menutupi bagian IL yang lebih besar.
  * **Volatilitas rendah:** Lebih sedikit perdagangan yang lebih kecil → IL lebih rendah secara alami, tetapi LP masih mendapatkan biaya lebih tinggi dibandingkan model biaya tetap.
* **Model kami menggunakan**
  * Harga pool yang diberi bobot secara eksponensial untuk mendeteksi perdagangan arbitrase.
  * Kurva biaya eksponensial berdasarkan dampak harga setiap Swap.
  * Batas biaya maksimum sebesar 5% untuk menjaga keadilan bagi trader.

{% hint style="success" %}
Ini memastikan biaya berskala secara dinamis dengan dampak trading sambil beradaptasi secara otomatis terhadap perubahan kondisi pasar.
{% endhint %}

* **Insentif yang Seimbang**\
  Para arbitrageur masih mempertahankan \~50% keuntungan mereka setelah biaya dinamis, memastikan mereka termotivasi untuk terus menjaga harga pool selaras dengan pasar.

#### 📌 Poin Penting

* Tidak bergantung pada prediksi volatilitas atau faktor makro lainnya.
* Beradaptasi secara otomatis terhadap volatilitas pasar berdasarkan perilaku trading aktual.
* Melindungi LP dari IL pada setiap Swap.
* Mempertahankan insentif yang kuat bagi para arbitrageur untuk menutup kesenjangan harga.
* Memberikan manfaat kepada trader dengan likuiditas yang lebih dalam dan biaya dasar yang lebih rendah.
