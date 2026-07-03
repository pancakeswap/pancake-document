# FAQ

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28101%29.png" alt=""><figcaption><p>\</p></figcaption></figure>

### Diğer blok zincirlerde PancakeSwap'ta ne yapmalıyım?

Her zamanki gibi likidite sağla, ticaret yap ve farming yap. Zaten çok zincirli bir kullanıcıysan, dağıtım yaptığımız diğer blok zincirlerde (örneğin Ethereum) PancakeSwap'ta likidite sağlamayı unutma. Bu varlıkları Bridge üzerinden aktarmana gerek kalmadan BNB Smart Chain'de sana CAKE ödülleri kazandırır; böylece daha da fazla CAKE kazanabilirsin!

### **Daha fazla çift gelecek mi?**

Evet, ancak kullanıcı fonlarının ve CAKE enflasyonunun güvenliğini ön planda tutmak için adım adım ilerliyoruz. Diğer blok zincirlerde PancakeSwap'a nelerin eklenmesi gerektiğini ve PancakeSwap'ın hangi diğer blok zincirlere dağıtılması gerektiğini topluluk sohbetlerinde bizimle paylaş.

### **LP token'larını stake etmenin gas maliyeti neden yüksek?**

İlk kurulum için küçük miktarda yerel token (örneğin Ethereum'da ETH) gereklidir. Bu nedenle ilk işlem biraz daha maliyetli olabilir.

Bunun yanı sıra crosschain farming'de başka ücretler de (çoğunlukla gas maliyetleri) söz konusudur. Daha fazla bilgi için [şu](faq.md#are-there-any-fees-when-i-do-crosschain-farming) bölüme göz at.

### **Stake ve unstake işlemleri neden 30 dakika sürüyor?**

Tüm cross-chain işlemlerin tamamlanması yaklaşık 30 dakika sürer. Bunun nedenleri şunlardır:

* İşlemlerin hem farming blok zincirinde (örneğin Ethereum) hem de BNB Chain'de yürütülmesi gerekir.
* Cross-chain mesajlarının iletilmesi zaman alır.
* Güvenliği sağlamak ve tüm verilerin farklı blok zincirler arasında senkronize ve tutarlı olmasını garantilemek için.

### **Toplanan CAKE ödüllerim nerede?**

Toplanan CAKE'in BNB Smart Chain'de dağıtılacak. CAKE bakiyeni kontrol etmek için cüzdanındaki blok zinciri ağını değiştir.

### **Cüzdanım farklı blok zincirler arasında geçiş yapmayı desteklemediği için toplayamıyorum!**

Çoklu zinciri ve zincir değiştirmeyi destekleyen farklı bir cüzdan uygulaması kullanmayı dene.

LP token'larının stake edilmesi ve unstake edilmesinin aynı zamanda BNB Smart Chain'deki cüzdanına kazanılan tüm CAKE'i de toplayacağını unutma. Bu nedenle farklı bir cüzdan uygulaması kullanmak istemiyorsan, kazandığın CAKE'i toplamak için biraz daha stake et veya küçük miktarda LP token'ı unstake et.

### Crosschain farming yaparken herhangi bir ücret var mı?

BNB Chain'de yerel farming'in aksine, diğer blok zincirlerde farming yapmak cross-chain etkinlikleri gerektirir. İşte söz konusu ücretler:

**1 - Proxy sözleşme oluşturma gas ücreti**

Crosschain farming için BNB Chain'de bir proxy sözleşmesi oluşturulması gerekir. Proxy sözleşmesi oluşturmanın gas maliyeti işleme dahildir.

Bu ücret yalnızca ilk "stake" işleminde bir kez alınır.

**2 - BNB Chain üzerindeki çağrılar için gas ücreti**

Kullanıcılar LP token'larını yatırdığında veya çektiğinde bir yürütücü, BNB Chain'de kullanıcılar adına işlem gerçekleştirir. Bu çağrıların gas maliyeti işleme dahildir.

Bu ücret her yatırma veya çekme işleminde alınır.

**3 - Diğer blok zincirler üzerindeki çağrılar için gas ücreti**

Kullanıcılar LP token'larını çektiğinde bir yürütücü, diğer blok zincirlerde (örneğin Ethereum) LP token'larını serbest bırakmak için son işlemleri gerçekleştirir. Bu çağrıların gas maliyeti işleme dahildir.

Bu ücret yalnızca para çekme işlemlerinde alınır.

**4 - Cross-chain mesajlaşma ücreti**

Cross-chain mesajlarımızı yönlendirmek için Celer tarafından desteklenen bir mesaj veri yolundan faydalanıyoruz. Bu nedenle mesajın bayt uzunluğuna bağlı olarak bir mesaj ücreti dahil edilir.

Bu ücret her stake işleminde alınır. Unstake işlemlerinde, güvenlik için BNB Chain ile diğer blok zincirler arasında iki yönlü iletişim gerektiğinden bu ücret iki kez alınır.

```
messagingFee = feeBase + message.length * feePerByte;
```

Formüldeki değişkenleri mesaj veri yolu sözleşmesinde bulabilirsin:

* Ethereum: `0x4066d196a423b2b3b8b054f4f40efb47a74e200c`
* BNB Chain: `0x95714818fdd7a5454f73da9c777b3ee6ebaeea6b`

**5 - Başlangıç fonu**

Bu teknik olarak bir "ücret" değildir.&#x20;

PancakeSwap crosschain farming'e başlayan her yeni kullanıcı için ilk "stake" işleminde BNB Chain cüzdanına 0,005 BNB yatırıyoruz. Farming zincirindeki (örneğin Ethereum'daki ETH) karşılık gelen yerel token miktarı, fiyat oracle'ı tarafından sağlanan piyasa kuru kullanılarak yatırma işleminden tahsil edilir.

