---
description: PancakeSwap'ta Yield Farming çok kolay!
---

# Farm Nasıl Kullanılır (Eski Sürüm)

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-header.png)

Farm'larda Yield Farming, PancakeSwap'ta CAKE ödülleri kazanmanın harika bir yoludur.

Syrup Pools'un aksine Farm'lar, likidite sağlamak ve likidite pozisyonu NFT'si ya da LP Token almak için **iki token** stake etmeni gerektirir; ardından bunları ödül kazanmak için Farm'a stake edersin. Bu sayede diğer token'larındaki pozisyonunu korurken CAKE kazanırsın!

{% hint style="warning" %}
Yield farming, Syrup Pools'a kıyasla daha iyi ödüller sunabilir; ancak **Kalıcı Olmayan Kayıp** (Impermanent Loss) riski taşır. Kulağa ürkütücü gelse de, başlamadan önce bu kavramı öğrenmeye değer.

Daha fazla bilgi için Binance Academy'nin [Kalıcı Olmayan Kayıp hakkındaki harika makalesine](https://academy.binance.com/en/articles/impermanent-loss-explained) göz at.
{% endhint %}

## Farm V3

### **Hazırlık**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2832%29.png)

Bir Farm'a girmek için bir likidite pozisyonuna ihtiyacın olacak. Farm'lar yalnızca kendi tam işlem çiftlerinden ve seçilen tam ücret kademesinden gelen likidite pozisyonlarını kabul edebilir; örneğin CAKE-BNB %0,25 Farm'ı yalnızca %0,25 ücret kademesiyle CAKE-BNB likidite pozisyonlarını kabul eder. Şunları kabul etmez:

* CAKE-BUSD gibi diğer çiftler
* Aynı çift ancak farklı ücret kademeleri: %0,05 ücret oranlı CAKE-BNB gibi

Tam LP pozisyonunu oluşturmak için doğru ücret oranı seçilerek o işlem çiftine likidite sağlaman gerekir. Yani CAKE-BNB %0,25 LP pozisyonları elde etmek için önce %0,25 ücret kademesiyle CAKE-BNB çiftine likidite sağlaман gerekir.

Kulağa korkutucu gelebilir ama çok da karmaşık değil. Adım adım inceleyelim.

### **Farm'ını Bul**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28239%29.png)

Devam etmeden önce sana uygun bir Farm seçmek isteyeceksin. Mevcut Farm'ların listesini görmek için [Farm sayfasını ziyaret et](https://pancakeswap.finance/farms).

Şu anda en yüksek ödül oranına sahip Farm'lar için APR'ye göre sıralama gibi farklı bir sıralama seçeneği belirleyebilirsin. APR'lerin bireysel pozisyonlar için global olarak hesaplandığını; fiyat aralığı ayarlarına bağlı olarak değişebileceğini unutma.

Kullanmak istediğin bir Farm bulduğunda, ileride gerekebileceği ihtimaline karşı işlem çiftini ve ücret oranını not al; örneğin BNB-CAKE ve %0,25.

### **Pozisyon oluşturmak için likidite sağla**

Stake edeceğin bir Farm bulduğuna göre artık likidite sağlaман gerekiyor:

1 — Kullanılabilir bir pozisyonun yoksa "Likidite Ekle" düğmesi görürsün; Farm sayfasından ayrılmadan "Likidite Ekle" penceresini açmak için sadece buna tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2840%29.png)

2 — Alternatif olarak listeden seçtiğin Farm'ın satırına tıklayabilirsin. Bu, daha fazla ayrıntı gösterecek şekilde açılır. Kart görünümünde daha fazla ayrıntı için "Ayrıntılar"a tıkla. Likidite eklemek için ayrıntı bölümündeki "XXX-YYY LP Ekle" bağlantısına tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28242%29.png)

### **Pozisyonlarını farm'a stake et**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28124%29.png)

Likidite eklemeyi tamamladıktan sonra pozisyonunu kullanmak istediğin farm'ın altında listelenmiş olarak görmelisin.

Birden fazla pozisyonun varsa hepsini yeni bir açılır pencerede görüntülemek için "Tümünü Görüntüle"ye tıklayabilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28198%29.png) ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28151%29.png)

Listelenen pozisyonda "Stake" düğmesine tıkla; cüzdanın onay isteyecek.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28229%29.png)

Kısa bir bekleyişin ardından pencere kapanır ve ayrıntılarda stake edilmiş pozisyonunu görürsün.

Farklı fiyat aralığı yapılandırmalarıyla birden fazla pozisyonu hızlıca stake etmek için yukarıdaki adımları tekrarlayabilirsin. Her pozisyon CAKE kazanır ve ayrı ayrı toplanması gerekir.

### **Farming ödüllerini topla**

Farm V3'te aynı farm'da birden fazla pozisyon stake edebilirsin. Stake edilen her pozisyon CAKE kazanır ve ayrı ayrı toplanması gerekir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28230%29.png)

