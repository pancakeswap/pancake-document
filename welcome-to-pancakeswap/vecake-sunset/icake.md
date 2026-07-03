---
description: veCAKE Staking ve IFO Tahsisleri
hidden: true
---

# iCAKE

### **Yeni iCAKE nedir?**

veCAKE'e geçişin ardından yeni iCAKE, veCAKE bakiyesine dayalı olacak

* Eski iCAKE gibi, PancakeSwap IFO halka açık satışlarındaki maksimum CAKE taahhüt limitini belirler. Örneğin 200 iCAKE'in varsa IFO halka açık satışlarına 200 CAKE taahhüt edebilirsin.
* Yeni iCAKE sayısı, her IFO'nun sonundaki veCAKE bakiyesi kullanılarak hesaplanır. Bu nedenle her IFO için farklı iCAKE sayına sahip olacaksın.
* veCAKE bakiyesi kalan kilit sürenle birlikte kademeli olarak azaldığından gelecekteki IFO'lardaki iCAKE'in de veCAKE bakiyenle birlikte azalacak. iCAKE sayını korumak için stake'e daha fazla CAKE ekle ya da kilitini yenile/uzat.

**iCAKE yeni bir token DEĞİLDİR; PancakeSwap IFO sistemi tarafından kullanılan sayısal bir metriktir.**

### iCAKE nasıl hesaplanır?

Sahip olduğun iCAKE sayısı, her IFO'nun sonundaki veCAKE bakiyesine önceden tanımlanmış bir oran uygulanarak hesaplanır.

veCAKE, kilitlediğin CAKE miktarına ve kilitte kalan süreye göre dinamik olarak hesaplanan bir değerdir. veCAKE'in nasıl hesaplandığı hakkında daha fazla bilgi edinmek için [buraya](https://docs.pancakeswap.finance/products/vecake/faq#52f27118-bbf3-448b-9ffe-e9e1a9dd97ef) bak.

veCAKE bakiyesinin üzerine ek bir oran uygulanır; bu oran mutfak tarafından her IFO için ayarlanır. Örneğin oran 2x ise ve bir sonraki IFO'nun sonunda 1 veCAKE'in varsa 2 CAKE'e kadar taahhüt edebilirsin.

Örnek:

* 100 CAKE'i 2 yıl için kilitledin.
  * Kalan kilit süren: `2 * 52 * 7 * 24 * 60 * 60 = 62899200` (saniye)
  * Maksimum kilit süresi: `(209 * 7 * 24 * 60 * 60) - 1 = 126403199` (saniye)
  * Şu an: `100 * (62899200 / 126403199) ~= 49,76` veCAKE'e sahipsin
* Bir sonraki IFO planlandı; bitiş zamanı tam olarak 1 hafta sonra, yani mevcut andan `604800` saniye sonra.
  * O zaman kalan kilit süren: `62899200 - 604800 = 62294400` (saniye)
  * O zaman: `100 * (62294400 / 126403199) ~= 49,28` veCAKE'e sahip olacaksın
* Bu IFO için oran `3x` olarak belirlendi
* Bu nedenle bu IFO için: `49,28 * 3 = 147,84` iCAKE'e sahipsin; bu da halka açık satışta 147,84 CAKE'e kadar taahhüt edebileceğin anlamına gelir.

### Kaç iCAKE'im olduğunu nasıl kontrol ederim?

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29.png" alt="" width="375"><figcaption></figcaption></figure>

iCAKE sayını [buradan](https://pancakeswap.finance/ifo) IFO sayfasında kontrol edebilirsin.

Yaklaşan bir IFO olmadığında iCAKE'in, saniye saniye kademeli olarak azalan gerçek zamanlı veCAKE bakiyesi kullanılarak hesaplanacağını unutma.

Yaklaşan bir IFO olduğunda iCAKE'in, anlık görüntü zamanındaki, yani IFO'nun sonu olan veCAKE bakiyesi kullanılarak hesaplanacak. IFO sona erene kadar iCAKE'in azalmayacak veya değişmeyecek.

### **iCAKE sayımı nasıl artırabilirim?**

iCAKE sayını istediğin zaman artırabilirsin:

* veCAKE staking pozisyonuna daha fazla CAKE ekleyerek.
* veCAKE staking pozisyonunu uzatarak.

[CAKE Staking Sayfasında](https://pancakeswap.finance/cake-staking)

### iCAKE hesaplamasındaki "Oran" nedir?

Oran, iCAKE hesaplanırken veCAKE bakiyesinin üzerine uygulanan ek bir kontrol faktörüdür.

Örneğin oran 2x ise ve bir sonraki IFO'nun sonunda 1 veCAKE'in varsa 2 CAKE'e kadar taahhüt edebilirsin.

Her IFO arasında mutfak ekibi "Oran"ı çeşitli metriklere göre optimize edecek. Yapılan ayarlama tüm sosyal medya kanallarında duyurulacak.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2810%29.png" alt="" width="375"><figcaption></figcaption></figure>

iCAKE hesaplamaları için mevcut "Oran" sayısını [IFO sayfasına](https://pancakeswap.finance/ifo) giderek kontrol edebilirsin.
