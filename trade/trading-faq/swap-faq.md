# Swap SSS

## Swap

### Exchange V3'te yeni olan neler?

* Yoğunlaştırılmış likidite — likidite, en aktif işlem gören fiyat aralığında yoğunlaştırılacak; bu da şu anlama geliyor:
  * Traderlar için daha düşük işlem Kayması
  * Likidite sağlayıcılar için potansiyel olarak daha fazla LP ücreti ödülü
* Esnek işlem ücreti yapısı — Likidite sağlayıcılar, likidite çiftleri oluştururken veya likidite sağlarken birden fazla işlem ücreti seviyesi arasından seçim yapabilir
* Özelleştirilebilir fiyat aralığı — Likidite sağlayıcılar ayrıca hangi fiyat aralıklarına likidite sağlamak istediklerini de seçebilir
* Değiştirilemez likidite pozisyonları — Her likidite pozisyonu, yapılandırmasına (fiyat aralığı gibi) karşılık gelen kendine özgü bir kimliğe sahip olacak. Bu nedenle aynı işlem çiftiyle ancak farklı yapılandırmalara ve likidite miktarlarına sahip birden fazla pozisyon oluşturabilecek ve yönetebileceksin
* Geriye dönük uyumlu — v3 Exchange ayrıca her zaman en iyi işlem rotasını sunmak için eski v2 ve kararlı Swap likidite çiftlerini de kullanacak
* Yerleşik limit emri — Profesyonel kullanıcılar, likidite sağlamada yeni özelleştirilebilir fiyat aralığını kullanarak, fiyat hedefe ulaştığında tüm tokenları istenen birine dönüştürecek etkili bir limit emri oluşturabilir



### Kendi tokenlarımı Exchange V3'e ekleyebilir miyim?

Herkes v3'te likidite yatırarak likidite havuzları oluşturabilir.

Ancak aşağıdaki tokenlar şu anda **DESTEKLENMEMEKTEDİR**:

* Transfer ücreti olan tokenlar
* Yeniden tabanlayan (rebase) tokenlar

Bu tokenlar için lütfen Exchange V3'e likidite **EKLEME**. Varlıkların likidite pozisyonunda sıkışabilir.



### **İşlemim neden gerçekleşmiyor?**

PancakeSwap, Swap yapmak, LP oluşturmak, Farm ve Havuzlarda stake etmek gibi zincir üzerindeki işlemleri tamamlamak için cüzdanla etkileşime giren bir DeFi uygulamasıdır.

**Gaz Ücretleri**

Bu nedenle, ilk yapılması gereken şey **zincir üzerindeki işlemlerin gaz ücretini ödemek için yeterli BNB'ye sahip olduğundan emin olmaktır**. Genellikle gaz ücreti, kuyruktaki işlem sayısına bağlı olarak dalgalanır; daha fazla işlem varsa işlemi geçirmek için daha yüksek gaz ücreti gerekebilir. BNB Smart Chain'de gaz ücreti genellikle BNB cinsinden cent'lerden bir USD dolara kadar değişir. Gaz ücreti hakkında daha fazla bilgi için [buraya bakın](https://academy.binance.com/en/glossary/gas).

**İşlem Ücretleri**

Swap işlemin hâlâ gerçekleşmiyorsa ve Kayma'yı revize etmen için bir hata gösteriyorsa — takas etmeye çalıştığın tokenların **işlem üzerinde herhangi bir ücret ve kısıtlaması olup olmadığını** kontrol etmek isteyebilirsin.

BNB Smart Chain'deki tokenların sözleşmelerinde **işlem ücreti** içermesi alışılmadık bir durum değildir; genellikle bu ücretler yakma için, adil başlangıçlı bir projenin hazinesini finanse etmek için kullanılabilir — örneğin, [bu APX tokeninde her işlemde bir yakma adresine gönderilmek üzere %1 vergi uygulanmaktadır](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax); böylece daha fazla işlem daha fazla yakma anlamına gelir ve APX token sahiplerine değer kazandırır.