Stake edilmiş bir pozisyondan CAKE ödülleri toplamak için Farm sayfasına dön ve toplamak istediğin farm ile pozisyonu bul. Şu an stake ettiğin farm'ları hızlıca filtrelemek için "Yalnızca Stake Edilenler" geçiş düğmesini kullanabilirsin.

Birden fazla stake edilmiş pozisyonun varsa hepsini yeni bir açılır pencerede görüntülemek için "Tümünü Görüntüle"ye tıklayabilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28241%29.png)

Pozisyonda "Topla" düğmesine tıkla; cüzdanın onay isteyecek. Kısa bir bekleyişin ardından CAKE ödülleri cüzdanına gönderilir.

### **Farm'da stake ederken likidite ekle veya kaldır**

Farm'da stake ederken unstake etmeden likidite ekleyebilir veya kaldırabilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28230%29.png)

Bunun için Farm sayfasına dön ve ayarlamak istediğin farm ile pozisyonu bul. Şu an stake ettiğin farm'ları hızlıca filtrelemek için "Yalnızca Stake Edilenler" geçiş düğmesini kullanabilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28267%29.png)

Token çiftini, ücret oranını, pozisyon kimliğini ve ">" okunu içeren pozisyon başlığına tıkla. Pozisyon ayrıntı sayfasına yönlendirileceksin.

Stake edilmiş pozisyondaki likiditeyi ayarlamak için "Ekle" veya "Kaldır" düğmesini kullan.

Pozisyonunu ayarlarken talep edilmemiş tüm CAKE ödüllerinin toplanıp cüzdanına gönderileceğini unutma.

### **Pozisyonlarını farm'dan unstake et**

Bir pozisyonu istediğin zaman unstake edebilirsin.

Unstake etmek için Farm sayfasına dön ve unstake etmek istediğin farm ile pozisyonu bul. Şu an stake ettiğin farm'ları hızlıca filtrelemek için "Yalnızca Stake Edilenler" geçiş düğmesini kullanabilirsin.

Birden fazla stake edilmiş pozisyonun varsa hepsini yeni bir açılır pencerede görüntülemek için "Tümünü Görüntüle"ye tıklayabilirsin.

Pozisyonda "Unstake" düğmesine tıkla; cüzdanın onay isteyecek. Kısa bir bekleyişin ardından pozisyon NFT'n bekleyen tüm CAKE ödülleriyle birlikte cüzdanına iade edilir.

## Farm V2

### Hazırlık

Yield farming'in kurulumu biraz çalışma gerektirir.

Bir Farm'a girmek için "LP Token"lara ihtiyacın olacak. Farm'lar yalnızca kendi tam LP Token'larını kabul edebilir; örneğin CAKE-BNB Farm'ı yalnızca CAKE-BNB LP Token'larını kabul eder.

Tam LP Token'ı elde etmek için o işlem çiftine likidite sağlaман gerekir. Yani CAKE-BNB LP Token'larını elde etmek için önce CAKE-BNB çiftine likidite sağlaман gerekir.

Kulağa korkutucu gelebilir ama çok da karmaşık değil. Adım adım inceleyelim.

### Farm'ını Bul

Devam etmeden önce sana uygun bir Farm seçmek isteyeceksin. [Farm sayfasını ziyaret et](https://pancakeswap.finance/farms) ve mevcut Farm'ların listesini göreceksin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2862%29.png)

Şu anda en yüksek ödül oranına sahip Farm'lar için **APR**'ye göre sıralama gibi farklı bir sıralama seçeneği belirleyebilirsin.

Kullanmak istediğin bir Farm bulduğunda, ileride gerekebileceği ihtimaline karşı BNB-CAKE gibi işlem çiftini not al.

### LP Token almak için likidite sağla

Stake edeceğin bir Farm bulduğuna göre LP Token'larını almak için likidite eklemelisin.

1. Listeden seçtiğin Farm'ın satırına tıkla. Daha fazla ayrıntı gösterecek şekilde açılır.
2. Solda bazı bağlantılar göreceksin. **(çiftin) LP Al** bağlantısına tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28131%29.png)

### LP Token'larını farm'a yerleştir

Artık LP Token'larına sahipsin; bunları Farm'da stake edip ödül kazanmaya hazırsın!

1 — [Farm sayfasına](https://pancakeswap.finance/farms) geri dön ve Farm'ını bul. Çiftini gösteren satırın herhangi bir yerine tıkla. Daha fazla ayrıntı gösterecek şekilde genişleyecek.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28244%29.png)

Hazır olduğunda **Etkinleştir** düğmesine tıklayıp cüzdanında işlemini onayla.

2 — Kısa bir bekleyişin ardından Etkinleştir düğmesi **LP Stake Et** olarak değişir. Tıkla ve yeni bir pencere açılır.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28171%29.png)

3 — Farming yapmak istediğin LP Token miktarını alana yaz ya da tüm LP Token'larını kullanmak için **Maks** düğmesine tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28109%29.png)

4 — Miktarı girdiğinde **Onayla** düğmesi aktifleşir. Tıkla. Cüzdanın işlemini onaylamak isteyecek.

5 — Kısa bir bekleyişin ardından pencere kapanır ve ayrıntılarda yeni stake edilmiş LP Token bakiyeni görürsün.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28261%29.png)

