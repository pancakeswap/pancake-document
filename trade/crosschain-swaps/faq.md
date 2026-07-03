# ❓ SSS

### 1. Cross-chain Swap'larda Kayma toleransı nasıl çalışır?

Cross-chain Swap'larda, seçtiğin Kayma toleransı yüzdesi hem kaynak hem de hedef zincirdeki Swap'lara bağımsız olarak uygulanır.

**Örnek:**

* BNB Chain'de BNB'yi Arbitrum'da ARB ile takas et
* Kayma toleransı %1 olarak ayarlandı
* Rota şöyle olabilir:
  1. BNB Chain'de BNB'yi USDC ile takas et
  2. USDC'yi Across aracılığıyla BNB Chain'den Arbitrum'a köprüle
  3. Arbitrum'da USDC'yi ARB ile takas et
* Bu durumda %1 Kayma toleransı ayrı ayrı şunlara uygulanır:
  * BNB Chain'deki Swap
  * Arbitrum'daki Swap

Bu, köprüleme sürecini Kayma ayarlarından etkilemeden işlemin her iki ayağındaki aşırı fiyat hareketlerine karşı korunmanı sağlar.

### 2. İşlemim başarısız olursa ne olur?

Cross-chain Swap'ın herhangi bir aşamada başarısız olması durumunda şu şekilde ele alınır:

1.  **Kaynak Zincirde Swap/İşlem Başarısızlığı**

    ➝ Kaynak zincirde orijinal token'ını anında geri alırsın.
2.  **Bridge İşlemi Başarısızlığı**

    ➝ Across, 90 dakika ile 2 saat içinde geri ödeme işlemi gerçekleştirir ve köprülenmiş varlığı kaynak zincirde geri alırsın. Relay ise SOL <> EVM arasındaki bu tür senaryolarda geri ödemeyi bir dakika içinde işler.
3.  **Hedef Zincirde Swap Başarısızlığı**

    ➝ Hedef zincirde köprülenmiş varlığı, hedef token'a nihai Swap olmaksızın alırsın.

{% hint style="info" %}
**Not:** İşlemlerinin durumunu her zaman cüzdan bağlantısı arayüzündeki işlem geçmişi sekmesinden kontrol edebilirsin.
{% endhint %}

### 3. Cross-chain Swap'larım MEV korumalı mı?

MEV Guard yalnızca Swap'ların MEV Guard etkin bir bağlı cüzdandan doğrudan başlatıldığı durumlarda BNB Chain'de desteklenir.

* Cross-chain Swap'ın kaynak zincir olarak BNB Chain üzerinde bir Swap içeriyorsa ve MEV Guard etkinse, bu Swap MEV korumalı olur.
* BNB Chain hedef zincirse, Swap köprüleme rölesisi/sistemi tarafından gerçekleştirilir ve bağlı cüzdanın başlatmadığı bir işlem olduğundan MEV korumalı olmaz.

{% hint style="info" %}
**Not:** Arbitrum ve Base gibi diğer zincirler şu anda PancakeSwap'ta MEV Guard korumasını desteklememektedir.
{% endhint %}

### 4. Zincirler arasında stablecoin takas edebilir miyim?

Evet — USDC, USDT ve DAI gibi stablecoin'leri desteklenen zincirler arasında doğrudan takas edip köprüleyebilirsin.

İki seçeneğin var:

1.  **Doğrudan Köprü:**

    Desteklenen stablecoin'leri (USDC, USDT gibi) bir zincirden diğerine doğrudan köprüle.
2.  **Diğer Token'larla Takas:**

    Köprülemeden önce veya sonra PancakeSwap'ın likidite havuzlarını kullanarak hedef zincirde desteklenen herhangi bir token'a da stablecoin takas edebilirsin.

{% hint style="info" %}
**Not:** Doğrudan köprüleme için desteklenen stablecoin'ler zincire göre farklılık gösterebilir.
{% endhint %}

### 5. Swap'larım PCSX kullanacak mı?

Hayır — PCSX, Cross-chain Swap'lara hizmet vermek için desteklenmemektedir.

PancakeSwap üzerindeki Cross-chain Swap'lar yalnızca şunlar üzerinden yönlendirilir:

* Zincir üstü Swap'lar için **PancakeSwap'ın likidite havuzları** (v2, v3, Infinity, StableSwap) ve
* Zincirler arasındaki varlıkların köprülenmesi için **Across ve Relay protokolleri**.

PCSX, bir Cross-chain Swap işleminin herhangi bir bölümünü kolaylaştırmak veya yönlendirmek için kullanılamaz.

### 6. Swap miktarında minimum veya maksimum bir sınır var mı?

Evet — Cross-chain işlemler için hem minimum hem de maksimum sınırlar geçerlidir.

* **Maksimum Sınır:**\
  Seçilen token ve zincir için mevcut bridge likiditesine bağlıdır. Bu değer, ağ ve likidite koşullarına bağlı olarak gerçek zamanlı dalgalanabilir.
* **Minimum Sınır:**\
  Röleicilerin bridge işlemini gerçekleştirmesinin ekonomik açıdan uygulanabilir olmasını sağlamak amacıyla belirlenir.

{% hint style="info" %}
**Not:** Kesin minimum ve maksimum sınırlar bridge token'ına göre değişir. İşlem miktarın izin verilen aralığın dışındaysa arayüz net bir hata mesajı gösterecek ve miktarı ayarlamanı isteyecektir.
{% endhint %}
