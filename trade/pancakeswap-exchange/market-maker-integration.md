---
hidden: true
---

# Piyasa Yapıcı Entegrasyonu

<figure><img src="https://lh3.googleusercontent.com/pHBaGjeEHE3pCfmOWyBxvRThu0HiDK9K3jAhAN9dLka4c3zBDij-n0e9yY4LA6YjqYj2m4tBPjfoGoZunt2VCwTcDqtlWU5Km61x2IQ_T66olebgLn-yy1VodKww4Fn2YQuR_fwcJSAbR0MgsHkD0RY" alt=""><figcaption></figcaption></figure>

### Ethereum Üzerinde Piyasa Yapıcı Entegrasyonu

PancakeSwap, yatırımcıların işlemlerini daha düşük maliyetle gerçekleştirmesine yardımcı olmak amacıyla Ethereum ve Binance Smart Chain üzerindeki piyasa yapıcılarla entegre edilmiştir.

AMM'ye ek olarak, PancakeSwap üzerindeki işlemler artık AMM'nin mevcut fiyatlarından daha iyi bir işlem gerçekleştirme imkânı sunmaları durumunda belirlenmiş beyaz listedeki piyasa yapıcılara yönlendirilebilmektedir. Bu yönlendirme, işlemlerin yalnızca piyasa yapıcıların aktif olarak daha iyi fiyat teklif ettiği durumlarda onlara yönlendirilmesini sağlamak için [Smart Router](smart-router-v2/) tarafından otomatik olarak gerçekleştirilir. AMM'nin daha rekabetçi olduğu durumlarda, yatırımcılar gerçekleştirme için AMM'lere yönlendirilir.

PancakeSwap üzerinde piyasa yapıcıların faaliyet gösterdiği 2 senaryo vardır.

**Senaryo 1: Mevcut AMM likidite havuzları**

PancakeSwap'ın belirli bir token için (ör. WETH/USDC) AMM'de zaten likiditesi varsa, PancakeSwap aynı işlem için piyasa yapıcılardan fiyat teklifi ister. PancakeSwap'ın Smart Router'ı daha sonra herhangi bir zamanda hangi likidite kaynağının en iyi fiyatı sunduğuna bağlı olarak işlem talebini AMM'ye veya piyasa yapıcılara yönlendirir.

**Senaryo 2: Mevcut AMM likidite havuzu yok**

Böyle bir senaryoda Smart Router, işlemi otomatik olarak piyasa yapıcılara yönlendirir. Ancak bu durum, projelerin daha sonra kendi AMM likidite havuzlarını kurmalarını ve merkeziyetsiz DEX likiditesini korumak için bizimle çalışmalarını engellemez.

### Ücretler

<figure><img src="https://lh6.googleusercontent.com/FKgYOPK6ykAbonNz4naPupdPg4W5XocmUJOEYeH7MsmY-0TrkSepYB2qir4PGlfgY6CKTS0nOq5XIXzm3dO9wGr-9pvXz1NXLSGMg3Ff9IlqIokcHiNDsB9eaoy3l395TL-O71480hetL-iRq1ILhUw" alt=""><figcaption></figcaption></figure>

PancakeSwap, piyasa yapıcılar tarafından gerçekleştirilen işlemler için yatırımcılardan herhangi bir ücret almaz. Ancak PancakeSwap, beyaz listedeki piyasa yapıcılardan onlar tarafından gerçekleştirilen hacimler için **%0,05** **işlem ücreti** alır. Stablecoin çiftleri arasındaki işlemler için indirimli **%0,01** **işlem ücreti** alınır. Lütfen aşağıdaki ücret dağılımına bakınız:<br>

<table><thead><tr><th width="178">İşlemler</th><th width="138">İşlem Ücretleri</th><th width="182">MM'den PCS ücreti</th><th width="147">Cake Yakımı</th><th align="center">Pancakeswap Hazinesi</th></tr></thead><tbody><tr><td>Diğer ağlardan köprülenmiş coinler</td><td>Yok</td><td>%0,25</td><td>%0,083</td><td align="center">%0,167</td></tr><tr><td>Ethereum'da stablecoin olmayan (ör. ETH/USDC)</td><td>Yok</td><td>%0,05</td><td>%0,017</td><td align="center">%0,033</td></tr><tr><td>BSC'de stablecoin olmayan (ör. BNB/USDT)</td><td>Yok</td><td>%0,05</td><td>%0,017 </td><td align="center">%0,033</td></tr><tr><td>Ethereum'da Stablecoin'den Stablecoin'e</td><td>Yok</td><td>%0,01</td><td>%0,003</td><td align="center">%0,007</td></tr></tbody></table>

