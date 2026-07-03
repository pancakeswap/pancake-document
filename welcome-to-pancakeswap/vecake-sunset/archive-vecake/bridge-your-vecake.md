# veCAKE'ini Bridge Et

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%281%29.png" alt=""><figcaption></figcaption></figure>

Diğer zincirlerde bCAKE (Farm getiri boostu) ve iCAKE (IFO halka açık satış tahsisi) gibi veCAKE avantajlarından yararlanmak için BNB Chain üzerinde basit bir köprüleme talebi gerçekleştirmen ve veCAKE bakiyeni ile PancakeProfile'ını diğer zincirlere senkronize etmen gerekiyor.

## Nasıl bridge edilir? <a href="#id-734b8113-0e00-40ff-bccb-9c129460e2e2" id="id-734b8113-0e00-40ff-bccb-9c129460e2e2"></a>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%285%29.png" alt=""><figcaption></figcaption></figure>

[CAKE Staking](https://pancakeswap.finance/cake-staking) sayfasına git ve veCAKE avantajlarının altındaki veCAKE Senkronizasyon kartını bul. Senkronizasyon modalını açmak için "Ayrıntıları Görüntüle"ye tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%281%29%20%281%29%20%281%29%20%281%29.png" alt="" width="253"><figcaption></figcaption></figure>

Modal içinde BNB Chain'deki veCAKE miktarını görebilirsin. Ayrıca hedef zincirler listesinde, veCAKE'ini ve Pancake Profile'ını her zincirdeki mevcut veCAKE ve Pancake Profile durumunla senkronize edebilirsin.

Senkronize etmek için zinciri seç ve "Senkronize Et"e tıkla, ardından cüzdan açılır penceresinde onayla.

Köprülemenin tamamlanması 20 dakikaya kadar sürebilir. Köprüleme ilerleme durumunu senkronizasyon modalından takip edebilirsin.&#x20;

Not:

* Aynı anda yalnızca bir zinciri bridge edebilirsin. veCAKE'ini birden fazla zincire senkronize etmek için yukarıdaki adımları tekrarla.
* Köprüleme talebi sırasında hedef zincirdeki gas maliyetini karşılamak için BNB alınır. BNB miktarı hedef zincire göre değişir. Ethereum ana ağı gibi zincirler, yüksek gas maliyeti nedeniyle senkronizasyon için önemli ölçüde daha pahalı olabilir.
* Gereksiz gas harcamasından kaçınmak için veCAKE'ini yalnızca avantajlarından yararlanmak istediğin zincire senkronize et.
* Daha fazla CAKE ekledikten veya veCAKE staking pozisyonunu uzattıktan sonra, avantajlarının güncel kalmasını sağlamak için hedef zincirlerdeki veCAKE bakiyesini güncellemek amacıyla yukarıdaki işlemi tekrarla.

## SSS <a href="#id-9d6ee706-cd48-4d71-a5f8-c3de3d7d3aad" id="id-9d6ee706-cd48-4d71-a5f8-c3de3d7d3aad"></a>

**S: veCAKE ve Pancake Profile'ımı ne sıklıkla senkronize etmem gerekiyor?**

C: veCAKE için yalnızca daha fazla CAKE eklediğinde, kilit süresini uzattığında veya yeniden kilitleme yaptığında senkronizasyon yapman gerekiyor. Hedef zincirlerdeki veCAKE bakiyen, BNB Chain'deki bakiyeyle birlikte doğrusal olarak azalacak.

Pancake Profile ve NFT'si için Özel Satışlara katılmak amacıyla iki senkronizasyon yapman gerekiyor. Birincisi, IFO yayınlandığında ve arayüzde görüntülenebilir hale geldiğinde; ikincisi ise talep etme işlemini etkinleştirmek için IFO satışı sona erdikten sonra yapılmalı.

**S: Köprüleme ne kadar sürer?**

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%281%29%20%281%29.png" alt="" width="253"><figcaption></figcaption></figure>

Hedef zincire bağlı olarak, köprüleme ve tam senkronizasyon genellikle 2-5 dakika sürer. Bazı yavaş zincirlerde bu süre 30 dakikaya kadar uzayabilir. Köprüleme talebini takip etmek için senkronizasyon modalındaki LayerZero gezgin bağlantısını kontrol edebilir ya da [https://layerzeroscan.com/](https://layerzeroscan.com/) adresine gidip BNB Chain işlem kimliğiyle arama yapabilirsin.

**S: BNB Chain'deki köprüleme işlemi neden başarısız oluyor?**

C:

* Hedef zincir için gas tahmini güncel olmayabilir. Lütfen sayfayı yenile ve tekrar dene.
* Ayrıca cüzdanda hedef zincirdeki gas ücretini karşılayacak yeterli miktarda BNB bulunduğundan emin ol.

**S: veCAKE veya Pancake Profile'ım neden bridge edilmedi?**

C:

* Kalan kilit süresi 1 günden az olan veCAKE pozisyonları bridge edilmez. Lütfen önce kilidi uzat ve senkronizasyonu tekrar dene.
* Senkronizasyonun tamamlanması 30 dakika kadar sürebilir. Köprüleme durumunun "Teslim Edildi" olduğunu doğrulamak için https://layerzeroscan.com/ adresine gidip BNB Chain işlem kimliğiyle arama yap.
* Köprüleme durumu "Başarısız" veya "Engellendi" ise daha fazla ayrıntı için genel kanal aracılığıyla elçilerimizden biriyle iletişime geç.
