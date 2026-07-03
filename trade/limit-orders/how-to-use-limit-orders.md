---
hidden: true
---

# Limit Emirleri Nasıl Kullanılır

## Limit Emirleri Nedir

Limit emri, kullanıcıların gerçekleştirme anındaki piyasa fiyatına güvenmek yerine belirli bir fiyattan veya daha iyi bir fiyattan varlık satın almasını veya satmasını sağlayan bir araçtır. Limit emirde fiyat garanti edilir, ancak emrin gerçekleştirilmesi garanti edilmez — limit emirler yalnızca fiyat emir koşullarını karşıladığında gerçekleştirilir.

## Limit emri nasıl kurulur

1. Swap sayfasına git ve "LIMIT"e tıklayarak limit emri seçeneğini seç veya şu bağlantıyı kullan: [https://pancakeswap.finance/swap/limit](https://pancakeswap.finance/swap/limit)
2. İşlem yapmak istediğin "Kaynak" ve "Hedef" tokenları seç. Bu örnekte sırasıyla USDC ve ETH'yi seçtik; yani USDC ile ETH satın almak istiyoruz.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%281%29.png)

1. İşlem yapmak istediğin miktarı gir. Limit fiyatının, mevcut piyasa fiyatını göstereceğine dikkat et; bu da hedef tokenların (ETH) çıktı miktarını tahmin edecektir
2. İstediğin limit fiyatını belirle. İşlemler YALNIZCA mevcut piyasa fiyatı limit fiyatından daha iyi veya eşit olduğunda gerçekleştirilir. Hedef token çıktı miktarı buna göre güncellenecektir.

Aşağıdaki örnekte, ETH fiyatı 1.900 $ veya daha iyi olduğunda ETH satın almak istiyoruz. Alınacak ETH miktarı 0,037 ETH'ye eşit veya daha fazla olacak. Yalnızca bu miktara eşit veya daha iyi teklifler emri doldurmaya uygun olacaktır. Bu miktar gaz maliyetleri ve ücretleri hesaba katar.&#x20;

{% hint style="info" %}
Önemli not: Ücretler çıktı token miktarından ödendiğinden, limit fiyatı gaz ve işlem ücretlerini içerir; bu nedenle kullanıcılar fiyatı ayarlarken bunu dikkate almalıdır. Örneğin, çok küçük bir emrin gaz ücretleri emrin çıktısının çok büyük bir yüzdesine ulaşabilir; bu da spot piyasa fiyatıyla rekabetçi olmayan gerçek bir limit fiyatını yansıtır.
{% endhint %}

3.  "Emri Ver"e bas. Emir ayrıntılarını iki kez kontrol et, yasal uyarıyı kabul et ve "Emri Onayla"ya bas.

    <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29%20%281%29.png" alt="" width="375"><figcaption></figcaption></figure>
4. İşlem tamamlandıktan sonra, emrini "Açık emirler" altındaki emir geçmişi bölümünde görebileceksin. \
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29%20%281%29.png)
5. Açık emirler, emri genişletip "Emri İptal Et" düğmesine tıklayarak her zaman iptal edilebilir.

Dikkate alınması gereken hususlar:

* Mevcut piyasa fiyatı belirlediğin limit fiyatından kötüyse emrin gerçekleştirilmeyebilir.
* İşlemler, emirleri doldurmak için rekabet eden zincir dışı alıcılar kullanan merkezi olmayan bir protokole dayanır. Bu alıcılar ücret talep etme hakkına sahiptir; protokol bu ücreti kazanan alıcı için çıktı tokenlarından düşer.&#x20;
* Alıcılar, ücretlerini belirlerken işlemlerin gaz ücretlerini de hesaba katabilir; bu da ücret miktarlarında dalgalanmalara yol açabilir.
* Bir limit fiyatı belirtirken, kullanıcılar arayüzde emir doldurulursa alacakları minimum hedef token miktarını görecekler. Yalnızca bu miktara eşit veya daha iyi teklifler yapan alıcılar emri doldurmaya uygun olacaktır. Bu miktar gaz maliyetleri ve işlem ücretlerini hesaba katar.
