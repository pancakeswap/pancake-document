# Syrup Pool SSS ve Sorun Giderme

## Sorun Giderme

### **Stake ettiğim Syrup Pool'u bulamıyorum!**

Syrup Pools sayfasındaki "Bitti" sekmesinin altında Syrup Pool'u bulabilmelisin.&#x20;

"Yalnızca Stake Edilenler" seçeneğini seçmek varlıklarını bulmayı kolaylaştırır.

### **Syrup Pool'dan token'larımı neden unstake edemiyorum?**

CAKE Stake Et, CAKE Kazan havuzlarından unstake yapaмıyorsan, cüzdanındaki SYRUP token'larını satıp satmadığını kontrol et. Bu token, Manuel CAKE havuzundaki CAKE'in üzerindeki 'mülkiyet kanıtı' işlevi görür.&#x20;

### **Stake/unstake yaptıktan sonra kazandığım token'lar neden sıfıra döndü?**

Endişelenme! Zaten cüzdanındalar.

Bir Syrup Pool'da veya farm'da stake ya da unstake yaptığında kazandığın token'lar aynı anda toplanıp cüzdanına gönderilir.

## **Genel Sorular**

### Syrup Pools APR'si nasıl hesaplanır?

> Syrup Pool APR'si = Yıllıklandırılmış ödüller (USD) / Syrup Pool'da stake edilen kullanıcı fonları (USD) \* 100

Temel bir örnek olarak, 300.000 USD değerinde ödülle ve içinde 3.000.000 USD değerinde stake edilmiş CAKE ile 60 günlük bir havuzu ele alalım.

APR, kullanıcılar tarafından stake edilen CAKE arttıkça ve CAKE fiyatı ile ödül token'ının fiyatı değiştikçe dalgalanır.

|                                                       | **Hesaplama**                     | Miktar                                     |
| ----------------------------------------------------- | --------------------------------- | ------------------------------------------ |
| Dağıtılacak toplam ödüller (USD değeri)               |                                   | 300.000 USD                                |
| Dağıtım süresi                                        |                                   | 60 gün                                     |
| Günlük dağıtım                                        | 300.000 / 60 =                    | Günlük 5.000 USD                           |
| **Yıllıklandırılmış ödüller (USD değeri)**            | 5.000 \* 365 =                    | **1.825.000 USD**                          |
| **Havuzda kullanıcılar tarafından stake edilen CAKE değeri (USD)** |                      | **3.000.000 USD**                          |
| **APR**                                               | (1.825.000 / 3.000.000) \* 100 =  | <p></p><p><strong>%60,833 APR</strong></p> |

### **Syrup Pool'umdaki "Bitiş" sayısı neyi ifade ediyor?**

Bu, o havuz için ödüllerin dağıtılmayı bırakacağı zamana kadar kalan blok sayısını gösterir. Havuz o bloğa ulaştığında token'larını unstake etmelisin; çünkü ondan sonra ödül almayacaksın.

### **Syrup Pools'taki ödüller nereden geliyor?**

Üç ana Syrup Pool türü vardır.

1. CAKE Stake Et, CAKE Kazan
2. CAKE Stake Et, başka token'lar kazan.&#x20;
3. Başka token'lar Stake Et, CAKE Kazan

"CAKE Stake Et, CAKE Kazan" Syrup Pools için ödüller [CAKE emisyonlarından](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics) gelir. Her blokta bu havuzlar için ödül olarak belirli sayıda CAKE token'ı ayrılır.

"CAKE Stake Et, başka token'lar kazan" türü için ödüller, Syrup Pool'a sponsor olan proje ekipleri tarafından sağlanır.

"Başka token'lar Stake Et, CAKE Kazan" türü için PancakeSwap hazinesi, ödül olarak dağıtmak üzere piyasadan CAKE satın alır. Bu havuzlar projelerin kendileri tarafından değil, PancakeSwap tarafından finanse edilir.

### SYRUP Token nedir?

PancakeSwap'ın SYRUP Token'ı, **Manuel** "CAKE Stake Et, CAKE Kazan" Syrup Pool ile etkileşime girdiğinde cüzdanına yatırılır. Stake için değildir.&#x20;

Temel olarak havuzda ne kadar CAKE stake ettiğini gösteren bir alacak belgesidir.

CAKE'ini o havuzdan unstake ettiğinde otomatik olarak iade edilir.

{% hint style="warning" %}
SYRUP token'larını satma! CAKE'ini Manuel CAKE havuzundan unstake etmek için SYRUP'unu iade etmen gerekir. İade ettiğin SYRUP miktarı, unstake ettiğin CAKE miktarıyla aynı olmalıdır.
{% endhint %}
