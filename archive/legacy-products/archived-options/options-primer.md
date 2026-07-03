# Options Başlangıç Rehberi



{% hint style="danger" %}
\[ARŞİVLENDİ] Options – 11 Mart 2025 itibarıyla\
Hâlâ çekilecek likiditenin varsa lütfen https://www.stryke.xyz/en/trade adresini ziyaret ederek bunu hemen yap.
{% endhint %}



## Opsiyon Nedir?

Opsiyonlar, alıcıya belirli bir süre (vade tarihi) içinde belirli bir fiyattan (kullanım fiyatı) bir varlık satın alma (alım opsiyonu) veya satma (satım opsiyonu) hakkı veren ancak bunu zorunlu kılmayan türev sözleşmelerdir.

## Opsiyon Türleri Nelerdir?

### Alım Opsiyonları (Call Options)

Alım opsiyonu, sahibine vade tarihinde veya öncesinde üzerine anlaşılan kullanım fiyatından temel varlığı satın alma hakkı tanır. Yatırımcılar temel varlığın fiyatının yükseleceğini öngördüklerinde alım opsiyonu satın alır. Bu, temel varlığa doğrudan sahip olmak zorunda kalmadan olası fiyat artışından yararlanmalarını sağlar.

> Bir yatırımcı, bir ay vadeli 50.000 $ kullanım fiyatıyla Bitcoin alım opsiyonu satın alır. O ay içinde Bitcoin fiyatı 50.000 $'ın üzerine çıkarsa yatırımcı, Bitcoin'i 50.000 $'dan satın alma seçeneğini kullanarak fiyat farkından kâr edebilir.

### Satım Opsiyonları (Put Options)

Satım opsiyonu, sahibine vade tarihinde veya öncesinde üzerine anlaşılan kullanım fiyatından temel varlığı satma hakkı tanır. Yatırımcılar temel varlığın fiyatının düşeceğini öngördüklerinde satım opsiyonu satın alır. Bu, temel varlığı açığa satmak zorunda kalmadan olası fiyat düşüşünden kâr etmelerini sağlar. Satım opsiyonları aynı zamanda yatırım portföylerindeki olası aşağı yönlü risklere karşı korunmak amacıyla da kullanılır.

> Bir yatırımcı, iki hafta vadeli 3.000 $ kullanım fiyatıyla Ethereum satım opsiyonu satın alır. Bu süre içinde Ethereum fiyatı 3.000 $'ın altına düşerse yatırımcı, Ethereum'u 3.000 $'dan satma seçeneğini kullanarak olası kayıpları azaltabilir.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign%20%282%29.jpg" alt=""><figcaption></figcaption></figure>

## Opsiyon Pozisyonları

Her opsiyon türü için iki olası pozisyon mevcuttur:

### **Uzun Opsiyon (Opsiyon Alıcısı)**

Bu pozisyon, opsiyonu edinmek için peşin prim ödemeyi içerir. Opsiyon kârlı sonuçlanırsa sahibi bir tazminat alır.

### **Kısa Opsiyon (Opsiyon Yazarı/Satıcısı)**

Bu pozisyonda satıcı, opsiyonu ihraç etmesi karşılığında peşin prim alır. Ancak opsiyon alıcı açısından kârlı sonuçlanırsa (temel fiyat, kullanım fiyatı ve opsiyon türüne bağlı olarak) satıcı bir tazminat ödemekle yükümlüdür.

## Amerikan ve Avrupa Opsiyonları

* **Amerikan Opsiyonlar:** Vade tarihinden önce herhangi bir zamanda kullanılabilir. Bu esneklik onları Avrupa opsiyonlarından daha değerli kılar.
* **Avrupa Opsiyonlar:** Yalnızca vade tarihinde kullanılabilir. Esneklik eksikliği nedeniyle genellikle Amerikan opsiyonlardan daha ucuzdur.

## Opsiyonlar Ne Zaman Kullanılır?

İşte bazı örnek kullanım senaryoları:

1. **Spekülasyon:** Bir yatırımcı Bitcoin fiyatının önümüzdeki ay yükseleceğine inanıyor. Beklenen fiyat artışından kâr elde etmek için Bitcoin alım opsiyonları satın alır.
2. **Korunma (Hedging):** Bir kripto para doğrulayıcısı Ethereum'daki olası fiyat düşüşlerine karşı korunmak istiyor. Fiyat belirli bir seviyenin altına düşerse zararlarını önlemek amacıyla Ethereum satım opsiyonları satın alır.
3. **Gelir Üretimi:** Büyük miktarda Ether tutan bir kripto yatırımcısı, elindeki varlıklar üzerinde alım opsiyonları yazarak prim kazanmaya karar verir; bu sayede hem prim geliri elde eder hem de olası yükseliş fiyat hareketlerine katılmaya devam eder.

## Opsiyon Fiyatlandırması

Opsiyon fiyatlandırması karmaşık olup çeşitli faktörler içerir; en yaygın kullanılan model Black-Scholes modelidir.

Opsiyon fiyatlandırmasını etkileyen temel faktörler:

