---
description: EVM zincirleri ile Aptos arasında CAKE Bridge et
---

# Nasıl Bridge Yapılır - EVM <> Aptos

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28113%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Aşağıdaki kılavuzda örnek olarak BNB Chain kullanılmıştır. Aynı süreç Ethereum için de geçerlidir.
{% endhint %}

## BNB Smart Chain'den Aptos'a CAKE Bridge Et

1 - Cüzdanının hem BNB Smart Chain hem de Aptos Mainnet'i desteklediğinden emin ol. Ya da tarayıcında her iki cüzdanın da yüklü olduğunu kontrol et.

Ardından [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/) sayfasını aç.

2 - Önce BNB Smart Chain cüzdanımızı bağlamamız gerekiyor.

"Connect" butonuna tıkla ve "EVM" bölümünden tercih ettiğin cüzdanı seç. Ardından cüzdan açılır penceresinde onayla ve onayla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Ardından Aptos cüzdanımızı bağlamamız gerekiyor.

Cüzdan bağlantı penceresinde "Aptos" bölümünden tercih ettiğin cüzdanı seç. Ardından cüzdan açılır penceresinde onayla ve kabul et.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Üstteki token seçim alanındaki "v" simgesine tıkla ve "CAKE" seç.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field.png)

5 - Aptos'a Bridge etmek istediğin CAKE miktarını gir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-amount-entered.png)

6 - Aptos cüzdanın yeni oluşturulmuşsa ve hiç APT (Aptos Coin) bakiyesi yoksa, "hedef zincirdeki gas" seçeneğini varsayılan ayarında bırakmانی öneriyoruz. Bridge, cüzdanına küçük miktarda APT yatıracaktır; bu hem Aptos yolculuğuna başlamanı kolaylaştırır hem de Bridge edilmiş CAKE'ini kayıt ettirip talep etmen için APT'e ihtiyacın olacaktır.

Bu seçeneği değiştirmek Bridge işleminin başarısız olmasına neden olabilir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-gas-on-dest.png)

7 - Bridge işlemini başlatmak için "Transfer"e tıkla ve cüzdan onay açılır penceresinden işlemi onayla.

Lütfen dikkat: BNB Smart Chain cüzdanının ve Aptos cüzdanının durumuna bağlı olarak **birden fazla** cüzdan onayı gerekebilir. Örneğin CAKE'i Aptos'a ilk kez Bridge ediyorsan şunları yapman gerekecek:

* Bridge sözleşmesinde CAKE harcamasını onayla (BNB Smart Chain cüzdanından)
* CAKE'i kayıt ettir (Aptos cüzdanından)

Daha fazla ayrıntı için [bu açıklamaya](aptos.md#bridging-cake-to-aptos-for-the-first-time) göz at.

8 - Arkanı yasla ve rahatlا. Yalnızca birkaç dakika sürmesi gerekir. Bridge işlemi tamamlandığında CAKE, Aptos cüzdanına yatırılacaktır. İlerlemeyi ilerleme çubuğuyla takip edebilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-complete-half.png)

## CAKE'i Aptos'a İlk Kez Bridge Etmek

CAKE'i Aptos cüzdanlarına Bridge etmek kayıt ve talep işlemlerini gerektirir. Bu, kullanıcı güvenliğini artırmak amacıyla uygulanmakta olup Aptos'a özgü bir durumdur.

### **Cüzdanında zaten APT (Aptos Coin) varsa:**

Henüz kayıtlı değilse Aptos cüzdanında CAKE'i kayıt ettirmen istenecektir. Bu durumda ek bir talep işlemine gerek yoktur.

### **Cüzdanında APT (Aptos Coin) yoksa:**

Bridge işlemi tamamlandıktan sonra CAKE'ini manuel olarak talep etmen gerekecektir. Talep için gereken gas ücretlerini karşılamak amacıyla kaynak cüzdanından Aptos cüzdanına APT token'ları gönderilecektir.

Bu kayıt ve talep adımları yalnızca Aptos'ta bir token'la ilk kez etkileşime girdiğinde uygulanır. Aynı token'ın sonraki transferlerinde bu işlemler gerekmez.

CAKE'i Aptos'a ilk kez Bridge etmeden önce Aptos adresinde gas ücretleri için yeterli APT olduğundan emin ol. Daha fazla bilgi için Aptos'un açıklamasına göz at: [https://theaptosbridge.com/faq#registering-claiming-assets](https://theaptosbridge.com/faq#registering-claiming-assets)

## Aptos'tan BNB Smart Chain'e CAKE Bridge Et

1 - Cüzdanının hem BNB Smart Chain hem de Aptos Mainnet'i desteklediğinden emin ol. Ya da tarayıcında her iki cüzdanın da yüklü olduğunu kontrol et.

Ardından [PancakeSwap CAKE Bridge](https://bridge.pancakeswap.finance/) sayfasını aç.

2 - Önce BNB Smart Chain cüzdanımızı bağlamamız gerekiyor.

"Connect" butonuna tıkla ve "EVM" bölümünden tercih ettiğin cüzdanı seç. Ardından cüzdan açılır penceresinde onayla ve kabul et.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-wallet-connect-modal.png)

3 - Ardından Aptos cüzdanımızı bağlamamız gerekiyor.

Cüzdan bağlantı penceresinde "Aptos" bölümünden tercih ettiğin cüzdanı seç. Ardından cüzdan açılır penceresinde onayla ve kabul et.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-default-state.png)

4 - Üstteki token seçim alanındaki "v" simgesine tıkla ve "CAKE" seç. Ardından Bridge yönünü tersine çevirmek için sayfanın ortasındaki çift ok butonuna tıkla.

Üst alanda "Aptos" ağının yer aldığından emin ol.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/upper-field-aptos.png)

5 - BNB Smart Chain'e Bridge etmek istediğin CAKE miktarını gir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/bridging-aptos-to-bsc-with-amount.png)

6 - BNB Smart Chain cüzdanın yeni oluşturulmuşsa ve hiç BNB (gas token) bakiyesi yoksa, "hedef zincirdeki gas" seçeneğini varsayılan ayarında bırakmانی öneriyoruz. Bridge, cüzdanına küçük miktarda BNB yatıracaktır. Bu, BNB Smart Chain'deki yolculuğuna başlamanı ve canlı PancakeSwap ekosistemini keşfetmeni kolaylaştıracaktır.

7 - "Transfer"e tıkla ve cüzdan açılır penceresinden işlemleri onayla.

8 - Arkanı yasla ve rahatla. Yalnızca birkaç dakika sürmesi gerekir. Bridge işlemi tamamlandığında CAKE, BNB Smart Chain cüzdanına yatırılacaktır. İlerlemeyi ilerleme çubuğuyla takip edebilirsin.
