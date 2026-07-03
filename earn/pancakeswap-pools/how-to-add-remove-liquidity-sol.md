# Likidite Nasıl Eklenir / Kaldırılır (SOL)

"Likidite", PancakeSwap'ın Exchange'inin nasıl çalıştığının merkezindedir. Likidite sayfası aracılığıyla her ikisini de Staking yaparak herhangi bir token çifti için likidite ekleyebilirsin.

Likidite eklemenin karşılığında o çift için işlem ücretleri ve (varsa) Farm ödülleri alacaksın.

PancakeSwap V3, **yoğunlaştırılmış likidite** sağlamanı mümkün kılar; yani liküditenin aktif olduğu fiyat aralığını kendin seçersin. Bu, sermayenin nasıl kullanıldığı konusunda sana daha fazla kontrol ve verimlilik sağlar.

{% hint style="warning" %}
**Not:** Bu kılavuzda gösterilen görseller yalnızca açıklama amaçlıdır; gerçek zamanlı verileri veya mevcut havuz istatistiklerini yansıtmayabilir.
{% endhint %}

***

## Likidite Ekleme

Likiditeyi iki şekilde ekleyebilirsin:

* **Seçenek 1:** Mevcut bir havuza ekle
* **Seçenek 2:** Halihazırda oluşturduğun bir pozisyona daha fazla token ekle

***

### Seçenek 1: Mevcut Bir Havuza Ekleme

#### Adım 1: Havuz Listesi Sayfasına Git

Burada Solana'daki tüm aktif V3 havuzlarını göreceksin.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28386%29.png" alt=""><figcaption></figcaption></figure>

#### Adım 2: Havuzunu Bulmak İçin Filtreleri Kullan

Sayfanın üstündeki filtreleri şunlar için kullanabilirsin:

*   Belirli bir token çiftini **ara**<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28387%29.png" alt=""><figcaption></figcaption></figure>
*   **Düzen görünümünü değiştir** (ızgara/liste)<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28388%29.png" alt=""><figcaption></figcaption></figure>
*   Havuzları TVL, Hacim, Ücretler veya APR'ye göre **sırala**<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28389%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Havuzun oluşturulduktan hemen sonra görünmüyorsa lütfen 5 dakikaya kadar bekle. TVL, hacim, ücretler ve APR istatistikleri, havuz üzerinden Swap'lar gerçekleştikçe yaklaşık her 15 dakikada bir güncellenir.
{% endhint %}

#### Adım 3: Likidite Ekleme Yöntemini Seç

İşleme şu şekillerde başlayabilirsin:

*   Havuz kartındaki **"Deposit"** butonuna tıkla<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28390%29.png" alt=""><figcaption></figcaption></figure>
*   VEYA "Pozisyonlarım" altındaki **"Yeni Pozisyon Oluştur"** butonuna tıkla<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28391%29.png" alt=""><figcaption></figcaption></figure>

#### Adım 4: Fiyat Aralığını Belirle

Bu bir V3 havuzu olduğundan liküditenin için bir fiyat aralığı seçmen gerekecektir:

*   **Hızlı ön ayar aralıklarını** (örn. ±%25) kullan veya özel bir aralık belirle<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28392%29.png" alt=""><figcaption></figcaption></figure>
*   Baz/kotasyon görünümü arasında geçiş yapmak için **fiyat yönü geçiş düğmesini** kullan<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28393%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Şu durumlarda **uyarılara** dikkat et:

* Seçilen aralığın piyasa fiyatından uzak olması
* Havuzun düşük liküditeye sahip olması
{% endhint %}

#### Adım 5: Yatırım Miktarını Gir

Sağlamak istediğin token miktarlarını gir

\*\* APR, her iki token için de miktarları girene kadar görünmeyecektir

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28394%29.png" alt=""><figcaption></figcaption></figure>

#### Adım 6: Önizle ve Onayla

*   **"Likidite Ekle"** butonuna tıkla

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28396%29.png" alt=""><figcaption></figcaption></figure>
*   Önizleme penceresinde pozisyonunu incele<br>

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28397%29.png" alt=""><figcaption></figcaption></figure>

Onaylandıktan sonra işlem gönderilecek ve pozisyonun oluşturulacaktır!

***

### Seçenek 2: Mevcut Bir Pozisyona Daha Fazla Likidite Ekleme

#### Adım 1: "Pozisyonlarım" Sayfasına Git

Burada tüm aktif V3 likidite pozisyonlarını göreceksin.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28398%29.png" alt=""><figcaption></figcaption></figure>

#### Adım 2: "+" Butonuna Tıkla

Bu, mevcut fiyat aralığına daha fazla token eklenmeni sağlar.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28399%29.png" alt=""><figcaption></figcaption></figure>

#### Adım 3: Yatırım Miktarını Gir

Eklemek istediğin token miktarlarını gir ve **"Onayla"** butonuna tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28400%29.png" alt=""><figcaption></figcaption></figure>

Onaylandıktan sonra başarı mesajı göreceksin.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28401%29.png" alt=""><figcaption></figcaption></figure>

***

## Likidite Kaldırma

Aktif pozisyonlarından herhangi birindeki liküditeyi doğrudan **Pozisyonlarım** sekmesinden kaldırabilirsin.

#### 1. **Pozisyonlarım** Sayfasına Git

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28402%29.png" alt=""><figcaption></figcaption></figure>

#### 2. Likidite Kaldırmak İstediğin Pozisyonu Seç

Pozisyonun yanındaki **"−"** simgesine tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28403%29.png" alt=""><figcaption></figcaption></figure>

#### 3. Kaldırmak İstediğin Miktarı Gir

Şunlardan birini yapabilirsin:

* Token miktarlarını manuel olarak gir
* **VEYA** mevcut pozisyonunun yüzdesini seçmek için **kaydırıcıyı** kullan

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28404%29.png" alt=""><figcaption></figcaption></figure>

#### 4. (İsteğe Bağlı) Likiditeyi Kaldırdıktan Sonra Pozisyonunu Açık Tut

Liküditenin **%100'ünü** kaldırırken **"Pozisyonumu açık tut"** seçeneğini seçersen:

* Token'ların çekilecektir
* Ancak pozisyonun geçmişi ve orijinal fiyat aralığın **Pozisyonlarım** altında **görünür kalmaya devam edecektir**

Fiyat aralığı görünümü dahil pozisyonu **tamamen kapatmak** istiyorsan:

* **"X"** simgesine tıkla

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28408%29.png" alt=""><figcaption></figcaption></figure>

#### 5. Aynı Fiyat Aralığını Yeniden Kullan

İlk kez likidite eklediğindeki adımları izleyerek aynı fiyat aralığına daha sonra **daha fazla likidite** de ekleyebilirsin.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28409%29.png" alt=""><figcaption></figcaption></figure>
