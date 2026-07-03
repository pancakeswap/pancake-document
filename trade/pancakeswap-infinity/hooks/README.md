# Hooks

{% hint style="info" %}
Geliştirici iseniz veya bir hook geliştirmeye yönelik ayrıntılı teknik dokümantasyon arıyorsanız lütfen [buraya](https://developer.pancakeswap.finance/contracts/infinity/guides/develop-a-hook) gidin.
{% endhint %}

Hook'lar, geliştiricilerin PancakeSwap Infinity'deki likidite havuzlarının davranışını genişletmesine ve özelleştirmesine olanak tanıyan güçlü eklentilerdir. Bunları likidite havuzlarına yeni özellikler ekleyen "eklentiler" veya "widget'lar" olarak düşünebilirsin.

#### 🔍 Hook'lar Nedir?

* Hook'lar; geliştiriciler, protokoller veya topluluk üyeleri tarafından oluşturulan ve davranışlarını geliştirmek veya değiştirmek amacıyla likidite havuzlarına eklenen harici akıllı sözleşmelerdir.
* Her havuzun yalnızca bir hook'u olabilir, ancak tek bir hook birçok havuza hizmet edebilir.
* Hook'lar şu gibi temel eylemlerin öncesinde veya sonrasında özel kod çalıştırabilir:
  * Bir havuzu başlatma
  * Swap yapma
  * Likidite ekleme/çıkarma
  * Bağış yapma<br>

**⛓️ Hook'lar Nasıl Çalışır:**

* Bir hook, havuz oluşturulurken seçilir ve sonradan değiştirilemez.
* Bir hook sözleşmesi, belirli eylemlerde (Swap, likidite ekleme vb.) tetiklenir ve sözleşme içinde tanımlananlar doğrultusunda bu eylemlerin öncesinde veya sonrasında mantığı uygular.
* Örneğin, bir hook şunları yapabilir:
  * CAKE sahiplerine Swap ücreti indirimi sunma
  * Özel ücretler uygulama ve ödülleri dağıtma
  * StableSwap veya TWAP tarzı emirler gibi yeni Swap mantığını etkinleştirme<br>

#### ⚙️ Hook Geri Çağırmaları

Hook'lar on belirli anda tetiklenebilir. Geliştiriciler hangilerini uygulayacaklarını seçebilir:

* beforeInitialize / afterInitialize
* beforeAddLiquidity / afterAddLiquidity
* beforeRemoveLiquidity / afterRemoveLiquidity
* beforeSwap / afterSwap
* beforeDonate / afterDonate<br>

Bunlar, hook'lar aracılığıyla oldukça özelleştirilebilir ve modüler davranışların uygulanmasına olanak tanır.

#### 🔧 İki Tür Hook

**Tür 1: Yetkilendirme Gerekmiyor**

Bu hook'lar otomatik olarak çalışır ve kullanıcı iznine ihtiyaç duymazlar. Swap'lar veya likidite değişiklikleri gibi eylemlerle tetiklenirler.



Örnekler:

* Dinamik Ücretler: Piyasa oynaklığına göre Swap ücretlerini ayarlama
* Ücret İadesi: CAKE tutan veya yüksek hacimde işlem yapan kullanıcılara indirim sunma



Örnek Akış (CAKE Ücret İndirimi):

1. Kullanıcı bir Swap başlatır.
2. Hook, `beforeSwap` hook geri çağırması aracılığıyla CAKE bakiyesini kontrol eder.
3. Kullanıcı tanımlanmış eşikler uyarınca yeterli CAKE tutuyorsa, havuz ücretlerinde %50 indirim alır.
4. İşlemin geri kalanı her zamanki gibi devam eder.<br>

{% hint style="success" %}
Bu hook'lar özel bir arayüz veya ek etkileşim gerektirmez. Faydalar otomatik olarak uygulanır.
{% endhint %}

**Tür 2: Kullanıcı Yetkilendirmesi Gerekli**

Bu hook'lar, kullanıcıların doğrudan onlarla etkileşime girmesini, yetkilendirme sağlamasını ve genellikle pozisyon oluşturmak veya yönetmek için fon transferini gerektirebilir.



Örnekler:

* Limit Emirler: Yalnızca hedef fiyata ulaşıldığında bir Swap gerçekleştirme.
* TWAP: Büyük emirleri daha iyi gerçekleştirme için daha küçük parçalara bölme.
* Aktif Likidite Yönetimi: Optimal getiri için LP pozisyonlarını otomatik olarak yönetme.



Örnek Akış (Limit Emir Hook'u):

1. Kullanıcı, hook sözleşmesiyle doğrudan etkileşime girer (normal Swap arayüzüyle değil).
2. Limit fiyatı, token çifti, miktar gibi ayrıntıları girer.
3. Hook, emri temsil eden bir makbuz token'ı çıkarır.
4. Daha sonra, havuz fiyatı hedefe ulaştığında hook, afterSwap kullanarak emri gerçekleştirir.
5. Kullanıcı, takas edilen varlıkları talep etmek için makbuz token'ını iade edebilir.

{% hint style="info" %}
Bu hook'lar genellikle özel bir arayüz gerektirir ve kullanıcıların hook sözleşmesinin fonlarını tutmasına güvenmesi ve onaylaması gerekir.
{% endhint %}

#### 🚀 Kullanım Durumları ve Yenilik

Hook'lar sınırsız olasılıkların kilidini açar; bunlar şunlardır:

* Özel AMM'ler (ör. stablecoin eğrileri)
* Likidite madenciliği ödülleri
* Otomatik işlem stratejileri, likidite yönetimi
* Zincir üzeri limit emirler, diğer emir türleri
* Dinamik fiyatlandırma ve ücret ayarlamaları
* Getiriyi artıran LP stratejileri<br>

Hook'larla geliştiriciler, PancakeSwap Infinity'nin mevcut altyapısını kullanarak tamamen yeni bir DeFi deneyimi oluşturabilir; bu sayede geliştirme süreci hızlanır ve maliyetler düşer.
