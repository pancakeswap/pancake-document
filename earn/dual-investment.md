# 🍩 Dual Investment

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201%20%282%29.png" alt=""><figcaption></figcaption></figure>

Dual Investment, piyasa hangi yöne giderse gitsin fonlarını belirlediğin bir hedef fiyata bağlamana ve sabit bir ödül kazanmana olanak tanır. Bir varlık seç, **Buy Low** ya da **Sell High** yönünü belirle, ardından bir hedef fiyat ve uzlaşma (settlement) tarihi seç. Uzlaşma anında anaparanı ve ödülünü, ya yatırdığın varlık cinsinden ya da hedef fiyatından dönüştürülmüş olarak alırsın.

Dual Investment, BNB Chain üzerinde **BTCB** ve **BNB** için **USDT** paritesiyle yayında.

{% hint style="info" %}
Dual Investment bir tasarruf ürünü değildir. Uzlaşma fiyatına bağlı olarak fonların hedef fiyatından başka bir varlığa dönüştürülebilir ve bu varlığın değeri yatırdığın tutardan düşük olabilir.
{% endhint %}

***

## Dual Investment nedir?

#### **İki sonuç, tek sabit ödül**

Her Dual Investment ürününün bir hedef fiyatı ve bir uzlaşma tarihi vardır. Abone olduğunda ödülün gösterilen APR ile kilitlenir. Uzlaşma anında piyasa fiyatı, iki sonuçtan hangisini alacağını belirler:

* **Fiyat hedefine ulaşmaz.** Orijinal varlığını ve ödülünü geri alırsın.
* **Fiyat hedefine ulaşır.** Anaparan ve ödülün, hedef fiyatından diğer varlığa dönüştürülür.

Her iki durumda da ödülü kazanırsın. Değişen tek şey hangi varlığı alacağındır.

#### **Buy Low**

BTCB veya BNB'yi bugünkü fiyatın altında almaktan memnun olacaksan Buy Low'u kullan. **USDT** yatırırsın ve güncel fiyatın altında bir hedef fiyat seçersin.

| Uzlaşma fiyatı          | Aldığın                                                         |
| ----------------------- | --------------------------------------------------------------- |
| Hedefinde veya üzerinde | USDT (anapara + ödül)                                           |
| Hedefinin altında       | Hedef fiyatından satın alınan BTCB veya BNB ve ödülün           |

#### **Sell High**

BTCB veya BNB'yi bugünkü fiyatın üzerinde satmaktan memnun olacaksan Sell High'ı kullan. **BTCB veya BNB** yatırırsın ve güncel fiyatın üzerinde bir hedef fiyat seçersin.

| Uzlaşma fiyatı          | Aldığın                                                |
| ----------------------- | ------------------------------------------------------ |
| Hedefinde veya altında  | BTCB veya BNB (anapara + ödül)                         |
| Hedefinin üzerinde      | Hedef fiyatından satılan USDT ve ödülün                |

#### **APR nasıl çalışır?**

APR, hedef fiyatın güncel fiyata ne kadar yakın olduğuna ve ürünün ne kadar süreceğine bağlıdır. Güncel fiyata daha yakın hedefler dönüştürülme ihtimali daha yüksek olduğu için daha yüksek APR öder. Daha uzaktaki hedefler daha az öder ancak orijinal varlığını geri alma ihtimalin daha yüksektir.

Ödülün şu şekilde hesaplanır:

`Reward = Subscription amount × APR × (Days to settlement ÷ 365)`

#### **Örnek: Buy Low**

BTCB $83,467'den işlem görüyor. %14,68 APR ile $82,000 hedefli 1 günlük bir Buy Low ürününe 1.000 USDT ile abone oluyorsun. Ödülün yaklaşık 0,40 USDT olur.

| Uzlaşma fiyatı     | Aldığın                               |
| ------------------ | ------------------------------------- |
| $82,000 veya üzeri | 1.000,40 USDT                         |
| $82,000'ın altı    | 0,0122 BTCB (1.000,40 USDT ÷ $82,000) |

BTCB $78,000'dan uzlaşırsa yine de $82,000'dan alım yaparsın. Değeri yaklaşık 951,60 USDT olan 0,0122 BTCB'ye sahip olursun; bu, yatırdığın tutardan düşüktür.

#### **Örnek: Sell High**

BTCB $83,467'den işlem görüyor. %89,28 APR ile $84,500 hedefli 1 günlük bir Sell High ürününe 0,01 BTCB ile abone oluyorsun. Ödülün yaklaşık 0,0000245 BTCB olur.

| Uzlaşma fiyatı     | Aldığın                                |
| ------------------ | -------------------------------------- |
| $84,500 veya altı  | 0,0100245 BTCB                         |
| $84,500'ın üzeri   | 847,07 USDT (0,0100245 BTCB × $84,500) |

BTCB $88,000'dan uzlaşırsa yine de $84,500'dan satış yaparsın. Değeri yaklaşık 882 USDT olacak BTCB karşılığında 847,07 USDT alırsın.

#### **Karşı taraftaki kim?**

Her ürün, pozisyonunun karşı tarafını üstlenen bir market maker tarafından fiyatlandırılır. Market maker'lar ödemeni güvence altına alan bir teminat (bond) yatırır. Bir market maker temerrüde düşerse talebin onların teminatıyla karşılanır.

***

