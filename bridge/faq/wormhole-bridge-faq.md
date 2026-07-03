---
hidden: true
---

# Wormhole Bridge SSS

### S: İşlemimi nasıl kontrol edebilirim? <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

#### Wormhole gezgini

Bridge durum sayfasında, işlemini Wormhole Gezgini'nde görüntülemeni sağlayacak bir bağlantı göreceksin. Kaynak zincir işlemin tamamlandığı ancak Wormhole tarafından henüz doğrulanmadığı durumlarda işlem durumun şöyle görünecektir:

<figure><img src="https://lh7-us.googleusercontent.com/yORDYXyM5E3AL_vFxZZ1Q5qeHv59yDodX5sFz2LNxLmjcBEYLJva6KaHacpuc2VPdccB7GjUflXRcus4l6gh7HD1Y6x0S6GU1xX03Z-9E9xA6JDFSnNgeErRHSF2wV_98qqyrgAL8p_9EBgXWKXRZU" alt=""><figcaption></figcaption></figure>

"Redeem bul" seçeneği, hedef zincir işlemini tamamlamak için takip edebileceğin alternatif bir yöntemdir. Wormhole Bridge'in durduğu veya Bridge işleminin durumunu güncellemekte başarısız olduğu durumlarda bu yöntemi kullanabilirsin. İşlemini talep etmek için önce talep butonuna tıkla.

<figure><img src="https://lh7-us.googleusercontent.com/DJTsB2sz0KxIuhUfFbqbb01acekDiLJzEVws1pYWfiNGFRaFnQa0lCW8Wv4L-W7GBdYBvDIB7wUgkFF7tk8zrVCS1EuarMROR0bECQS2NHqMiGpcMrVfaVWGGqJPJXZmOxQIPUcjceDgE8WUk9wJviQ" alt=""><figcaption></figcaption></figure>

Ardından işlemini devam ettirme seçeneği gösterilecektir. Talep işlemini tamamlayabileceğin foruma (bağlantı bir sonraki soruda) yönlendirilmek için buna tıkla. <br>

### S: \<zincir>'e token gönderdim - tokenlarım hedef cüzdanıma ulaşmadı ama kaynak cüzdanımdan çıktı. Ne yapmalıyım?[​](https://portalbridge.com/docs/faqs/troubleshooting#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-wallet-what-do-i-do) <a href="#i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w" id="i-have-sent-tokens-to-chain---my-tokens-did-not-arrive-in-my-target-wallet-but-have-left-my-origin-w"></a>

Ya a) bunları talep etmen gerekiyor, ya da talep işlemi zaten başarılıysa b) cüzdanına eklemen gerekiyor:

**a) Talep etme:**

* [https://portalbridge.com/#/redeem](https://portalbridge.com/#/redeem) adresine git
* Kaynak zincirini ve ilgili işlem kimliğini (cüzdanında veya blokzincir gezgininde adresinle bulabilirsin) girmen gerekiyor

<figure><img src="https://lh7-us.googleusercontent.com/v4gdm8TKNfhuq8cRaHWwn-EuJKCuzWSXl5zt76DDHq3N6TBqP-ntLVZNS5CMbIUBvtE2qI2eCpw_ean4hSicvrLCYhlz8TI5WxgzN3zBpo2wqInZvYuaXCcxU3k6nF6l-On05Ak4vjdZPLhJcQZXybc" alt=""><figcaption></figcaption></figure>

* Recover'a tıkla
* Redeem'e tıkla ve cüzdan onayını kabul et

**b) Cüzdanına ekleme:**

**Metamask:**[**​**](https://portalbridge.com/docs/faqs/troubleshooting#metamask)

* Metamask varlıklar sekmesinde token'ları içe aktar'a tıkla
* Sözleşme adresi, ilgili blok gezgini işleminde ve token adına tıklanarak bulunabilir. Token adına tıkladığında yeni bir pencere açılacak ve sözleşme adresi profil özetinde sağ tarafta yer alacaktır.
* Ayrıca bir sembol gerekiyor - token'ı tanımak için istediğin herhangi bir şey olabilir.
* Özel token ekle'ye tıkla

Video eğitimini buradan izle - Metamask cüzdanına token nasıl eklenir [buraya bakabilirsin.](https://portalbridge.com/docs/video-tutorials/how-to-manually-add-tokens-to-your-wallet#metamask)

### X token'ını Bridge ettim ama şimdi takas edemiyorum. Hiçbir DEX'te likit piyasa yok,[​](https://portalbridge.com/docs/faqs/troubleshooting#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets) <a href="#i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets" id="i-bridged-x-token-but-cannot-swap-it-now-no-dex-has-liquid-markets"></a>

Hedef zincirde likiditesi olmayan bir token Bridge ettin. Bunu geri Bridge etmek için Portal Bridge kullanman gerekecektir. Bunu, token sözleşme adresini (cüzdanında veya blokzincir gezgininde adresinle bulabilirsin) Portal "token seç" arama alanına yapıştırarak yapabilirsin.

Likit piyasalara kapsamlı bir genel bakışı [buradan](https://portalbridge.com/docs/faqs/liquid-markets) bulabilirsin.

#### Hedef zincirde tokenlarımı nasıl talep edebilirim?[​](https://portalbridge.com/docs/faqs/troubleshooting#how-can-i-redeem-my-tokens-on-the-target-chain) <a href="#how-can-i-redeem-my-tokens-on-the-target-chain" id="how-can-i-redeem-my-tokens-on-the-target-chain"></a>

Transfer sürecinde sayfayı yanlışlıkla yenilediysen veya tokenlarını talep etmediysen, [buradaki](https://portalbridge.com/docs/tutorials/how-to-use-recovery-workflow) eğitimi takip edebilirsin.
