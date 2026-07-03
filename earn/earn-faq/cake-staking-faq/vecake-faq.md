---
hidden: true
---

# veCAKE SSS

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28340%29.png" alt=""><figcaption></figcaption></figure>

#### Kilitli CAKE ile veCAKE arasındaki fark nedir? <a href="#bb73a991-c71b-402c-a0c3-64b8666626c2" id="bb73a991-c71b-402c-a0c3-64b8666626c2"></a>

veCAKE, kilitli CAKE sahiplerine gösterge ağırlığı oylaması, ekstra teşvikler, getiri güçlendirme ve daha fazlası dahil olmak üzere daha fazla avantaj ve güç sunan sabit vadeli CAKE staking'in yeni bir versiyonudur.

#### Yeni veCAKE dağıtıldığında CAKE havuzu ödülleri ne olur? <a href="#a078f885-3eed-4b91-98fc-1d7062415da3" id="a078f885-3eed-4b91-98fc-1d7062415da3"></a>

CAKE havuzu ödül emisyonları, tüm veCAKE sahiplerini toplam arza göre veCAKE bakiyelerine oranla ödüllendirmek üzere yönlendirilecek.

CAKE ödülleri ve haftalık gelir paylaşımı ödülleri artık her Perşembe haftalık olarak talep edilebilir.

Ödüller almaya devam etmek için kullanıcıların yeni veCAKE staking'e geçiş yapması gerektiğini unutma.

#### CAKE'imi kilit altında tutabileceğim maksimum süre nedir? <a href="#id-9224ca4c-1f31-4052-8ed7-3bb896e396f3" id="id-9224ca4c-1f31-4052-8ed7-3bb896e396f3"></a>

CAKE'ini kilit altında tutabileceğin maksimum süre artık 4 yıla uzatıldı.

#### veCAKE yeni bir token mu? Transfer edilebilir mi? <a href="#id-26bce2a7-fb4c-453c-b4bb-e2d446660c77" id="id-26bce2a7-fb4c-453c-b4bb-e2d446660c77"></a>

veCAKE, kilitlenen CAKE miktarına ve kalan kilit süresine göre canlı olarak üretilen bir sayıdır. Standart bir token değildir ve transfer edilemez.

#### Neden veCAKE bakiyem değişti? Bakiyesi nasıl hesaplanır? <a href="#id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef" id="id-52f27118-bbf3-448b-9ffe-e9e1a9dd97ef"></a>

veCAKE bakiyesi, kalan kilit süresine göre doğrusal olarak sıfıra iner. Bu nedenle kilit açma zamanına yaklaştıkça bakiyen azalır.

veCAKE bakiyesi şu şekilde hesaplanabilir:

```javascript
lockedAmount // kilitlenen CAKE miktarı
currentTime // mevcut zaman
lockEndTime // kilit açma zamanı
maxLockTime = 209 * 7 * 24 * 60 * 60 - 1 = 126403199 // maksimum kilit süresi (4 yıl)

remainingLockTime = lockEndTime - currentTime
veCAKE = lockedAmount * (remainingLockTime / maxLockTime)
```

#### veCAKE'imi nasıl artırabilirim? <a href="#dddbafc4-7361-46a3-a040-09812f8a660e" id="dddbafc4-7361-46a3-a040-09812f8a660e"></a>

Aktif bir veCAKE pozisyonun olduğunda veCAKE bakiyeni artırmak için daha fazla CAKE ekleyebilir ya da kilit süresini yenileyebilir/uzatabilirsin.

#### Pozisyon kilidinin açıldığında ne olur? Hemen yenileyebilir miyim? <a href="#a819a132-aa20-41f1-9d92-3227ad0e2ead" id="a819a132-aa20-41f1-9d92-3227ad0e2ead"></a>

veCAKE staking pozisyonunun kilidi açıldığında tüm stake edilmiş CAKE'i çekebilirsin.

