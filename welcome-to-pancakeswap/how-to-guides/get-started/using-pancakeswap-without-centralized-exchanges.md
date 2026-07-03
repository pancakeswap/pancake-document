---
description: >-
  PancakeSwap'ı kullanmaya başlamak için Binance, Coinbase, Kraken, Huobi, OKEx
  veya başka herhangi bir merkezi borsada hesap açmana gerek yok!
hidden: true
---

# Merkezi Borsalar Olmadan PancakeSwap Kullanma

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-pancakeswap-without-cex-header.png)

PancakeSwap merkezi olmayan bir uygulamadır. Bu, Binance veya diğer merkezi platformların aksine kullanabilmek için hesap oluşturmana gerek olmadığı anlamına gelir... tek ihtiyacın bir kripto cüzdanı. Peki merkezi bir borsa kullanmadan PancakeSwap'a kripto nasıl getirebilirsin?

Bu rehberde, varlıklarını BNB Smart Chain cüzdanına aktarmak ve PancakeSwap kullanmaya başlamak için "cross-chain bridge" kullanma sürecinde sana rehberlik edeceğiz.

### **Varlıklarını diğer blok zincirlerinden BNB Smart Chain'e taşı**

Ethereum veya diğer ağlardan BNB Smart Chain'e token aktarmak için çeşitli cross-chain bridge'ler kullanabilirsin.

Aşağıdaki rehberlerde, üç farklı cross-chain bridge kullanarak çeşitli blok zincirlerinden BNB Smart Chain'e USDT aktarımını göstereceğiz.

{% tabs %}
{% tab title="🥞🌉 Pancake Bridge (önerilen)" %}
![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28168%29.png)

[**PancakeSwap Bridge**](http://bridge.pancakeswap.finance) — Stargate tarafından desteklenen yerel varlık cross-chain bridge'i.

Bu bridge, stabilcoinlerini sorunsuz şekilde BNB Chain'e taşımanı ve canlı PancakeSwap Topluluğu ile daha geniş BNB Ekosistemine katılmanı sağlıyor!

📖 [Nasıl kullanılacağını öğren](https://medium.com/pancakeswap/launching-pancakeswap-bridge-a-partnership-with-stargate-21c1c9f491a8)
{% endtab %}

{% tab title="AnySwap" %}
AnySwap kullanarak USDT'yi Polygon (MATIC) blok zincirinden BSC'ye taşımayı deneyelim.

1. Polygon (MATIC) cüzdanını USDT ve gas için biraz MATIC ile hazırla.
2. AnySwap yalnızca MetaMask, OKEx Wallet ve Coin98 Wallet'ı desteklediğinden, başka bir cüzdan uygulaması kullanıyorsan cüzdanını MetaMask'a aktarmanı öneririz.
3. [https://anyswap.exchange/#/router](https://anyswap.exchange/#/router) adresine git
4. Cüzdanını bağla ve ağını Polygon (MATIC) Mainnet olarak değiştir.
5.  "From" olarak MATIC mainnet'teki USDT'yi, "To" olarak BSC mainnet'teki USDT'yi seç. Ardından aktarmak istediğin USDT miktarını gir.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-055554AM-Google%20Chrome_AnySwap%20-%20Cross%20Chain%20Protocol.png" alt="" data-size="original">
6. USDT'ni onaylamak için "Approve USDT"ye tıkla.
7. AnySwap'ın USDT'ni başka bir BSC adresine yatırmasını istiyorsan "+ Send To" butonunu kullan.
8. "Swap"e tıkla ve son cross-chain işlemlerini tamamla.
9. Ağın ne kadar yoğun olduğuna bağlı olarak tüm süreç yaklaşık 10-30 dakika sürecek.
10. Tamamlandığında BSC cüzdanında fonlarını almalısın. Artık BNB Smart Chain'de bazı token'ları Swap etmek için PancakeSwap kullanmaya başlayabilirsin!
{% endtab %}

{% tab title="O3 Hub" %}
⚠️ **O3 Swap beta aşamasındadır. Lütfen kendi riskinizi göz önünde bulundurarak işlem yapın.**

USDT'yi ERC-20 blok zincirinden BNB Smart Chain'e taşımak için O3 Hub'ı kullanmayı deneyelim.

1. ERC-20 (Ethereum Mainnet) cüzdanını USDT ve gas için biraz ETH ile hazırla.
2. O3 Hub yalnızca MetaMask ve O3 Wallet'ı desteklediğinden, başka bir cüzdan uygulaması kullanıyorsan cüzdanını MetaMask'a aktarmanı öneririz.
3. [https://o3swap.com/hub](https://o3swap.com/hub) adresine git
4.  Hem ETH hem de BSC için MetaMask veya O3 cüzdanını bağla. MetaMask'taki ağını Ethereum Mainnet olarak değiştir.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-054852AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
5.  "You pay" olarak ERC-20 USDT'yi, "You will receive" olarak BEP-20 USDT'yi seç. Ardından aktarmak istediğin USDT miktarını gir.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-053358AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
6.  "To" alanının bağlandığın doğru BNB Smart Chain cüzdan adresini gösterdiğini iki kez kontrol et.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-053441AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
7. Her şeyin doğru olduğundan emin ol. "Swap"e tıkla.
8. USDT'ni onaylamak ve son cross-chain işlemini tamamlamak için ekrandaki talimatları takip et.
9.  Ağın ne kadar yoğun olduğuna bağlı olarak tüm süreç yaklaşık 10-30 dakika sürecek. Geçmişe ilişkin sekme üzerinden ilerlemeyi takip edebilirsin.

    <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/MBP3-2021.10.19-054520AM-Google%20Chrome_O3swap.png" alt="" data-size="original">
10. Tamamlandığında BSC cüzdanında fonlarını almalısın. Artık BNB Smart Chain'de bazı token'ları Swap etmek için PancakeSwap kullanmaya başlayabilirsin!

Ayrıca O3 Swap'ın [bu kullanıcı rehberine](https://docs.o3swap.com/o3-swap-user-guide/hub#2.-hub-swap) de göz atabilirsin.
{% endtab %}
{% endtabs %}
