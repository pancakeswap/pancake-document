# SSS

{% hint style="info" %}
Sorularının yanıtlarını hızlıca bulmak için kenar çubuğunu kullan!
{% endhint %}

## Limit Emirleri ve TWAP

Lütfen Orbs tarafından sağlanan SSS'ye bakın:

[https://www.orbs.com/dtwap-and-dlimit-faq/](https://www.orbs.com/dtwap-and-dlimit-faq/)

## Limit V2 (Kullanımdan Kaldırıldı)

### Emirlerimi neden bulamıyorum?

V2 limit emirleri artık kullanımdan kaldırılmıştır; lütfen şu bağlantıyı kullanarak eriş:

[https://pancakeswap.finance/limit-orders](https://pancakeswap.finance/limit-orders)

### Emirim neden gerçekleştirilmedi?

Limit emirler hedef fiyata ulaştıklarında gerçekleştirilir; ancak gaz dalgalanmaları nedeniyle gerçek gerçekleştirme fiyatı arayüzde belirlediğin fiyattan farklı olabilir. Genellikle gerçekleştirme fiyatı ile istenen fiyat neredeyse aynı olmalıdır; ancak özellikle küçük bir emir (~<1000 $) verdiysen gerçekleştirme fiyatı ücretleri karşılamak için biraz daha yüksek olabilir.&#x20;

Bu nedenle emrin gerçekleştirilmeyebilir çünkü:

* İstenen fiyat ve miktarda fiyat etkisi nedeniyle tüm emri doldurmak mümkün olmadı.
* Limit emirdeki tokenlardan birinde transfer ücreti var (aşağıya bak).

**Bir emir göndermeden önce lütfen arayüzdeki gerçek gerçekleştirme fiyatına bakın.**

{% hint style="info" %}
Lütfen dikkat: emir geçmişi tablosu verileri Subgraph'tan alır ve biraz gecikmeli bilgi gösterebilir.
{% endhint %}

### Transfer ücreti olan tokenlar için limit emri verebilir miyim?

**Hayır.** Transfer ücreti olan tokenlar limit emirlerle kullanılmamalıdır. Kendi riskini üstlenerek devam et.

### Limit emirleri kullanırken Kayma nasıl ayarlanır?

Limit emirlerde Kayma geçerli değildir. Girdi miktarını (ör. 1000 CAKE) ve çıktı miktarını (ör. 20 BNB) belirtirsin; limit emirler, çift fiyatı istenen fiyata ulaşırsa girdi miktarın için (1000 CAKE) belirtilen çıktı miktarından (20 BNB) az almayacağını garanti eder. **Transfer ücreti olan tokenların limit emirlerle kullanılmaması gerektiğini unutma** (yukarıyı oku)

### Gerçek gerçekleştirme fiyatı "asla gerçekleşmez" diyor. Bu ne anlama geliyor?

Temel olarak çok küçük miktarda token takas etmeye çalışıyorsun; bu yüzden gaz ücretini karşılamak için yeterli token yok. Genel olarak, bu hatadan kurtulmak için "girdi" alanındaki miktarı artırman gerekiyor.&#x20;

### Limit emirlerimin son kullanma tarihi var mı?

Açık emirlerin son kullanma tarihi 90 gündür. Emrin sona erdikten sonra asla gerçekleştirilmeyebilir. Lütfen sona eren emirleri iptal et.&#x20;

Özelleştirilebilir son kullanma tarihi özelliği yakın gelecekte planlanmaktadır.

### Neden piyasa fiyatının altında limit emri veremiyorum?

Piyasa fiyatının altında satış yapmak için limit emirlere değil, **Stop Limit Emirlere** ihtiyacın var. Stop Limit Emirleri özelliği yakında geliyor.

### Bir emir verdim ve emir tablosunda görünmüyor veya "beklemede" durumunda takılı kaldı.

Emir geçmişi subgraph'tan geliyor ve bu nedenle biraz gecikmeli bilgi gösterebilir. Genellikle gecikmeler en kötü ihtimalle birkaç dakikayı aşmaz. Lütfen emir geçmişi tablosunun sağ alt köşesindeki subgraph göstergesine bakın.