İşlem ücreti kapsayıcı (takas miktarının bir kısmı adresin dışına gönderilir, bu nedenle tahmin edilen girdi için çıktı beklenenden az olur) veya hariç (adresinden ekstra token göndermek için ek transfer gerektirmesi, bu nedenle tahmin edilen çıktı için girdi beklenenden fazla olur) olsun, işlemi imzalamak için anlaşılan girdi ve çıktı miktarlarını etkiler. Pek çok durumda işlem, vergi nedeniyle girdi ve çıktı gerekliliklerini karşılayamaz.

**İşlem Ücretleriyle Swap Yapmak**

Herhangi bir tokeni takas etmeden önce, işlem ücreti mekanizmasının olup olmadığını anlamak için web sitelerini ziyaret ettiğinden emin ol (birçok proje bunu _vergi_ olarak adlandırmaktadır). Varsa, işlem ücretini karşılayacak yeterli Kayma belirlediğinden emin ol — örneğin %5 işlem ücreti varsa Kayma, işlem miktarına ve tokenın likiditesine bağlı normal işlem Kaymasına ek olarak en az %5 artı olarak ayarlanmalıdır; yaklaşık %5,5-%6.

Bazı dolandırıcılıklar dahil aşırı durumlarda bazı tokenlar zincirde transferlerin çoğunu veya tamamını engelliyor ya da yalnızca belirli adreslerin satış yapmasına izin veriyor; bu durumda tokeni başarıyla takas etmek imkânsız. Takas etmeye çalıştığın token hakkında bilgi edin ve herhangi bir ücret ve kısıtlamadan haberdar ol!



### Yeni Swap arayüzü v2 veya kararlı Swap likiditesini kullanıyor mu?

Evet. Yeni Swap v3, en iyi işlem rotasını bulmak için PancakeSwap v3, v2 ve kararlı Swap likiditesini kullanır.



### Bölünmüş yönlendirme nedir?

Swap v3'te, en iyi oran ile işlemini gerçekleştirmek için işlemin birden fazla rotaya bölünmesi mümkündür.

İşleminin nasıl yönlendirildiğine dair daha fazla ayrıntı için, genişletmek ve ayrıntıları görüntülemek üzere "Rota" bölümündeki "v" düğmesine dokun.

