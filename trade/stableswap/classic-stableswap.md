# Classic StableSwap

Classic StableSwap, Curve Finance'ın AMM'sinin PancakeSwap'ta uygulanmasıdır. Likidite havuzu aşırı dengesiz olmadığı sürece fiyatları daha eşit tutmak amacıyla sabit ürün formülünün (x\*y=k) üzerine doğrusal değişmez sabit toplam eğrisi (x+y=k) ekler. Sonuç olarak, StableSwap'lar benzer fiyatlı varlıklarla sınırlı olduğundan, kalıcı olmayan kayıp çok fazla endişe kaynağı değildir (aşırı fiyat ayrışması durumları hariç) ve Kayma, yalnızca sabit ürün formülünü kullanan normal AMM'den daha düşüktür.

StableSwap üzerinde bir Swap (işlem) gerçekleştirdiğinde, normal PancakeSwap AMM'deki olağan %0,25'ten daha düşük işlem ücreti ödersin. Ücret dağılımı şu şekildedir:

* %50 LP ödülü olarak
* %40 CAKE geri alımı ve yakımı için
* %10 PancakeSwap Hazinesi için

## StableSwap Ücretleri

Çiftlere ait ücretler aşağıdaki tabloda özetlenmiştir:

<table><thead><tr><th width="150">Kararlı Çift</th><th width="132">İşlem Ücretleri</th><th width="118.33333333333331">LP Ödülleri</th><th width="124">CAKE Geri Alımı</th><th>PancakeSwap Hazinesi</th></tr></thead><tbody><tr><td>USDT-BUSD</td><td>%0,01</td><td>%0,005</td><td>%0,004</td><td>%0,001</td></tr><tr><td>USDC-BUSD</td><td>%0,01</td><td>%0,005</td><td>%0,004</td><td>%0,001</td></tr><tr><td>USDC-USDT</td><td>%0,01</td><td>%0,005</td><td>%0,004</td><td>%0,001</td></tr><tr><td>HAY-BUSD</td><td>%0,04</td><td>%0,02</td><td>%0,016</td><td>%0,004</td></tr><tr><td>HAY-USDT</td><td>%0,04</td><td>%0,02</td><td>%0,016</td><td>%0,004</td></tr><tr><td>axlUSDC-USDT</td><td>%0,04</td><td>%0,02</td><td>%0,016</td><td>%0,004</td></tr><tr><td>BNBx-WBNB</td><td>%0,04</td><td>%0,02</td><td>%0,016</td><td>%0,004</td></tr><tr><td>stkBNB-WBNB</td><td>%0,04</td><td>%0,02</td><td>%0,016</td><td>%0,004</td></tr></tbody></table>

Mutfak ekibi, ürünü daha da test etmek ve geliştirmek amacıyla StableSwap çiftlerini kademeli olarak devreye alacak ve ücretleri gözden geçirecektir.

## Neden normal AMM Swap yerine StableSwap kullanmalıyım?

* Aynı işlem adımlarıyla stablecoin'lerini veya benzer varlık fiyatlarına sahip diğer çiftlerini daha verimli şekilde takas et
* StableSwap işleviyle işlem Kayması, normal AMM'ye kıyasla daha düşüktür
* StableSwap işlem ücretleri, normal AMM'ye kıyasla daha düşüktür
