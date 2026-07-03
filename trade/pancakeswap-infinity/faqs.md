# SSS

1. **Infinity, PancakeSwap V3'ten nasıl farklıdır?**\
   Infinity; programlanabilir hook'lar, daha fazla [havuz türü](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) (LBAMM ve CLAMM gibi) ve gaz tasarrufu gibi yeni özellikler ekler. Ancak temel Swap ve likidite sağlama mekanikleri, LBAMM havuzlarında likidite sağlamadaki bazı küçük farklılıklar dışında büyük ölçüde v3'e benzerdir.\
   <br>
2.  **LBAMM ile CLAMM arasındaki fark nedir?**

    1. **LBAMM (Likidite Defteri AMM):** Her biri farklı fiyat seviyelerinde likidite tutan likidite bin'leri kullanır. LP'ler bin'ler arasında likidite sağlayabilir, Swap'lar bir bin içinde tek bir fiyat seviyesinde gerçekleştirilir.
    2. **CLAMM (Yoğunlaştırılmış Likidite AMM):** Kullanıcıların tıpkı PancakeSwap V3'te olduğu gibi özel fiyat aralıklarında likidite sağlamasına olanak tanır.

    \
    Daha fazla ayrıntı için [buraya](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/pool-types) git. \
    <br>
3. **Farm ödüllerimi nasıl talep ederim ve neden 8 saatte bir ile sınırlıdır?**\
   Likidite pozisyonlarından farm ödüllerini "Hasat" düğmesine tıklayarak talep edebilirsin. Infinity, tüm aktif farm pozisyonlarında toplu talep yapılmasına olanak tanıyarak gaz maliyetini düşürür. Ödüller, gaz maliyetlerini ve hesaplamayı optimize etmek için her 8 saatte bir hesaplanır ve işleme alınır. \
   \
   Farming mekanizması hakkında daha fazla ayrıntı için [buraya](https://docs.pancakeswap.finance/trade/pancakeswap-infinity/farms) git. \
   <br>
4.  **Infinity hook'ları nasıl çalışır?**\
    Hook'lar, bir havuza ekstra işlevsellik katan özelleştirilebilir akıllı sözleşme uzantılarıdır. Swap'lar veya likidite olayları sırasında ek eylemler tetikleyebilirler; örneğin ücretleri ayarlama, indirim sunma veya başka mantık uygulama gibi.<br>

    Hook'lar, oluşturulduğunda bir havuza eklenir. Çoğu durumda **kullanıcıların herhangi bir ek adım atmasına gerek yoktur**. Swap yaparak veya her zamanki gibi likidite sağlayarak, hook'un mantığı ilgili havuz için geçerliyse otomatik olarak faydasından yararlanırsın.<br>

    👉 **Aktif hook'ları ve ayrıntılarını her havuzun sayfasında "Havuz Özellikleri" bölümünde görüntüleyebilirsin.**\
    <br>
5.  **Bir LBAMM havuzundan pozisyonumu çekerken neden herhangi bir ücret almadım?**\
    LBAMM (Likidite Defteri AMM) havuzlarında ücretler, aktif likidite bin'lerine otomatik olarak eklenir. Bu şu anlama gelir:

    1. Pozisyonunu çektiğinde, kazandığın ücretler çektiğin toplam token miktarına dahil edilir.
    2. Geleneksel AMM'lerin aksine, ayrı bir "tahsil edilecek ücretler" bakiyesi yoktur; hepsi pozisyonunun değerine dahil edilir.

    \
    Çekim sırasında ek token fark etmediysen bunun nedeni şunlar olabilir:

    1. Pozisyonun, pozisyonunun süresince fiyat hareketleri nedeniyle elde ettiği ücretlerden daha fazla kalıcı olmayan kayba uğramış olabilir.
    2. Likiditein, işlemlerin gerçekleştiği aktif bin'lerde yer almıyor olabilir.
