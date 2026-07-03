# Limit Emirleri Nasıl Kullanılır

PancakeSwap'taki ücret kazandıran limit emirleri, geleneksel limit emirlerinden farklı çalışır. Bir kullanıcı limit emri verdiğinde, aslında PancakeSwap Infinity havuzuna **tek taraflı likidite** sağlamış olur.

Piyasa fiyatı hareket ettikçe, havuzdaki swap'lar kullanıcının likiditesini kullanabilir. Bu gerçekleştiğinde, yatırılan tokenlar tamamen çıktı tokenlarına dönüştürülür ve kullanıcı şunları alır:

* Çıktı tokenları ve
* Likiditesine karşı gerçekleştirilen swap'lardan kazanılan işlem ücretleri.

***

**Örnek: BNB'yi USDT için Satmak**

* **BNB/USDT havuzundaki mevcut fiyat:** BNB başına 600 USDT
* **Kullanıcının hedef / limit fiyatı:** BNB başına 700 USDT

Süreç:

1. Kullanıcı BNB'yi 700 USDT'ye satmak için limit emri verir.
2. BNB'si havuzda 700 USDT/BNB fiyatına en yakın tick'e yatırılır.
3. Dış piyasa fiyatı 700 USDT'ye ulaştığında, havuz fiyatı eşleşecek şekilde ayarlanır (arbitraj fırsatları / daha iyi fiyatlama nedeniyle).
4. Bu noktada kullanıcının BNB'si USDT'ye dönüştürülür.
5. Bu süreçte kullanıcı, likiditesini kullanan her swap'tan ücret kazanır.
6. Likidite tamamen tüketildiğinde, dönüştürülen USDT (artı ücretler) otomatik olarak çekilir ve kullanıcının cüzdanına gönderilir.

***

### Adım adım rehber

Satmak / satın almak istediğin bir token çifti (ör. BNB/CAKE) ve miktarı seç

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Hedef / limit fiyatını ayarla

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Limit emrini ver ve "Onayla". Likidite senin adına limit fiyatına en yakın tick'e yerleştirilir

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Havuz fiyatı hedefinize ulaştığında emrin gerçekleşir. İstediğin çıktı tokenları + ücretler otomatik olarak çekilir ve cüzdanına gönderilir.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Emir Durumu

Emir durumunu buraya tıklayarak görüntüleyebilirsin

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Emrin aşağıdaki durumlardan birinde olabilir:**

| Durum            | Açıklama                                                                                  |
| ---------------- | ---------------------------------------------------------------------------------------- |
| Beklemede        | Fiyatın hedefe ulaşması bekleniyor                                                        |
| Gerçekleşti      | Emir gerçekleşti ve fonlar cüzdanına gönderildi                                           |
| Kısmen Gerçekleşti | Emrinin yalnızca bir kısmı gerçekleşti. Her iki tokeni de tutacaksın (ör. bir kısım BNB, bir kısım USDT) |
| İptal Edildi     | Emri iptal ettin. Tüm fonların sana iade edildi                                           |

### SSS

**S: Limit emri vermek için ücret ödemem gerekiyor mu?**

C: Hayır. Bunun yerine emrin gerçekleştiğinde işlem ücretlerinde %0,1 kazanırsın.

**S: Herhangi bir çift için emir verebilir miyim?**

C: Lansmanında yalnızca seçili çiftler desteklenmektedir. Daha fazla çift daha sonra eklenecektir.

**S: Minimum emir boyutu nedir?**

C: 50 $. Bu, aşırı gaz maliyetine yol açabilecek küçük emirleri önler.&#x20;

**S: Emrimin yalnızca bir kısmı gerçekleşirse ne olur?**

C: Her iki tokeni de tutacaksın. İstediğin zaman iptal edebilir ve kazanılan ücretler dahil her iki tokeni de çekebilirsin.

**S: Emrim gerçekleşti ama cüzdanımda fonları henüz görmedim?**

C: Bu çok nadir senaryolarda gerçekleşebilir, ancak fonların her zaman güvendedir. Fonları manuel olarak talep etmek için emir ayrıntıları arayüzündeki "Çek" düğmesini kullan.
