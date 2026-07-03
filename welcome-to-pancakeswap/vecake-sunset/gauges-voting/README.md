---
description: CAKE emisyonunun nasıl dağıtılacağına karar vermek için veCAKE'ini kullan
hidden: true
---

# Gauges Voting

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2811%29.png" alt=""><figcaption></figcaption></figure>

#### Gauge nedir?

Gauges Voting'i anlamak için CAKE emisyonu gerektiren herhangi bir ürünü bir dizi gauge olarak düşünebilirsin. Bunlar arasında farmlar, CAKE haftalık ödül havuzu, pozisyon yöneticisi kasaları vb. yer alır.

veCAKE sahipleri artık CAKE'in hangi ürüne ne kadar % gideceğine karar vermek için veCAKE'lerini oy olarak kullanabilirler. Bir gauge, Gauges Voting aracılığıyla ne kadar fazla veCAKE biriktirirse, temel likidite havuzuna/pozisyon yöneticisi kasasına o kadar fazla CAKE emisyonu tahsis edilir.

{% hint style="info" %}
Her epoch'taki (E-0) oylar, bir sonraki epoch (E+1) için CAKE emisyonunu belirler ve bu değişiklikler yalnızca mevcut epoch sona erdikten sonra yürürlüğe girer.
{% endhint %}

#### Gauge Türleri

İki tür gauge bulunuyor: 'core' ve 'non-core'. Birincisine yapılan CAKE emisyonları Mutfak tarafından kontrol edilirken, topluluk 'non-core' havuzlara yapılan emisyonları veCAKE ile oy kullanarak etkiler.

1. 'Core' gauge'lar, başlıca token'lar ve stablecoin'lerle (WBTC, ETH, BNB, USDC, USDT vb.) eşleştirilmiş çiftleri içerir. Mutfak ekibi, bu çiftlerin protokol gelirine önemli ölçüde katkıda bulundukları için yeterli CAKE ödülleri almalarını sağlayacak.
2. 'Non-core' gauge'lar, 'core' gauge olarak sınıflandırılmayan diğer tüm gauge'ları temsil eder.

## Nasıl Oy Kullanılır?

### 1 - Oylama programını anla

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

Gauge ağırlık oylaması her iki haftada bir yapılır. Gelir paylaşımında olduğu gibi epoch başlangıcı, her çift Perşembe UTC 00:00'dadır.

Yukarıdaki örnekte:

* Epoch 1, 1. Haftanın ilk Perşembesi UTC 00:00'da başlar.
* Epoch 1, 2 hafta sonra, 3. Haftanın 15. Perşembesi UTC 00:00'da sona erer.
* Kullanıcılar 1. ile 14. gün arasında UTC 00:00'dan itibaren oy kullanabilir.
* Oylar düzenleniyor ve sayılıyor olduğundan 14. ile 15. gün arasında UTC 00:00'da **hiç** oy kullanılamaz.
* Oylama sonuçları, Epoch 1'in sonu olan 15.'de UTC 00:00'da anlık görüntüyle kaydedilir.
* Oylama sonuçları, epoch sona erdikten sonraki 72 saat içinde uygulanır.

### 2 - Uygun hale gel

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2812%29.png" alt=""><figcaption></figcaption></figure>

veCAKE kalan kilit süresine göre kademeli olarak azaldığından, oylama sonuçları her epoch'un sonunda anlık görüntüyle alınır. Bu, toplam veCAKE sayısını ve her kullanıcının sahip olduğu veCAKE miktarını kapsar.

Yukarıdaki örnekte:

* Epoch 1'in sonuçları, UTC 00:00'daki 15.'deki veCAKE bakiyelerine göre belirlenir.
* veCAKE pozisyonu 15. tarihinde veya daha önce açılan kullanıcıların, anlık görüntü anında veCAKE bakiyesi 0 olacaktır. Bu nedenle Epoch 1 için oy güçleri yoktur.

Bu nedenle uygun olmak için, mevcut epoch'un bitiş/anlık görüntü zamanından **SONRA** açılan aktif bir veCAKE pozisyonuna sahip olman gerekir.

Yukarıdaki örnekte:

* Epoch 1'de oy kullanmak istiyorsan, 21. veya daha sonraki bir tarihte ya da 3. haftanın Perşembesinde açılan bir veCAKE pozisyonuna sahip olman gerekir.

### 3 - Mevcut oylama sonuçlarını kontrol et

"CAKE staking" sayfasına git, aşağı kaydır ve "Gauges Voting" bölümünü bul, ardından "Gauge'leri Kontrol Et"e tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2813%29.png" alt=""><figcaption></figcaption></figure>

Sol üst bölümde şunları bulabilirsin:

* veCAKE miktarın.
* Mevcut epoch için anlık görüntü zamanı ve oylama bitiş zamanı.
* Mevcut epoch'un oylama sonuçlarına göre bir sonraki epoch'ta dağıtılacak toplam CAKE ödül sayısı.
* Kullanılan toplam veCAKE oy sayısı.

Sağ üst kısımda her gauge'ın aldığı % oranını gösteren bir pasta grafik bulunuyor.

Alt kısımda, mevcut epoch'ta kazandıkları oy sayısını ve beklenen % ağırlığını gösteren tüm oylama gauge'larının eksiksiz listesi yer alıyor. Ayrıca iki önemli gauge özelliğini ayrıntılandıran "boost" ve "caps" alanları da bulunuyor. Daha fazla ayrıntı için okumaya devam et.

