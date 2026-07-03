# Infinity CLAMM & LBAMM

#### 🔷 CLAMM (Yoğunlaştırılmış Likidite AMM)

CLAMM, likidite sağlayıcılarının sermayelerini **belirli fiyat aralıkları** içinde tahsis etmesine olanak tanır. Bu şunlara yol açar:

* **Daha yüksek sermaye verimliliği**: Aktif işlem fiyatlarında daha fazla likidite.
* **Daha derin likidite**: Yatırımcılar için daha iyi gerçekleştirme.
* **Aktif LP yönetimi**: LP'lerin fiyat hareketlerine göre pozisyonlarını ayarlaması gerekir.
* Aralık dışı pozisyonlar için daha yüksek **kalıcı olmayan kayıp** potansiyeli.

{% hint style="info" %}
CLAMM, sabit çarpım formülü üzerinde çalışır (X \* Y = K). Her likidite pozisyonu, değiştirilemez ve NFT olarak temsil edilir.
{% endhint %}

#### 🔷 LBAMM (Likidite Defteri AMM veya "Bin Havuzu")

LBAMM, her biri belirli bir fiyat seviyesinde likidite tutan **ayrık fiyat bin'lerini** uygular. LBAMM, **sabit toplam formülünü (X + Y = K)** takip eder.



**Temel özellikler:**

* Bir bin içinde **0 fiyat etkisi** ile işlemler.
* **Değiştirilebilir likidite** (her bin içindeki likidite bir ERC-20 token'ıdır).
* LP pozisyonlarını ayarlamak için **daha düşük gaz maliyetleri**.
* **Farklı likidite şekillerini destekler** (ör. çarpık, tekdüze).
* Bin başına düz fiyatlandırma eğrisi nedeniyle **düşük oynaklıklı** çiftler için daha uygundur.

> 🥞 **PancakeSwap, hook'larla LBAMM havuzları sunan ilk protokoldür.**

{% hint style="success" %}
Hem CLAMM hem de LBAMM havuzları, geliştiricilerin havuz davranışını özelleştirmesine olanak tanıyan **hook'ları** destekler. Havuz türleri, protokol yeniden dağıtımı gerektirmeden eklenebilecek yeni Havuz Yöneticileri aracılığıyla genişletilebilir.
{% endhint %}

<table data-header-hidden><thead><tr><th width="170.94921875"></th><th width="284.57421875"></th><th></th></tr></thead><tbody><tr><td>Özellik</td><td><strong>CLAMM</strong></td><td><strong>LBAMM</strong></td></tr><tr><td><strong>Fiyatlandırma Eğrisi</strong></td><td>Sabit Çarpım (X * Y = K)</td><td>Sabit Toplam (X + Y = K)</td></tr><tr><td><strong>Likidite Token'ı</strong></td><td>Değiştirilemez (NFT)</td><td>Değiştirilebilir (bin başına ERC-20)</td></tr><tr><td><strong>En İyi Kullanım</strong></td><td>Hem yüksek hem de düşük oynaklıklı çiftler</td><td>Düşük oynaklıklı çiftler</td></tr><tr><td><strong>Avantajlar</strong></td><td><ol><li>Sermaye verimliliği</li><li>Geniş/tam aralıkta gaz verimliliği</li><li>Yaygın benimseme</li></ol></td><td><ol><li>Bin içinde 0 fiyat etkisi</li><li>Daha ucuz LP yönetimi</li><li>Esnek likidite şekilleri</li></ol></td></tr><tr><td><strong>Hook Desteği</strong></td><td>✅</td><td>✅</td></tr></tbody></table>

***

### 🧮 Ücretler

PancakeSwap Infinity, Statik ve Dinamik ücret ayarları aracılığıyla esnek ve genişletilebilir bir ücret sistemi destekler. Bu yapı, hem havuz oluşturucularına hem de LP'lere farklı işlem stratejileri ve risk profilleri için optimize etme gücü verir.

#### 🔁 Dinamik Ücretler

* Dinamik Ücretler, hook sözleşmeleri aracılığıyla gerçek zamanlı olarak belirlenir.
* Bu ücretler, oynaklık, işlem hacmi, kullanıcı durumu (ör. CAKE varlıkları) veya hook'a kodlanmış özel mantık gibi harici faktörlere göre dalgalanabilir.
* Dinamik ücretlere sahip havuzlar, havuz oluşturulurken bu ayarı etkinleştirmeli ve `beforeSwap` aracılığıyla ücretleri değiştirebilen bir hook eklemelidir.
* Bir havuz başlatıldıktan sonra ücret türü (dinamik veya statik) değiştirilemez.

Dinamik ücretler maksimum esneklik sunar ve hem LP'ler hem de Swap yapanlar için piyasa koşullarına göre ücret yapılarını optimize eder.

#### 📌 Statik Ücretler

* Statik Ücretli havuzlar, havuz oluşturulurken belirlenen sabit bir ücrete sahiptir.
* Bu ücretler, havuz başlatıldıktan sonra değiştirilemez.
* Daha basit kullanım durumları için veya ücret yapısının öngörülebilir olmasının önemli olduğu durumlarda uygundur.<br>

**🔒 Maksimum Ücret Tavanları:**

* CLAMM Havuzları: %100'e kadar (çoğunlukla uzmanlaşmış veya deneysel kullanım durumları için)
* LBAMM Havuzları: %10 ile sınırlı<br>

**🏛 Protokol Ücreti (statik ücretli havuzlar için):**

* PancakeSwap, Infinity havuzlarına protokol ücreti uygular
* LP ücretinin %33'ü, %0,4 ile sınırlı

| **LP Ücreti**    | **Protokol Ücreti** |
| ---------------- | ------------------- |
| %1               | %0,33               |
| %2               | %0,4 (sınırlı)      |
| Dinamik Ücretli Havuz | %0               |

#### 🛠️ Havuz Oluşturucular için Kurulum Notları

* Bir havuzu PoolManager aracılığıyla başlatırken oluşturucu şunları seçmek zorundadır:
  * Havuzun statik mi yoksa dinamik ücret mi kullandığı
  * Bir hook sözleşmesinin eklenip eklenmediği (dinamik ücretler için zorunludur)

Bu ayarlar kalıcıdır ve havuzun ömrü boyunca nasıl davranacağını tanımlar.
