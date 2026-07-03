# CAKE Tokenomics v1

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/en-1129.png)

## **Emisyon oranı** <a href="#emission-rate" id="emission-rate"></a>

### **Blok başına**

| **Metrik**                                                                   | **Emisyon/blok (CAKE)** | **Emisyon/gün (CAKE)** |
| ---------------------------------------------------------------------------- | ----------------------: | ---------------------: |
| Emisyon                                                                      |                      40 |              1.152.000 |
| Haftalık Yakılan [(PID 138)](cake-tokenomics-v1.md#why-is-the-cake-burn-manual) |                 -25,75 |               -787.600 |
| **Efektif Emisyon**                                                          |            **<14,25\*** |          **364.400\*** |

\*Efektif Emisyon aslında bu miktarın biraz altındadır: piyangoya ayrılan miktardan ek olarak günlük 45.000 CAKE saptırılarak yakılmaktadır (PID 137 - Ayrıntılar aşağıda).

Yukarıdakilere ek olarak, Geliştirici adresine de %9,09 oranında dinamik bir CAKE miktarı [mint edilir](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns). Bu, 100 CAKE hasat edilirse 9,09 CAKE'in ek olarak mint edilerek Geliştirici Adresine gönderildiği anlamına gelir.

{% hint style="info" %}
Geliştirici adresine mint edilen tüm CAKE, haftalık yakımda yakılır ve hiçbir zaman dolaşıma girmez.&#x20;

Bu nedenle yukarıdaki emisyon oranına dahil etmedik.
{% endhint %}

## Dağıtım <a href="#distribution" id="distribution"></a>

| Dağıtılan Yer                 | Ödül/blok (emisyonun %'si) | Ödül/blok (toplam CAKE) |            Ödül/gün |
| ----------------------------- | -------------------------: | ----------------------: | ------------------: |
| Farm'lar ve Piyango           |                     10,62% |                    4,25 |    122.400 (yaklaşık) |
| bunun saptırılan ve yakılan kısmı |                        |                         |             -46.000 |
| Syrup Pool'lar                |                        25% |                      10 |    288.000 (yaklaşık) |
| **Toplam Günlük CAKE Emisyonu** |                          |                         | **364.400 (yaklaşık)** |

## **Diğer Deflasyonist Mekanizmalar** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
Yakma işlemi şu anda manüeldir. [Yakma işlemlerini buradan görüntüle](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

Yukarıdakilerin yanı sıra CAKE aşağıdaki şekillerde de yakılır:

* PancakeSwap V2'de yapılan her işlemin **%0,05**'i
* Geliştirici adresine gönderilen CAKE'in **%100**'ü
* IFO'lardan elde edilen CAKE performans ücretlerinin **%100**'ü
* Profil Oluşturma ve NFT basımına harcanan CAKE'in **%100**'ü
* Farm Açık Artırmalarında teklif verilen CAKE'in **%100**'ü
* Piyango biletlerine harcanan CAKE'in **%20**'si
* Günlük **45.000** CAKE (tarihsel olarak piyangoya ayrılan) _(Bu CAKE için Farm üretir - PID 137)_
* Her Tahmin piyasası turundaki **%3** CAKE yakmak için satın alınır
* Auto CAKE Havuzundaki her getiri hasatının **%2**'si
* NFT Market'teki her NFT satışının **%2**'si CAKE yakmak için kullanılır

## CAKE yakımı neden manüeldir?

PancakeSwap, MasterChef sözleşmesinin blok başına 40 CAKE emit etmesiyle bir MVP (minimum uygulanabilir ürün) olarak hızlıca piyasaya çıktı. Bu nedenle erken ekip, CAKE mint mantığını özelleştirme gibi ek işlevler eklemedi. Yeni bir MasterChef'e geçiş çok fazla zaman ve çaba gerektireceğinden ekip, iki havuz oluşturarak manuel yakma süreciyle bunun yerine CAKE emisyonlarını azaltmayı tercih etti:

* Legacy Piyango Havuzu (PID - 137) - piyangodan yakılan CAKE
* Yakma Havuzu (PID - 138) - blok başına yakılan CAKE

Bu havuzlar Farm'larla benzer şekilde çalışır; Şefler her CAKE emisyon azaltma oylamasının ardından blok başına 40 CAKE'ten buna ayrılan yüzdeyi ayarlayabilir.

{% hint style="warning" %}
Yakma günü ana sayfada gösterilen arz aniden birkaç milyon CAKE artabilir.&#x20;

Endişelenme — **BU CAKE ASLINDA HİÇBİR ZAMAN DOLAŞIMA GİRMEZ:**
{% endhint %}

Bu görünür artış, yakılmak üzere ayrılan tüm CAKE'in hafta boyunca nasıl depolandığından kaynaklanmaktadır.&#x20;

PID-137 ve PID-138 her iki havuza gönderilen CAKE, haftalık token yakımları tamamlanmadan önce hasat edilir ve bu durum sitede gösterilen Toplam Arzın yaklaşık 6 milyon artmasına neden olur. Bunun nedeni, bekleyen CAKE'in yakma günü hasat edilene kadar Toplam Arzda kayıtlı olmamasıdır. Token yakma işlemi tamamlandıktan sonra yaklaşık 6 milyon "Bugüne Kadar Yakılan" kısmında görünür.&#x20;

## CAKE Arzını kendin nasıl doğrularsın?

PancakeSwap ana sayfasında gösterilen dolaşımdaki CAKE arzının doğru olduğunu teyit etmek için:

1. BscScan'daki CAKE token sözleşmesine git ve [Yakma Adresinde ne kadar CAKE tutulduğuna bak.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) Bu, yakılmış (dolaşımdan SONSUZA KADAR çıkarılmış ve geri alınması imkânsız) CAKE'in toplam miktarıdır.
2. Ardından bu yakılan miktarı, BscScan'ın gösterdiği "Toplam Arz"dan çıkar.
3. Bu sana gerçek CAKE arzını verir.



#### **CAKE'in deflasyonist mekanikleri hakkında bir sonraki sayfada daha fazlasını oku.** <a href="#read-more-about-cakes-deflationary-mechanics-on-the-next-page" id="read-more-about-cakes-deflationary-mechanics-on-the-next-page"></a>
