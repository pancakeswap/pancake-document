---
hidden: true
---

# Dumb Mode

### Genel Bakış

PancakeSwap Perpetuals'taki [**Dumb Mode**](https://perp.pancakeswap.finance/en/futures/v2/BTCUSD?theme=light\&chain=bsc), bir dayanak varlığın değerindeki dakika dakika dalgalanmalar üzerinde işlem yapmayı tercih eden traderlar için ideal olan basitleştirilmiş bir işlem deneyimi sunar. Dumb Mode, gürültüyü azaltarak işlemleri sadeleştirir ve kullanıcıların kısa vadeli pozisyonlara kolayca giriş yapıp çıkmasına olanak tanır.

### Nasıl Çalışır

Kullanıcılara farklı yatırım getirisi oranlarıyla 5 dakika, 15 dakika, 30 dakika ve 1 saatlik sona erme pencereleri sunulur. Kullanıcılar bir dayanak varlık için long veya short seçeneğini tercih edebilir.

Sona erme süresinin sonunda, dayanak varlık kazanan pozisyondaysa (long için açılış fiyatından yüksek fiyat, short için açılış fiyatından düşük fiyat), kullanıcılar kâr elde eder.

Her sona erme döneminin farklı bir yatırım getirisi (ROI) vardır. Sona erme süresi ne kadar uzun olursa ROI o kadar yüksek olur. Yüzdeler ve ücretler aşağıdaki gibidir:<br>

| Sona Erme Süresi | Kazanılan ROI (ücretler dahil net)\* | Kaybedilen ROI | Ücretler (Kazanımda) |
| ----------------- | --------------------------- | ---------- | ----------------- |
| 5 dakika         | %50                         | -%100      | Teminatta %6  |
| 15 dakika        | %55                         | -%100      | Teminatta %6  |
| 30 dakika        | %70                         | -%100      | Teminatta %6  |
| 1 saat            | %83                         | -%100      | Teminatta %6  |

\*Kazanılan ROI, piyasa koşullarına bağlı olarak zaman zaman ayarlanabilir. Güncellemeler için bu sayfayı kontrol edin.

Örneğin, aşağıdaki senaryoda:

* Seçilen Pozisyon: Long
* Yatırılan Teminat: 100 USDT
* Sona Erme Süresi: 60 saniye
* Açılışta BTCUSD fiyatı: 50.000 $
* 60 saniye sonra BTCUSD fiyatı: 50.001 $

Kullanıcı **100 USDT \* %75 = 75 USDT** kâr eder.

Dumb Mode pozisyonu nasıl açılacağı hakkında daha fazla bilgi için [buraya](dumb-mode-guide.md) tıkla.

### Piyasalar ve Marj Varlıkları

Dumb Mode, **BNB Chain** üzerinde aşağıdaki piyasaları ve marj varlıklarını destekler:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Piyasa</td><td>Marj Varlıkları</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p><p>CAKEUSD</p><p>BNBUSD</p><p>SOLUSD</p></td><td><p>USDC</p><p>USDT</p><p>CAKE</p><p>ETH</p><p>BTC</p><p>HAY</p></td></tr></tbody></table>

Dumb Mode, **Arbitrum, opBNB ve Base Zincirlerinde** aşağıdaki piyasaları ve marj varlıklarını destekler:

<table data-header-hidden><thead><tr><th width="330"></th><th></th></tr></thead><tbody><tr><td>Piyasa</td><td>Marj Varlıkları</td></tr><tr><td><p>BTCUSD</p><p>ETHUSD</p></td><td><p>USDC</p><p>USDT</p><p>ETH</p><p>BTC</p></td></tr></tbody></table>

Daha fazla varlık/zincir desteği geliştirme aşamasındadır.

### Ücretler

Kazanılan bir işlem durumunda anaparanın veya teminatın **%6**'sı ücret olarak alınır. Bu, ROI hesaplanmadan önce zaten hesaba katılır.

<br>