Pozisyonunu yenilemek için tüm CAKE'i çekmen ve kilitleme miktarını ve kilit süresini seçerek yeni bir staking pozisyonu oluşturman gerekir.

#### 1 hafta için kilitlediğimde neden kalan kilit süresi 1 haftadan az? <a href="#id-79f8be72-0138-48da-a609-e47a091be03c" id="id-79f8be72-0138-48da-a609-e47a091be03c"></a>

Yeni veCAKE ile kilitlerken kilit açma süresi en yakın Perşembeye UTC saatiyle yuvarlanır. Örneğin Salı günü 1 hafta için kilitlediğinde gerçek kilit açma süren 2 gün sonra olan bu Perşembe olacak.

Gerçek kilit açma sürenini altta önizleyebilirsin.

#### CAKE havuzuna daha fazla CAKE kilitleyebilir miyim? <a href="#id-2cc44f53-8e03-48dd-8caa-66c4942c9d39" id="id-2cc44f53-8e03-48dd-8caa-66c4942c9d39"></a>

Hayır.

veCAKE dağıtıldıktan sonra CAKE staking havuzu kullanımdan kaldırılacak ve artık herhangi bir CAKE uzatması veya yatırımı kabul etmeyecek.

CAKE kilitleme ve avantajlarından yararlanmak için veCAKE sayfasına git.

#### Neden geçiş yapamıyorum? <a href="#id-4d8fd967-e743-4496-b030-5955be861373" id="id-4d8fd967-e743-4496-b030-5955be861373"></a>

CAKE havuzundan veCAKE'e geçiş yapabilmek için aktif bir pozisyonun olması gerekir. CAKE havuzu staking pozisyonun zaten kilidi açıldıysa, bu CAKE'leri çekip yerel bir veCAKE staking pozisyonu oluştur.

Bazı durumlarda kalan CAKE havuzu kilit süren 7 günden az olduğunda geçiş gerçekleştirilemiyor. Bu durumda kilid açılmasını bekle, CAKE'leri çek ve yerel bir veCAKE staking pozisyonu oluştur.

#### Kilitli CAKE'imi erken çekebilir miyim? <a href="#id-5972f3cf-81dd-46d4-8a85-7972d722a53c" id="id-5972f3cf-81dd-46d4-8a85-7972d722a53c"></a>

Hayır.

Kilitlendikten sonra CAKE, kilit açma zamanına kadar veCAKE sözleşmesinde stake kalacak.

#### CAKE'imi kısmen geçirebilir miyim? <a href="#id-0c4cdba6-7994-4fed-80d1-76597444f761" id="id-0c4cdba6-7994-4fed-80d1-76597444f761"></a>

Hayır.

Tüm CAKE havuzu pozisyonunu yalnızca bir seferde geçirebilirsin.

#### iCAKE, bCAKE, vCAKE ve rCAKE'e ne olacak? <a href="#d828038d-6066-469e-a8d3-5bf4b95699b2" id="d828038d-6066-469e-a8d3-5bf4b95699b2"></a>

**iCAKE için:**

IFO iCAKE artık veCAKE'i destekleyecek şekilde yükseltildi. Göz at:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/icake.md" %}
[icake.md](../../../welcome-to-pancakeswap/vecake-sunset/icake.md)
{% endcontent-ref %}

**bCAKE için:**

Farm güçlendirici bCAKE artık veCAKE'i destekleyecek şekilde yükseltildi. Göz at:

{% content-ref url="../../../welcome-to-pancakeswap/vecake-sunset/bcake/" %}
[bcake](../../../welcome-to-pancakeswap/vecake-sunset/bcake/)
{% endcontent-ref %}

**vCAKE için:**

Oylama vCAKE artık veCAKE'i destekleyecek şekilde yükseltildi. Göz at:

{% content-ref url="../../../protocol/voting/voting-guide/" %}
[voting-guide](../../../protocol/voting/voting-guide/)
{% endcontent-ref %}

