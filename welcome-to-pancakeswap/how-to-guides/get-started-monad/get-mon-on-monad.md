---
hidden: true
---

# Monad'da MON Edinme

### 1. **Neden MON'a İhtiyacın Var**

MON, Monad blok zincirinin **yerel token'ıdır**. Şunlar için ihtiyacın olacak:

* Herhangi bir işlem için (swap, likidite ekleme vb.) **gas ücretlerini öde**
* PancakeSwap'ta **likidite pozisyonları oluştur ve yönet**
* **Herhangi bir Monad dApp ile etkileşime gir**

***

### 2. **MON Edinmenin Başlıca Yolları**

Başlangıç noktana ve tercihlerine bağlı olarak MON edinmenin **dört ana yolu** vardır.

| Yöntem                              | En uygun kişi                                            | Cüzdan gerekiyor mu?       | Notlar                               |
| ----------------------------------- | -------------------------------------------------------- | -------------------------- | ------------------------------------ |
| **Merkezi Borsalar (CEX)**          | Fiat ile alım yapan yeni başlayanlar veya kullanıcılar   | ✅ Evet (dApp'lere erişmek için) | En yaygın giriş noktası         |
| **PancakeSwap (DEX)**               | Halihazırda Monad'da token'ı olan DeFi kullanıcıları    | ✅ Evet                     | Doğrudan MON'a Swap et               |
| **Cüzdan Uygulamasından Satın Al** | Mobil öncelikli kullanıcılar                             | ✅ Evet                     | Bazı cüzdanlar uygulama içi alım sunar |
| **Başka Zincirden Bridge**         | Ethereum, BNB Chain, Base vb.'de fonu olan kullanıcılar | ✅ Evet                     | Varlıkları Monad'a getir             |

Hepsini inceleyelim:

#### I. **Merkezi Borsadan (CEX) MON Satın Al**

Kripto dünyasına yeni giriyorsan veya henüz cüzdanın yoksa, **büyük bir borsadan** MON satın almak en doğrudan seçenektir.

#### ✅ Ne yapacaksın:

1. Merkezi bir borsada (örn. Binance) **hesap oluştur**.
2. Fiat (USD, EUR vb.) veya diğer kripto para birimleriyle **MON satın al**.
3. PancakeSwap gibi dApp'lerle etkileşime geçmek için **MON'u** **kendi gözetiminizde olan Monad cüzdanına** **çek**.

***

#### II. **PancakeSwap'ta (DEX) MON Swap Et**

Monad'ı zaten kullanıyor musun? Monad ağında **USDC** veya **USDT** gibi token'ların varsa, bunları **PancakeSwap** üzerinden doğrudan MON ile Swap edebilirsin.

#### ✅ Ne yapacaksın:

* Cüzdanını Monad üzerinden PancakeSwap'a bağla.
* **Swap** sayfasına git.
* Monad tabanlı token'ını MON ile Swap et.

> 🧠 Not: Swap işleminin kendisini ödemek için yine de az miktarda MON'a ihtiyacın olacak. Hiç MON'un yoksa önce CEX veya bridge yöntemini kullan.

***

#### III. **Cüzdan Uygulamasından Doğrudan MON Satın Al**

Bazı cüzdanlar Apple Pay, Google Pay, kredi kartı veya MoonPay gibi sağlayıcılar aracılığıyla **uygulama içi kripto satın almayı** destekler.&#x20;

#### ✅ Ne yapacaksın:

1. Cüzdanını aç.
2. "Buy" veya "Buy Crypto"ya dokun.
3. **MON**'u seç.
4. Ödeme yöntemini seç ve adımları takip et.

Bu, borsa hesabı oluşturma adımını atlamak isteyen mobil öncelikli kullanıcılar için kullanıcı dostu bir seçenektir.

***

#### IV. **Başka Bir Blok Zincirinden MON Bridge Et**

**BNB Chain**, **Ethereum** veya **Base** gibi farklı bir zincirde token'ların mı var? **Bridge platformları** kullanarak Solana'ya fon getirebilirsin.

#### ✅ Ne yapacaksın:

1. [https://monadbridge.com/](https://monadbridge.com/) adresini ziyaret et
2. Token'ını ve gönderdiğin zinciri seç.
3. Hedef olarak **Monad**'ı seç.
4. Bridge işlemini tamamla ve bridgelenen token'ı Monad cüzdanında al.
5. O token'ı PancakeSwap kullanarak **MON**'a Swap et.

***

### 3. **Son İpucu**

Swap etmekten likidite sağlamaya kadar her Monad işlemi için **gas olarak MON gerekir**. Her işlemden sonra cüzdanında biraz MON bulundurmaya dikkat et; yoksa sıkışıp kalabilirsin.
