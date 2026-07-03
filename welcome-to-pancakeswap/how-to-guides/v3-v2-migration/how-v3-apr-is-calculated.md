# V3 APR Nasıl Hesaplanır

{% hint style="info" %}
V3 Likidite ve Farm'larında, yeni fungible olmayan likidite ve özelleştirilebilir fiyat aralığı özelliğiyle birlikte her LP pozisyonunun kendine ait LP ücreti ve CAKE farming APR'si olacaktır.
{% endhint %}

Toplam APR, LP ücreti APR'si ve CAKE ödülü APR'sinin birleşiminden oluşur.

### LP Ücreti

Teorik olarak, bir fiyat aralığı ve kullanıcının eklemek istediği likidite göz önüne alındığında, beklenen sonraki 7 günlük ücreti şu şekilde tahmin edebiliriz:&#x20;

$$
fee_{next7d} = fee_{in} \frac{\Delta{L}}{L_{in} + \Delta{L}}
$$

* $$fee_{in}$$ : Kullanıcının belirlediği fiyat aralığında son 7 günde biriken ücret tutarı
* $$L_{in}$$: Kullanıcının belirlediği fiyat aralığındaki mevcut likidite
* $$\Delta{L}$$: Kullanıcının fiyat aralığına eklemek istediği likidite

#### Aralıktaki Ücret

$$fee_{in}$$ için geçmiş işlem hacmi verilerini, ücret katmanını ve geçmiş fiyat verilerini kullanarak aralıktaki fiyatı tahmin ederiz.

$$fee_{in} = f_tV_{7d}\frac{T_{in}}{T_{7d}}$$

* $$f_t$$: Ücret katmanı
* $$V_{7d}$$: Son 7 günün toplam işlem hacmi
* $$T_{in}$$: Son 7 gün içinde fiyatların belirlenen fiyat aralığında kaldığı süre (saniye cinsinden)
* $$T_{7d}$$: Saniye cinsinden 7 gün

### Cake APR

#### Pool Tahsisi

MC v3'teki saniye başına toplam ödül CAKE miktarı upkeep kullanır ve `latestPeriodCakePerSecond` ile türetilebilir.

`cakePerSecond = lastestPeriodCakePerSecond / 1e12 / 1e18`

Her Pool'da `poolInfo`'yu kullanarak `poolInfo.allocPoint / totalAllocPoint`'i bölerek `poolWeight`'i elde edebiliriz.

#### Global Cake APR

Global APR, toplam aktif ve stake edilmiş likidite miktarı ile Pool CAKE ödül emisyonları kullanılarak hesaplanır.

`APR (global) = (cakePerSecond * 31536000) / (totalAllocPoint / pool.allocPoint) * 100 * cakeUSD / totalStakedLiquidityUSD`

`totalStakedLiquidityUSD`, MasterChef v3'te stake edilmiş tüm aralıktaki pozisyon tick'lerinden oluşan mevcut Pool aktif stake edilmiş likiditesini USD olarak temsil eder.

#### Pozisyon Cake APR

Bireysel pozisyonların APR'leri, fiyat aralığı ayarlarına göre değişiklik gösterebilir.

$$
ARP_p = {\frac{USD_{r}}{USD_{p}}} {\frac{L_{p}}{L_{lm}}}
$$

* $$USD_r$$: Pool'da yıllık kazanılan CAKE ödülünün USD değeri
* $$USD_p$$: Pozisyondaki toplam USD değeri
* $$L_{p}$$: Pozisyon likiditesi
* $$L_{lm}$$: LMPool tarafından takip edilen toplam stake likiditesi
