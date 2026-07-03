---
hidden: true
---

# Farming SSS

### Neden birden fazla APR var?

V3'te likidite sağlarken varlıklarını konsantre ederek toplam mevcut likviditenin payını artırabilir ve daha yüksek bir ödül yüzdesi kazanabilirsin.&#x20;

Bu nedenle pozisyon fiyat aralığı ayarlarına bağlı olarak her likidite pozisyonunun kendi LP ücreti APR'si ve farming APR'si olur.

Global APR, aktif pozisyonlardaki toplam CAKE ödüllerinin USD cinsinden toplam varlık miktarına bölünmesiyle hesaplanır; bu aktif pozisyonlar şu an farm'da stake edilmektedir. Dolayısıyla global farming APR yalnızca genel bir referanstır ve her pozisyon için bireysel APR'leri temsil etmez.

Farming APR'nizi görüntülemek için her farm altında listelenen pozisyonlarını kontrol et.

###

### Farm'da stake ederken likidite pozisyonum aralık dışına çıkarsa ne olur?

V3'te yalnızca aktif (aralık içinde) likidite pozisyonları farm'lardan CAKE kazanır.

Fiyat aralık dışına çıktığında pozisyon CAKE ödülleri almayı durdurur.

Fiyat yeniden aralık içine girdiğinde pozisyon CAKE ödülleri almaya başlar. Stake yapanların herhangi bir ek işlem yapmasına gerek yoktur.



### Her zaman aralık içinde olup ücret ödülleri kazanmak için pozisyonumu otomatik olarak ayarlamanın bir yolu var mı?

PancakeSwap v3, BNB Chain ve Ethereum'da kullanılabilen Zap aracılığıyla tek tıkla likidite yatırmayı destekler.



### Daha küçük bir aralıkla likidite pozisyonu kullanmak her zaman daha mı iyi?

Daha küçük bir fiyat aralığına likidite sağlamak, likviditenini konsantre etmeye yardımcı olarak fiyat aralığındaki toplam aktif likiditeye göre göreli payını artırır ve potansiyel olarak daha fazla CAKE ödülü kazandırır.

Ancak yalnızca aktif likidite pozisyonlarının CAKE ödülleri kazanacağını aklında tut. Bu, yalnızca mevcut işlem fiyatı likidite pozisyonunda tanımlanan fiyat aralığı içinde olduğunda ödül kazanacağın anlamına gelir.

Pozisyon fiyat aralığını ayarlaман gerekiyorsa unstake etmen, likiditeyi kaldırman ve güncellenmiş fiyat aralığıyla yeni bir pozisyon oluşturman gerekir. Sık ayarlamaların her zaman en optimal strateji olmadığını; kalıcı olmayan kaybı gerçekleştirdiğini ve birden fazla işlemi tamamlamak için belirli miktarda gas maliyeti getirdiğini aklında tut.



### Tek bir farm'da kaç pozisyon stake edebilirim?

Bir farm'da stake edebileceğin pozisyon sayısı için maksimum bir sınır yoktur.

Ancak her pozisyondan ödülleri manuel olarak toplamak için gas harcaman gerektiğini aklında tut. Getiri işlemlerinde her zaman gas maliyetini hesaba kat.



### Ödüllerimi ne sıklıkla toplamalıyım?

Ödüllerini ne sıklıkla toplayacağın sana kalmış; ancak toplama işleminin küçük bir ücret gerektirdiğini aklında tutmakta fayda var. Bu ücreti "Topla"ya tıkladıktan sonra cüzdanında onay sırasında görebilirsin**.**

Bu, MetaMask cüzdanında görünen toplama ücretini gösterir. Farklı cüzdanlar bilgileri biraz farklı biçimde gösterebilir. Ücretleri daha az sıklıkla ödemek için ödüllerinin bir süre büyümesini bırakmayı düşün.



### Farm'da stake ederken pozisyonumu ayarlamak istersem ne yapmalıyım?

Farm'da stake ederken unstake etmeden likidite ekleyebilir veya kaldırabilirsin. Ayarlamak istediğin likidite pozisyonunu bul, başlığına/kimliğine tıkla; "Ekle" ve "Kaldır" düğmelerinin bulunduğu pozisyon ayrıntı sayfasına yönlendirileceksin.

