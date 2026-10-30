---
description: '2026-08-21'
---

# Shared Inventory Hook'a Giriş

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2816%29.png" alt=""><figcaption></figcaption></figure>

Beş pariteyi fiyatlamak, beş kat sermayeye mal olmamalı. Ama onchain'de her varlık ihraççısının karşılaştığı durum tam olarak bu: likidite her pariteye bağlı olduğu için her yeni parite, bir sermaye parçası daha koymak demek - çoğu da o parite tam olarak o fiyat aralığında işlem görene kadar hiçbir şey kazanmadan öylece bekliyor. Yeni bir pariteyi fiyatlamak istediğin her seferinde ona yeni sermaye LP olarak sağlıyorsun — bu sermaye de o tek pariteye kilitleniyor ve başka hiçbir yerde kullanılamıyor.

Shared Inventory Hook (SIH) bu bağı koparır. PancakeSwap Infinity'nin en yeni hook'u — ve sermaye verimliliği için geliştirilen ilk hook.

_💡 Hatırlatma: Hook, bir Infinity havuzuna bağlanan ve swap sırasında özel mantık çalıştıran bir akıllı kontrattır (eklenti gibi) — yeni bir platform kurmaya gerek yok._

Peki nasıl çalışıyor?

Her havuzda ayrı bir yığın kilitlemek yerine, bir RWA varlık ihraççısı **tek bir ortak envanteri** fonlar ve shared inventory hook, işlem gören hangi pariteyse ona bu envanterden derinlik sunar — tam swap gerçekleştiği anda, just-in-time. Mutfaktaki her yemeğe tek bir erzak odasının yetmesi gibi düşün; her biri için ayrı bir erzak odasına gerek yok. Tek bir bakiye, birçoğunun işini yapar.

SIH'i sermaye açısından verimli kılan bu tek değişiklik, üç şekilde kendini gösterir:

* **Sermaye aktif kalır ve çalışır.** Hook envanterindeki likidite swap anında just-in-time enjekte edilir; böylece boşta beklemek yerine aktif çalışır ve sana ücret kazandırır.
* **Tek bir bakiyeden, birden çok pariteden ücret fırsatı.** Tek bir envanter, hizmet verdiği tüm paritelerde kazanç sağlar; böylece çok daha az sermaye ile ücret akışını yakalarsın.
* **Daha düşük fiyat etkisi.** Swap anında fiyatlanan likidite daha derin olduğundan, SIH en iyi fiyatı sunduğunda büyük işlemler daha düşük fiyat etkisi görür.
* **Artan sermaye verimliliği.** Bir kez fonla; aynı sermaye, SIH etkin her paritede derinliği destekler. Ayrıca yeni bir parite için sermaye eklemeden SIH'i etkinleştirebilirsin.

> \*\*Zaten ikna oldun mu? Varlıklarını sermaye verimli şekilde onchain'e taşı — bu formu doldur → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

**Kanıt onchain'de**

SIH bu Ağustos'ta bStocks ile canlıya çıktı ve en önemli rakam, bu sermayenin ne kadar sıkı çalıştığı. Son hook anlık görüntüsünde (21 Ağu 2026), ortak envanterin %75'i üç pariteye aktif olarak dağıtılmış durumda (hook envanteri \~297 bin $, aktif \~224 bin $). Olgunlaşmış iki parite olan CRCLB ve MUB'da kullanım oranı \~%99 (%98,96 / %98,95). Geleneksel V3 CLAMM havuzlarında boşta duracak sermaye burada aralık içinde ve fiyatlıyor.

İlk haftalarında (21 Ağu'ya kadar) üç parite, \~297 bin $'lık ortak envanterden hizmet alarak 5.713 swap'ta \~710 bin $ işlem gördü ve %0,25'lik ücret kademesinde LP ücreti kazandı.

_**Kaynaklar:** Dahili Dune Dashboard_ **Canlı havuzlar:** [CRCLB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x311af0ed06dd701fddc4e7c6a74023dd0cf866ee9635788425fb0eff9c4c5d13) · [MUB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x772906e0ff95e562c34151e17c03666d5623146389f53706aeb11d9570d93640) · [GMEB/USDT](https://pancakeswap.finance/liquidity/pool/bsc/0x852edfc1051132f9d42e045a7e2501e6f8510d36f8c8c13b24ff32bdad395ddb)

**Bu nereye gidiyor**

Model ölçeklenecek şekilde tasarlandı — daha fazla parite, 7/24 işlem gören binlerce piyasaya yayılan tek bir ortak bakiye. Bir tokenın tüm parite yelpazesini, arkasındaki sermayeyi katlamadan onchain'e taşımanın gördüğümüz en hızlı yolu bu.

Canlı SIH havuzları [PancakeSwap Earn sayfasında](https://pancakeswap.finance/liquidity/pools?chain=bsc\&type=1\&network=56\&network=1\&network=8453\&network=143\&network=4663\&network=42161\&network=324\&network=59144\&network=204\&network=8000001001) yer alıyor — **Infinity**'yi aç ve havuz özellikleri altında **Shared Inventory**'yi ara. SIH şu anda CRCLB / USDT, MUB / USDT ve GMEB / USDT'de etkin.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28157%29.png" alt=""><figcaption></figcaption></figure>

_Not: Bireysel LP'ler bu havuzlara Earn üzerinden şimdiden likidite ekleyebilir — bu mevduat, ortak envanterden ayrı tutulan kalıcı havuz likiditesi olur._

_**Önemli:**_

_SIH, envanter yalnızca swap anında devreye alındığı için standart bir LP pozisyonuna göre fiyat kaymasına daha az maruz kalır. Risksiz değildir. Operatör hâlâ piyasayla birlikte hareket eden envanter tutar. Her onchain stratejide olduğu gibi sonuçlar hacme, envantere, hedge'e ve piyasa koşullarına bağlıdır._

Sermaye verimliliğini en üst düzeye çıkarmaya hazır mısın? Token paritelerinde SIH'i hemen etkinleştir → [https://forms.gle/LV24KsoDfJdu2RQU9](https://forms.gle/LV24KsoDfJdu2RQU9)

Stack'em, The Chefs 🥞

***

_Sorumluluk reddi: Bu içerik yalnızca genel bilgilendirme ve eğitim amaçlıdır. Finansal, hukuki veya başka bir profesyonel tavsiye olarak yorumlanmamalıdır. Dijital varlık fiyatları oynak olabilir. Yatırımının değeri düşebilir veya yükselebilir._