Daha fazla bilgi için [buraya bakın](../pancakeswap-exchange/fees-and-routes.md#customize-routing-preferences).



### Belirli likidite kaynaklarını nasıl özelleştirebilir veya devre dışı bırakabilirim?

Yeni Swap v3, en iyi işlem rotasını bulmak için PancakeSwap v3, v2 ve kararlı Swap likiditesini kullanır. Ancak işleminin belirli likidite kaynaklarından geçmesini istemiyorsan bunları özelleştirebilir veya devre dışı bırakabilirsin.

Bir işlem rotasını görüntülerken "Yönlendirmeyi Özelleştir" düğmesine tıkla. Veya Swap arayüzünün sağ üst köşesindeki dişli ⚙️ düğmesine tıkla ve "Yönlendirmeyi Özelleştir"i seç.

"Yönlendirmeyi Özelleştir" açılır penceresinde, hangi likidite kaynağını kullanmak istediğini seçebilirsin. Veya çok adımlı (multihop) rotaları tamamen devre dışı bırakabilirsin.

Not: multihop'ları devre dışı bırakmak belirli işlem çiftlerinde artan Kayma veya daha kötü işlem oranına yol açabilir. Dikkatli ilerle.

Daha fazla bilgi için [buraya bakın](../pancakeswap-exchange/fees-and-routes.md#customize-liquidity-sources).



## Likidite

### Ücret seviyeleri nedir ve doğru olanı nasıl seçilir?

Exchange v3'te, likidite sağlarken aynı token çifti için birden fazla farklı işlem ücreti (%0,01, %0,05, %0,25 ve %1) arasından seçim yapabilirsin.

Örneğin, CAKE-BNB için her işlemde %0,25 işlem ücreti uygulayan %0,25 çifti olabilir. Ancak bazı likidite sağlayıcılar, daha iyi fiyat teklifi sunan ve daha fazla işlem hacmi çeken %0,05 ücret oranıyla CAKE-BNB işlem çiftine likidite sağlamayı tercih edebilir.

Hangi işlem ücreti yapılandırmasını seçeceğinin "doğru" bir cevabı yoktur. Bu, işlem çiftindeki tokenlara bağlıdır. Genellikle, oynaklığa bağlı kalıcı olmayan kayıpları daha iyi telafi etmek için oynak tokenların daha yüksek işlem ücretine sahip olması gerekir. Öte yandan stablecoin'ler gibi tokenların fiyat hareketleri daha küçük ve kalıcı olmayan kayıpları daha düşüktür; bu nedenle işlem ücretleri daha düşük olmalıdır.

Bir token çifti seçerken "Likidite Ekle" arayüzü senin için otomatik olarak en popüler ücret seviyesini seçecektir.



### Neden yatırdığım iki token USD değeri olarak eşit değil?

Exchange V3'te, bir likidite pozisyonundaki temel varlıklar USD cinsinden her zaman eşit değere sahip olmayacak. Bu, bir pozisyonun fiyat aralığı ayarlarına ve çiftin mevcut fiyatına bağlı olacak.

Aslında. Pozisyonun aralık dışına çıkması durumunda tüm tokenlar tek bir varlığa dönüştürülür. Ayrıca mevcut fiyatı kapsamayan bir fiyat aralığına likidite sağlayabilir ve yalnızca tek bir varlık yatırabilirsin. Daha fazla bilgi için okumaya devam et ⬇️



### Likidite pozisyonum aralık dışına çıkarsa ne olur?

Mevcut fiyat pozisyonunda tanımlanan fiyat aralığının dışına çıkarsa herhangi bir işlem ücreti ödülü kazanamazsın.

Bunun yanı sıra, fiyat koşulunun yönüne bağlı olarak tüm tokenlar tek bir varlığa dönüştürülür.

Örneğin, CAKE/BUSD pozisyonu BUSD başına CAKE için 3 ile 5 BUSD fiyat aralığıyla yapılandırılmışsa. CAKE fiyatı BUSD başına 5 BUSD'ye eşit veya daha yüksekse pozisyondaki tüm varlıklar BUSD'ye dönüştürülür ve bunun tersi de geçerlidir.

Fiyat tekrar aralığa dönerse işlem ücreti ödülleri almaya başlayacağını ve ek işlem gerekmediğini lütfen unutma.



### Daha küçük bir aralıkla her zaman likidite sağlamak daha mı iyi?

Daha küçük bir fiyat aralığına likidite sağlamak, likiditeni belirli bir fiyat aralığına yoğunlaştırmaya yardımcı olur; fiyat aralığındaki toplam likiditeye karşı göreli paylarını artırır ve potansiyel olarak daha fazla işlem ücreti ödülü kazanmanı sağlar.

Ancak, yalnızca aktif likidite pozisyonlarının işlemlerden işlem ücreti ödülü kazanacağını unutma. Bu, yalnızca mevcut işlem fiyatı likidite pozisyonunda tanımlanan fiyat aralığı içinde olduğunda ödül kazanacağın anlamına gelir.



### Pozisyonum her zaman aralıkta olacak ve ücret ödülü kazanacak şekilde otomatik olarak ayarlamanın herhangi bir yolu var mı?

PancakeSwap v3, BNB Chain ve Ethereum'da mevcut olan Zap aracılığıyla tek tıkla likidite yatırmayı destekler.



### v3 Exchange için işlem ücreti dağılımı nasıl olacak?

|                    | %0,01 | %0,05 | %0,25 | %1  |
| ------------------ | ----- | ----- | ----- | --- |
| Likidite Sağlayıcı | %67   | %66   | %68   | %68 |
| CAKE Yakımı         | %15   | %15   | %23   | %23 |
| Hazine              | %18   | %19   | %9    | %9  |

### LP ücreti ödülleri Exchange v2'de olduğu gibi otomatik olarak birleşiyor mu?

Hayır.

Exchange v3'te işlem ücreti ödüllerini manuel olarak talep etmen gerekecek. Bunu pozisyon detay sayfasında yapabilirsin. Tüm v3 likidite pozisyonlarını likidite sayfasında bulabilirsin.



### LP APR'ı neler etkiler?

Exchange v3'te LP ücreti ödül APR'ı likidite pozisyonları arasında değişebilir. Aşağıdaki faktörlere dayanır:

* İşlem hacmi\
  \- daha fazla hacim daha fazla ücret ödülü üretir
* Likidite çifti ücret seviyesi\
  \- daha yüksek ücret seviyesi bireysel işlemlerden daha fazla ücret ödülü üretir
* Yatırılan token sayısı\
  \- pozisyondaki daha fazla token, toplam aktif likiditeye karşı daha büyük göreli bir pay anlamına gelir; bu da işlemlerden daha fazla işlem ücreti ödülü kazanır
* Seçilen fiyat aralığı\
  \- daha küçük fiyat aralığı, yatırılan aynı token miktarı için daha yüksek yoğunluk sağlar; bu da toplam aktif likiditeye karşı daha büyük göreli bir paya ve işlemlerden daha fazla işlem ücreti ödülüne dönüşür
* Şu anda aktif olan likidite miktarı\
  \- seninle aynı aralıkta likiditelerini yatıran ve yoğunlaştıran daha fazla kullanıcı varsa toplama karşı daha küçük göreli pay nedeniyle daha az işlem ücreti kazanırsın
* Likidite pozisyonunun aktif olup olmadığı\
  \- yalnızca aktif likidite pozisyonları işlem ücreti ödülü kazanır



### v2 likiditesi sağlayabilir miyim?

v2 likiditesi sağlamak artık tavsiye edilmemektedir. Verimliliği artırmak için yeni özelliklerden yararlanmak üzere v3 likiditesini kullanmanı tavsiye ederiz.

v2 likiditesi eklemek istersen:

* Token çiftinin bir v3 havuzu yoksa veya v3'teki en büyük havuzdan daha fazla v2 likiditesi varsa, "V2 Likiditesi Ekle" görünecektir. v2 likiditesi eklemeye geçmek için tıkla
* Alternatif olarak, her zaman v2 likidite sağlamayı kullanmak için URL'de `/v2` kullan



### Yeni oluşturduğum bir çifte neden likidite ekleyemiyorum?

Eski Exchange V2'den kaynaklanan bir hata nedeniyle (her UniSwap V2 fork'unda mevcut), aşağıdaki durumlarda normal PancakeSwap likidite arayüzü ve sözleşme çağrılarını kullanarak bir çifte likidite ekleyemezsin:

* FactoryV2'de `createPair` çağrılarak ve başlangıç likiditesi yatırılmadan ve başlangıç LP tokenları mint edilmeden çift oluşturulmuşsa
* Ardından, çiftteki tokenlardan biri `sync` çağrılırken havuz sözleşmesine manuel olarak transfer edilmişse

{% hint style="info" %}
Son zamanlarda, BNB Chain'deki PancakeSwap Exchange V2'de bu tür saldırılarda artış gözlemlendi.&#x20;

Likidite çiftini başlangıç likiditesiyle çift oluşturarak token için işlem çiftini oluşturmak amacıyla arayüzümüzü kullanmanı şiddetle tavsiye ederiz.
{% endhint %}

Şefler bu sorunu çözmek için çalışırken, BscScan kullanarak bunu çözmek için adım adım bir rehber aşağıdadır:

#### Havuz adresini ve BscScan sayfasını bul

<div align="left"><figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/cannot%20add%20v2%20liquidity-error%20pump.jpg" alt="" width="280"><figcaption></figcaption></figure></div>

Çiftin etkilenmesi durumunda hata mesajında işlem çifti/havuzu için BscScan sayfasına bağlantıyı görürsün.

Alternatif olarak, Factory V2'ye ([Bsc](https://bscscan.com/address/0xca143ce32fe78f1f7019d7d551a6402fc5350c73#readContract)) gidip "Sözleşmeyi Oku", "6. getPair"e tıklayabilir, işlem çiftindeki iki tokenın adreslerini girebilir ve "Sorgula"ya tıklayabilirsin. Dönüş alanında çift adresini görmelisin.

#### Hangi tokenın yatırıldığını kontrol et ve diğer tokeni havuza manuel olarak transfer et

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28335%29.png)

