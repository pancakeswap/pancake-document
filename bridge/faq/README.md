# ❓ Bridge SSS

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28144%29.png" alt=""><figcaption></figcaption></figure>

## Bridge Yapmadan Önce

1.  **CAKE Bridge etmek için mobil cüzdanlar veya MetaMask dışındaki cüzdanlar kullanılabilir mi?**

    Şu anda PancakeSwap CAKE Bridging; Coinbase Wallet, MetaMask ve MetaMask uyumlu cüzdanları desteklemektedir. Daha fazla cüzdan desteği yakında gelecektir.

    _İpucu:_ Özel anahtar veya tohum ifadesi kopyalama/yapıştırmanın risklerini önlemek için Bridge işlemleri için masaüstü cüzdan uzantıları aracılığıyla yeni cüzdanlar oluşturmanı öneririz.
2.  **Neden bir rota veya token kullanılamıyor?**

    Bazı rotalar Bridge kapasitesine, token desteğine veya likit durumuna bağlıdır. Lütfen daha sonra tekrar dene ya da farklı bir sağlayıcı dene. Zincir başına mevcut token'lar doğrudan Bridge arayüzünde gösterilir.
3.  **Bridge işlemini gönderirken hata alıyorum.**

    "MAX" butonu yerine miktarı manuel olarak girmeyi dene; gerekirse miktardaki ondalık basamakları kaldır.
4.  **Bridge teklifimde neden "X'i yerel ücreti karşılamaya yetmiyor" yazıyor?**

    ![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%289%29%20%283%29.png)

    Bridge işlemi, kaynak zincirin yerel token'ında ödenen gas ücretleri gerektirir. Örneğin:

    * BNB Chain → BNB
    * Ethereum → ETH
    * Aptos → APT

    İşlemi tamamlamak için gereken ücretleri karşılamak amacıyla kaynak cüzdanında yeterli yerel token bulunduğundan emin ol.
5.  **Buton neden "X CAKE Aşıldı" gösteriyor?**

    Güvenliği sağlamak amacıyla BSC ile Aptos arasında CAKE Bridge etmek için günlük kapasite sınırı bulunmaktadır. Daha küçük bir miktar dene ya da bekleyip daha sonra tekrar dene. Sınırlar, talebe göre Chefs tarafından dinamik olarak ayarlanır.
6.  **Neden belirli bir token'ı bulamıyorum?**

    Token, seçilen rotada desteklenmeyebilir veya likidite eksikliği yaşıyor olabilir. Başka bir zincir veya farklı bir miktar dene.
7.  **BNB Chain'den Ethereum'a farklı bir adrese Bridge yapabilir miyim?**

    Hayır, güvenlik nedeniyle Bridge işlemi yalnızca EVM zincirlerde aynı adresler arasında çalışmaktadır.
8.  **Neden 0,00000001 CAKE'ten az Bridge edemiyorum?**

    Aptos'taki CAKE dahil Aptos token'larının maksimum 8 ondalık basamağı vardır. 0,00000001'in altındaki işlemler reddedilecek veya aşağı yuvarlanacaktır. Bu durum Ethereum Bridge işlemleri için de geçerlidir. Kalan miktar kaynak cüzdanında kalır.

***

## Bridge Sonrası

1.  **Onayladıktan sonra Bridge transferini iptal edebilir miyim?**

    Hayır, başlatıldıktan sonra Bridge işlemi sağlayıcı tarafından yürütülür ve iptal edilemez. Geri almak için varlıkları yeni bir işlemle Bridge et.
2.  **İşlemim "beklemede" takılı kalırsa ne olur?**

    Bridge işlemi 30 dakikaya kadar sürebilir. İşlem durumunu ilgili Bridge sağlayıcısının gezgininde hash'ini aratarak kontrol et:

    * Debridge: [https://app.debridge.finance/orders](https://app.debridge.finance/orders)
    * LayerZero Scan: [https://layerzeroscan.com/](https://layerzeroscan.com/)
    * Stargate Explorer: [https://stargate.finance/](https://stargate.finance/)
    * cBridge: [https://celerscan.com/](https://celerscan.com/)

    60 dakika sonra hâlâ beklemedeyse [sosyal kanallarımız](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) aracılığıyla yöneticilerimizle iletişime geç.
3. **CAKE'imi almadım. Ne yapmalıyım?**
   * CAKE'i Aptos'a ilk kez Bridge ederken CAKE'ini **manuel olarak talep etmen** gerekebilir. Aptos cüzdanında gas için yeterli APT olduğundan emin ol. [Aptos Bridge kılavuzuna](https://docs.pancakeswap.finance/bridge/bridging/aptos) ve [Aptos açıklamasına](https://theaptosbridge.com/faq#registering-claiming-assets) bak.
   * BNB Chain veya Ethereum'a Bridge ederken bazı cüzdanlar bakiyeni görüntülemek için CAKE'in token adresini manuel olarak eklenmeni gerektirebilir. Örnek olarak bu [MetaMask kılavuzunu](https://support.metamask.io/manage-crypto/tokens/how-to-display-tokens-in-metamask/) takip et; diğer cüzdanlarda benzer adımlar uygulanabilir.
   * 60 dakika sonra hâlâ CAKE'ini göremiyorsan [sosyal kanallarımız](https://docs.pancakeswap.finance/welcome-to-pancakeswap/contact-us/social-accounts) aracılığıyla yöneticilerimizle iletişime geç.
