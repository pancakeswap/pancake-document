# 🧙 Page 1

## PancakeSwap NFT Marketplace'ten NFT'ni Nasıl Çekersin

PancakeSwap NFT Marketplace sayfaları artık kullanılamıyor, ancak marketplace akıllı sözleşmesi hâlâ aktif. Satışa koyduğun bir NFT satılmadıysa hâlâ marketplace sözleşmesinin elinde duruyor. Listelemeyi doğrudan BscScan üzerinden iptal ederek NFT'ni kendin geri alabilirsin.

Bu işlem NFT başına birkaç dakika sürer ve gas için yalnızca küçük bir miktar BNB'ye mal olur.

### Başlamadan önce

Şunlara ihtiyacın olacak:

* **NFT'yi listelerken kullandığın aynı cüzdan.** Bir listelemeyi yalnızca onu oluşturan cüzdan iptal edebilir.
* **Bir tarayıcı cüzdanı** (örneğin MetaMask, Trust Wallet extension veya Binance Wallet extension), **BNB Smart Chain** ağına ayarlı.
* Gas ödemek için **küçük bir miktar BNB**. Her NFT kendi işleminde çekilir.

Şu adresleri elinin altında tut:

| Öğe                        | Adres                                        |
| -------------------------- | -------------------------------------------- |
| Marketplace sözleşmesi     | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Pancake Squad koleksiyonu  | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Pancake Bunnies koleksiyonu | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Güvende kal**
>
> * Yalnızca `0x17539cCa21C7933Df5c980172d22659B8C345C5A` marketplace sözleşmesiyle etkileşime gir. BscScan URL'sindeki adresi her zaman kontrol et.
> * NFT'ni çekmek için **asla** BNB veya token göndermen gerekmez ve asla bir onay (`approve` veya `setApprovalForAll`) imzalaman gerekmez. Bir web sitesi ya da kişi senden bunu istiyorsa bu bir dolandırıcılıktır.
> * PancakeSwap sana asla DM atmaz ve tohum ifadeni istemez.

### 1. Adım: Hâlâ listelenmiş olan NFT'lerini bul

Çekmek istediğin her NFT için iki bilgiye ihtiyacın var: **koleksiyon adresi** ve **token ID**.

1. BscScan'de marketplace sözleşmesinin [Read Contract sayfasını](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) aç.
2. **`viewAsksByCollectionAndSeller`** bölümünü bul ve genişlet.
3. Alanları doldur:
   * `collection`: yukarıdaki tablodan koleksiyon adresi (örneğin Pancake Squad için `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller`: cüzdan adresin
   * `cursor`: `0`
   * `size`: `100`
4. **Query**'ye tıkla.
5. `tokenIds` sonucuna bak. Bunlar o koleksiyonda hâlâ listelenmiş olan token ID'lerin ve çekebileceğin NFT'ler.
6. Birden fazla koleksiyonda NFT listelediysen, her koleksiyon için 3 ile 5. adımları tekrarla.

**`tokenIds` boşsa (`[]`)**, o koleksiyonda aktif listelemen yok demektir. NFT'n ya satıldı (bu durumda BNB'yi zaten aldın) ya da listelemeyi daha önce iptal ettin (bu durumda zaten cüzdanında).

**Bir koleksiyonda 100'den fazla listelemen varsa**, sonuçtaki son sayı bir sonraki cursor'dır. Kalanını görmek için bu sayıyı `cursor` olarak kullanıp tekrar sorgula.

**NFT'n Pancake Squad veya Pancake Bunnies dışında bir koleksiyondansa**, aynı sayfada **`viewCollections`** bölümünü genişlet, `cursor = 0` ve `size = 100` gir ve marketplace'in desteklediği tüm koleksiyonları görmek için **Query**'ye tıkla.

### 2. Adım: NFT'ni çek

1. BscScan'de marketplace sözleşmesinin [Write Contract sayfasını](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) aç.
2. **Connect to Web3**'e tıkla ve NFT'yi listeleyen aynı cüzdanı bağla. Cüzdanının BNB Smart Chain üzerinde olduğundan emin ol.
3. **`cancelAskOrder`** bölümünü bul ve genişlet.
4. Alanları doldur:
   * `_collection`: 1. Adım'daki koleksiyon adresi
   * `_tokenId`: 1. Adım'daki token ID, düz bir sayı olarak (örneğin `1234`)
5. **Write**'a tıkla ve işlemi cüzdanında onayla. BNB göndermezsin; yalnızca gas ödersin.
6. İşlem başarılı olduğunda NFT cüzdanına geri döner.
7. Çekmek istediğin her NFT için tekrarla.

İşe yaradığını doğrulamak için 1. Adım'ı tekrar çalıştır. Token ID artık listede görünmemeli.

### Sorun giderme

| Sorun                                                     | Ne anlama geliyor ve ne yapmalısın                                                                                                                                                                          |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Hata: `Order: Token not listed`                           | Bağlı cüzdan bu koleksiyonda bu token ID'yi listelememiş ya da NFT zaten satılmış veya çekilmiş. Orijinal cüzdanı ve doğru koleksiyon adresi ile token ID'yi kullandığını kontrol et.                       |
| Write düğmesi hiçbir şey yapmıyor                         | Cüzdanın muhtemelen yanlış ağda. BNB Smart Chain'e geç ve yeniden bağlan.                                                                                                                                   |
| Gas yetersiz veya bakiye yetersiz                         | Gas'i karşılamak için cüzdanına küçük bir miktar BNB ekle.                                                                                                                                                  |
| NFT'yi listeleyen cüzdana artık erişimim yok              | Listelemeyi yalnızca orijinal cüzdan iptal edebilir. PancakeSwap dahil hiç kimse senin adına çekemez.                                                                                                       |
