# 🌊 Likidite Havuzları

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/liquidity-header.png)

## Exchange V3 <a href="#id-03e94594-5a75-4687-b260-0dc69574b953" id="id-03e94594-5a75-4687-b260-0dc69574b953"></a>

Yeni Exchange V3'te likidite, fungible olmayan pozisyonlar biçiminde yönetilecektir. Likidite sağlarken ücretlerden pay almaya devam edeceksin.

Token'ını bir Likidite Havuzuna eklediğinde Liquidity Provider NFT token'ları alacak ve ücretlerden pay kazanacaksın.

### **Fungible olmayan likidite pozisyonları**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28238%29.png" alt=""><figcaption></figcaption></figure>

V3'te likidite sağlayıcılar artık likiditelерini hangi fiyat aralığına yerleştirmek istedikleri konusunda daha fazla kontrole sahiptir. Bu nedenle V3'te bir Likidite Havuzuna token eklediğinde kendine özgü ayarlara sahip yeni bir fungible olmayan likidite pozisyonu oluşturacaksın.

Bu nedenle V3'te likidite pozisyonları NFT'dir. Bu NFT'lerin devredilebilir olduğunu ve temsil ettikleri varlıkların ile kazanılan işlem ücretlerinin sahipliğini simgelediğini lütfen unutma.

V3'te işlem ücretleri artık pozisyonda otomatik olarak bileşik faize çevrilmeyecektir. Her pozisyon detay sayfasından manuel olarak talep edebilirsin.

Likiditenizi kaldırarak istediğin zaman fonlarını geri alabilirsin.

### **Aktif likidite ve fiyat aralıkları**

V3'te likidite sağlayıcılar, pozisyonlarını yalnızca fiyat belirli bir aralık içindeyken likidite sağlayacak şekilde yapılandırabilir. İşlem fiyatı aralık dışına çıkarsa pozisyon yalnızca çiftteki bir tür token'dan oluşur ve pasif hale gelir.

Pasif likidite pozisyonları işleme katılmaz ve herhangi bir işlem ücreti kazanamaz.

### **Yoğunlaştırılmış likidite**

V3'te likidite sağlayıcılar token yatırımlarını yalnızca belirli bir fiyat aralığında likidite sağlayacak şekilde yoğunlaştırabildiğinden, aynı miktarda temel varlıkla V3 çok daha büyük bir işlemi destekleyebilir.

Bu durum V2 ile karşılaştırıldığında çok daha yüksek bir göreli likidite seviyesiyle sonuçlanır. Likidite sağlayıcılar aynı sermaye miktarıyla daha fazla işlem ücreti kazanabilir.

İşte bir örnek:

> Baller ve Claire, her ikisi de 1.000 USD değerinde token varlığıyla CAKE/USDT havuzuna likidite sağladı. CAKE'in mevcut fiyatı 5 USDT'dir.
>
> PancakeSwap v2'ye benzer şekilde Baller, likidisitesini tüm fiyat aralığına yaydı. Bu nedenle tüm sermayesini, 500 USDT ve 100 CAKE'i yatırdı.
>
> Claire ise PancakeSwap v3'teki yeni yoğunlaştırılmış likidite özelliğinden yararlanarak CAKE başına 2 ile 12,5 USDT fiyat aralığında bir pozisyon oluşturdu. 185 USDT ve 37 CAKE yatırdı; toplam değeri 370 dolar. Artık kalan 630 doları başka yerlerde, örneğin yüksek CAKE getirisi elde etmek ve bir dizi PancakeSwap ekosistemi avantajından yararlanmak için Syrup Pool'da CAKE kilitlemek gibi alanlarda kullanabilir.
>
> CAKE, 2 ile 12,5 USDT fiyat aralığında kaldığı sürece hem Baller hem de Claire aynı miktarda işlem ücreti ödülü alacak; oysa Claire likidite havuzuna çok daha az sermaye yatırdı.

### **İşlem ücretleri**&#x20;

Likidite sağlamak, insanlar Swap işlemlerini tamamlamak için likidite havuzunu kullandığında işlem ücretleri biçiminde sana ödül kazandırır.

Birisi PancakeSwap'ta işlem yaptığında, her Exchange V3 likidite havuzundaki her atlama (Swap) için, likidite havuzu ücret kademesine bağlı olarak işlemci %0,01 ile %1 arasında değişen bir ücret öder. Ücret oranları ve ücret dağılımları aşağıda gösterilmektedir:

<details>

<summary>İşlem Ücretleri (EVM)</summary>

| Ücret Bileşeni / Ücret Kademesi | %0,01 | %0,05 | %0,25 | %1  |
| ------------------------------- | ----- | ----- | ----- | --- |
| Likidite Sağlayıcı              | %67   | %66   | %68   | %68 |
| CAKE Yakma                      | %15   | %15   | %23   | %23 |
| Hazine                          | %18   | %19   | %9    | %9  |

