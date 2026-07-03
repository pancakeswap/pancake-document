---
description: Tek tıklamayla likidite ekleme
---

# Zap

### Zap Nedir <a href="#id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd" id="id-27eed32c-a46a-44f9-98ee-2a3f74e0dadd"></a>

Zap, kolayca likidite eklemenizi sağlayan bir özelliktir. Zap ile havuzda gereken token'lardan bağımsız olarak, bakiyende olan herhangi bir token ile likidite sağlayabilirsin. Sadece fiyat aralığını belirle, sağlamak istediğin miktarı seç ve işlemi gerçekleştir. Token'ların, en düşük fiyat etkisi ve Kayma ile en verimli şekilde takas edilirken likidite pozisyonunu oluşturacak şekilde otomatik olarak dengelenecektir.

### Desteklenen Zincirler

* v3 - BNB Chain'deki tüm havuzlar, Ethereum ve Arbitrum ağlarında seçili havuzlar
* Infinity - BNB Chain'deki tüm CLAMM havuzları (hook'suz)

### Nasıl Kullanılır <a href="#id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352" id="id-438fff0f-f1da-4147-9fe3-6dc1dc2ef352"></a>

Şu an için Zap şunları desteklemektedir:

* 🆕 Herhangi bir token!
* Tek token kullanarak
* 🆕 İkili token kullanarak
* 🆕 Ya da... birden fazla token kullanarak (evet, toz toplayıcı gibi kullanılabilir)

#### Başlangıç <a href="#e43d56cd-978e-4503-8b7a-974428d4142c" id="e43d56cd-978e-4503-8b7a-974428d4142c"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29.png" alt=""><figcaption></figcaption></figure>

Zap'ı kullanmak için Likidite Ekle sayfasına git, likidite sağlamak istediğin işlem çiftini, ücret kademesini ve fiyat aralığını seç.

Ardından likidite sağlamak istediğin token miktarını seç.

Bir veya daha fazla token'ın bakiyesi yetersiz olduğunda Zap seçeneği otomatik olarak belirecektir.

Zap penceresini açmak için bağlantıya tıkla.

#### Zap'ı Başlatma <a href="#d65281e2-90db-4280-afd0-f24157c88a9b" id="d65281e2-90db-4280-afd0-f24157c88a9b"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29.png" alt=""><figcaption></figcaption></figure>

Yeni "Zap ile gir" penceresinde aşağıdaki alanları bulacaksın:

1. Zap yaptığın (likidite sağladığın) işlem çifti.
2. Yatırım token'ı/token'ları ve yatırmak istediğin miktar/miktarlar. Zap için token ekleyip çıkarabilirsin.
3. Yeni pozisyonun fiyat aralığı. Farklı fiyat gösterimleri arasında geçiş yapmak için oklara tıklayabilirsin.
4. Zap özelliğinin yatırım token'larını nasıl işleyeceğine dair ayrıntılı döküm.
5. Şunları içeren bir istatistik özeti:
   1. Yeni likidite pozisyonu için tahmini USD değeri.
   2. Yeni likidite pozisyonundaki tahmini token miktarı.
   3. Zap sonrası tahmini kalan USD cinsinden miktar. Çoğu durumda 0 olmalıdır. Likidite havuzunun veya token'ların likiditesi çok düşükse bu değer artabilir.
   4. Zap sırasında token takasları ve yeniden dengelemeler için fiyat etkisi.
   5. Likidite ekleme ve pozisyon oluşturma için fiyat etkisi.
   6. Zap ücreti. Likidite çiftine bağlı olarak ücret oranı değişebilir.

{% hint style="warning" %}
Mevcut bakiyene göre Zap miktarını yeniden yapılandırman gerekebilir. Token'lardan birinde bakiyen yoksa lütfen o token'ı kaldır.
{% endhint %}

{% hint style="info" %}
"V3 Likiditesi Ekle" bölümündeki ayarların, yatırım miktarı ve fiyat aralığı ayarları dahil olmak üzere Zap penceresine otomatik olarak aktarıldığını fark edebilirsin.
{% endhint %}

#### Zap İşlemini Başlatma <a href="#id-6cc5fa08-d336-46d9-8fdd-199bcbae8267" id="id-6cc5fa08-d336-46d9-8fdd-199bcbae8267"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%282%29.png" alt="" width="375"><figcaption></figcaption></figure>

Son olarak "Onayla"ya tıkla ve token izni için cüzdan açılır penceresinde onayla.

Ardından nihai onay penceresini açmak için "Önizle"ye tıkla. Devam etmeden önce lütfen nihai onay penceresinde gösterilen tüm istatistik ve tahminleri dikkatle incele; özellikle etki rakamlarını ve maksimum Kayma'yı.

Son olarak "Likidite Ekle"ye tıkla ve cüzdan açılır penceresinde onayla.

İşlem onaylandıktan sonra yeni ve parlak pozisyonunu "Pozisyonum" sayfasında göreceksin.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### Daha Fazla Ayar <a href="#id-217348b6-db9d-4336-9060-d8cbd8171cd9" id="id-217348b6-db9d-4336-9060-d8cbd8171cd9"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29.png" alt="" width="375"><figcaption></figcaption></figure>

Zap deneyimini daha fazla özelleştirmek istiyorsan sağ üst köşedeki dişli simgesine tıkla. Ayarlarda şunları yapılandırabilirsin:

* Zap sırasındaki maksimum Kayma.
* İşlem son tarihi için zaman çizelgesi.
* Token yeniden dengeleme yaparken KyberSwap'ın toplanmış likidisitesini kullanıp kullanmayacağın. Yalnızca PancakeSwap Havuzlarında ticaret yapmak istiyorsan bunu kapat.
* Degen modu, son derece yüksek Kayma'lı Zap işlemleri gerçekleştirmek için kullanılabilir. Normal kullanım için önerilmez; kendi sorumluluğunda kullan.

{% hint style="warning" %}
Kayma ve Son Tarih ayarlarının Swap ve Likidite sayfasından bağımsız olduğunu lütfen unutma.
{% endhint %}

#### İkili token ile Zap

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Artık likiditeni ikili token ile Zap'layabilirsin. Bu, mevcut bakiyenin fiyat ayarlarıyla eşleşmediği ve talep ettiği token miktarı ve oranıyla uyuşmadığı durumlarda işe yarar. Sadece Zap'la, oran otomatik olarak yeniden dengelenecektir.

#### Çok sayıda token ile Zap

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>

Evet, tıpkı toz token toplayıcı gibi çalışır. Cüzdanındaki küçük bakiyeleri temizlemek ve bunları işlem ücretlerinden kazanmaya başlamak için bir pozisyona koymak için uygundur.&#x20;
