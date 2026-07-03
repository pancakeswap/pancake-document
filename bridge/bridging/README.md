---
description: CAKE'i Ethereum, BNB Chain, Aptos ve daha fazlası arasında Bridge et
---

# 🌉 Bridging

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28118%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
EVM'lerden/EVM'lere Bridging (Yeni site): [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge)

Aptos'tan/Aptos'a Bridging (V1 Bridge): [https://bridge.pancakeswap.finance/](https://bridge.pancakeswap.finance/)
{% endhint %}

## Kripto dünyasında Bridge nedir?

* Kripto'da Bridge; farklı blokzincir ağları arasında varlık transfer etme sürecini ifade eder.
* Çeşitli ağlar arasında veri ve varlık transferine olanak tanıyarak birlikte çalışabilirliği artırır.

\
Bridge kullanmak isteyebileceğin bazı nedenler:

* Farklı kripto token'ları satın almak
* Yalnızca belirli bir ağda mevcut olan bir NFT oluşturmak
* Daha ucuz işlemlerle para tasarrufu yapmak
* Başka bir ağda bulunan bir dapp kullanmak

***

## CAKE, çok zincirli bir token

Çok zincirli genişlememiz ve dağıtımımızla birlikte CAKE artık BNB Chain'e özgü, ancak Base, Arbitrum, Solana, Ethereum, ZKsync, Linea, opBNB ve Aptos'ta da kullanılabilen çok zincirli bir token haline geldi.

Diğer zincirlerden herhangi birindeki CAKE, BNB Smart Chain'deki CAKE'e eşittir. Bu zincirler arasında her zaman 1:1 oranında ve CAKE üzerinden herhangi bir ücret alınmadan Bridge edilebilir.

**Lütfen unutma: yalnızca bir CAKE vardır.** Farklı zincirlerde CAKE'in farklı sürümleri bulunmaz. Tüm blokzincirler genelinde toplam CAKE arzı, bu [oylama önerisinde](https://pancakeswap.finance/voting/proposal/0xc988547f7b6c435764c840623685b0c2d13ebcc91d1672d39c51b6d14207f9a5) belirtildiği gibi 400 milyon ile sınırlıdır.

***

## PancakeSwap Bridge nedir?

PancakeSwap Bridge; farklı blokzincirler arasında varlıklarını doğrudan PancakeSwap arayüzü üzerinden taşımana olanak tanıyan kullanışlı, uygulama içi bir araçtır. Harici Bridge sitelerini ziyaret etmek yerine, BNB Chain, Ethereum, Base, Arbitrum ve daha fazlası gibi zincirler arasında desteklenen token'ları tek bir yerden Bridge edebilirsin.

PancakeSwap Bridge, güvenilir üçüncü taraf sağlayıcılar tarafından desteklenmekte olup fiyat, hız ve güvenilirlik kriterlerine göre en iyi rotayı seçen bir **toplayıcı** olarak çalışır.

CAKE Bridge etmeyi öğrenmek için aşağıdaki bölümlerdeki eğitimlere ve SSS'ye göz at.

***

## 🔗 Nasıl Çalışır

### Toplayıcılar Aracılığıyla Bridging

PancakeSwap Bridge, güvenilir üçüncü taraf Bridge protokollerinin üzerinde akıllı bir katman olarak hareket eder. Bir Bridge transferi başlattığında PancakeSwap:

* Optimum rotalar için entegre birden fazla Bridge'i kontrol eder
* İşlemini seçilen sağlayıcıya gönderir

Bridging, emanetsizdir (non-custodial) — varlıkların PancakeSwap'ın gözetimine girmez. Transferler doğrudan Bridge sağlayıcıları tarafından yürütülür.

### Desteklenen Bridge Sağlayıcıları

Şu anda şunlarla entegre çalışıyoruz:

* deBridge
* cBridge
* LayerZero
* Stargate
* Meson

> Not: Her sağlayıcının farklı Bridge mekanizmaları, desteklenen zincirleri, ücretleri ve limitleri vardır.

***

### Desteklenen Zincirler ve Token'lar

#### Şu Anda Desteklenen Zincirler

* BNB Chain
* Base
* Arbitrum
* Ethereum
* opBNB
* ZKsync
* Linea
* Aptos (V1 sitesi)

#### Bridge İçin Mevcut Token'lar

Mevcut token'lar zincire ve rotaya göre değişir. Yaygın olarak desteklenen token'lar arasında şunlar bulunur (bunlarla sınırlı değildir):

* CAKE
* USDT
* USDC
* ETH

***

#### Sınırlamalar ve İstisnalar

Bazı token'lar, Bridge kısıtlamaları veya likidite sorunları nedeniyle desteklenmeyebilir. Bunlar, en iyi kullanıcı deneyimi sunmak amacıyla filtrelenmiştir. Örneğin:

**cBridge için:**

* Wrapped BNB (BNB Chain)
* USDT (Arbitrum)
* USDC.e (Arbitrum)

**deBridge için:**

* cUSDCv3 (Ethereum)
* cUSDCv3 (Polygon)
* cUSDCv3 (Arbitrum)

_Yukarıdakiler örnek niteliğindedir. Zincir başına gerçek mevcut token'lar doğrudan Bridge arayüzünde gösterilmektedir._

***

### 💸 Ücretler ve Maliyetler

#### Bridge Ücretleri

* Temel Bridge sağlayıcısı tarafından alınır
* Genellikle transfer başına küçük bir ücret içerir
* Bridge'ini onaylamadan önce açıkça gösterilir

***

#### Gas Maliyetleri

* İşlemi başlatmak için **kaynak zincirde** gas ücreti ödersin
* Bazı sağlayıcılar **hedef zincirde** de gas talep edebilir
* **İpucu:** Bridge'in her iki tarafında da her zaman yerel token'lar (örn. ETH, BNB) bulundur

***

#### Minimum Miktarlar ve Kısıtlamalar

Bazı Bridge rotaları şunları zorunlu kılar:

* **Minimum/maksimum Bridge miktarları** (örn. minimum 10 USDC)
* **Desteklenen token ondalık sayıları veya formatları** (örn. yalnızca ERC-20 token'lar)

Arayüz, geçersiz transferleri otomatik olarak tespit edip gösterecektir.

***

### ⏳ İşlem Süreleri ve Takip

#### Bridging Ne Kadar Sürer?

Bridge transferleri genellikle birkaç **dakika** içinde tamamlanır; bu süre şunlara bağlıdır:

* Kaynak ve hedef zincirler
* Ağ yoğunluğu
* Bridge sağlayıcısının verimliliği

#### Transferini Takip Etme

Gönderildikten sonra işlem durumunu sağlayıcıya özgü gezginler aracılığıyla görüntüleyebilirsin:

* [deBridge Gezgini](https://app.debridge.finance/orders)
* [LayerZero Scan](https://layerzeroscan.com/)
* [Stargate Gezgini](https://stargate.finance/)
* [CelerScan (cBridge)](https://celerscan.com/)

Bir işlem uzun süre takılı kalırsa ilgili gezgini kontrol et ya da [yardım](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/faq/help) için [sosyal kanallarımız](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) üzerinden yöneticilerimizle iletişime geç.

***

### 🧠 Bridge Etmeden Önce İpuçları

* **Her iki zincirde de gas token'ları bulundur** (örn. ETH + BNB)
* İlk kez Bridge ediyorsan **küçük miktarlarla başla**
* Yüksek zincir aktivitesi dönemlerinde Bridge etmekten kaçın (daha yüksek gas ücretlerine yol açabilir)
* Her iki zincirde de token uyumluluğunu doğrula
* Kaynak ve hedef ağları her zaman iki kez kontrol et

***

### Ek Bilgi: CAKE Omni-chain Fungible Token (OFT) Adresleri

1. **BNB Chain**
   * `cake`: `0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82` ([link](https://bscscan.com/address/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82))
   * `cakeOFTProxy`: `0xb274202daBA6AE180c665B4fbE59857b7c3a8091` ([link](https://bscscan.com/address/0xb274202daba6ae180c665b4fbe59857b7c3a8091#code))
2. **Ethereum**
   * `cakeOFT`: `0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898` ([link](https://etherscan.io/address/0x152649eA73beAb28c5b49B26eb48f7EAD6d4c898))
3. **Aptos**
   * `cakeOFT`: `0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6` ([link](https://explorer.aptoslabs.com/account/0x159df6b7689437016108a019fd5bef736bac692b6d4a1f10c941f6fbb9a74ca6/modules/run/oft/set_fee?network=mainnet))
4. **Arbitrum**
   * `cakeOFT`: `0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c` ([link](https://arbiscan.io/address/0x1b896893dfc86bb67Cf57767298b9073D2c1bA2c))
5. **zkSync**
   * `cakeOFT`: `0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD` ([link](https://explorer.zksync.io/address/0x3A287a06c66f9E95a56327185cA2BDF5f031cEcD#contract))
6. **Linea**
   * `cakeOFT`: `0x0D1E753a25eBda689453309112904807625bEFBe` ([link](https://explorer.linea.build/address/0x0D1E753a25eBda689453309112904807625bEFBe))
7. **Base**
   * `cakeOFT`: `0x3055913c90Fcc1A6CE9a358911721eEb942013A1` ([link](https://basescan.org/address/0x3055913c90Fcc1A6CE9a358911721eEb942013A1#code))
8. **opBNB**
   * `cakeOFT`: `0x2779106e4F4A8A28d77A24c18283651a2AE22D1C` ([link](https://opbnbscan.com/address/0x2779106e4F4A8A28d77A24c18283651a2AE22D1C?tab=Contract\&p=1))