#### Şu anda desteklenen varlıklar

Şu anda desteklenen ve piyasa yapıcıya göre artıp azalabilecek varlıklar şunlardır:

**Ethereum Üzerinde**

* **Ana varlıklar:** WETH, WBTC
* **Stablecoin'ler:** USDT, USDC, DAI, BUSD
* **Diğer popüler ERC-20 varlıkları:** MATIC, DYDX, CRV, LINK, APE, CVX, STG, LDO, SNX, RNDR, FET

**Binance Smart Chain Üzerinde:**

* **Ana varlıklar:** BNB, ETH, BTCB
* BNB olmayan tokenlar: ARB, OP

AMM'lerin aksine, piyasa yapıcıların herhangi bir miktarda işlem yapamayacağını ve gerçekleştirecekleri miktarların kendi likiditelerine bağlı olduğunu unutma. Çok büyük emirlerin bazen tamamen karşılanamaması olağandışı değildir. Kullanıcıların her işlemin kendi ihtiyaçlarına göre fiyat ve miktarı yansıtıp yansıtmadığından emin olmak için teklifleri dikkatlice incelemelerini tavsiye ederiz.

**Piyasa yapıcı kesinti süreleri**

Piyasa yapıcıların 7/24 teklif vermesi beklenmez. Piyasa yapıcının geçici olarak teklif sunamayabileceği bazı durumlar (ör. önemli ekonomik gelişmeler, sistem güncellemeleri) vardır. Bu dönemlerde söz konusu token'ların basitçe işlem göremeyeceğini ve piyasa yapıcının tekrar çevrimiçi olmasını beklemeni tavsiye ederiz.

#### SSS

**S.** Piyasa yapıcılar Aptos'a entegre edilecek mi?

**C:** Olası bir seçenek. Şimdilik, daha iyi bir kullanıcı deneyimi için likiditesi artırmak amacıyla yalnızca Ethereum ve Binance Smart Chain üzerinde piyasa yapıcı entegrasyonunu başlatıyoruz. Diğer zincirleri izlemeye devam edeceğiz.

**S.** Kullanıcılardan ücret almıyorsa PancakeSwap nasıl gelir elde edecek?

**C:** PancakeSwap kullanıcılardan herhangi bir ücret almayacak, ancak piyasa yapıcılardan küçük bir komisyon alarak bunu CAKE geri alımı ve yakımı için kullanacaktır.

**S.** Likidite sağlayıcıları LP ücretleri kazanmaya devam edecek mi?

**C:** Evet, likidite sağlayıcılar %0,17 işlem ücreti ödülü (LP ücretleri) ve CAKE farm'larından getiri kazanmaya devam edecektir.

**S.** Piyasa yapıcılar AMM'ye likidite ekleyecek mi? Bu durum APR'nin düşmesine neden olur mu?

**C:** Piyasa yapıcılar kendi ayrı likiditelerini korur; dolayısıyla AMM'deki işlemlerden herhangi bir APR kazanmayacaklardır. Yalnızca LP'ler, AMM havuzlarına likidite sağlamaktan ücret ve APR kazanacaktır.

**S.** Ethereum PancakeSwap'ta likidite sağlıyorum. Herhangi bir şey yapmam gerekiyor mu?

**C:** Hayır, herhangi bir şey yapman gerekmiyor. AMM aracılığıyla gerçekleştirilen işlemler için LP ücretleri kazanmaya devam edecek ve CAKE'te getiri elde etmeyi sürdüreceksin.

**S.** Piyasa yapıcı nasıl olunur?

**C:** Piyasa yapıcılarla bireysel bazda çalışıyoruz. Bizimle çalışmakla ilgileniyorsan doğrudan bize veya yöneticilerimize ulaşabilirsin.
