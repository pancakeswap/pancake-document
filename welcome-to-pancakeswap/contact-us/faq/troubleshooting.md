---
description: Yaygın hata mesajları. Gördüğün hataya atlamak için kenar çubuğunu ➡️ kullan.
---

# Hata Giderme

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/troubleshooting-header.png)

Bazen net bir çözümü olmayan bir sorunla karşılaşabilirsin. Bu sorun giderme ipuçları, karşılaştığın sorunları çözmenize yardımcı olabilir.

## **Exchange'deki Sorunlar**

### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: PancakeRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: pancakerouter: insufficient\_output\_amount.

Token Swap yapmaya çalışıyorsun ancak Kayma toleransın çok düşük ya da likidite yetersiz.

{% tabs %}
{% tab title="Çözüm" %}
1. Sayfanı yenile ve daha sonra tekrar dene.
2. Aynı anda daha küçük bir miktar için Ticaret yapmayı dene.
3. Kayma toleransını artır:
   1. Likidite sayfasındaki ayarlar simgesine dokun.
   2. Kayma toleransını biraz artır ve tekrar dene. ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
4. Son olarak, daha az ondalık basamaklı bir miktar girmeyi dene.
{% endtab %}

{% tab title="Neden" %}
**Bu durum genellikle düşük likiditeli tokenlarla Ticaret yaparken ortaya çıkar.**

Yani takas etmeye çalıştığın tokenlardan birinin Likidite Havuzu'nda yeterli miktarı bulunmuyor: bu muhtemelen çok az kişinin işlem yaptığı düşük piyasa değerli bir token.

Ancak satılamayan bir dolandırıcılık token'ını takas etmeye çalışıyor olma ihtimalin de var. Bu durumda PancakeSwap bir token'ı engelleme veya fonları iade etme imkânına sahip değildir.
{% endtab %}
{% endtabs %}

### **INSUFFICIENT\_A\_AMOUNT veya INSUFFICIENT\_B\_AMOUNT**

> Fail with error 'PancakeRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'PancakeRouter: INSUFFICIENT\_B\_AMOUNT'

Bir likidite havuzuna (LP) likidite eklemeye/çıkarmaya çalışıyorsun ancak çiftteki iki token'dan birinin miktarı yeterli değil.

{% tabs %}
{% tab title="Çözüm" %}
**Sayfanı yenile ve tekrar dene ya da daha sonra tekrar dene.**

Hâlâ çalışmıyor mu?

1. Likidite sayfasındaki ayarlar simgesine dokun.
2. Kayma toleransını biraz artır ve tekrar dene.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%284%29.png)
{% endtab %}

{% tab title="Neden" %}
Hata, yetersiz A token veya B token miktarıyla (çiftteki tokenlardan biri) bir likidite havuzuna (LP) likidite ekleyip çıkarmaya çalışmaktan kaynaklanır.

Fiyatlar çok hızlı güncellenirken Kayma toleransın çok düşük olabilir.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Uzmanlar için çözüm" %}
Tamam, bu sorunu gerçekten çözmek istiyorsun. Ne yaptığını bilmiyorsan bunu yapmanı gerçekten önermiyoruz.

Şu anda bu sorunu PancakeSwap sitesinden çözmenin kolay bir yolu yok: sözleşmeyle doğrudan etkileşime girmen gerekecek. amountAMin'i küçük bir değere ayarlayarak Router sözleşmesi üzerinden doğrudan likidite ekleyebilir, ardından tüm liküditeyi çekebilirsin.

**LP sözleşmesini onayla**

Onaylamaya çalıştığın LP token'ının sözleşmesine git.\
Örneğin, ETH/WBNB çifti: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. **Write Contract** seçeneğini, ardından **Connect to Web3** seçeneğini seçip Cüzdan'ını bağla. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. **"1. approve" bölümüne** girerek aşağıdakileri girerek LP token'ını router için onayla:
   1. spender (address): etkileşime girmeye çalıştığın LP token'ının sözleşme adresi
   2. value (uint256): -1

**"balanceOf" sorgula**

1. **Read Contract** sekmesine geç.
2. **5. balanceOf** bölümüne Cüzdan adresini gir ve **Query**'ye tıkla.
3. Dışa aktarılan sayıyı not et. Bu, bir sonraki adımda ihtiyaç duyacağın uint256 formatında LP içindeki bakiyeni gösterir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2874%29.png)