{% hint style="info" %}
BNB zinciri dışında bir EVM blok zincirinde crosschain farming yapıyorsan cross-chain işlemlerin onaylanması için yaklaşık 30 dakika beklemelisin.

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/crosschain-farm-wait.png" alt="" data-size="original">

Bir crosschain farming işleminin ilerleme durumunu takip etmek için stake edilmiş bakiyenin yanındaki dairesel simgeye tıkla ya da sağ üst köşedeki "Son İşlemler" bölümüne göz at.
{% endhint %}

{% hint style="warning" %}
BNB zinciri dışında bir EVM blok zincirinde ilk kez crosschain farming yapıyorsan ilk kurulum için küçük miktarda yerel token (örneğin Ethereum için ETH) gereklidir. Bu nedenle ilk işlem biraz daha maliyetli olabilir.
{% endhint %}

### Farm'a LP Token ekleme veya çıkarma

Daha sonra bir Farm'a daha fazla LP Token eklemek veya bir kısmını çıkarmak isteyebilirsin. Bunu istediğin zaman kolayca yapabilirsin.

1. [Yield Farms sayfasına](https://pancakeswap.finance/farms) dön. Sayfanın üst kısmında **Yalnızca Stake Edilenler** geçiş düğmesini göreceksin. Geçiş düğmesine tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28240%29.png)

Artık listede yalnızca LP Token sahibi olduğun çiftleri görmelisin; bu da Farm'ını bulmayı kolaylaştırır.

1. LP Token'larına sahip olduğun Farm'ı bul ve ayrıntıları görüntülemek için satıra tıkla. Sağ tarafta bir **-** ve **+** düğmesi görürsün. LP Token kaldırmak için **-**'ye, daha fazla LP Token eklemek için **+**'ya tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28102%29.png)

1. İlk kez LP Token stake ederken kullandığına benzer bir pencere açılır. Önceki gibi unstake/stake etmek istediğin miktarı yaz ya da mevcut tüm LP Token'ları kaldırmak/eklemek için **Maks**'a tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2879%29.png)

1. Bilgilerinin doğru olduğundan emin ol. Hazır olduğunda **Onayla** düğmesine tıklayıp cüzdanında işlemi onayla.
2. Kısa bir bekleyişin ardından LP Token çiftinin ayrıntı bölümünde yeni bakiyeni görürsün. LP Token'larını unstake ettiysen, toplanmamış ödüllerin otomatik olarak tahsil edilmiş olacak.

### Farming ödüllerini topla

Farming, zamanla sana CAKE ödülleri getirir. Bu ödülleri toplayıp daha fazla LP Token almak, Syrup Pools'ta stake etmek, Piyango oynamak veya istediğin başka şeyler için kullanabilirsin.

### Ödüllerini toplamak için Farm'ına dön

Farm ve Syrup Pool ödüllerini Ana Sayfa'dan birlikte toplayabilirsin. Yalnızca farming ödüllerini toplamak istiyorsan devam et.

Ödüllerini toplamak için seçtiğin Farm'ı ziyaret edip seni bekleyen CAKE'i toplaман gerekir.

1 — [Buradan](https://pancakeswap.finance/farms) Farm sayfasına dön.

2 — LP Token'larını stake ettiğin Farm'ı bul ve ayrıntıları görüntülemek için satıra tıkla. "Kazanılan CAKE" bölümünde ödüllerinin tahmini değerini görmelisin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28181%29.png)

3 — **Topla** düğmesine tıklayıp cüzdanında işlemi onayla. Kısa bir bekleyişin ardından CAKE istediğin gibi kullanman için cüzdanına aktarılır.

{% hint style="info" %}
BNB zinciri dışında bir EVM blok zincirinde crosschain farming yapıyorsan farming ödüllerini toplamak için her zaman BNB Smart Chain'e geçmen gerekir.

Cüzdanın zincir değiştirmeyi desteklemiyorsa LP token'larını stake etmek veya unstake etmek her zaman CAKE'ini toplar. Toplanan CAKE'in BNB Smart Chain'de dağıtılacağını unutma.

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28164%29.png" alt="" data-size="original">
{% endhint %}

## Ödüllerimi ne sıklıkla toplamalıyım?

Ödüllerini ne sıklıkla toplayacağın sana kalmış; ancak toplama işleminin küçük bir ücret gerektirdiğini aklında tutmakta fayda var.

Bu ücreti **Topla** düğmesine tıkladıktan sonra cüzdanında onay sırasında görebilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28281%29.png)

Bu, MetaMask cüzdanında görünen toplama ücretini gösterir. Farklı cüzdanlar bilgileri biraz farklı biçimde gösterebilir. Ücretleri daha az sıklıkla ödemek için ödüllerinin bir süre büyümesini bırakmayı düşün.

Hepsi bu kadar! [PancakeSwap Syrup Pools'un nasıl kullanılacağına](https://docs.pancakeswap.finance/get-started/syrup-pool-guide) da bakarak ödül kazanmak isteyebilirsin.

İyi farming'ler!