Likidite pozisyonunun fiyat aralığı yapılandırmalarını ayarlamak istiyorsan farm'dan unstake etmen, tüm likiditeyi kaldırman ve yeniden likidite ekleyerek yeni bir pozisyon oluşturman gerekir.



### Farming APR'sini ne etkiler?

Farm v3'te CAKE ödül APR'si likidite pozisyonları arasında değişebilir. Şu faktörlere bağlıdır:

* Farm'lara CAKE emisyon oranı\
  \- Daha fazla CAKE, tüm farm'lar için daha yüksek getiri sağlar. [Tokenomics sayfamızda](https://docs.pancakeswap.finance/tokenomics/cake/cake-tokenomics) daha fazlasını oku
* Farm çarpanı\
  \- Daha yüksek çarpanlı farm'lar, tüm farm'lara oranla daha fazla CAKE alır. v3 ile v2 + StableSwap farm'larının iki ayrı çarpan seti kullandığını unutma. Ethereum ve BNB Chain'deki farm'lar da iki ayrı çarpan seti kullanır.
* Pozisyona yatırılan token sayısı\
  \- Pozisyondaki daha fazla token, farm havuzundaki toplam aktif likviditenin göreli payını artırır ve daha fazla CAKE ödülü sağlar
* Seçilen fiyat aralığı\
  \- Daha küçük fiyat aralığı, yatırılan aynı miktar token için daha yüksek konsantrasyon sağlar; bu da farm havuzundaki toplam aktif likviditenin göreli payını artırır ve daha fazla CAKE ödülü kazandırır
* Şu an aktif olan likidite miktarı\
  \- Seninle aynı aralıkta likidite yatırıp konsantre eden daha fazla kullanıcı varsa, toplam aktif likviditenin göreli payın küçüleceğinden daha az CAKE ödülü kazanırsın
* Likidite pozisyonunun aktif olup olmadığı\
  \- Yalnızca aktif likidite pozisyonları farm'dan CAKE ödülü kazanır



### "Pozisyonları Güncelle" açılır penceresi neden görüyorum?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28321%29.png)

V3'ün lansmanından kısa süre sonra Chefs, ödül hesaplamalarını daha doğru ve güvenilir hâle getirmek için Farm'larda bir güncelleme uyguladı. Bu açılır pencereyi görüyorsan bazı pozisyonlarının güncellenmesi gerekiyor demektir.

"Tümünü Güncelle" düğmesine tıklayıp cüzdan açılır penceresinde onayla.

Chefs'in bu güncellemeyi Farm V3'ün lansmanı ile bu güncellemenin uygulandığı tarih arasındaki geçmiş stake verilerine de uyguladığını unutma. Fazladan CAKE ödülleri varsa 1 Mayıs 2023'ten önce cüzdanına airdrop edilecek.



### V3'te 2x çarpanlı bir farm neden V2'deki 1x çarpanlı bir farm'dan daha düşük APR'ye sahip?

Her şeyden önce, APR'leri karşılaştırırken iki farm arasındaki toplam stake edilmiş likiditenin eşit olduğundan emin olman gerekir.

Bunun ötesinde, artık her birinin kendi CAKE emisyon akışına sahip birden fazla farm grubumuz var. Ve her farm grubu ayrı çarpan setleri paylaşır.

Bireysel bir farm, aşağıdakilere göre CAKE emisyonları alır:

* A = Ait olduğu farm grubu için saniye/blok başına toplam CAKE
* B = Ait olduğu gruptaki toplam çarpan sayısı
* C = Sahip olduğu çarpan

`Blok/saniye başına CAKE = C / B * A`

Yukarıdaki sayıları her bir [MasterChef](/broken/pages/-MeTWzQOSmb1ej51HT0I) sözleşmesinde bulabilirsin.



### V3 Farm'larında bCAKE kullanabilir miyim?

Evet

V3 Farm'ları için bCAKE, PancakeSwap Farm V3'ün dağıtımından kısa süre sonra gelecek. Takipte kal.
