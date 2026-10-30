---
description: '2026-09-04'
---

# RWA Sermaye Verimsizliği — ve Shared Inventory Bunu Nasıl Çözer

Bir PancakeSwap vaka çalışması deneyi (Bölüm 1: Kurulum)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28217%29.png" alt=""><figcaption></figcaption></figure>

Bu, iki bölümlük vaka çalışmasının ilk bölümü. Bu bölümde RWA varlık ihraççılarının karşılaştığı gerçek sermaye verimliliği sorununu ortaya koyuyor, PancakeSwap'in Shared Inventory Hook'unun (SIH) bu sorunu nasıl çözmeyi amaçladığını tanıtıyor ve onchain verilerle test etmek için canlı bir vaka çalışması deneyini duyuruyoruz.

Önümüzdeki birkaç hafta içinde Bölüm 2: Sonuçlar'ı yayınlayacağız.

***

### 🧩 Sermaye Verimliliği Sorunu Nedir?

RWA sektörü tek bir rakamı çok sever: **ne kadarının tokenize edildiği.** Neredeyse her raporun manşeti bu - yeni bir varlık sınıfının gelişi, milyarlarca dolarlık ihraç, yüzlerce yüzde büyüme.

Ama gömülüp kalan ikinci bir rakam daha var ve bu belki daha belirgin bir sinyal: **bunun ne kadarı gerçekten işlem görebiliyor?**

