# Dinamik Ücret Hook'u

PancakeSwap'ın resmi Dinamik Ücret Hook'u, Likidite Sağlayıcıları ile Yatırımcılar arasında daha adil bir değer alışverişi oluşturmak için tasarlanmıştır. LP'leri aşırı kalıcı olmayan kayıptan (IL) korurken piyasanın yatırımcılar için verimli kalmasını sağlar.

PancakeSwap çekirdek ekibi tarafından geliştirilen bu hook, geleneksel sabit ücret modellerine akıllı ve uyarlanabilir bir alternatif sunmak için özel olarak hazırlanmıştır.

#### 🔍 Neden Dinamik Ücretler?

Büyük arbitraj işlemleri havuzlarda daha fazla fiyat sapmasına yol açarak LP'ler için IL'yi artırır. Dinamik ücret modelimiz, bu riski dengelemek amacıyla büyük arbitraj işlemlerine orantılı olarak daha yüksek ücretler uygular; arbitrajcıların kâr etmesine ve fiyatları dengede tutmasına yetecek alan bırakırken.

#### 📊 Bu, Diğer Modellerden Nasıl Farklıdır?

Geçmişte kullanılan diğer modeller, oynaklığı tahmin etmek ve ücretleri ayarlamak için geçmiş verileri ve diğer faktörleri kullandı. Ancak:

* Geçmiş veriler gecikmiş bir göstergedir ve gelecekteki oynaklığı doğru biçimde tahmin edemeyebilir.
* Dış piyasa olayları (düzenleyici değişiklikler veya ekonomik dönüşümler gibi) geçmiş eğilimleri güvenilmez hale getirebilir.
* Parametre yoğun, karmaşık modeller aşırı uyum riski taşır; geçmiş verilerle iyi performans gösterir ancak yeni, görülmemiş koşullarda zayıf kalır.

Bizim yaklaşımımız daha basit, uyarlanabilir ve gerçek zamanlı işlem davranışına dayalıdır.

#### ⚙️ Nasıl Çalışır

* **Oynaklığı veya diğer makro faktörleri tahmin etmiyoruz**\
  Bunun yerine modelimiz, farklı piyasa koşullarındaki arbitrajcı davranışından doğal olarak yararlanır:
  * **Yüksek oynaklık:** Daha fazla arbitraj işlemi, daha büyük hacimlerde → LP'ler için daha yüksek ücretler, IL'nin daha büyük bir kısmını karşılar.
  * **Düşük oynaklık:** Daha az, daha küçük işlemler → IL doğası gereği düşüktür, ancak LP'ler sabit ücret modelinden daha yüksek ücret kazanmaya devam eder.
* **Modelimiz şunları kullanır:**
  * Arbitraj işlemlerini tespit etmek için üstel ağırlıklı havuz fiyatı.
  * Her Swap'ın fiyat etkisine dayalı üstel ücret eğrisi.
  * Yatırımcı adaletini korumak için maksimum %5 ücret tavanı.

{% hint style="success" %}
Bu, ücretlerin işlem etkisiyle dinamik olarak ölçeklenmesini ve değişen piyasa koşullarına otomatik olarak uyum sağlamasını güvence altına alır.
{% endhint %}

* **Dengeli Teşvikler**\
  Arbitrajcılar, dinamik ücretlerin ardından kârlarının yaklaşık %50'sini korur; bu da onların havuz fiyatlarını piyasayla uyumlu tutmak için motive olmalarını sağlar.

#### 📌 Temel Çıkarımlar

* Oynaklık veya diğer makro faktör tahminlerine bağımlılık yok.
* Gerçek işlem davranışına göre piyasa oynaklığına otomatik uyum.
* Her Swap bazında LP'leri IL'den korur.
* Arbitrajcıları fiyat açıklarını kapatmak için güçlü teşviklerle destekler.
* Daha derin likidite ve daha düşük temel ücretlerle yatırımcılara fayda sağlar.
