# Temel Özellikler

### 1️⃣ Singleton

PancakeSwap v3'te her likidite havuzunun kendi sözleşmesi vardı; bu durum havuz oluşturmayı ve birden fazla havuz üzerinden Swap yapmayı daha pahalı hale getiriyordu.

Infinity, Singleton modelini uygulayarak bunu düzeltiyor. Artık tüm havuzlar PoolManager adlı tek bir sözleşmede bulunuyor. Bu değişiklik, havuz oluşturma gaz maliyetlerini %99'a kadar düşürüyor ve gereksiz token transferlerini önleyerek çok atlamalı Swap'ları (birden fazla havuzdan geçen Swap'lar) çok daha ucuz hale getiriyor.

#### ⚙️ **Nasıl çalışır:**

* Her havuzun verisi, benzersiz bir havuz kimliği kullanılarak paylaşımlı bir sözleşmede depolanır.
* Yeni bir havuz oluşturmak artık tam bir sözleşme dağıtımı değil, yalnızca bir durum güncellemesidir.
* Havuzlar arasında Swap yapmak daha hızlı ve daha az gaz kullanır.<br>

Bu Singleton yaklaşımı, Flash Accounting ve ERC-6909 gibi diğer optimizasyonlarla birlikte PancakeSwap Infinity'yi günümüzde mevcut en gaz verimli DEX platformlarından biri haline getirmeye yardımcı olur.

***

### ⚡️ Flash Accounting

Flash Accounting, çok atlamalı Swap'lar ve likidite değişiklikleri gibi karmaşık işlemler sırasında gaz ücretlerini azaltmaya yardımcı olan güçlü bir optimizasyondur.

Eski sürümlerde (v3 gibi), tokenlar bir işlemin her adımında her havuzdan girip çıkıyordu. Bu durum, özellikle çok atlamalı Swap'larda yüksek gaz maliyetlerine yol açıyordu.

Flash Accounting ile bu artık gerekli değil. Her adımdan sonra token'ları taşımak yerine, PancakeSwap Infinity tüm token hareketlerini dahili olarak takip eder ve tüm işlemin sonunda yalnızca bir nihai transfer gerçekleştirir. Bu, çok miktarda gaz tasarrufu sağlar.

#### ⚙️ **Nasıl Çalışır:**

* Infinity ile etkileşime girdiğinde (ör. Swap yapma veya likidite ekleme), sistem borçlu olduğun veya alacağın token'ların net bakiyesini hesaplar.
* Bu net token bakiyeleri, Ethereum'un Cancun güncellemesiyle (EIP-1153) tanıtılan yeni bir özellik olan Geçici Depolama kullanılarak geçici olarak saklanır.
* Geçici Depolama, yalnızca işlem süresi boyunca devam ettiğinden geleneksel depolamadan daha ucuzdur; kalıcı yazma veya okuma gerekmez.

***

### 🪙 Yerel Token Desteği

Singleton mimarisi ve Flash Accounting'in sunulmasıyla, PancakeSwap Infinity artık likidite havuzlarında yerel gaz token'larını (ör. BNB, ETH) doğrudan destekliyor; artık sarma ve sarma açma işlemi gerekmiyor.

#### ✅ Temel Özellikler

* **Doğrudan Yerel Token Havuzları:** Artık WETH veya WBNB'ye gerek kalmadan ETH/USDC, BNB/CAKE gibi havuzlar oluşturabilirsin.
* **Gaz Verimli:** Yerel token transferleri, ERC-20 token transferlerinden yaklaşık %50 daha ucuzdur; bu da Swap'lar ve likidite işlemleri için daha düşük gaz maliyeti sağlar.<br>

**Daha Önce Kaldırılmıştı, Şimdi Yeniden Etkinleştirildi:** Uygulama karmaşıklığı ve likidite parçalanması nedeniyle yerel token desteği önceki sürümlerde mevcut değildi.

***

### 📈 Özel Fiyatlandırma Eğrileri

PancakeSwap Infinity, geliştiricilere havuzlar için özel fiyatlandırma modelleri oluşturma gücü veriyor; bu sayede çoğu AMM'de kullanılan geleneksel modelin ötesine geçiliyor.

{% hint style="success" %}
**Geliştiriciler, belirli varlık türlerine veya işlem stratejilerine göre uyarlanmış tamamen yeni Swap davranışları ve likidite modelleri oluşturabilir.**
{% endhint %}

#### 🔧 Özel Fiyatlandırma Eğrileri Nedir?

Özel fiyatlandırma eğrileri, geliştiricilere şunları yapmalarına olanak tanır:

* Özel tanımlı Swap davranışlarına sahip havuzlar oluşturarak yerel havuz yöneticisi mantığını atlatma.
* Swap'lar veya likidite değişiklikleri için token miktarlarının hesaplanma biçimini değiştirme.
* Şunlar gibi özel ücret mekanikleri dahil etme:
  * Likidite çekim ücretleri
  * Stratejiye dayalı iadeler veya cezalar

Tüm bunlar, Swap parametrelerini dinamik olarak izleyebilen ve değiştirebilen öncesi / sonrası Swap hook geri çağırmaları aracılığıyla mümkün kılınmaktadır.

#### 🛠 Örnek Kullanım Durumları

* **StableSwap Eğrileri:** 1:1 fiyat oranı etrafında daha düz eğriler tasarlayarak USDC ve USDT gibi varlıklar arasındaki fiyat etkisini azalt.
* **RWA'lar:** Dinamik arzlı farklı varlık türleri için özel davranışlar oluştur.
* **Hook Düzeyinde Ücretler:** Geliştirici ücretleri gibi havuz düzeyinden farklı benzersiz ücretler uygula.
* **Özel Risk Modelleri:** Fiyatlandırmayı oynaklığı, oracle verilerini veya harici metrikleri yansıtacak şekilde ayarla.

{% hint style="info" %}
Önceki AMM sürümlerinde (ör. PancakeSwap v2/v3), fiyatlandırma mantığı sabit kodlanmış ve katıydı. PancakeSwap Infinity'nin mimarisi, daha sermaye verimli ve özelleştirilmiş havuzlar oluşturma yeteneğini açığa çıkarır.
{% endhint %}

#### 🔍 Geliştirici Esnekliği

* Geliştiriciler, fiyatlandırma mantığını geçersiz kılmak için özel hook sözleşmeleri dağıtabilir.
* `beforeSwap` ve `afterSwap` gibi hook geri çağırmaları, token deltalarının nasıl hesaplandığı ve uygulandığı üzerinde tam kontrol sağlar.

***

### 🧮 ERC-6909: Verimli Çoklu Token Muhasebesi

PancakeSwap Infinity, tek bir sözleşme içinde birden fazla token'ın dahili muhasebesini yapmak için tasarlanmış hafif ve gaz verimli bir token standardı olan [ERC-6909](https://eips.ethereum.org/EIPS/eip-6909)'u benimsiyor. Geleneksel ERC-20 operasyonlarının çoğunu mint ve burn primitifleriyle değiştiriyor; bu da önemli gaz tasarrufları ve basitleştirilmiş işlem akışlarıyla sonuçlanıyor.

#### ⚙️ Nasıl Çalışır

Token'ları her etkileşimde protokole girip çıkarmak yerine, ERC-6909 token'ları dahili bakiyeleri temsil eder:

* Mint: Kullanıcılar token yatırdığında veya işlem yaptığında, talep olarak ERC-6909 token'ları almayı tercih edebilirler.
* Burn: Daha sonra, tekrar ERC-20 token'larını transfer etmek yerine, kullanıcılar bakiyeleri kapatmak veya yeni işlemleri finanse etmek için bu ERC-6909 token'larını yakabilirler.

Bu model, genellikle daha yüksek gaz maliyetlerine neden olan ve üçüncü taraf mantığıyla (ör. USDC'nin kara liste kontrolleri) etkileşime giren harici token transferlerine duyulan ihtiyacı önemli ölçüde azaltır.

#### 🪙 ERC-6909'un Faydaları

<table><thead><tr><th width="262.9921875">Özellik</th><th width="497.7421875">Fayda</th></tr></thead><tbody><tr><td>✅ Dahili Bakiye Talepleri</td><td>Kullanıcı ve sözleşme arasında tekrar tekrar token transfer etmeye gerek yok</td></tr><tr><td>✅ Gaz Verimli Mint/Burn</td><td>Token'dan bağımsız sabit ek yük, harici sözleşme çağrısı yok</td></tr><tr><td>✅ ERC-1155'ten Daha Basit</td><td>Daha küçük kod boyutu, geri çağırma yok, toplu transfer gereksinimi yok</td></tr><tr><td>✅ Çoklu Token Desteği</td><td>Tek bir sözleşme, izole bakiyelerle birden fazla token türünü takip edebilir</td></tr><tr><td>✅ PoolManager ile Uyumlu</td><td>Gereksiz ERC-20 onaylarını ve transferleri ortadan kaldırır</td></tr></tbody></table>

#### 🚀 Kullanım Durumları

* **Yüksek frekanslı yatırımcılar:** Gaz yoğun transferlerden kaçın ve dahili bakiyeleri kullanarak doğrudan etkileşime gir.
* **Likidite yöneticileri:** Aşırı token hareketleri olmadan pozisyonları daha verimli biçimde aç ve kapat.

#### 💡 Temel Notlar

* Kullanıcılar, token transferlerini hemen kapatmaları gerekmediğinde ERC-6909 akışını tercih ederek etkinleştirir.
* Dahili bakiyeler birleştirilebilir ve daha sonra net olarak kapatılabilir; bu da güçlü kullanıcılara daha fazla kontrol ve esneklik sağlar.

***

### 💸 Donate Yöntemi

`donate()` yöntemi, kullanıcıların bir havuzdaki aralık içindeki likidite sağlayıcılara token bağışlayarak doğrudan teşvik etmesine olanak tanır. Bu yöntem, yalnızca havuz token'larının desteklenmesini sağlamak amacıyla ödemeleri kolaylaştırmak için havuzun ücret muhasebesi sistemine dayanır.

#### 🔹 Temel Özellikler:

* **LP'lere Doğrudan Ödemeler:** Bağışlar doğrudan likidite sağlayıcılara yapılır ve havuzun aktif aralığında likiditeyi koruyanları ödüllendirir.
* **Yalnızca Havuz Token'larını Destekler:** `donate()` yöntemi, uygun dağıtımı sağlamak amacıyla ücret muhasebesi sistemini kullandığından yalnızca havuzun token'larındaki bağışları destekler.
* **Tüm Kullanıcılara Açık:** Herhangi bir kullanıcı `donate()` yöntemini çağırabilir; bu sayede herkes aktif likidite sağlamayı teşvik edebilir.

`donate()` yöntemi LP'leri teşvik etmek için güçlü bir araç olsa da, bağışçıların bağışlarının diğer kullanıcılar tarafından ön adımlanabileceğinin farkında olması gerekir. Bu durum, bir bağış yapılmadan hemen önce bir kullanıcının havuza hızla likidite ekleyerek bağışlanan fonların bir kısmını alması durumunda gerçekleşebilir.

Ön koşu önlemek için bağışçıların bağış mekanizmalarını tasarlarken şunlar gibi ek stratejiler düşünmeleri gerekebilir:

* Fırsatçı ön koşu yeteneğini en aza indirecek şekilde bağışların gerçekleşmesini sağlama.
* Bağışların bu şekilde istismar edilmediğinden emin olmak için zaman gecikmeleri veya belirli koşullar ekleme (önce / sonra bağış hook geri çağırmalarını kullanarak).