Örneğin, %0,25 ücret kademeli bir havuzda:

* Tüm aktif (aralık içindeki) likidite pozisyonları arasında toplam 10 CAKE ve 10 BNB token'ı bulunmaktadır.
* Biri 1 CAKE ile 1 BNB alışverişi yapar.
* Bir başkası 1 BNB ile 1 CAKE alışverişi yapar.
* Aktif likidite sağlayan aralık içindeki likidite sağlayıcılar işlemlerden toplam 0,0017 CAKE ve 0,0017 BNB kazandı.
* Mevcut fiyatı kapsamayan ve dolayısıyla pasif olan fiyat aralıklı pozisyonlar işleme katkıda bulunmaz ve herhangi bir ücret kazanamaz.

</details>

<details>

<summary><strong>İşlem ücretleri (Solana)</strong></summary>

**Mevcut V3 CLMM Havuzu Ücret Kademeleri:**\
%0,01, %0,02, %0,03, %0,04, %0,05, %0,1, %0,15, %0,16, %0,18, %0,2, %0,25, %0,4, %0,6, %0,8, %1, %2, %3, %4

**Not:** Ücret **dağılımı tüm ücret kademelerinde aynıdır**.

| Ücret Bileşeni                       | Toplam Swap Ücretinin %'si | Açıklama                                                             |
| ------------------------------------ | -------------------------- | -------------------------------------------------------------------- |
| **LP'ler (Likidite Sağlayıcılar)**   | %84                        | Aktif fiyat aralığında likidite sağlayan LP'ler tarafından kazanılır |
| **Yakma**                            | %8                         | CAKE arzını azaltmak için kalıcı olarak kaldırılır                   |
| **Hazine**                           | %8                         | PancakeSwap protokol hazinesine ayrılır                              |

**Örnek: %0,25 CAKE/SOL Havuzunda Ücret Dağılımı**

1. **Havuz Kurulumu:** Toplam aktif likidite: 10 CAKE ve 10 SOL (aralık içi pozisyonlar).
2. **Swaplar Gerçekleşiyor:**
   * A Kullanıcısı 1 CAKE → 1 SOL Swap ediyor.
   * B Kullanıcısı 1 SOL → 1 CAKE Swap ediyor.
3. **Toplanan Toplam Ücretler:**
   * İşlem başına %0,25 × 2 işlem = **0,005 CAKE + 0,005 SOL**.
4. **Ücret Dağılımı:**
   * **LP'lere %84:** 0,0042 CAKE + 0,0042 SOL
   * **Yakma için %8:** 0,0004 CAKE + 0,0004 SOL
   * **Hazineye %8:** 0,0004 CAKE + 0,0004 SOL
5. **LP Kazançları:**
   * Yalnızca **aralık içindeki LP'ler** ücret kazanır. Ücretler her LP'nin payına göre orantılı olarak dağıtılır.
   * **Aralık dışındaki LP'ler** **hiç ücret kazanamaz**.

</details>

### **CAKE Kazanma**

Likidite sağlayıcı olmayı daha da değerli kılmak için likidite pozisyonlarını [CAKE Farm'ları](https://pancakeswap.finance/liquidity/pools)nda kullanarak taze getiri elde edebilirsin; bu süreçte işlem ücreti ödüllerini de kazanmaya devam edersin.

***

## Exchange V2

### LP Token'ları

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28142%29.png" alt=""><figcaption></figcaption></figure>

Örnek olarak, bir Likidite Havuzuna **CAKE** ve **BNB** yatırdıysan **CAKE-BNB LP** token'ları alırsın.

Aldığın LP token sayısı, CAKE-BNB Likidite Havuzu'ndaki payını temsil eder.

Ayrıca likiditenizi kaldırarak istediğin zaman fonlarını geri alabilirsin.

### **İşlem ücreti kazanma**

Birisi PancakeSwap'ta işlem yaptığında, her Exchange V2 likidite havuzundaki her atlama (Swap) için işlemci sabit %0,25 ücret öder; **bunun %0,17'si** işlem ücretleri biçiminde Likidite Havuzuna geri eklenir.

### **CAKE Kazanma**

Eski Exchange V2, yeni Exchange V3 ile paralel şekilde çalışmaya devam edecektir. Bu nedenle bazı işlem çiftleri PancakeSwap Exchange V2'de kalmaya devam edecek ve karşılık gelen V2 Farm'larına sahip olacaktır. Exchange sürümlerini belirlemek için etiketleri kontrol et.



## Kalıcı Olmayan Kayıp (IL)

Likidite sağlamak risksiz değildir; kalıcı olmayan kayba maruz kalabilirsin.

["Basitçe söylemek gerekirse, kalıcı olmayan kayıp; token'ları AMM'de tutmak ile cüzdanda tutmak arasındaki farktır." - Nate Hindman](https://blog.bancor.network/beginners-guide-to-getting-rekt-by-impermanent-loss-7c9510cb2f22)