Bu, kullanıcıların BNB Chain yolculuğuna kolayca başlamasını sağlamak içindir. Tüm toplanan CAKE'e sahip olmana rağmen gas için BNB edinmeden canlı PancakeSwap ekosistemine dahil olamamanın ne kadar can sıkıcı olduğunu biliyoruz.

Bu ücret yalnızca ilk "stake" işleminde bir kez alınır.

### Emisyonlar nereden geliyor?&#x20;

_10 Ekim 2022'de güncellendi_

Şu an için Chefs, CAKE havuzundan tüm crosschain farm'lara blok başına 0,0189 CAKE yönlendirdi.&#x20;

İşte emisyon dağılımı:

<table><thead><tr><th width="249"></th><th>Çarpan</th><th>Blok başına CAKE</th></tr></thead><tbody><tr><td><strong>CAKE Havuzu</strong></td><td>-</td><td><strong>8,9811</strong></td></tr><tr><td><strong>Tüm Crosschain Farm'lar</strong></td><td>-</td><td><strong>0,0189</strong></td></tr><tr><td>Ethereum ETH/USDC</td><td>0,5x</td><td>0,0105</td></tr><tr><td>Ethereum ETH/USDT</td><td>0,2x</td><td>0,0042</td></tr><tr><td>Ethereum WBTC/ETH</td><td>0,2x</td><td>0,0042</td></tr></tbody></table>

### Yatırma, toplama ve çekme işlemleri sırasında ne olur?

PancakeSwap crosschain farming, aynı PancakeSwap MasterChef ile BNB Chain'de farming yapmak için bir "vekil" LP token kullanmak gibidir. CAKE ödülleri, aynı MasterChef sözleşmesi tarafından kontrol edilen ve güvence altına alınan BNB Chain'de hesaplanır ve dağıtılır.

#### Yatırma İşleminde:

1. Kullanıcılar farming blok zincirlerinde (örneğin Ethereum) LP token yatırma talebinde bulunur.
2. LP token'lar farming vault sözleşmelerine aktarılır.
3. "Yatırma" mesajını BNB Chain'e iletmek için Celer mesaj veri yolu kullanılır.
4. BNB Chain'deki bir yürütücü, aynı miktarda farming token'ı "vekil" olarak basar ve ardından bunları farm'lara yatırır.

#### Toplama İşleminde:

CAKE ödülleri BNB Chain'de hesaplanıp dağıtıldığından kullanıcılar, cross-chain işlemlerine gerek kalmadan tek bir BNB Chain işlemiyle CAKE ödüllerini talep edebilir.

#### Çekme İşleminde:

1. Kullanıcılar farming blok zincirlerinde (örneğin Ethereum) LP token çekme talebinde bulunur.
2. "Çekme" mesajını BNB Chain'e iletmek için Celer mesaj veri yolu kullanılır.
3. BNB Chain'deki bir yürütücü, farming token'larını farm'lardan çeker, bu token'ları yakar, kullanıcıya kazanılan CAKE'i aktarır ve doğrulama mesajını orijinal farming blok zincirine iletmek için Celer mesaj veri yolunu kullanır.
4. Farming blok zincirindeki bir yürütücü her şeyi doğrular ve ardından LP token'larını vault sözleşmelerinden serbest bırakır.
