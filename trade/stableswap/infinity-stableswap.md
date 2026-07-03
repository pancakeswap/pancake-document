# Infinity StableSwap

### Genel Bakış

Infinity StableSwap, [PancakeSwap Infinity](https://docs.pancakeswap.finance/trade/pancakeswap-infinity) içinde aynı fiyattan işlem görmesi beklenen varlıkları takas etmek için optimize edilmiş bir havuz türüdür; stablecoin'ler (ör. USDC/USDT) veya sıkı sabitlenmiş varlıklar (ör. sarılmış token çiftleri, likit staking tokenları ve likit yeniden staking tokenları) bunlara örnek verilebilir.

Curve'ün StableSwap NG tasarımından ilham alınan Infinity mimarisi üzerinde çalışan bir StableSwap Hooks tarafından desteklenmektedir. Şu anda BNB Chain'de kullanılabilir olup ilerleyen dönemde ek zincirlere genişletilmesi planlanmaktadır.

***

### Nasıl Çalışır

Infinity StableSwap, sabit toplam ile sabit ürün arasında hibrit bir kararlı değişmez eğri kullanır:

* Sabitlemeye yakın → eğri sabit toplamına yakın davranır; bu da 1:1 civarındaki işlemler için çok düşük Kayma sağlar.
* Sabitlemeden uzakta → eğri kademeli olarak sabit ürüne doğru geçiş yapar; bu büyük dengesizlikler veya fiyat ayrışması olayları sırasında havuzu korumaya yardımcı olur.

Bu özelliği, sıkı fiyatlandırmanın ve düşük Kaymanın en çok önem taşıdığı kararlı çiftler için özellikle etkili kılar.

***

### Temel Özellikler

Sabitlemeye yakın Swap'lar için optimize edilmiştir: Yaklaşık olarak aynı fiyattan işlem görmesi beklenen varlıklar arasındaki işlemler için düşük Kayma.

Basit likidite sağlama: Likidite sağlayıcıları (LP'ler), CLAMM havuzlarının aksine fiyat aralıkları seçmek veya yönetmek zorunda kalmadan her iki tokeni de orantılı olarak yatırır.

ERC-20 LP tokenları: LP pozisyonun standart bir ERC-20 tokeni olarak temsil edilir; bu da getiri programları, puan kampanyaları ve diğer DeFi protokolleriyle kullanmayı kolaylaştırır.

Dinamik ücretler: Ücretler havuz denge koşullarına göre ayarlanabilir; havuzu dengeye doğru yardımcı olan işlemleri ödüllendirirken dengesizliği kötüleştirenleri caydırır.

Infinity yönlendirme desteği: İşlemler en iyi fiyatı sunduklarında otomatik olarak StableSwap havuzlarından yönlendirilir — traderlar için ekstra adım gerekmez.

Ayarlanabilir Yükseltme (A) parametresi: Havuz operatörleri değişen piyasa koşullarına uyum sağlamak için A parametresini zamanla yukarı veya aşağı artırabilir; ani değişiklikleri önleyen güvencelerle birlikte.

***

### Havuz Parametreleri

StableSwap havuz davranışı, genellikle havuz oluşturma zamanında belirlenen küçük bir parametre kümesi tarafından yönetilir.

#### Yükseltme Katsayısı (A)

A parametresi, havuzun 1:1 fiyat sabitlemesine ne kadar sıkı bağlı kaldığını kontrol eder.

| A değeri   | Etki                                                                                    |
| -------- | ------------------------------------------------------------------------------ |
| Daha yüksek A | Sabitleme etrafında daha sıkı eğri; 1:1'e yakın daha düşük Kayma; dengesizliğe daha duyarlı |
| Daha düşük A  | Daha gevşek eğri; standart sabit ürün havuzuna daha benzer davranır               |

Pratik kural: Güçlü ve güvenilir sabitlemeye sahip varlıklar için daha yüksek A kullan (ör. USDC/USDT). Daha gevşek veya daha oynak sabitlemelere sahip varlıklar için daha düşük A kullan (ör. bazı LST çiftleri).

A parametresi, belirli bir süre boyunca havuz operatörü tarafından kademeli olarak yukarı veya aşağı artırılabilir. Değişiklikler, manipülasyonu veya ani fiyat değişimlerini önleyen güvencelerle kademeli olarak uygulanır.

#### Sabitlemeden Sapma Ücreti Çarpanı

Havuz dengeden uzaklaştığında efektif ücretleri ayarlayan ek bir parametre. Havuzu daha da dengesiz hale getirecek işlemleri caydırmaya yardımcı olur ve havuzu piyasa baskısı veya fiyat ayrışması olayları sırasında daha sağlam kılar.

#### Dinamik Ücretler

Her Swap'ta alınan ve likidite sağlayıcılara ödenen bir ücret. Infinity StableSwap dinamik ücretleri destekler — yani belirli bir işlemdeki efektif ücret, havuzun mevcut durumuna göre değişebilir (ör. işlemin dengeyi iyileştirip iyileştirmediği veya kötüleştirip kötüleştirmediği).

***

### Infinity StableSwap - Classic StableSwap Karşılaştırması

PancakeSwap'ın mevcut StableSwap'ını daha önce kullandıysan, işte nelerin değiştiği — ve nelerin aynı kaldığı.

| <p><br></p>                 | Classic StableSwap                                        | Infinity StableSwap                                                |
| --------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------ |
| Fiyatlandırma eğrisi               | Kararlı değişmez (hibrit sabit toplam / sabit ürün) | Aynı kararlı değişmez eğri, sabitlemeye yakın aynı düşük Kayma            |
| ERC-20 LP tokenları            | ✅ Evet                                                     | ✅ Evet                                                              |
| Havuz oluşturma               | Operasyon yoğun; ekip tarafından manuel kurulum gerektirir              | İzinsiz — herkes havuz oluşturabilir                          |
| Swap ücretleri                   | Çift başına sabit (ör. USDC/USDT için %0,01)                 | Dinamik ücretler — işlemin havuz dengesini nasıl etkilediğine göre ayarlanır |
| Yükseltme (A) parametresi | Statik — bir kez belirlenir, değiştirilemez                      | Ayarlanabilir — zamanla kademeli olarak yukarı veya aşağı artırılabilir          |
| Sabitlemeden sapma ücreti çarpanı      | ❌ Desteklenmiyor                                           | ✅ Destekleniyor — fiyat ayrışması olayları sırasında havuzu korumaya yardımcı olur           |
| Gaz verimliliği              | Standart                                                  | İyileştirilmiş — Infinity'nin Singleton ve Flash Accounting'inden yararlanır |

#### Değişmeyen neler

* Temel fiyatlandırma eğrisi ve sabitlemeye yakın düşük Kayma davranışı değişmedi.

#### Yeni ve daha iyi olan neler

* İzinsiz Havuz Oluşturma: Havuzlar, manuel ekip kurulumu gerektirmeden izinsiz olarak oluşturulabilir.
* Dinamik ücretler LP'leri korur: Tek bir sabit ücret yerine ücret, işlemin havuz dengesine yardımcı olup olmadığına göre işlem başına ayarlanabilir — bu da havuzu oynaklık koşullarında daha dayanıklı kılar.
* Uyarlanabilir A parametresi: Yükseltme katsayısı, dağıtım sonrasında sonsuza kadar sabit kalmak yerine piyasa koşulları değiştikçe zamanla ayarlanabilir.

***

### Sık Sorulan Sorular

Infinity StableSwap için hangi varlıklar uygundur?

Aynı fiyattan işlem görmesi beklenen varlıklar: stablecoin'ler (USDC, USDT, BUSD, vb.), aynı varlığın sarılmış eşdeğerleri (ör. WBTC/cbBTC) ve bağ oynaklığının düşük olduğu seçili likit staking tokenları / likit yeniden staking tokenları (LST/LRT) çiftleri.

<br>

Infinity StableSwap, eski PancakeSwap StableSwap'tan nasıl farklı?

Infinity StableSwap, PancakeSwap Infinity üzerinde bir Hooks olarak uygulanmaktadır; bu da Infinity'nin tüm altyapı avantajlarını, Singleton ve Flash Accounting aracılığıyla daha düşük gaz maliyetleri ve daha esnek bir ücret sistemi dahil miras aldığı anlamına gelir. Ayrıca eski StableSwap'ın sunmadığı dinamik ücretler ve ayarlanabilir yükseltme gibi yeni özellikleri de destekler.

<br>

Pozisyonumu zamanla yönetmem gerekiyor mu?

Hayır. CLAMM'dan farklı olarak fiyat aralıkları belirlemeniz veya ayarlamanız gerekmez. Likiditeni her zaman tam eğri boyunca aktiftir; bu nedenle pozisyonunun "aralık dışına çıkma" riski yoktur.

<br>

Yalnızca bir tokenla likidite sağlayabilir miyim?

Evet, tek token yatırmaları desteklenmektedir.

<br>

Dinamik ücretler nasıl çalışır?

Infinity StableSwap'ta, Swap ücreti işlemin havuzun dengesini nasıl etkilediğine bağlı olarak işlem başına değişebilir. Havuzu dengeye geri döndürmeye yardımcı olan işlemler daha düşük efektif ücret ödeyebilirken, dengesizliği kötüleştiren işlemler daha yüksek ücret ödeyebilir. Bu, LP'leri korumak ve daha sağlıklı havuz koşullarını sürdürmek için tasarlanmıştır.



***



## Infinity StableSwap Havuzu Oluşturma



Infinity StableSwap havuzları izinsizdir — PancakeSwap ekibinden onay almadan herkes oluşturabilir.

<br>

### Adım adım

1\. Farm/Likidite sayfasına git ve Havuz Oluştur'a tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown.png" alt=""><figcaption></figcaption></figure>

<br>

2\. Havuz türü seçeneklerinden StableSwap Havuzu'nu seç.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%281%29.png" alt=""><figcaption></figcaption></figure>

<br>

3\. Havuzun için token çiftini seç (ör. USDC / USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%282%29.png" alt=""><figcaption></figcaption></figure>

<br>

4\. Havuz Parametreleri

| Parametre             | Ne işe yarar                                                                                                    |
| --------------------- | --------------------------------------------------------------------------------------------------------------- |
| Swap Ücreti              | Her Swap'ta alınan ve LP'lere ödenen ücret. Sıkı kararlı çiftler için varsayılan %0,01'dir.                                 |
| A (Yükseltme)     | Eğrinin sabitlemeye ne kadar sıkı bağlı kaldığını kontrol eder. Daha yüksek = 1:1'e yakın daha düşük Kayma, ancak dengesizliğe daha duyarlı. |
| Sabitlemeden Sapma Ücreti Çarpanı | Havuz dengeden uzaklaştığında ücretleri ölçekler; dengesizliği kötüleştiren işlemleri caydırır.                |
| Hareketli Ortalama Süresi   | Dinamik ücret ayarlamaları için hareketli ortalama fiyatı hesaplamak üzere kullanılan zaman penceresi.                             |

⚠️ Parametreleri dikkatli belirle. Hatalı parametreler — özellikle gevşek sabitlenmiş bir varlık için çok yüksek A — LP'ler için riski artırabilir. Emin değilsen varlık türün için ön ayarı kullan ve Gelişmiş ayarları değiştirmekten kaçın.

<br>

Bir Havuz Parametresi Ön Ayarı seç — bu, varlık türün için önerilen parametreleri otomatik olarak belirler. Yine de Gelişmiş geçişi aracılığıyla bunları manuel olarak ayarlayabilirsin.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%283%29.png" alt=""><figcaption></figcaption></figure>

| Ön Ayar                            | A    | Sabitlemeden Sapma Ücreti Çarpanı | Hareketli Ortalama Süresi (saniye) |
| --------------------------------- | ---- | --------------------- | ----------------------------- |
| Fiat Kurtarılabilir Stablecoin'ler       | 1000 | 10                    | 600                           |
| Kripto Teminatlı Stablecoin'ler | 100  | 12,5                  | 600                           |
| Likit Yeniden Staking Tokenları           | 500  | 10                    | 600                           |

<br>

&#x20; Hangisini seçeceğinden emin değil misin?&#x20;

* USDC/USDT gibi çiftler için Fiat Kurtarılabilir Stablecoin'leri kullan
* Algo veya kripto destekli stablecoin'ler için Kripto Teminatlı Stablecoin'leri kullan
* stkBNB/WBNB gibi LRT çiftleri için Likit Yeniden Staking Tokenları'nı kullan.

<br>

5\. Başlangıç likiditesini oluşturmak için yatırma miktarını gir. Her iki token miktarı eşit olmalıdır (ör. 1 USDC ve 1 USDT).

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%284%29.png" alt=""><figcaption></figcaption></figure>

<br>

6\. Havuzu Önizle'ye tıkla, ayarlarını gözden geçir, onay kutusunu işaretle ve ardından Havuz Oluştur'a tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/unknown%20%285%29.png" alt=""><figcaption></figcaption></figure>