**rCAKE için:**

Tüm veCAKE sahipleri (yerel veya taşınmış) otomatik olarak yeni gelir paylaşımı havuzuna kaydedilecek. Gelir payları mevcut takvime göre dağıtılır. Eski gelir paylaşımı havuzu sonlandırılacak; kullanıcılar avantaj kartına giderek bekleyen ödüllerini talep edebilir. Göz at:

{% content-ref url="/broken/pages/wQegezs7c6A2HzQjPEjh" %}
[Bozuk bağlantı](/broken/pages/wQegezs7c6A2HzQjPEjh)
{% endcontent-ref %}

#### veCAKE ile etkileşim için çoklu imza cüzdanları kullanılabilir mi?

Evet

Ancak beyaz listeye alınmamış adresler için veCAKE staking sözleşmesinde bir `noContract` değiştiricisi uygulandı. Sabit vadeli CAKE staking havuzundan stake etmeyi veya geçiş yapmayı etkinleştirmek için tüm sözleşme tabanlı çoklu imza cüzdanlarının bir kerelik kendi kendini beyaz listeye ekleme işlemi gerçekleştirmesi gerekir.

Beyaz listeye eklemek için aşağıdaki sayfalardan birini ziyaret et:

* [https://pancakeswap.finance/cake-staking](https://pancakeswap.finance/cake-staking)
* [https://pancakeswap.finance/gauge-voting](https://pancakeswap.finance/gauge-voting)
* [https://pancakeswap.finance/pools](https://pancakeswap.finance/pools)

Bir istem görünmeli. "Beyaz Listeye Ekle"ye tıkla ve çoklu imza cüzdanında işlemi gerçekleştir.

veCAKE'in sahibine bir işlem gönderilecek; bu sahip, herhangi bir sözleşmenin kendi kendini beyaz listeye eklemesine izin veren izinsiz bir yazma fonksiyonuna sahip bir sözleşmedir.

İstem görünmezse [BscScan](https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11) üzerinden işlemi yürütmek için şu talimatları izle:

```
// çağır:
VECakeOwner.setWhitelist(bool _status = true)

// VECakeOwner adresi:
https://bscscan.com/address/0xe6cdC66A96458FbF11F632B50964153fBDa78548#writeContract#F11
```

#### Neden birden fazla APR var?

CAKE'i kilitleyerek veCAKE almak, PancakeSwap tarafından inşa edilen ürün paketinde bir dizi harika avantaj sağlar. Avantajlar ve teşvikler farklı biçimlerde ve farklı kaynaklardan gelir. Bu nedenle birden fazla APR vardır.

Hepsini eş zamanlı olarak kazanabilirsin; dolayısıyla birleşik APR tüm APR'lerin toplamı olacak.

veCAKE'den elde edilen pek çok başka avantajın [Farm Getiri Güçlendirici bCAKE](../../../welcome-to-pancakeswap/vecake-sunset/bcake/) veya [IFO iCAKE](../../../welcome-to-pancakeswap/vecake-sunset/icake.md) gibi APR formatında ölçülemeyen avantajlar da olduğunu unutma. Bunlara da mutlaka göz at.

#### veCAKE Havuzu APR'si nedir?

Bu, oranı veCAKE Havuzu oylama göstergesi tarafından kontrol edilen CAKE emisyonlarından gelen teşviktir.

Bu göstergeye yapılan emisyonu artırmak için [Gösterge Oylama](../../../welcome-to-pancakeswap/vecake-sunset/gauges-voting/)'ya göz at.

#### Gelir Paylaşımı APR'si nedir?

Bu, DEX ürünlerinde toplanan swap ücretlerinden gelen protokol geliri paylaşımından elde edilen teşviktir.

Daha fazla bilgi için [Gelir Paylaşımı](/broken/pages/wQegezs7c6A2HzQjPEjh)'na göz at.
