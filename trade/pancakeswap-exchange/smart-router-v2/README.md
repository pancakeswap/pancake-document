---
hidden: true
---

# Smart Router (V2)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Smart%20Router.png" alt=""><figcaption></figcaption></figure>

PancakeSwap Smart Router, daha iyi likidite ve fiyatlandırma sunmak için AMM ve stableswap'ı (BNB Chain) ve AMM ile piyasa yapıcıları (Ethereum) birbirine bağlayan bir yönlendirme algoritmasıdır. Yatırımcılara en iyi fiyatı bulmak için birden fazla havuzda işlemleri gerçekleştiren akıllı bir emir yönlendirme algoritması kullanır. StableSwap hakkında daha fazla bilgi için [buraya tıkla](/broken/pages/nNPogTZMxocdyFIBYbkE) ve Piyasa Yapıcı entegrasyonu hakkında daha fazla bilgi için [buraya tıkla](../market-maker-integration.md).

Kitchen, ürünü daha fazla test etmek ve geliştirmek için StableSwap çiftlerini kademeli olarak kullanıma sunacak.

## AMM Swap'larım için neden Smart Router kullanmalıyım?&#x20;

* Benzer varlık fiyatlarına sahip stablecoin'lerini veya diğer çiftleri aynı işlem adımlarıyla daha verimli şekilde takas et.
* Normal PancakeSwap AMM'den daha iyi işlem gerçekleştirme sunabilecek piyasa yapıcılara karşı Swap yap.
* StableSwap fonksiyonu sayesinde işlem Kayması, normal AMM'den daha düşüktür.
* StableSwap işlem ücretleri, normal AMM'ye kıyasla daha düşüktür.

## Hâlâ Geliştiriliyor&#x20;

* Çıktıda daha iyi arayüz.
* Daha verimli işlemler için bölünmüş rotalar. Ör. Yönlendirici, işlem büyüklüğüne ve likiditesine bağlı olarak ücretlerden tasarruf etmek amacıyla çiftin %50'sini farklı bir rotaya gönderir.&#x20;
