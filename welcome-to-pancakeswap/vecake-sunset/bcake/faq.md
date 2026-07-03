# SSS

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-bCAKE-FAQ.png)

### bCAKE çarpanları nasıl hesaplanır?

Farklı farmlarda farklı bCAKE boost çarpanları aldığını fark edebilirsin.

Bunun nedeni, bCAKE - Farm Booster çarpanlarının aktivasyon veya yenileme sırasında şu metrikler kullanılarak hesaplanmasıdır:

* `userLpBalanceInFarm`: Farmda stake ettiğin likidite miktarı.&#x20;
  * `NonfungiblePositionManager.positions(uint256 tokenId).liquidity`
* `totalLpBalanceInFarm`: Farmda stake edilen toplam likidite miktarı ya da V3 LP havuzundaki mevcut aktif likidite miktarı. bCAKE ikisi arasındaki daha küçük sayıyı seçer.
  * `MasterChefV3.poolInfo(uint256 pid).totalLiquidity`
  * `PancakeV3Pool.liquidity`
* `veCAKE.balanceOf(user)`: Sahip olduğun gerçek zamanlı veCAKE sayısı
* `veCAKE.totalSupply`: Gerçek zamanlı toplam veCAKE arzı

Çarpan şu yöntemle hesaplanır:

1. `resultA = constantA *`` ``userLpBalanceInFarm`
2. `resultB = totalLpBalanceInFarm * veCAKE.balanceOf(user) / veCAKE.totalSupply * constantB`
3. `boostMultiplier = min(``userLpBalanceInFarm, (resultA + resultB)) / resultA`

`constantA` ve `constantB`, mutfak ekibi tarafından belirlenir ve topluluk geri bildirimleri ile piyasa koşullarına göre ilerleyen dönemlerde ayarlanabilir. `constantB`, LP fiyat farklılıklarını telafi etmek için farklı farmlar arasında değişiklik gösterir.

`constantA` ve `constantB` şu adreslerden alınabilir:

* `FarmBooster.cA`
* `FarmBooster.cBOverride(uint256 pid) > 0 ? FarmBooster.cBOverride(uint256 pid) : FarmBooster.cB`

Ama şunu söyleyebiliriz:

{% hint style="info" %}
**Özetle**

Ne kadar fazla LP (likidite) boost etmek istersen

O kadar fazla CAKE'i daha uzun süreler için kilitlemen gerekir
{% endhint %}

### Aktivasyondan sonra bile neden çarpanlarım değişiyor?

Şunu unutma: **Farming pozisyonuna veya CAKE staking havuzuna yapılan herhangi bir kullanıcı eylemi, en son farm ve CAKE staking havuzu verilerine göre boost çarpanını otomatik olarak günceller.** Bunlar şunları içerir ancak bunlarla sınırlı değildir:

* Farmda pozisyon stake etme/çekme
* Farmdan CAKE ödüllerini hasat etme
* CAKE staking süresini uzatma
* Sabit süreli staking pozisyonuna daha fazla CAKE ekleme
* CAKE staking pozisyonunu esnek modele dönüştürme

{% hint style="warning" %}
Lütfen dikkat et:&#x20;

Güncel olmayan veriler kullanılarak gerçekleşebilecek olası suistimal ve hile girişimlerini önlemek ve adaleti sağlamak amacıyla Farm booster, izinsiz ve topluluk yönetişimine dayalı olarak tasarlanmıştır. Bu nedenle **herkes**, en son verileri kullanarak herhangi birinin boost çarpanlarını güncellemek için MasterChef V3 sözleşmesindeki `updateLiquidity(address _tokenId)` fonksiyonunu çağırabilir.

Bunun yanı sıra mutfak ekibi, bCAKE özellikli tüm farming pozisyonlarını izleyecek ve güncel olmayan çarpanları olan pozisyonları güncelleyecektir.
{% endhint %}

### Neden bir pozisyonu boost edemiyorum?

