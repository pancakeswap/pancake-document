---
description: ApolloX will launch Trading Rewards Program on V2
hidden: true
---

# Trading Ödül Programı

### Ödül Programına Genel Bakış

Ayrıntılar aşağıdaki gibidir:

Etkinlik süresi: Tarihler döngüden döngüye ve farklı zincirlere göre değişir

Ödül Dağıtım Zamanı: Her döngü günlük 00:00 (UTC) ile 23:59 (UTC) arasındadır. Ödüller ertesi gün yaklaşık 03:00 (UTC)'de dağıtılır. Kullanıcıların ödüller dağıtıldıktan sonra 30 gün içinde talep etmeleri gerekmektedir. Talep edilmezse platform ödülleri geri alır.&#x20;

Ödül miktarı: Günlük maksimum 15.000 USD değerinde APX ile sınırlıdır

Etkinlik kuralları: V2'de işlem yapan kullanıcılar bir ödül ödeneğinden kazanır. APX'i DAO'da stake ederek veNFT elde eden kullanıcılar, veNFT'den hesaplanan Güç değerine karşılık gelen artırma çarpanlarından yararlanır.&#x20;

| Güç Değeri                | Artırma Çarpanı      |
| ------------------------- | -------------------- |
| 50.000 < Güç =<100.000    | 1,5                  |
| 100.000 < Güç =<300.000   | 2                    |
| Güç > 300.000             | 2,5                  |

Trading Ödülleri hesaplama formülü:&#x20;

Her trading ödül döngüsünün sonunda, APX ödüllerinin ağırlığını ve miktarını belirlemek için kullanıcının o döngüdeki efektif işlem ücretleri ve stake miktarı hesaplanır. Formül aşağıdaki gibidir:

r = R\*W / sum(Wi)



Parametreler:

| r       | Kullanıcının bu döngü için APX ödülü                                                                                                                                                                                                                                                                                    |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Kullanıcının bir önceki günkü V2 işlem ücreti katkısı ve son APX token fiyatı tarafından belirlenir                                                                                                                                                                                                                     |
| W       | <p>Bireysel toplam ağırlık puanı W=f*w, burada;</p><p>f, kullanıcının bu döngüde katkıda bulunduğu efektif işlem ücretlerini ifade eder ve USD'ye dönüştürülür.</p><p>w, kullanıcının bu döngüde APX'i DAO'da stake ederek elde ettiği artırma çarpanıdır. (Daha fazla bilgi için yukarıdaki tabloya bakın)</p> |
| sum(Wi) | Tüm kullanıcıların toplam puanı. Wi herhangi bir bireysel kullanıcının puanını, sum(Wi) ise tüm kullanıcı puanlarının toplamını temsil eder                                                                                                                                                                              |

&#x20;

R için hesaplama formülü aşağıdaki gibidir:

R=Min(Dolar değeri çarpanı \* İşlem Ücreti, Dolar değeri üst sınırı)/ Max(APX Son Fiyat, APX Fiyat Tabanı)

* Dolar değeri çarpanı: Bu dönem 0,70
* İşlem Ücreti: Önceki günkü V2 ücret gelirinin USD'ye dönüştürülmüş değeri
* Dolar değeri üst sınırı: Sistem yapılandırmasına göre 15.000
* APX Son Fiyat: En güncel APX token fiyatına göre
* APX Fiyat Tabanı: Bu dönem 0,04

Hüküm ve Koşullar

* Her döngünün sonunda ApolloX, kullanıcı geri bildirimlerine ve piyasa koşullarına göre program kurallarını değiştirebilir. Ödüller doğrusal olmayan bir şekilde dağıtılacaktır.
* Etkinlik süresince platform, ALP havuzuna aktarılan V2 işlem ücreti gelirinin yüzdesini %50'den %20'ye düşürecek. Kalan %30 ise APX geri alımı için kullanılacaktır.
* V2'deki her işlem çifti için işlem ücretlerindeki farklılık nedeniyle, efektif işlem hacimleri aynı olsa bile kullanıcıların aldıkları ödüller farklılık gösterebilir.
* Her döngü için dağıtılacak ödüller aşağıdaki sözleşme adresinde saklanacaktır: 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX bu etkinlik için nihai yorum hakkını saklı tutar.

Risk Uyarısı: Kripto vadeli işlem ticareti önemli risk taşır. Tüm işlem faaliyetleri kendi takdirine ve riski üstlenmeye hazır olarak gerçekleştirilir. Buradaki bilgiler ApolloX'ten finansal veya yatırım tavsiyesi olarak değerlendirilmemelidir. ApolloX, ApolloX kullanımından kaynaklanabilecek herhangi bir kayıptan sorumlu tutulamaz.

### Ödülleri Talep Etme

Trading ödül programı, ApolloX dostlarımız tarafından yürütüldüğünden ödülünü talep etmek için lütfen aşağıdaki adımları izle:\
\
1. Adım: [PancakeSwap Perpetuals Sayfasına](https://perp.pancakeswap.finance/en/futures/v2/) git

2. Adım: Sayfanın üst kısmındaki Trading Reward (V2) sekmesine tıkla

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

3. Adım: Mevcut ödül durumunu kontrol etmek için ApolloX ödül talep sayfasına yönlendirileceksin. Etkinlik süresi içinde ödüllerini talep etmek için "Talep Et"e tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
