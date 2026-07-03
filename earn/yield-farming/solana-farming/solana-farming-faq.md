# Solana Farming SSS

### 1. SOL Farming nasıl çalışır?

* V3 Farming **kampanya tabanlıdır**, yani farm'lar yalnızca belirli bir süre boyunca aktif olur.
* Kampanya süresince:
  * Ödül token'ları **aktif likidite pozisyonlarına** **her saniye** dağıtılır.
  * Farming APR'si havuz listesi sayfasında ve pozisyonlarım sayfasında gösterilir.
* Kampanya sona erdikten sonra:
  1. **Daha fazla ödül** dağıtılmaz.
  2. **Farming APR'si** havuz listesi sayfasında ve pozisyonlarım sayfasında **artık gösterilmez**.
  3. Farm **pasif** hâle gelir; ancak oluşturucu daha fazla ödül ekleyerek yeniden başlatabilir.

### 2. Farming ödülleri kazanmak için LP NFT'mi stake etmem gerekiyor mu?

* **Stake gerekmez**.
* Aktif bir farm'ı olan bir havuzda likidite pozisyonun **aktif (aralık içinde)** olduğu sürece ödülleri otomatik olarak kazanırsın.

### 3. Farm güçlendiricisi var mı?

* **Hayır**, V3 farm'ları herhangi bir güçlendirme mekanizmasını **desteklemez**.
* Ödüller yalnızca havuzdaki aktif likviditenin payına göre belirlenir.

### 4. Aynı havuz için birden fazla farm oluşturulabilir mi?

* **Hayır**, yalnızca **token çifti ve ücret kademesi başına tek bir farm** oluşturulabilir.

### 5. SOL farm'ları nasıl yapılandırılır?

#### A. Token Ödülleri

* Farm başına en fazla **3 farklı ödül token'ı** atanabilir.
* Belirlendikten sonra ödül token türleri **değiştirilemez**.
* Farm oluşturucu şunları yapabilir:
  * Ayrılan ödül token'larını **artırma**.
  * Kampanya sona erdikten sonra **farming süresini uzatma**.

#### B. Kampanya Süresi

* Kampanyalar en az **7 gün**, en fazla **90 gün** sürebilir.

### 6. Oluşturulduktan sonra farm düzenlenebilir mi?

Farm oluşturucular **oluşturulduktan sonra** şu parametreleri düzenleyebilir:

1. Ödül dağıtım oranı (saniye başına)
2. Kampanya bitiş tarihi
3. Ödül token'ı ve karşılık gelen ödül miktarı ekleme (yalnızca başlangıçta 3'ten az token atanmışsa)