**Likidite Ekle veya Çıkar**

Router sözleşmesine git: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Yukarıdaki gibi **Write Contract** ve **Connect to Web3** seçeneklerini seç.
2. **addLiquidity** veya **removeLiquidity** işlevini bul (hangisini yapmak istiyorsan).
3. LP'deki her iki token'ın adreslerini gir.
4. **liquidity (uint256)** alanına yukarıdaki "balanceOf"tan elde ettiğin uint256 sayısını gir.
5. **amountAMin** veya **amountBMin** için düşük bir değer gir: her ikisi için de 1 dene.
6. **to (address)** alanına Cüzdan adresini ekle.
7. Deadline, işlemin gerçekleştirildiği zamandan büyük bir epoch zamanı olmalıdır.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28136%29.png)

{% hint style="warning" %}
Bu çok yüksek Kayma'ya neden olabilir ve kullanıcının frontrun durumunda bir miktar fon kaybetmesine yol açabilir
{% endhint %}
{% endtab %}
{% endtabs %}

### PancakeRouter: EXPIRED

> The transaction cannot succeed due to error: PancakeRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Tekrar dene; ancak işlemi oluşturur oluşturmaz onayla (imzala ve yayınla).

Bu durum, işleme başladığında ama son tarihi geçene kadar imzalayıp yayınlamadığında oluşur. Yani "Onayla" butonuna yeterince hızlı basmadın.

### Pancake: K

> The transaction cannot succeed due to error: Pancake: K. This is probably an issue with one of the tokens you are swapping.

"Hedef" alanındaki miktarı değiştirmeyi dene; böylece "(tahmini)" sembolü "Kaynak" alanına geçer. Ardından hemen Swap işlemini başlat.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Pancake-K-Solution%20%282%29.png)

Bu durum genellikle kendi ücreti olan bir token'ı takas etmeye çalışırken ortaya çıkar.

### Pancake: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Pancake: TRANSFER\_FAILED.

