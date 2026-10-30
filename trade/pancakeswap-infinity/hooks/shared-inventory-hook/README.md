# Shared Inventory Hook

PancakeSwap'in resmi Shared Inventory Hook'u (SIH), her havuza ayrı likidite kilitlemek yerine tek bir sermaye havuzunun, token'larını paylaşan tüm havuzlarda market-make yapmasına olanak tanımak üzere tasarlanmıştır. Trader'lara daha derin fiyat teklifleri ve daha düşük fiyat etkisi sunarken, likidite sağlayıcılarının aynı kapsama için daha az sermaye kullanmasını sağlar.

PancakeSwap çekirdek ekibi tarafından geliştirilen bu hook, envanterlerini parçalamadan zincir üzerinde birden fazla pariteye fiyat teklifi vermek isteyen varlık ihraççıları ve market maker'lar için özel olarak hazırlanmıştır.

#### 🔍 Neden Shared Inventory?

Birden fazla pariteye geleneksel yöntemle likidite sağlamak, ayrı havuzlara ayrılmış sermayeyi kilitlemek anlamına gelir ve bu sermayenin büyük kısmı işlemler arasında atıl bekler. SIH ise token başına tek bir bakiye tutar ve bunu yalnızca bir swap'ın ihtiyaç duyduğu anda likidite olarak enjekte eder; böylece aynı sermaye, o token'ı paylaşan her havuzu destekleyebilir.

#### 📊 Diğer Modellerden Farkı Nedir?

Geleneksel yoğunlaştırılmış likidite, anaparanın tamamını tek bir havuza yatırmayı gerektirir. Sanal bakiye uzlaşma katmanları gibi diğer cross-pool yaklaşımlar ise genellikle AMM'nin dışında yer alır; bu durumda likidite, zincir üzerindeki havuz derinliği olarak görünmeyebilir ve aggregator'lar tarafından doğrudan yönlendirilemeyebilir.

SIH'in likiditesi, hook tarafından her swap'ta PancakeSwap Infinity CLAMM havuzuna girer ve havuzdan çıkar; bu nedenle router'ların görebildiği ve karşısında işlem doldurabildiği gerçek havuz derinliği olarak görünür.

#### ⚙️ Nasıl Çalışır?

* **Just-in-time (JIT) enjeksiyonu**\
  Her swap'tan önce hook, havuza yapılandırılmış bir yoğunlaştırılmış likidite pozisyonu mint eder; swap gerçekleştikten sonra pozisyonu burn eder ve net sonucu uzlaştırır. Pozisyon yalnızca tek bir swap süresince var olur; bakiye, ihtiyaç duyan bir sonraki havuza hizmet etmek için serbest kalır.
* **Tek bakiye, çok havuz**\
  Envanter hook'un kendi token bakiyesidir, havuz başına yatırım yoktur. Birden fazla havuzda kullanılacak her token, tüm bu havuzlar arasında paylaşılır.

{% hint style="success" %}
Bu, bir havuzun sunduğu derinliği, havuzun doğrudan elinde tuttuğu sermayeden ayırır: fonlanmış bir hook, bir token'ı paylaşan çok sayıda havuzda derin ve dar likidite sunabilir.
{% endhint %}

* **Yapılandırılabilir hook**\
  Hook, hizmet verdiği her havuz için fiyat aralığı ve derinlik açısından ayarlanabilir, bağımsız bir yapılandırma tutar. Bandı taşımak yalnızca bir yapılandırma güncellemesi gerektirir; bu da fiyat tekliflerini hareketli bir referans fiyatın etrafında yeniden ortalamayı kolaylaştırır.

#### 📌 Önemli Çıkarımlar

* Tek bir paylaşılan token bakiyesi, o token'ı kullanan her havuzu destekler. Yeni bir havuz eklemek yeni anapara gerektirmez.
* Tamamen zincir üzerinde ve birleştirilebilir: SIH likiditesi gerçek havuz derinliğidir ve hem PancakeSwap hem de üçüncü taraf aggregator'lar tarafından yönlendirilebilir.
* Trader'lar büyük işlemlerde daha derin fiyat teklifleri ve daha düşük fiyat etkisi elde eder; operatörler ise geleneksel sermayenin bir kesriyle aynı trading ücretlerini kazanır.
