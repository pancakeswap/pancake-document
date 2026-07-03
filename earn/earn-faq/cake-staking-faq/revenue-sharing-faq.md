---
hidden: true
---

# Gelir Paylaşımı SSS

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-revenuesharing.png" alt=""><figcaption></figcaption></figure>

### Paylar (rCAKE) nasıl hesaplanır? <a href="#id-50b7c683-feb0-47f6-809f-39c1a0976bb5" id="id-50b7c683-feb0-47f6-809f-39c1a0976bb5"></a>

Her haftalık dağıtımda her kullanıcının payı şunlara göre yeniden hesaplanır:

1. Sahip oldukları kilitli CAKE miktarı
2. Kilitli CAKE'lerinin haftalara yuvarlanmış kalan kilit süresi ve izin verilen maksimum kilit süresi (şu an 52 hafta)

Örneğin:

Bir kullanıcının 50 CAKE kilitli olduğunu ve kalan kilit süresinin 10,3 hafta olduğunu varsayalım; kullanıcının `50 * (10 / 52) ~= 9,61` payı vardır.

### Pozisyonumu güncelledim; neden hâlâ 0 payım var? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Paylar (rCAKE), her Çarşamba 23:59 UTC'de yapılan haftalık dağıtımda güncellenir. Güncellenmiş paylarını görmek için bir sonraki haftalık dağıtımdan sonra tekrar kontrol et.

### Aktif bir staking pozisyonum olmasına rağmen neden paylarım sıfır? <a href="#id-9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="id-9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Paylar (rCAKE) hesaplanırken kalan kilit süresi haftalara aşağı yuvarlanır. Bu nedenle pay alabilmek için staking pozisyonunun bir sonraki dağıtımdan daha erken açılmadığından emin olmalısın.

Örneğin 1. hafta dağıtımı için pay alabilmek için şunlar gereklidir:

* 2 Ağustos 23:59 UTC'den önce katıl.
* 9 Ağustos 23:59 UTC'den sonra açılan aktif bir sabit vadeli CAKE staking pozisyonuna sahip ol.

Staking pozisyonun 9 Ağustos 23:59 UTC'den önce açılıyorsa 1. hafta için 0 pay alırsın.

### Bir dağıtım dönemine hafta ortasında katılabilir miyim? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Hayır, belirtildiği üzere paylar dağıtım döneminin başında her hafta Çarşamba 23:59 UTC'de hesaplanır. Bu nedenle bir sonraki dağıtımdan itibaren pay alacak ve o zamandan ödüller biriktirmeye başlayacaksın.

### Daha fazla pay nasıl alabilirim? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Paylar CAKE miktarına ve kalan kilit süresine göre hesaplandığından daha fazla pay almak için şunları yapabilirsin:

* Daha fazla CAKE kilitle
* Staking pozisyonunu uzat

CAKE ekledikten veya uzattıktan sonra payların gerçek zamanlı olarak güncellenMEdiğini ve yalnızca her haftalık dağıtımda güncellendiğini unutma.

### CAKE eklerken veya staking'i uzatırken staking pozisyonumu güncellemem gerekiyor mu? <a href="#id-71d1d397-ac1c-454b-abd9-15492860f05c" id="id-71d1d397-ac1c-454b-abd9-15492860f05c"></a>

Hayır, yalnızca bir kez kayıt olman yeterlidir. Sonraki tüm CAKE staking havuzu işlemleri otomatik olarak gelir paylaşımı havuzunu bilgilendirecek ve bir sonraki haftalık dağıtımda paylarını güncelleyecek.

### Neden haftalık enjekte edilen ödüller çeşitli takip araçlarında (Info sayfası gibi) görüntülenen hacimle %100 eşleşmiyor?

Haftalık enjekte edilen CAKE ödüllerinin sayısı, çeşitli takip araçlarında görüntülenen hacimden hesaplanan rakamlarla %100 eşleşmeyebilir. Birden fazla dış faktör dönüştürülebilecek CAKE ödüllerinin sayısını etkileyebilir:

* İşlem ücreti dönüştürülürken ve işlenirken CAKE token fiyatı
* İşlem ücreti dönüştürülürken ve işlenirken temel varlık fiyatları
* Gas ve operasyonel maliyeti tasarruf etmek için BNB Chain dışındaki blok zincirlerden elde edilen gelirler aylık olarak işlenir. Haftalık ortalama alınarak bir aylık gecikmeyle enjekte edilirler.
* Bazı işlem çiftlerinin işlem ücreti işlenirken yetersiz likiditeye sahip olması.
* Bazı işlem çiftlerinin ücretlerinin işlenmesini önleyen özel mantığa sahip token'lar içermesi.

Chefs, daha fazla işlem ücretinin işlenip CAKE'e dönüştürülebilmesi için araçlar ve uygulamalar üzerinde çalışmaya devam ediyor.
