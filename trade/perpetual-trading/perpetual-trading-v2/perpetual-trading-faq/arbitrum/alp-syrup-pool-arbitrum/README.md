# ALP Syrup Pool (Arbitrum)

ALP, PancakeSwap Perpetuals V2'de likiditeyi destekleyen bir tokendir. Kullanıcılar, USDC, USDT, DAI, ETH ve BTC gibi teminat tokenları kullanarak ALP mint'ler/satın alır. Bu tokenlar, ApolloX tarafından desteklenen PancakeSwap Perpetuals işlem motoruna likidite sağlar. ALP tokenları **cüzdanlar arasında transfer edilemez** ve yalnızca **ALP sözleşmesi aracılığıyla mint'lenebilir/satılabilir ve ALP havuzunda stake edilebilir**.

### Adım Adım Rehber

#### ALP Satın Alma/Mint'leme

1. [PancakeSwap ALP Havuzu (V2)](https://perp.pancakeswap.finance/en/ALP) sayfasına gitmek için tıkla ve cüzdanını bağla
2. Cüzdanını bağladıktan sonra **ALP Satın Al**'a tıkla. ALP satın almak için herhangi bir ALP havuzu varlığını kullanabilirsin.
3. Bilgileri onayladıktan sonra işlemi tamamlamak için **ALP Satın Al**'a tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Buy%20ALP%20Module.png" alt=""><figcaption></figcaption></figure>

**ALP Stake Etme (Arbitrum)**

1. Pancake ALP Pano Sayfasında **Şimdi Stake Et**'e tıkla veya [buraya](https://pancakeswap.finance/pools?chain=arb) tıkla

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/png%20%284%29.png" alt=""><figcaption></figcaption></figure>

2. CAKE-ALP Syrup Pool'u seç
3. ALP'yi **Etkinleştir** ve **Stake Et**'e tıkla
4. Stake edilecek ALP miktarını seç ve **onayla**'ya tıkla

**ALP Satma**

1. &#x20;ALP Havuzu (V2) sayfasına gitmek için tıkla ve cüzdanını bağla
2. Cüzdanını bağladıktan sonra **ALP Sat**'a tıkla.

ALP Satış Koşulları:

* &#x20;Kullanıcı, satın alma tarihinden itibaren 48 saat sonra ALP satabilir
* &#x20;Satılabilecek ALP token miktarı: min\[(Likidite havuzunun değeri - Kullanıcının pozisyonlarının değeri)\*%50]/ALP Piyasa Fiyatı. Örneğin, likidite havuzunun değeri 10.000.000 USDT, kullanıcının pozisyonunun değeri 5.000.000 USDT ve ALP Piyasa Fiyatı 2 USDT ise, ALP kullanıcısının satabileceği maksimum miktar 1.250.000 olur.&#x20;
* Aynı zamanda, kullanıcıların ALP tokenlarını sattıktan sonra aldıkları varlık miktarı ALP likidite havuzunu aşamaz. Örneğin, likidite havuzunda yalnızca 1000 USDT varsa, kullanıcıların alacağı maksimum USDT miktarı 1000 USDT olacak ve kalan ALP'ler diğer kripto paralar için satılabilecektir.