## Dual Investment nasıl kullanılır?

#### **Dual Investment sayfasına git**

[pancakeswap.finance/dual-investment](https://pancakeswap.finance/dual-investment?chain=bsc) adresine git veya PancakeSwap ana gezinme çubuğundaki **Dual Investment**'a tıkla.

#### **1. Bir hedef varlık seç**

**BTCB** veya **BNB**'yi seç. Her kart, o varlık için güncel fiyatı ve tüm ürünlerde sunulan APR aralığını gösterir.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28407%29.png" alt=""><figcaption></figcaption></figure>

#### **2. Bir yön seç**

USDT yatırıp varlığı daha düşük fiyattan almak için **Buy Low**'u, ya da varlığı yatırıp daha yüksek fiyattan satmak için **Sell High**'ı seç.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28430%29.png" alt=""><figcaption></figcaption></figure>

#### **3. Bir uzlaşma tarihi ve hedef fiyat seç**

Listeyi daraltmak için süre filtrelerini (**1 Day**, **< 3 Days**, **< 7 Days** ve daha uzunları) kullan. Ürünler uzlaşma tarihine göre gruplanır. Her satır hedef fiyatı, güncel fiyata uzaklığını ve APR'yi gösterir.

Her uzlaşma tarihinin yanındaki geri sayım, abone olmak için ne kadar süren kaldığını gösterir. Abonelikler uzlaşmadan önce kapanır.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28475%29.png" alt=""><figcaption></figcaption></figure>

#### **4. Abonelik tutarını gir**

İstediğin hedefte **Subscribe**'a tıkla, ardından bir tutar gir veya **MAX**'a dokun. Her ürünün abonelik başına bir minimum ve maksimum değeri ile sabit bir toplam kapasitesi vardır. Bir hedef tamamen dolduğunda yeniden açılamaz, bu yüzden başka bir hedef fiyat seçmen gerekir.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28476%29.png" alt="" width="375"><figcaption></figcaption></figure>

#### **5. İncele ve onayla**

Yönü, hedef fiyatı, uzlaşma tarihini ve her iki sonucu da incele.&#x20;

Onaylarken oran kısa bir süre sabit tutulur. Süresi dolarsa veya oran değişirse sayfa yeni bir oran getirir ve devam etmeden önce kabul etmeni ister.

#### **6. Ödemeni talep et**

Uzlaşmadan sonra bir pozisyonda **Claim**'e, ya da uzlaşmış tüm pozisyonları tek seferde talep etmek için **Claim all**'a tıkla. Ödemen, uzlaşma sonucuna göre belirlenen varlık cinsinden cüzdanına gönderilir.

***

## Dual Investment SSS

#### **Dual Investment nedir?**

Dual Investment, fonlarını bir hedef fiyata bağlamana ve sabit bir ödül kazanmana olanak tanıyan bir üründür. Uzlaşma anında anaparanı ve ödülünü, ya orijinal varlığın cinsinden ya da hedef fiyatından diğer varlığa dönüştürülmüş olarak alırsın.

#### **Hangi varlıklar destekleniyor?**

BNB Chain üzerinde USDT ile eşleştirilmiş BTCB ve BNB.

#### **Buy Low ile Sell High arasındaki fark nedir?**

Buy Low, USDT yatırıp BTCB veya BNB'yi güncel fiyatın altındaki bir hedef fiyattan satın almana olanak tanır. Sell High ise BTCB veya BNB yatırıp güncel fiyatın üzerindeki bir hedef fiyattan satmana olanak tanır.

#### **Her iki sonuçta da ödül kazanır mıyım?**

Evet. Ödül abone olduğunda sabitlenir ve her iki sonuçta da ödenir. Uzlaşma anında aldığın varlık cinsinden, anaparanla birlikte ödenir.

#### **Uzlaşma tarihinden önce çekim yapabilir miyim?**

Hayır. Abone olduktan sonra fonların uzlaşmaya kadar kilitlenir ve abonelik iptal edilemez.

#### **APR'ler ürünler arasında neden farklı?**

Güncel fiyata daha yakın hedefler ve daha kısa uzlaşma tarihleri, dönüşüm ihtimali daha yüksek olduğu için genellikle daha yüksek APR öder. Oranlar canlı olarak fiyatlanır ve bir ürünü açtığın an ile onayladığın an arasında değişebilir.

#### **Abone olurken oran neden değişti?**

Oranlar market maker'lar tarafından canlı olarak fiyatlanır ve yalnızca kısa bir süre sabit tutulur. Oranın süresi dolarsa, oran değişirse veya başka bir kullanıcı o fiyatı senden önce doldurursa sayfa yeni bir oran getirir ve devam etmeden önce kabul etmeni ister.

#### **Ödememi talep etmem gerekiyor mu?**

Evet. Uzlaşmadan sonra ödemeni **Your Holdings** bölümünden talep et. Pozisyonları tek tek talep edebilir veya **Claim all**'ı kullanabilirsin.

#### **Pozisyonumun karşı tarafını kim üstleniyor?**

Market maker'lar her ürünü fiyatlandırır ve pozisyonunun karşı tarafını üstlenir. Ödemeni güvence altına alan bir teminat yatırırlar; bir market maker temerrüde düşerse talebin bu teminatla karşılanır.

#### **Hangi ücretler alınıyor?**

Ücretsizdir.
