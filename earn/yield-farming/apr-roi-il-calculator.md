# APR/ROI/IL Hesaplayıcısı

V3 Likidite ve Farm'larda, yeni değiştirilemez likidite ve özelleştirilebilir fiyat aralığı özelliğiyle her LP pozisyonunun kendi LP ücreti ve CAKE farming APR'si olacak.

Likidite sağlamayı daha sorunsuz ve az zorlu hâle getirmek için, likidite sağlarken veya farming yaparken dilediğin zaman kullanabileceğin yeni otomatik APR göstergeleri ve yeniden tasarlanmış ROI hesaplayıcısı kullanıma sunuldu.

## Otomatik APR hesaplama ve göstergeler <a href="#id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5" id="id-12d7c8c1-d0d7-4d5e-99ea-5f5b7f5378e5"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28293%29.png" alt=""><figcaption></figcaption></figure>

Likidite sağlarken otomatik APR göstergesi, yaptığın yapılandırma değişikliklerine tepki verir ve ayarlarına göre APR'yi hesaplar.

Örneğin çoğu durumda fiyat aralığı ayarlarını daraltırsan APR yükselir.

LP ücreti APR'leri için lütfen şuna dikkat et:

* Tahmini LP ücreti ödül miktarı, seçilen ücret kademesine göre değişir; ücret ödüllerini manuel olarak talep etmen ve birleştirmen gerekir.
* APR rakamları, Subgraph'e bağımlı olan geçmiş işlem hacmi kullanılarak hesaplanır ve dizin oluşturma gecikmelerine tabi olabilir.

Farming APR'leri için:

* Tahmini CAKE ödül miktarı, farm'lara yapılan canlı CAKE emisyonlarına dayanır. Gelecekteki emisyon düzenlemelerine bağlı olarak değişebilir.

{% hint style="info" %}
Rakamlar mevcut oranlar ve havuz koşullarına göre hesaplanır; çeşitli dış değişkenlere bağlı olarak değişebilir. Bu rakamlar yalnızca bilgi amaçlı tahminlerdir ve kesinlikle garantili getirileri temsil etmez.
{% endhint %}

Bu APR göstergesini şu yerlerde bulabilirsin:

* "Likidite Ekle" sayfası — LP ücreti APR'sini gösterir
* Mevcut her likidite pozisyonunun ayrıntı sayfası — LP ücreti APR'sini gösterir\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28326%29.png)
* Farm sayfası, her farm altındaki pozisyon içinde — LP ücreti ve CAKE ödüllerini içeren birleşik APR'yi gösterir\
  ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28138%29.png)<br>

## Geliştirilmiş ROI hesaplayıcısı <a href="#id-6f06dc46-ff61-4022-a29d-3ebe67a50607" id="id-6f06dc46-ff61-4022-a29d-3ebe67a50607"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28146%29.png" alt=""><figcaption></figcaption></figure>

Otomatik APR göstergelerini her gördüğünde tıklayarak yeni ROI hesaplayıcısını açabilirsin. Yeni ROI hesaplayıcısı, V3 konsantre likidite sağlama ve farming ihtiyaçlarına uygun çeşitli eklenen özelliklerle yeniden tasarlandı.

Her bölümü birlikte inceleyelim:

### Yatırım Miktarı, "Stake Süresi" ve "Bileşik Yapma Sıklığı" <a href="#a398a29b-a1af-4ec3-9cc6-9e07e620c134" id="a398a29b-a1af-4ec3-9cc6-9e07e620c134"></a>

Bu üçü, önceki ROI hesaplayıcısında da bulunan temel girdilerdir. Şunları tanımlamak için kullanılır:

1. Likidite pozisyonuna USD cinsinden ne kadar varlık yatırdığın.
2. Bu varlıkların pozisyonda ne kadar süre stake edileceği.
3. Ödülleri ne sıklıkla pozisyona geri bileşikleyeceğin.



⓵ **Yatırım Miktarı**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/deposit-amount.gif)

Miktarı USD cinsinden manuel olarak girebilir ya da cüzdanındaki token bakiyesine göre 100 $, 1.000 $ veya izin verilen maksimum tutarı hızlıca doldurmak için hızlı işlem düğmelerini kullanabilirsin.



⓶ **Stake Süresi**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/stake-durations.gif)

Varlıkların likidite pozisyonunda ne kadar süre stake edileceğini şu seçeneklerden birini seçerek belirleyebilirsin: 1 gün, 7 gün, 30 gün, 1 yıl ve 5 yıl.

Getiri miktarı, stake süresine göre hesaplanır.



⓷ **Bileşik Yapma**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/compounding.gif)

Pozisyon tarafından üretilen ödülleri ne sıklıkla toplayıp geri bileşikleyeceğini seçebilirsin. 12 saat, 1 gün, 7 gün ve 30 gün arasından seçim yapabilirsin.

Getiri miktarı ve APY, seçimine göre hesaplanır. Pozisyonunu bileşiklemek istemiyorsan soldaki onay kutusunun işaretini kaldır.