#### Gauge Boost ve Emisyon Sınırları

CAKE ödüllerinin en verimli gauge'lara gitmesini sağlamak için her gauge'a boost ve/veya emisyon sınırı uygulanabilir. Bu iki özellik aynı anda da var olabilir.

Gauge Boost, bir gauge'ın aldığı oy sayısına uygulanan ve 1x ile 2,5x arasında değişen bir çarpandır (V3 havuzlarına ait gauge'lar 2x ile sınırlandırılmıştır). Bu, önemli işlem çiftleri için oyları ve likiditeni teşvik etmek amacıyla kullanılır.

Emisyon sınırı, bir gauge'ın alabileceği % ağırlığının maksimum sınırıdır ve %2 ile %20 arasında değişir. Bu, dağıtımda adilliği teşvik etmek ve gauge sisteminin suistimalini önlemek amacıyla kullanılır.

Örneğin:

* Bir gauge'ın 10 oyu, 2x boost'u ve %15 sınırı var. Toplam oy sayısı 100.
* Boost uygulandıktan sonra bu gauge'ın toplam (100) oylara karşı 20 oyu, %20 ağırlığı olacak.
* Ancak %15 sınırı olduğundan, bu gauge'ın bir sonraki epoch'ta alacağı CAKE ödüllerinin nihai % oranı %15 olarak ayarlanacak.

#### Gauge Boost ve Emisyon Sınırları nasıl belirlenir?

Gauge başvuru sürecinde başvuru sahiplerinden gauge'a atamak istedikleri boost çarpanı değerini ve emisyon sınırı %'sini önermeleri istenir. Bunların, tüm gauge başvurusuyla birlikte veCAKE sahipleri tarafından oylanması gerekir.

Tüm gauge'lar için varsayılan seçenek 1,00x çarpan ve %5 emisyon sınırıdır. Bunlar gelecekteki önerilerle değiştirilebilir.

{% hint style="info" %}
Oylama sonuçlarının haftalık olarak güncellendiğini lütfen unutma. Sayılar, yaklaşan Perşembe UTC 00:00'daki veCAKE bakiyelerine göre hesaplanır.
{% endhint %}

### 4 - Oy vermek için gauge ekle

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2814%29.png" alt=""><figcaption></figcaption></figure>

Bir gauge'a oy vermek için aşağı kaydır ve "Oylarım" bölümünü bul. "Gauge Ekle"ye tıkla.

Açılır pencerede mavi "+" ikonuna tıklayarak oy listenize gauge ekleyebilirsin. Listede mevcut oylama sonuçlarını, boost ve sınırları görebilirsin.

Bir gauge'ı hızlıca bulmak için blok zincirleri, ücret kademeleri ve likidite türlerine göre filtreleme yapabilir ya da arama alanına token ticker'ını yazabilirsin.

### 5 - Her gauge için ne kadar % veCAKE kullanacağını seç

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2815%29.png" alt=""><figcaption></figcaption></figure>

Gauge'ları ekledikten sonra, veCAKE'inin ne kadarının her gauge'a gideceğini seçebilirsin.

Bunun nedeni şudur:

* veCAKE kalan kilit süresiyle birlikte kademeli olarak azalır. Tam olarak kaç veCAKE oylayacağını tahmin etmek ve hesaplamak pratik değildir.
* Her yaklaşan epoch'ta yeniden oy vermek zahmetlidir. Bu nedenle gauges oylaması, oy kararlarının yeni bir oy yapılana kadar tüm gelecek epoch'lara taşınacak şekilde tasarlanmıştır.

Yukarıdaki örnekte:

* Şu anda 2,62 veCAKE'm var.
* CAKE-BNB'ye %80 ayırmaya karar verdim; bu şu an için 2,10 veCAKE.
* USDC-ETH'ye %20; bu da şu an için 0,52 veCAKE.
* Toplam veCAKE'm kalan kilit süresiyle birlikte kademeli olarak azalacak. Anlık görüntü anında daha az veCAKE'm olabilir, ancak %80 - %20 kararım nihai sonuçlara uygulanmaya devam edecek.
* Üstelik, yeni bir oy talebi göndererek güncelleme yapana veya kilit açılması nedeniyle veCAKE'm sıfıra düşene kadar bu %80 - %20 kararı her gelecek epoch'a uygulanacak.

Kararını onayladıktan sonra "Oyu Gönder"e tıkla ve cüzdanda onayla.

### 6 - Oylarını güncelle

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2817%29.png" alt=""><figcaption></figcaption></figure>

Oyun gönderildikten sonra oylarının "Mevcut Oylar" olarak güncellendiğini ve kalan veCAKE'in güncellendiğini görebilirsin.

Her gauge için oylama kararının yalnızca 10 günde bir güncellenebileceğini unutma. Bir oy talebi gönderdikten sonra, oylanmış tüm gauge'lara güncelleme için başka bir talep göndermeden önce 10 günlük bir bekleme süresi uygulanır.

Oy kararını güncellemek için % oranını değiştir ve yeniden gönder.

{% hint style="info" %}
CAKE ekleyerek veya kilit süresini uzatarak daha fazla veCAKE kazandıktan sonra tüm gauge'ları oy talebini yeniden göndererek manuel olarak güncellemenin gerektiğini lütfen unutma.

% kararlarını değiştirip değiştirmediğinden bağımsız olarak 10 günlük bekleme süresi geçerlidir.
{% endhint %}