BscScan'deki token bakiyesi alanından havuza hangi tokenın yatırıldığını kontrol edebilirsin. Genellikle eşleştirilmiş token olmalıdır. (WBNB, USDT, vb. gibi...)

Onayladıktan sonra, diğer varlığı havuz sözleşmesine manuel olarak transfer etmelisin. Bunu tercih ettiğin Cüzdan uygulamasında havuz adresini alıcı olarak girerek yapabilirsin.

Herhangi bir miktarı transfer edebilirsin; ancak bu aslında bir havuza varlık "bağışlamak" anlamına geldiğinden. Likidite tokenları mint etmeden likiditene varlıklarını transfer edeceksin. Bu nedenle bu miktarı minimal tutmanı tavsiye ederiz.

{% hint style="warning" %}
ÖNEMLİ: Tokeni transfer ettikten sonra hemen havuzda `sync()` çağırmalısın.
{% endhint %}

Bunu yapmak için işlem çifti için BscScan sayfasına git, "Sözleşmeyi Yaz", "8. Sync"e git ve "Yaz" düğmesine tıkla. İşlemi gerçekleştirmeden önce cüzdanını bağlaman gerekecek.

İşlem onaylandıktan sonra PancakeSwap arayüzünde sonraki likiditeyi ekleyebilirsin.