Cüzdan'ında işlem yapmak istediğinden en az %30 daha fazla token bulundurmaya dikkat et ya da daha düşük bir miktar için işlem yapmayı dene. Maksimum satış yapmak istiyorsan %100 yerine %70 veya %69'u dene.\
tDoge veya tBTC gibi Restoratif Rebase token'larının tasarımından kaynaklanır.\
[Restoratif rebase token'larının nasıl çalıştığını anla](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Bu sorunun bir diğer olası nedeni, kötü niyetli token ihraç edenin kendi token'ı için işlemleri askıya almış olmasıdır. Ya da satış işlemini yalnızca belirli cüzdan adresleri için mümkün kılmış olabilirler. Olası dolandırıcılıklardan korunmak için lütfen her zaman kendi araştırmanı yap. Swap yapmaya çalıştığın ancak bu hata koduyla başarısız olan token bir airdrop'tan geliyorsa, bu büyük olasılıkla bir dolandırıcılıktır. Herhangi bir token onayı gerçekleştirme veya herhangi bir bağlantıyı takip etme; bunu yapmaya çalışırsan fonların risk altında olabilir.

### İşlem gerçekleştirilemedi

Daha küçük bir miktar için işlem yapmayı dene ya da ayarlar simgesi aracılığıyla Kayma toleransını artır ve tekrar dene. Bunun nedeni düşük likidite.

### **Fiyat Etkisi Çok Yüksek**

Daha küçük bir miktar için işlem yapmayı dene ya da ayarlar simgesi aracılığıyla Kayma toleransını artır ve tekrar dene. Bunun nedeni düşük likidite.

### estimateGas başarısız oldu

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Çözüm" %}
**Bu hatayı bir BNB çiftinden likidite çıkarırken aldıysan:**

Lütfen "WBNB Al" seçeneğini seç ve tekrar dene.

**Bu hatayı Swap yapmaya çalışırken aldıysan:**

Lütfen Swap yapmaya çalıştığın token'ın proje ekibiyle iletişime geç. \*\*\*\* Bu sorunun proje ekibi tarafından çözülmesi gerekiyor.
{% endtab %}

{% tab title="Neden" %}
**Bu sorun (Swap yaparken) V1 PancakeSwap router'ını sözleşmelerine sabit kodlamış token'lardan kaynaklanır.**

Bu uygulama en iyi ihtimalle tavsiye edilmez; bu projelerin bunu yapmasının nedeni, her satın alımın token'ın belirli bir yüzdesini LP'lere gönderdiği tokenomics yapılarından kaynaklanıyor gibi görünmektedir.

Etkilenen projelerin V2 router'ıyla büyük ihtimalle çalışmayacağı anlaşılıyor: büyük olasılıkla yeni router adresimize işaret eden yeni token sürümleri oluşturmaları ve mevcut token sahiplerini yeni token'larına taşımaları gerekecek.

Bu tür token'lar oluşturan tüm projelerin, kullanıcılarının bu token'ları V2 LP'ye eklemesini önlemek için çaba göstermesini öneririz.

Güncel router adresi [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

Token takas etmeye çalışırken işlem başarısız oluyor ve bu hata mesajı görüntüleniyor. Bu hata, Trust Wallet kullanan mobil cihazlarda rapor edilmiştir.

{% tabs %}
{% tab title="Çözüm" %}
1. Artırılmış Kayma toleransıyla işlemi yeniden dene.
2. 1. adım sorunu çözmezse, işlemin için SafePal gibi başka bir Cüzdan kullanmayı düşün.
{% endtab %}

{% tab title="Neden" %}
**Bu durum genellikle Trust Wallet'ta yetersiz Kayma toleransıyla token işlemi yaparken ortaya çıkar.**

Sorunun tam ayrıntıları hâlâ araştırılmaktadır.
{% endtab %}
{% endtabs %}

### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

Token takas etmeye çalışırken işlem başarısız oluyor ve bu hata mesajı görüntüleniyor. Bu hata tüm platformlarda rapor edilmiştir.

{% tabs %}
{% tab title="Çözüm" %}
1. Yeterli miktarda kullanılabilir fona sahip olduğundan emin ol.
2. Sözleşmeye, işlem yapmaya çalıştığın fon miktarını harcaması için izin verdiğinden emin ol.
{% endtab %}

{% tab title="Neden" %}
Bu hata, yetersiz izinle token işlemi yaparken veya Cüzdan'ında yetersiz fon olduğunda oluşur.\
tDoge veya tBTC gibi tau varlıkları gibi Restoratif Rebase'li token'larla işlem yapıyorsan, önce bu [Rebase token'ları kılavuzuyla](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c) nasıl çalıştıklarını anladığından emin ol.
{% endtab %}
{% endtabs %}

## **Farm'larla İlgili Sorunlar**

### Fail with error 'ds-math-sub-underflow'

MasterChef sözleşmesine olan LP token izin limitini aştın.

**Bu sorunu çözmek için unrekt veya BscScan gibi token onay yöneticisini kullan**

## **Syrup Pool'larla İlgili Sorunlar**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

CAKE-CAKE havuzundan unstake yapmak için Cüzdan'ında yeterli SYRUP yok.

**Unstake yapmaya çalıştığın CAKE miktarı kadar en az o kadar SYRUP edin.**

1. Exchange'den SYRUP satın al. 100 CAKE unstake etmek istiyorsan en az 100 SYRUP'a ihtiyacın var.
2. Unstake işlemini tekrar dene.

Hâlâ başarısız oluyorsa, stake edilmiş token'larını unstake etmek için doğrudan sözleşme üzerinden "emergencyWithdraw" işlemi gerçekleştirebilirsin.

1. Şu adrese git: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. **"Connect to Web3"** seçeneğine tıkla ve Cüzdan'ını bağla. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. **"4. emergencyWithdraw"** bölümüne "0" gir ve "Write"a tıkla.

Bu işlem, stake edilmiş token'larını unstake edecek ve toplanmamış CAKE ödüllerini kaybettirecektir.

{% hint style="warning" %}
**Bu işlem henüz hasat etmediğin ödülleri kaybettirecektir.**
{% endhint %}

Bu durumun tekrar yaşanmaması için **SYRUP'ını satma.** "Stake CAKE Earn CAKE" havuzundan unstake yapmak için ona hâlâ ihtiyacın var.

Bu hata, SYRUP token'larını sattığın veya transfer ettiğin için oluştu. SYRUP, CAKE-CAKE Syrup Pool'unda stake yaptığında 1:1 oranında basılır. leaveStaking çağrısı yapılırken (CAKE'ini havuzdan unstake etmek) SYRUP'un 1:1 oranında yakılması gerekir; yeterince yoksa havuzdan unstake yapamazsın.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Gaz Yetersizliği Hatası

> Warning! Error encountered during contract execution \[out of gas]

Bir işlem gerçekleştirmeye çalışırken düşük bir gaz limiti belirledin.

{% tabs %}
{% tab title="Çözüm" %}
İşlemi imzalamadan önce Cüzdan'ında **gas limitini** (gaz fiyatını değil!) manuel olarak artırmayı dene.

200000 limiti genellikle yeterlidir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2821%29.png)

Yukarıdaki örnek Metamask'tan alınmıştır; gaz limitini nasıl ayarlayacağından emin değilsen Cüzdan'ının belgelerine bak.
{% endtab %}

{% tab title="Neden" %}
Temel olarak, Cüzdan'ın (Metamask, Trust Wallet, vb.) yapmaya çalıştığı işlemi tamamlayamıyor.

Cüzdan'ın gaz limitinin çok düşük olduğunu tahmin ediyor; bu nedenle işlev çağrısı tamamlanmadan önce gaz tükeniyor.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Çözüm" %}
1. Etkileşime girmeye çalıştığın akıllı sözleşmenin onayını kaldırmak için Unrekt.net kullan
2. Harcama limitine sınır koymadan sözleşmeyi tekrar onayla
3. Sözleşmeyle etkileşime girmeyi tekrar dene.
{% endtab %}

{% tab title="Neden" %}
Bu durum, sözleşmeyi ilk onayladığında harcama izninize bir limit koyduğunda ve ardından limitten daha fazlasını takas etmeye çalıştığında oluşur.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

Muhtemelen içinde az ödül kalan eski bir Syrup Pool'dan unstake yapmaya çalışıyorsun. Aşağıdaki çözüme bak.

Değilse, Cüzdan'ında olmayan token'ları göndermeye çalışıyor olabilirsin (örneğin, bekleyen bir işleme zaten atanmış bir token'ı göndermeye çalışmak). Bu durumda kullanmaya çalıştığın token'ların sende olduğundan emin ol.

{% tabs %}
{% tab title="Çözüm" %}
İlk olarak, [ekibi bilgilendirerek](../social-accounts.md) unstake yapmaya çalıştığın havuzu söyle; böylece ödülleri tazelesinler. Acilen unstake yapmak istiyorsan ve bekleyen ödüllerini kaybetmeni sakıncası yoksa emergencyWithdraw işlemini dene:

Stake edilmiş token'larını unstake etmek için doğrudan sözleşme üzerinden "emergencyWithdraw" işlemi gerçekleştirebilirsin.

1. Unstake yapmaya çalıştığın Syrup Pool'un sözleşme adresini bul. Bunu Cüzdan'ının işlem günlüğünde bulabilirsin.
2. [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) adresine git ve arama çubuğuna sözleşme adresini gir.
3. **Write Contract** seçeneğini seç.
4. **"Connect to Web3"** seçeneğine tıkla ve Cüzdan'ını bağla.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. **"3. emergencyWithdraw"** bölümünde "Write"a tıkla.

Bu işlem, stake edilmiş token'larını unstake edecek ve toplanmamış ödülleri kaybettirecektir.

{% hint style="warning" %}
**Bu işlem henüz hasat etmediğin ödülleri kaybettirecektir.**
{% endhint %}
{% endtab %}

{% tab title="Neden" %}
Bu hata genellikle eski bir Syrup Pool'dan unstake yapmaya çalışırken ortaya çıkar; ancak çekilirken hasat etmen için havuzda yeterli ödül kalmamıştır. Bu durum işlemin başarısız olmasına neden olur.
{% endtab %}
{% endtabs %}

## **Tahmin ile İlgili Sorunlar**

[Bozuk bağlantıyı](</broken/pages/8zN9xzaYD1DvxZvzLzug> "mention") kontrol et

## **Diğer Sorunlar**

### Sağlayıcı Hatası

> Provider Error\
> No provider was found

Bu durum, MetaMask veya Binance Chain Wallet gibi bir tarayıcı uzantısıyla bağlanmaya çalışırken uzantıyı yüklemediysen ortaya çıkar.

{% tabs %}
{% tab title="Çözüm" %}
Bağlanmak için resmi tarayıcı uzantısını yükle ya da [PancakeSwap'e Cüzdan nasıl bağlanır](https://docs.pancakeswap.finance/get-started/connection-guide) kılavuzumuzu oku.
{% endtab %}
{% endtabs %}

### Desteklenmeyen Zincir Kimliği

Zincirini BNB Smart Chain'e geç. Yardıma ihtiyacın varsa Cüzdan'ının belgelerine bak.

### Already processing eth\_requestAccounts. Please wait.

Cüzdan uygulamanızda oturum açtığından ve BNB Smart Chain'e bağlı olduğundan emin ol.

### SAFEMOON ve benzeri token'ları satın alma sorunları

SAFEMOON işlemi yapmak için ayarlar simgesine tıklayıp **Kayma toleransını %12 veya daha fazlasına ayarlaman** gerekir.\
Bunun nedeni **SafeMoon'un her işlemde %10 ücret alması**:

* %5 ücret = mevcut tüm sahipler arasında yeniden dağıtılır
* %5 ücret = likidite eklemek için kullanılır

Bu aynı zamanda satın alırken beklediğinden daha az token alabilmesinin de nedeni.\
[Safe Moon Nasıl Satın Alınır](https://community.trustwallet.com/t/how-to-buy-safemoon/155742) hakkında daha fazla bilgi edin.

### Dahili JSON-RPC hataları

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Metamask aracılığıyla bazı token'larda likidite çıkarmaya çalışırken ortaya çıkar. Sorunun kök nedeni hâlâ bilinmiyor. Alternatif bir Cüzdan kullanmayı dene.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

İşlem ücretlerini karşılamak için yeterli BNB'n yok. Cüzdan'ında daha fazla BEP-20 ağ BNB'sine ihtiyacın var.

### Hata: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Cüzdan'ında işlem için gaz limitini artır. Gaz limitini nasıl artıracağını öğrenmek için Cüzdan'ının belgelerine bak.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Nedenin belirsiz. Tekrar denemeden önce şu adımları izle:

1. Gaz limitini artır
2. Kayma'yı artır
3. Önbelleği temizle

## **Profil ile İlgili Sorunlar**

### Hata! Cüzdanında herhangi bir Pancake Collectible bulunamadı.

Bu sorunun arkasındaki mantığı araştırıyoruz. Bu arada lütfen geçici çözümü dene.

{% tabs %}
{% tab title="Geçici Çözüm 1" %}
1. "Koleksiyon" sayfasına git, ardından profil sayfasına geri dön.\
   Bağlantıyı bulamazsan doğrudan [https://pancakeswap.finance/collectibles](https://pancakeswap.finance/collectibles) adresine git.
2. Profil oluşturmayı tekrar dene.
{% endtab %}

{% tab title="Geçici Çözüm 2" %}
Ortamı değiştir.

* Önbelleği temizle ve tekrar dene.
* Farklı bir tarayıcıda tekrar dene.
* Farklı Cüzdan uygulamalarında tekrar dene.
* Farklı ağda dene (Wi-Fi ile mobil veri arasında geçiş yap)
{% endtab %}
{% endtabs %}

### Kullanıcı adı kontrolü sürekli dönüyor

İki olası neden var.

1. Tarayıcıda birden fazla Cüzdan yüklü.
2. Ağ sorunu.

{% tabs %}
{% tab title="Çözüm 1" %}
Kök neden: Tarayıcıda birden fazla Cüzdan yüklü.\
\
Cüzdanlar arasında çakışma yaratabilir. Bu durum PancakeSwap'in kontrolünde değildir ve bir şey yapma imkânımız yok.

1. Tarayıcıda yalnızca tek bir Cüzdan bırak, diğerlerini kaldır.
2. Cüzdan'ı yeniden bağla ve kullanıcı adı ayarlamayı tekrar dene.
{% endtab %}

{% tab title="Çözüm 2" %}
Kök neden: Ağ kararsız.

Yeniden denemen gerekiyor.

1. Metin alanına girilen her şeyi tamamen sil.
2. Kullanıcı adını yeniden yaz ve birkaç saniye bekle.
3. Çalışmazsa sayfayı yenile ve tekrar dene.
{% endtab %}
{% endtabs %}