Asıl mesele bu iki rakam arasındaki fark. Referans takipçi olan [rwa.xyz](http://rwa.xyz) üzerinde, onchain'de _temsil edilen_ değerin miktarı, herhangi bir anda karşısında _işlem yapılabilen_ miktarın çok ötesinde — veriler, kilitli, referans ve dağıtılmış değerin **işlem gören defterlerdeki değerden bir büyüklük mertebesinden fazla** olduğunu gösteriyor.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28380%29.png" alt=""><figcaption></figcaption></figure>

_Kaynak: app.rwa.xyz/stocks_

Bir RWA ihraççısı için tuzak tam olarak bu. Bir hisse senedini, ETF'yi veya tahvili tokenize etmek işin kolay kısmı - onun sıkı ve güvenilir şekilde işlem görmesini sağlamak ise asıl zorluk ve sermaye verimliliğinin kazanıldığı ya da kaybedildiği yer burası. Asıl hedef, trader'ların tokenize varlığı _gerçekten trade edebilmesini_ kolay ve ucuz hale getirmek - hacim ve ücretler nihayetinde buradan gelir.

Ve bunun neden sadece bir likidite değil, özellikle bir _sermaye verimliliği_ sorunu olduğunu şöyle açıklayabiliriz.

#### Fiyatlanan her havuz kendine özel bir USDT yığını ister

Geleneksel bir yoğunlaştırılmış likidite (CLAMM) havuzunda tek bir RWA paritesini işlem görebilir kılmak için ihraççıların, alıcıların satış yapabileceği özel bir quote varlığı — USDT — bulundurması gerekir. On parite listelerseniz CLAMM modeli **on ayrı USDT yığınının** fonlanmasını gerektirir; parite başına bir yığın ve hiçbiri diğerine yardım edemez. Böylece quote sermayesi, birbirinden yalıtılmış siloya bölünüp parçalanır.

Bunu kendi defterimizde ölçtük. **PancakeSwap'te canlı olan 7 tokenize hisse senedi havuzunu** (her biri geleneksel bir V3 CLAMM havuzu olarak çalışıyor) aldık ve özel USDT miktarını çıkardık.

Anlık görüntü: **2 Eylül 2026.**

<table data-search="false"><thead><tr><th>Parite</th><th>Havuzdaki özel USDT</th><th>Havuz TVL</th></tr></thead><tbody><tr><td>CRCLB / USDT</td><td>$352,836</td><td>$654,170</td></tr><tr><td>SPYB / USDT</td><td>$170,644</td><td>$355,677</td></tr><tr><td>SNDKB / USDT</td><td>$123,262</td><td>$227,068</td></tr><tr><td>GMEB / USDT</td><td>$64,323</td><td>$135,665</td></tr><tr><td>MUB / USDT</td><td>$19,146</td><td>$35,733</td></tr><tr><td>DRAMB / USDT</td><td>$11,041</td><td>$22,032</td></tr><tr><td>SOXLB / USDT</td><td>$4,082</td><td>$8,276</td></tr><tr><td><strong>Toplam</strong></td><td><strong>$745,334</strong></td><td><strong>$1,438,621</strong></td></tr></tbody></table>

Bu, özel olarak tahsis edilmiş **\~745 bin $ USDT** demek.

Üstelik bu sadece bir defteri olan isimler.

SNXXB, KORUB, SOXSB ve DJTB'nin hiç CLAMM USDT defteri yok — tokenize edilmişler ama işlem yapmak zor.

***

### 🎯 Bir İhraççı Neyi Optimize Etmeli?

Mekanikleri bir kenara bırakırsak, bir RWA ihraççısının özünde üç şeyi çözmesi gerekir:

1. **Varlığının gerçekten ve verimli şekilde işlem görebilmesi** — sadece amiral gemisi tokenlarda değil, her varlıkta sıkı fiyatlar.
2. **Bunun için bağlanan mümkün olan en az sermaye** — Quote varlığı pahalıdır; on USDT yığınını özel olarak fonlamak pek verimli değildir.
3. **Bir trading masası işletmemek —** Her gün likidite altyapısı işletmeye gerek kalmadan varlık ihraç edebilmek.

Yani asıl soru, likiditenin farklı yapılandırılıp yapılandırılamayacağı — ve PancakeSwap'in Shared Inventory Hook'u tam olarak bunu çözmek için tasarlandı.

***

### 🥞 Shared Inventory Hook (SIH)

**SIH, bir RWA ihraççısının her parite için ayrı bir özel yığın yerine tek bir ortak USDT havuzundan birçok pariteyi desteklemesini sağlayan bir PancakeSwap Infinity hook'udur.**

SIH bunu likiditeyi tam zamanında (just-in-time) sağlayarak yapar ve şunları mümkün kılar:

* Paritelerde daha derin fiyatlar
* Özellikle büyük işlemlerde daha düşük fiyat etkisi
* Daha az sermaye ile daha fazla parite fiyatlandığı için RWA ihraççıları için serbest kalan sermaye

Bu iddiaları pratikte görelim.

Aynı **2 Eylül 2026** anlık görüntüsüne göre SIH, tek bir hook'ta **635.028 $** envanter tutuyor, **180.467 $** ortak USDT ile **11 pariteyi** fiyatlıyor ve **%87,7** kullanım oranıyla çalışıyor. Bununla SIH, **17.299 işlemde 3,56 milyon $** hacim işledi.

Yani **\~700 bin $'lık tek bir ortak USDT bakiyesi \~11 pariteyi fiyatlıyor; karşılığında \~745 bin $ yalnızca 7 pariteyi fiyatlıyor**.

Aynı iş, sadece sermayenin tekrarlanmasını durduracak şekilde tasarlandı.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28381%29.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28395%29.png" alt=""><figcaption></figcaption></figure>

İhraççıların önem verdiği konulara eşlersek:

* Geleneksel olarak N adet özel USDT bakiyesi → ✅ SIH ile tek bir ortak havuz
* İhraç edilmiş ama işlem görmeyen → ✅ işlem görebilir\
  Canlı fiyatın etrafında just-in-time enjekte edilen ortak envanter, V3 USDT defteri olmayan tokenların da yalnızca mint edilmekle kalmayıp fiyatlanabilmesi anlamına gelir.
* Bir masa işletmek → ✅ yetkilendirilmiş bir operatör\
  İhraççı envanteri sağlar; hook ve operatörü fiyatlamayı üstlenir.

***

### 🔬 Shared Inventory Simulator'ı Dene

SIH'in nasıl davrandığını etkileşimli karşılaştırma aracımızla sezgisel olarak kavra **→** [https://pancakeswap-shared-inventory.netlify.app/](https://pancakeswap-shared-inventory.netlify.app/)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28406%29.png" alt=""><figcaption></figcaption></figure>

Bu, SIH'in geleneksel bir CLAMM defteriyle **üst düzey, normalleştirilmiş bir karşılaştırmasıdır** — sermaye verimliliği mekaniğinin net biçimde izole edilebilmesi için gerçek dünyadaki bir dizi etken iki tarafta da sabit tutulmuştur. Bu bir anlama modelidir, kâr-zarar tablosu (P\&L) değildir.

Üç sekme:

* **Simulator sekmesi** - envanter, aralık genişliği ve akışla oynayarak SIH'in farklı koşullarda benzer bir CLAMM havuzuna karşı nasıl performans _gösterebileceğini_ gör.
* **Comparison sekmesi** - SIH, aynı havuzlarda bir **PancakeSwap V3 CLAMM** defteriyle doğrudan karşılaştırılır; böylece ortak USDT havuzu ile özel USDT arasındaki fark, bağlanan sermaye ve kapsam açısından yan yana görülebilir.
* **Live data sekmesi** — bu çalışmaya güç veren onchain sorgulardan çekilen verilerle SIH'in şu anda _gerçekte_ nasıl performans gösterdiğini ölç.

Simulator, Shared Inventory Hook'un nasıl çalıştığını göstermeye yardımcı olmayı amaçlar. Dene, sonra önümüzdeki birkaç hafta içinde yayınlayacağımız gerçek sonuçlarla karşılaştır.

***

### 🧪 Deney

**Önümüzdeki birkaç hafta** boyunca SIH'i canlı çalıştırıyor ve onchain kaynaklar kullanarak yukarıdaki sermaye verimliliği iddialarına karşı ölçüyoruz. Her hafta SIH performansı ve mimarisi hakkında yeni bilgi parçacıkları paylaşacağız.

**Çalışmadaki canlı RWA pariteleri:** CRCLB, MUB, GMEB, SNDKB, SPYB, SOXLB, SOXSB, DRAMB, SNXXB, KORUB, DJTB.

_Not: SNXXB, KORUB, SOXSB ve DJTB'nin hiçbir geleneksel CLAMM defteri yok._

**Sonuçları önümüzdeki birkaç hafta içinde PancakeSwap'in** [**Twitter**](https://x.com/PancakeSwap) **hesabında yayınlayacağız.**

Yayınlanacak sonuçlar şunları kapsayacak:

* **Tam performans veri seti -** Önümüzdeki birkaç haftadaki tüm SIH verileri tek bir tabloda birleştirilmiş olarak.
* **Sermaye tahsisi sorusu -** SIH'in bir RWA ihraççısına gerçekte ne kadar sermaye kazandırdığı.
* **Beklentiyi aştı / kaçırdı -** SIH'in beklentilerin üzerine çıktığı ve geliştirilmesi gereken yerler.
* **Hüküm -** SIH'in RWA sermaye verimliliği için gerçekte ne kadar etkili olduğuna dair temellendirilmiş bir sonuç.

_Veri hakkında not: Buradaki rakamlar canlı onchain sorgulardan ve herkese açık parite verilerinden alınmıştır, kaynaklar metin içinde belirtilmiştir. Bazı karşılaştırmalar farklı zaman aralıkları kullanıyor ve bunları işaretledik — çalışma, bu giriş yazısının yalnızca soruyu çerçeveleyebildiği yerlerde eşit koşullarda ölçüm yapacak şekilde tasarlandı._

***

### Varlıklarında SIH'i Etkinleştirmek İster misin?

Bir RWA ihraççısıysan ve fiyatladığın her havuz için ayrı bir USDT yığını fonlamaktan bıktıysan, bu tam sana göre.

Şu anda RWA ihraççılarını sisteme alıyoruz. Bu Google formunu doldur, varlığının SIH'te fiyatlanması için sana yol gösterelim - [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Okuduğun için teşekkürler! En son gelişmeler için bizi [X](https://x.com/PancakeSwap) üzerinden takip et, sohbete [Telegram](https://t.me/PancakeSwap) ve [Discord](https://discord.gg/pancakeswap) üzerinden katıl.

Hadi inşa edelim,\
The Chefs 🥞

***

_Sorumluluk reddi: Bu içerik yalnızca genel bilgilendirme ve eğitim amaçlıdır. Finansal, hukuki veya başka bir profesyonel tavsiye olarak yorumlanmamalıdır. Dijital varlık fiyatları oynak olabilir. Yatırımının değeri düşebilir veya yükselebilir._
