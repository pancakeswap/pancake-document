---
description: Trading Reward SSS
---

# SSS

{% hint style="danger" %}
\[Arşivlendi] Trading Reward – 23 Ağustos 2024 itibarıyla
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/faq-tradingreward.png" alt=""><figcaption></figcaption></figure>

## Genel

#### İşlem hacmim neden takip edilmedi?

* Hacim rakamlarının güncellenmesi zaman alır ve SubGraph gecikmelerine tabidir. Lütfen daha sonra tekrar kontrol et
* İşlemin, ücret kademesi dahil [Trading Reward sayfasında](https://pancakeswap.finance/trading-reward#rewards-breakdown) vurgulanan **tam** işlem çifti üzerinden yönlendirilmesi gerekir. İşlem rotalarını nasıl görüntüleyeceğine dair [bu rehbere](https://docs.pancakeswap.finance/products/pancakeswap-exchange/fees-and-routes#check-the-fee-rate-and-fee-amount-that-is-currently-applied) göz at
* Bu program için yalnızca V3 işlem çiftleri uygundur
* Lütfen hem Ethereum hem de BNB Chain'de Trading Reward programına uygun aynı cüzdan adresini kullan
* Bir çift içindeki işlem hacmin çok küçükse herhangi bir ödül talep etmeye uygun olmayabilirsin
* Üçüncü taraf işlem toplayıcılarını kullanmak, işlemlerin diğer likidite sağlayıcılarına yönlendirilmesine ve takip edilememesine yol açabilir

#### Çok fazla işlem yaptım ama neden çok az ödül aldım?

Trading Reward miktarı, söz konusu işlemlerde ödenen işlem ücretine dayanır.

İşlemlerin örneğin %0,01 gibi düşük ücretli çiftler üzerinden yönlendiriliyorsa işlemin için çok küçük bir ücret ödüyorsun. Bu nedenle ödül miktarı da buna göre düşer.

## Top Traders Kampanyası

#### Kampanyayı kazanmak için tüm süre boyunca gerekli sıralamada kalmam gerekiyor mu?

Hayır, yalnızca **kampanyanın sonunda** gerekli sıralamanın üzerinde olman yeterlidir. Ancak daha yüksek sırada olman ve sıramı koruması önerilir. Gerekli sıralamanın dışına düşmediğinden emin olmak için sık sık kontrol etmeyi unutma.

#### Sıralama neye göre belirlenir?

Sıralama, her kullanıcının işlem yaparak biriktirdiği ödül miktarına göre belirlenir. Ödül miktarı, işlemlerde ödedikleri ücretin sabit bir yüzdesine eşittir.

## CAKE Stakers Kampanyası

#### Adresim önceki kampanya için uygundu. Neden en son kampanya için uygun değil?

Her kampanyanın, anlık görüntü zamanındaki minimum veCAKE miktarı eşiği gibi kendine özgü uygunluk gereksinimleri vardır.

Ayrıca anlık görüntü zamanı, her kampanyanın bitiş zamanı olarak belirlenir. veCAKE zamanla azaldığından veCAKE bakiyen gelecekteki kampanyalar için eşiğin altına düşebilir.

veCAKE'ini artırman gerekebilir. Sayfadaki talimatları takip etmen yeterlidir.

#### Neden talep edilemeyen ek ödüllerim olduğu yazıyor?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28227%29.png)

Anlık görüntü zamanındaki veCAKE miktarı, kampanyadan kazanabileceğin maksimum ödül miktarını belirler. "Maksimum Ödül Üst Sınırı" bölümündeki dipnota bakabilirsin.

Kampanya aktifken veCAKE'ini artırabilir ve bu üst sınırı istediğin zaman yükseltebilirsin.

#### "Anlık görüntü zamanındaki veCAKE" nedir?

veCAKE, kalan kilit süresi azaldıkça zamanla giderek düşer. Bu nedenle IFO iCAKE'e benzer şekilde, belirli bir zamandaki (statik olan) veCAKE bakiyesi olan anlık görüntü veCAKE bakiyesi, yeterlilik ölçütü olarak kullanılmak için daha uygundur.

Trading Reward'da anlık görüntü zamanı, her kampanyanın bitiş tarihini ifade eder. Dolayısıyla "anlık görüntü zamanındaki veCAKE bakiyen", "kampanya bitiş zamanındaki veCAKE bakiyen" anlamına gelir.

#### "Anlık görüntü zamanındaki veCAKE" kampanyayla nasıl ilişkilidir?

* Anlık görüntü zamanındaki veCAKE bakiye sayın gerekli eşiğin üzerinde olmalıdır
* Kazanabileceğin maksimum ödül miktarı, anlık görüntü zamanındaki veCAKE bakienin y%'siyle bağlantılıdır

Örneğin:

1. Alice 1. günde 300 CAKE'i 2 yıl (104 hafta) süreyle kilitledi. 1. günde Alice'in veCAKE bakiyesi `300 * 104 * 7 * 24 * 60 * 60 / 126403199 ~= 149` olacak.
2. 1. günde 100 veCAKE eşiğiyle ve %1 ödül üst sınırıyla bir Trading Reward kampanyası başlatıldı. Kampanya 30 gün sonra sona eriyor.
3. 30 gün sonra Alice'in pozisyonunda yaklaşık 99,71 haftalık kalan kilit süresi olacak ve bu nedenle `300 * 99.71 * 7 * 24 * 60 * 60 / 126403199 ~= 143` veCAKE bakiyesi bulunacak.
4. Bu nedenle bu kampanya için Alice'in anlık görüntü zamanındaki veCAKE'i `143` olacak.
5. 143, 100'den büyük olduğundan Alice kampanyaya katılmaya uygundur ve Trading Reward kazanmak için uygun çiftlerde işlem yapmaya başlayabilir.
6. %1 ödül üst sınırıyla Alice'in bu kampanyadan kazanabileceği maksimum CAKE miktarı `143 * %1 = 1,43` CAKE olacak.
7. Alice, kampanya sona ermeden önce istediği zaman veCAKE'ini artırabilir; daha fazla CAKE kilitleyerek ya da pozisyonunu uzatarak.

#### Kampanya süresince anlık görüntü zamanındaki veCAKE'imi nasıl kontrol edebilirim?

Trading Reward sayfasından kontrol edebilirsin.

Anlık görüntü zamanındaki veCAKE'in eşiğin altındaysa veya ödüllerin şu anda onun tarafından sınırlandırılıyorsa sayfa seni uyaracaktır.

Bu durumlarda, sayfadan ayrılmadan veCAKE'ini artırmak için "veCAKE'ini Artır" düğmesine tıklayabilirsin.

#### Kampanya süresince veCAKE'imi artırabilir miyim?

Evet, kampanya sona ermeden önce istediğin zaman veCAKE'ini artırabilirsin. "Anlık görüntü zamanındaki veCAKE'in" buna göre güncellenecektir.
