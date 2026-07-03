# 🔀 Cross-chain Swap'lar

Cross-chain Swap'lar, kullanıcıların zincirler arasında token'ları sorunsuz biçimde takas etmesine olanak tanır; tüm bunlar tek, akıcı bir işlemle gerçekleşir.

Cross-chain Swap'lar şu zincirler arasında desteklenmektedir:

* BNB Chain
* Ethereum
* Solana
* Arbitrum
* Base
* zkSync
* Linea

{% hint style="success" %}
**İşlemler şimşek hızında gerçekleşir; genellikle birkaç saniye ile bir dakika içinde tamamlanır.**
{% endhint %}

***

### 🔍 Nasıl Çalışır

1. Kullanıcı Kaynak / Hedef zinciri ve token'ı seçer
2. PancakeSwap yönlendiricisi en verimli rotayı hesaplar
3. Swap'lar, kaynak ve hedef zincirlerdeki PancakeSwap likidite havuzları (v2, v3, Infinity, StableSwap'lar) kullanılarak gerçekleştirilir
4. Köprüleme, ortak protokollerimiz aracılığıyla yönetilir: [Across](https://across.to/) (EVM <> EVM için), [Relay](https://relay.link/bridge) (SOL <> EVM için)

{% hint style="success" %}
**Cross-chain Swap'lar, hem kaynak hem de hedef zincirde yeterli likiditesi olan her token için kullanılabilir.**
{% endhint %}

***

### 💸 Ücretler

* **PancakeSwap, Cross-chain işlemler için herhangi bir ücret almaz.**
* Ücretler şunlardan oluşur:
  1. **İşlem Ücreti:** Kaynak ve hedef zincirlerdeki likidite havuzlarında gerçekleştirilen Swap'lar için ödenir
  2. **Bridge Ücreti:** Varlıkların köprülenmesi için röleciilere ödenir

***

### 🎯 Intent'ler Nedir?

Intent'ler, kullanıcıların nasıl gerçekleştirileceğiyle ilgilenmeden istedikleri sonucu tanımlamasına olanak tanır.

Intent Örnekleri:

* "Base üzerindeki 1 ETH'yi Arbitrum'da en az 3000 USDC ile takas et"

Intent'ler olmadan, kullanıcının şunları manuel olarak yapması gerekirdi:

* ETH'yi Arbitrum'a köprüle
* En iyi ETH → USDC fiyatını sunan bir DEX bul

{% hint style="success" %}
**Intent'lerle — sistem her şeyi otomatik olarak halleder.**
{% endhint %}

**Intent tabanlı tasarımın avantajları:**

* Sorunsuz kullanıcı deneyimi
* Daha hızlı işlem süreleri
* Tek tıklamayla, tek işlemle tamamlama

***

### 🔐 Denetimler

Cross-chain güvenlik alanındaki saygın isimlerle birden fazla denetim turu gerçekleştirdik:

* [**Pashov Audit Group**](https://developer.pancakeswap.finance/crosschain/pashov-audit.pdf)
* [**BurraSec**](https://developer.pancakeswap.finance/crosschain/burrasec-audit.pdf)