#### Lansman fiyatını tanımlamak istersem ne yapmalıyım?

Tokeni transfer ederken ve havuzu düzeltirken havuzu lansman fiyatına ayarlamalısın.

Transfer edilecek miktar şunlar kullanılarak hesaplanabilir:

* `tokenInside`: Havuza zaten transfer edilmiş token. Genellikle eşleştirilmiş token olmalıdır. (WBNB, USDT, vb. gibi...)
* `tokenToSend`: Havuza gönderilecek olan token. Genellikle proje tokenın olmalıdır
* `tokenInside.price`: tokenInside'ın USD fiyatı
* `tokenToSend.price`: tokenToSend'in USD fiyatı (lansman fiyatı)
* `pool`: V2 havuzu

Aşağıdaki formülle:

`amountToSend = tokenInside.balanceOf(pool) / tokenInside.decimal() * tokenInside.price / tokenToSend.price * tokenToSend.decimal()`

Sonuç 0'dan küçükse (genellikle lansman fiyatı çok büyük olduğunda olur. Önce havuza daha fazla `tokenInside` yatırman gerekebilir)



### Kararlı LP ve eski v2 LP nasıl yönetilir?

[Likidite](https://pancakeswap.finance/liquidity) sayfasına giderek bunları her zamanki gibi yönetebilirsin.



### USDT'yi etkinleştirmeden/onaylamadan önce neden onayı sıfırlamam gerekiyor?

Ethereum mainnet'inde işlem yaparken USDT tokeni, onayları ve token izinlerini yönetmek için farklı bir mantık izler.&#x20;

Bu nedenle harcama izinleri çok düşük olduğunda. Yeni bir tane ayarlamadan önce onayı sıfırlamanı gerektirir.