1. Farm booster yalnızca seçili farmlar için kullanılabilir. İleride daha fazla farm eklenecek. Şimdilik **yeşil roket ikonuyla birlikte yeşil APR rakamını ara.**\
   ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bCAKE-boost-tag.png)<br>
2. Birden fazla sözleşmenin dahil olması nedeniyle bazı sözleşme etkileşimleri biraz daha fazla gas token'ı (BNB) gerektirir. Bu nedenle cüzdanında yeterli BNB bulunduğundan emin ol. Hata devam ederse işlemin gas limitini manuel olarak artırmayı dene.

### Alabileceğim maksimum bCAKE Boost Çarpanı nedir?

Şu anda bir kullanıcının farm booster için alabileceği maksimum boost 2,5x olup orijinal APR'nin 2,5 katını sunar.

Alabileceğin maksimum boost'un stake etmeye çalıştığın likidite türüne göre değiştiğini unutma:

* V3: maksimum 2x
* V2, StableSwap: maksimum 2,5x
* Pozisyon Yöneticileri: maksimum 2,5x

### bCAKE Boost Çarpanlarımı nasıl artırabilirim?

* veCAKE staking pozisyonuna daha fazla CAKE ekle
* veCAKE staking pozisyonunun süresini uzat veya yenile

Kısaca:

**Daha fazla CAKE stake et, daha uzun süre stake et**

[bCAKE boost çarpanlarının nasıl hesaplandığı hakkında daha fazla bilgi edin](faq.md#how-are-the-bcake-multipliers-calculated).

### Ekstra boost edilmiş CAKE ödülleri nereden geliyor?

**Rahatla, bCAKE'i mümkün kılmak için ekstra emisyon ayrılmıyor.**

veCAKE CAKE staking'e benzer şekilde bCAKE, bireysel kullanıcıların diğerlerine karşı payını artırır.

bCAKE'nin devreye alınmasından sonra temel APR düşse de mutfak ekibi bunun iyi bir değiş tokuş olduğuna inanıyor; çünkü sadık CAKE severlerin farming getirisini artırıyor, CAKE'e olan talebi artırıyor ve CAKE staking için harika bir teşvik görevi görüyor.

### Aldığım çarpan neden düşük?&#x20;

bCAKE - farm booster, hem veCAKE staking pozisyonunu hem de likidite farming pozisyonunu diğer kullanıcılara karşı değerlendirerek çalışır. Kısaca:

> Farmda daha fazla liküditeyi boost etmek isteyen kullanıcıların havuzda daha uzun süre daha fazla CAKE kilitlemesi gerekir.

Bu tasarım, avantajların yalnızca büyük yatırımcılara değil, farming pozisyonuna kıyasla önemli bir CAKE staking pozisyonuna sahip her kullanıcıya sunulmasını sağlar.

Çarpanın nasıl hesaplandığı hakkında daha fazla bilgiye [buradan](https://docs.pancakeswap.finance/products/yield-farming/bcake/faq#how-are-the-bcake-multipliers-calculated) ulaşabilirsin.

### Neden yalnızca x sayıda farm booster kullanılabilir?

bCAKE, PancakeSwap'ın temel ürünlerinden biri olan likidite farming'i güncellemeyi içerdiğinden, mutfak ekibi yayılımı daha yavaş ve istikrarlı bir şekilde ele almak istiyor.

Bu nedenle ilk ürün yayın aşamasında pek çok parametre çok muhafazakârdır. Kullanıcıların boost edebileceği farm sayısı, hangi farmların boost edilebileceği ve boost çarpanını almanın güçlük parametresi dahil.

**Mutfak ekibi parametreleri topluluk geri bildirimlerine göre ayarlayacak.**

### **bCAKE V3 denetlendi mi?** <a href="#id-68559543-51e4-438c-9a0a-1e6ece7d2133" id="id-68559543-51e4-438c-9a0a-1e6ece7d2133"></a>

bCAKE hem dahili hem de harici denetçiler tarafından denetlenmiştir.

Denetim raporlarına buradan göz at: [https://docs.pancakeswap.finance/readme/audits](https://docs.pancakeswap.finance/readme/audits)