{% hint style="info" %}
V3'te LP ücretleri ve kazanılan CAKE'in manuel olarak toplanması ve bileşiklenmesi gerekir.
{% endhint %}

### &#x20;⓸ Geçmiş Fiyat <a href="#id-19cd815c-ef3d-496a-8469-fb0164f3946b" id="id-19cd815c-ef3d-496a-8469-fb0164f3946b"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28305%29.png)

Bu, seçilen çiftin geçmiş fiyat hareketini referans almanı sağlayan görüntüleme amaçlı bir bölümdür.

Geçmiş fiyat hareketlerini farklı zaman dilimlerinde inceleyebilir; örneğin fiyatın genellikle ne kadar dalgalandığını görerek daha yüksek APR ile daha düşük kalıcı olmayan kayıp riski arasında denge kuracak uygun bir fiyat aralığı ayarı belirleyebilirsin.

* MIN — minimum fiyat
* MAX — maksimum fiyat
* AVG — ortalama fiyat
* CURRENT — mevcut fiyat

{% hint style="info" %}
Fiyat grafiği yalnızca gerçek V3 çiftine ait verileri kullanır. Bu nedenle V3 dağıtımından önceki fiyat verileri mevcut değildir. Dört fiyat metriği, seçili zaman dilimini temsil eder ve seçime göre değişir.
{% endhint %}

### ⓹ Fiyat Aralığı <a href="#bbec6919-1404-4523-815e-063405a961f1" id="bbec6919-1404-4523-815e-063405a961f1"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/price-range.gif)

Bu bölümü kullanarak farklı fiyat aralıklarına ne kadar likidite yatırıldığını inceleyebilir ve likidite sağlamak istediğin fiyat aralığını belirleyebilirsin.

Başlığın altında dağılım grafiğini bulabilirsin. Likidite miktarı ne kadar büyükse grafik o kadar yüksek olur.

Fiyat aralığı ayarlarını şu şekillerde değiştirebilirsin:

* Grafikte minimum ve maksimum fiyat sınırını artırmak veya azaltmak için iki tutacağı sürükle.
* Seçili aralığı kaydırmak için iki tutacak arasındaki alana tıkla.
* Min ve maks fiyat alanlarındaki + ve - düğmelerine tıkla.
* Fiyat alanlarındaki sayılara tıklayıp manuel olarak gir.

Dağılım grafiğinde gezinmek istersen:

1. Yakınlaştırmak ve uzaklaştırmak için artı ve eksi büyüteç düğmelerini kullan.
2. Sola ve sağa kaydırmak için X (alt) eksenini sürükle.

Tüm fiyat aralığına likidite sağlamak istiyorsan "Tam Aralık"a tıkla.

### ⓺ Farklı baz ile fiyatları görüntülemek için fiyat yönünü değiştir <a href="#id-5c3bdfaf-bd66-4942-873d-d617eeeab53d" id="id-5c3bdfaf-bd66-4942-873d-d617eeeab53d"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/flip-directions.gif)

Bazı token çiftleri için fiyatları belirli baz tokenlarla görüntülemek daha kolay ve sezgiseldir. Örneğin BNB/USDT çifti için çoğu kişi "BNB başına kaç USDT" şeklinde görüntülemeyi tercih eder.

Fiyat görüntülemesini kolayca değiştirebilirsin. "Fiyatları şu şekilde görüntüle:" yazan düğmeye tıklayarak çiftteki iki token arasında baz değiştirebilirsin.

### ⓻ Ayarları içe ve dışa aktar (uygula) <a href="#d18cf936-315e-4432-a3a5-f65976651073" id="d18cf936-315e-4432-a3a5-f65976651073"></a>

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/apply-settings.gif)

ROI hesaplayıcısını "Likidite Ekle" penceresinde açtığında veya mevcut bir pozisyonu görüntülerken aşağıdaki ayarlar otomatik olarak içe aktarılır; bunları yeniden ayarlamana gerek kalmaz:

1. Yatırdığın varlık miktarı
2. Fiyat aralığı
3. Seçilen ücret kademesi

ROI hesaplayıcısında yapılandırmayı tamamladıktan sonra "Ayarları Uygula" düğmesine tıklayarak hesaplayıcıdaki ayarları "Likidite Ekle" penceresine hızlıca aktarabilir, bunları manuel olarak eşleştirmekten kurtulursun.

### ⓼ Farming ödülleri ve APR hesaplama <a href="#id-584c385b-5f76-42e5-8751-8344d6bd4749" id="id-584c385b-5f76-42e5-8751-8344d6bd4749"></a>

ROI hesaplayıcısını "Farm" sayfası üzerinden açarsan farming ödülleri hesaplamalara dahil edilir.

Ödül dağılımını görmek için ayrıntı bölümlerini genişletebilirsin.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28156%29.png" alt=""><figcaption></figcaption></figure>
