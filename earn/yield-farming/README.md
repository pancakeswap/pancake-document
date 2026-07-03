# 🚜 Yield Farming

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/yield-farms-header.png)

Yield Farms, kullanıcıların LP Token'larını stake ederek PancakeSwap'ı desteklerken CAKE kazanmalarını sağlar.

Farming'e başlamak için [Farm Nasıl Kullanılır rehberimize](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) göz at.

[Farm akıllı sözleşmelerini nasıl bulacağını öğren](../../archive/how-to-use-farms-with-bscscan.md)

{% hint style="warning" %}
Yield farming, Syrup Pools'a kıyasla daha iyi ödüller sunabilir; ancak **Kalıcı Olmayan Kayıp** (Impermanent Loss) riski taşır. Kulağa ürkütücü gelse de, başlamadan önce bu kavramı öğrenmeye değer.

Daha fazla bilgi için Binance Academy'nin [Kalıcı Olmayan Kayıp hakkındaki harika makalesine](https://academy.binance.com/en/articles/impermanent-loss-explained) göz at.
{% endhint %}

## Ödül hesaplamaları

Yield Farm APR hesaplamaları şunların her ikisini de kapsar:

* Likidite sağlayarak kazanılan **LP ödülleri APR** ve;
* Farm'da LP Token'larını stake ederek kazanılan **Farm temel ödülleri APR**.

Neden? Çünkü CAKE kazanmak için LP token'larını bir farm'da stake ettiğinde, likidite havuzuna likidite sağlamaya devam edersin; dolayısıyla LP ödülleri de kazanırsın!

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Frame%201.png)

Peki bu rakamları nasıl hesaplıyoruz?

### Farm Temel Ödül APR'sinin Hesaplanması

**Farm Temel APR**'si, farm çarpanına ve farm'daki toplam likidite miktarına göre hesaplanır — bu, farm'a dağıtılan CAKE miktarıdır.

### LP Ödül APR'sinin Hesaplanması

Bunun üzerine, çiftçiler likidite sağlamak karşılığında **LP ödülleri** de alır. İşte **LP ödüllerinin** hesaplanmasına dair bir örnek:

![](https://lh4.googleusercontent.com/rJswz2qvCNTcODcClHxqlLpanSLsfbGtVw75MMPicBN1iKTKCuEYlPuoFAqskoy24DB9JBmATWb8dk3WmY1_BFDZoS94sWTBZhZrcnG711rC8ltDXPR3gdl8D50eWq_cfiBriKcl)

Yukarıdaki WBNB/BUSD çiftinde şu değerleri görüyoruz:

**Likidite:** 387,42 Milyon $\
**24S Hacim:** 96,97 Milyon $\
**7G Hacim:** 709,73 Milyon $

* Yıllık ücretleri hesapla
  * Havuzdaki likidite sağlayıcıların **ücret payını** hesaplamak için 24 saatlik hacmi kullan (%0,17 işlem ücreti yapısına göre):\
    $96.970.000 × 0,17/100 = **$164.849**
  * Ardından, havuzun tahmini **yıllık ücretlerini** hesaplamak için bu **ücret payını** kullan (mevcut 24 saatlik hacme göre):\
    $164.849 × 365 = **$60.169.885**
* Artık **LP ödülleri APR**'sini hesaplamak için yıllık ücretleri kullanabiliriz: **Yıllık ücretleri** **likiditeye** böl:\
  ($60.169.885 / $387.420.000) × 100 = **%15,53 LP ödül APR**
