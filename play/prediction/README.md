# 🔮 Tahmin

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/prediction-header.png)

PancakeSwap Tahmin, eğlenceli ve basit bir merkeziyetsiz tahmin piyasasıdır.

> **BNB, BTC veya ETH fiyatının yükseleceğini mi yoksa düşeceğini mi tahmin et – doğru tahmin et ve kazan!**

### Platformlar

PancakeSwap Tahmin'i şuralarda oynayabilirsin:

* **Masaüstü / dApp**: [PancakeSwap Tahmin Rehberi](https://docs.pancakeswap.finance/play/prediction/prediction-guide)
* **Telegram Mini Uygulaması (yalnızca BNBUSD)**: [Tahmin Botu](https://docs.pancakeswap.finance/play/prediction/prediction-mini-app)

### Özet: Nasıl Çalışır

1. **Tahmin edeceğin varlığı seç**: Şu anda **BNB Chain**, **zkSync Era** ve **Arbitrum One** üzerinde kullanılabiliyor.
2. **YUKARI veya AŞAĞI seç**: Varlık fiyatının "CANLI" aşaması sona erdiğinde (her tur = 5 dakika) daha yüksek mi yoksa daha düşük mü olacağını tahmin et.
3. Bahis miktarını belirle: Herhangi bir BNB miktarı
4. **Pozisyonunu sabitle**: Yerleştirildikten sonra bahsin değiştirilemez.
5. **Kazan veya kaybet**:
   * **YUKARI** seçtiysen, turun sonunda _Kapanış Fiyatı_ > _Kilit Fiyatı_ ise kazanırsın.
   * **AŞAĞI** seçtiysen, turun sonunda _Kapanış Fiyatı_ < _Kilit Fiyatı_ ise kazanırsın.

### Mekanikler ve Ücretler

* **Desteklenen Zincirler: BNB Chain, zkSync Era, Arbitrum One**
* **Tur sıklığı**: Her **5 dakikada** bir (sürekli turlar).
* **Katılım ücreti**: Her turun toplam ödül havuzunun **%3**'ü; bunun bir kısmı **CAKE geri alımlarına** gider.
* **Kazançlar**: Sonuçlar kesinleştikten sonra istediğin zaman talep edebilirsin.
* **Ödemeler**, her havuzdaki bahis oranına göre hesaplanır:
  * Ödeme Oranı (YUKARI Havuzu) = _(Her iki havuzun toplam değeri ÷ YUKARI Havuzunun değeri)_
  * Ödeme Oranı (AŞAĞI Havuzu) = _(Her iki havuzun toplam değeri ÷ AŞAĞI Havuzunun değeri)_
  * Bkz: hesaplanmış örnek için [SSS](prediction-faq.md)

### Sonuçlar

* **Kazan:** Toplam potu diğer kazananlarla paylaşırsın (%3 ücret düşüldükten sonra)
* **Kaybet:** Bahis miktarının tamamını kaybedersin

**Özel Durumlar**:

* **Beraberlik** (Kilit Fiyatı = Kapanış Fiyatı): Tüm bahisler eve gider.
* Karşıt bahis yoksa:
  * Kazanırsan: İlk bahsinin %97'sini geri alırsın (%3 ücret geçerli).
  * Kaybedersen: Bahsinin tamamını eve bırakırsın.
* **İptal:** Örneğin Oracle arızası durumunda kullanıcılara ilk bahis miktarları iade edilir.

### Fiyat Akışları (Oracle'lar)

| Zincir    | Piyasalar                                | Amaç                                                                         | Oracle                     |
| --------- | ---------------------------------------- | ---------------------------------------------------------------------------- | -------------------------- |
| BNB Chain | BNBUSD, BTCUSD, ETHUSD, CAKEUSD (durduruldu) | _Kilit Fiyatı_ ve _Kapanış Fiyatı_'nı belirler (yaklaşık 20 saniyede güncellenir). | **Chainlink**              |
| BNB Chain | Tümü                                     | Arayüzdeki canlı grafiği besler (yalnızca referans amaçlı).                   | Binance / TradingView Feed |

#### **ChainLink Oracle**

* Her tahmin piyasası turunun Kilit fiyatı ve Bitiş fiyatı için kullanılır. 20 saniyeye kadar aralıklarla güncellenir.
* Tahmin sözleşmemiz, bir kullanıcının kazanıp kazanmadığını belirlemek için kullanılan fiyatları ayarlamak amacıyla BNB Chain üzerindeki ChainLink Oracle fiyat akışını kullanır.
* Arayüzdeki "Chainlink" grafiği için kullanılır.

#### **Binance**

* PancakeSwap tahmin piyasası arayüzünde gerçek zamanlı fiyat güncellemeleri için kullanılır.
* Arayüzdeki "TradingView" grafiği için kullanılır.

İki farklı fiyat akışı kullandığımız için Binance'den gelen gerçek zamanlı fiyat güncellemeleri ile ChainLink Oracle fiyatı arasında küçük farklılıklar olabilir. Ancak bunlar önemli miktarda sapmamalıdır.

### Sözleşme Adresleri

BNB Chain:

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)