* **Temel Varlık Fiyatı:** Temel varlığın mevcut piyasa fiyatı.
* **Kullanım Fiyatı:** Opsiyon sahibinin temel varlığı satın alabileceği veya satabileceği fiyat.
* **Oynaklık:** Temel varlıktaki fiyat dalgalanmalarının derecesi.
* **Vadeye Kalan Süre:** Opsiyonun sona ermesine kalan süre.
* **Faiz Oranları:** Risksiz getiri oranı.

Opsiyon fiyatlandırması, bir opsiyon yatırımcısı opsiyonu satın aldığında yazarın aldığı primi/ücreti belirler. Opsiyon yazarları, opsiyonlarının Para İçinde (ITM) sona ermesi durumunda tazminat ödeme riskiyle karşı karşıyadır (alıcı için kârlı). Bu nedenle alıcılardan kazandıkları primler, bir ITM olayının olasılığını adil biçimde yansıtmalıdır.

PancakeSwap CLAMM options primleri, aşağıdaki varsayımlarla Black-Scholes modelinden türetilir:

* Risksiz oran sıfır kabul edilir.
* Oynaklık, temel varlığın 30 günlük tarihi oynaklığına dayalıdır \[ima edilen oynaklığın (IV) vekili olarak kullanılır].

Birkaç istisna şunlardır:

* $ETH ve $BTC IV'si, kullanım fiyatları eşleşiyorsa doğrudan Deribit'ten alınır. Kullanım fiyatları eşleşmiyorsa Deribit'ten en yakın üst ve alt kullanım fiyatları, sapma derecesine göre ağırlıklandırılarak IV belirlenir.
* $ARB, ETH'ye karşı temel varlığın efektif kullanım fiyatını hesaplayarak 30 günlük beta bazlı tarihi oynaklık kullanır; ardından ETH'ye karşı temel varlığın betasıyla çarpılan IV elde edilir.

Yüksek oynaklığa sahip varlıkların primi, daha düşük oynaklıklı varlıklara kıyasla daha pahalı olacaktır; çünkü opsiyonun ITM sona ermesi yazarlar için daha büyük risk taşır.

## Opsiyon Uzlaşması

### Uzlaşma Koşulları

* Uzlaşma, vadede opsiyonun parasallık durumuna göre belirlenir.
* Uzlaşma yalnızca kullanım sırasında opsiyon Para İçinde (ITM) ise hesaplanır.

### ITM Koşulları

* **Alım Opsiyonu:** Uzlaşmadaki Spot Fiyat > Kullanım Fiyatı
* **Satım Opsiyonu:** Uzlaşmadaki Spot Fiyat < Kullanım Fiyatı

### Uzlaşma Hesaplaması

* **Alım Opsiyonu:** #Opsiyon \* (Uzlaşmadaki Spot Fiyat - Kullanım Fiyatı)
* **Satım Opsiyonu:** #Opsiyon \* (Kullanım Fiyatı - Uzlaşmadaki Spot Fiyat)

### Parasallık (Moneyness)

Parasallık, bir opsiyonun içsel değerini ifade eder; opsiyonun kullanım fiyatının kullanım anındaki spot fiyatla karşılaştırılmasıyla belirlenir.

### Sınıflandırma

1. Para Dışında (OTM):
   1. Opsiyon, uzlaşmadaki spot fiyat kullanım fiyatından farklıysa ve hemen uzlaşma gerçekleşseydi hiçbir değer alınıp verilmeyecekse OTM'dir.
   2. Koşullar:
      1. Alım Opsiyonu: Spot Fiyat < Kullanım Fiyatı
      2. Satım Opsiyonu: Spot Fiyat > Kullanım Fiyatı

{% hint style="info" %}
2.000 $ kullanım fiyatlı bir $ETH alım opsiyonu, spot fiyat 1.800 $ ise OTM olur (1.800 $ < 2.000 $, yani OTM).
{% endhint %}

2. Paraya Eşit (ATM):
   1. Uzlaşmadaki spot fiyat kullanım fiyatına eşitse ve hemen uzlaşma gerçekleşseydi hiçbir değer alınıp verilmeyecekse opsiyon ATM'dir.
   2. Koşullar: Hem Alım hem Satım Opsiyonu: Spot Fiyat = Kullanım Fiyatı

{% hint style="info" %}
1.800 $ kullanım fiyatlı bir $ETH alım opsiyonu ve satım opsiyonu, spot fiyat da 1.800 $ ise ATM olur (1.800 $ = 1.800 $, yani ATM).
{% endhint %}

3. Para İçinde (ITM):
   1. Uzlaşmadaki spot fiyat kullanım fiyatından farklıysa ve hemen uzlaşma gerçekleşseydi değer alınıp verilecekse opsiyon ITM'dir.
   2. Koşullar:
      1. Alım Opsiyonu: Spot Fiyat > Kullanım Fiyatı
      2. Satım Opsiyonu: Spot Fiyat < Kullanım Fiyatı

{% hint style="info" %}
1.600 $ kullanım fiyatlı bir $ETH alım opsiyonu, spot fiyat 1.800 $ ise ITM olur (1.800 $ > 1.600 $, yani ITM).
{% endhint %}

Opsiyon alıcısının kazandığı uzlaşma, opsiyon yazarının kaybettiği teminata eşittir. Uzlaşma, ödenen opsiyon primini dışarıda bırakır; bu prim, opsiyon alıcıları ve yazarları için kâr veya zarar hesaplanırken dikkate alınır.
