# Arbitrum

31 Ağustos 2023'te PancakeSwap Perpetuals, Arbitrum'da V2 Trading Ödülleri Programını başlatacak. Arbitrum'da [ALP'yi CAKE Syrup Pool'da stake eden](https://pancakeswap.finance/pools?chain=arb) kullanıcılar artırma çarpanlarından yararlanabilir. Ayrıca bu programda kazanılan ödüller için herhangi bir vesting süresi bulunmamaktadır. Kullanıcılar USDC ödüllerini istedikleri zaman talep edebilir. Ayrıntılar aşağıdaki gibidir:

Başlangıç zamanı: 31 Ağustos 2023, 08:00 (UTC)

Etkinlik (Dönem) süresi: Her Perşembe 08:00:00 UTC'den ertesi Perşembe 07:59:59'a kadar, 1 hafta sürmektedir

Ödül Dağıtım Zamanı: Her döngü günlük 00:00 (UTC) ile 23:59 (UTC) arasındadır. Ödüller her Perşembe yaklaşık 08:00 (UTC)'de dağıtılır. Kullanıcının seviyesi güncellendikten sonra ödüller hesaplanır ve dağıtılır. Kullanıcıların ödüller dağıtıldıktan sonra 30 gün içinde talep etmeleri gerekmektedir. Talep edilmezse platform ödülleri geri alır.&#x20;

Ödül miktarı: İlk 5 hafta için işlem ücretlerinin %25'i (USDC cinsinden). Bu ödül havuzu daha sonra seviyelere göre dağıtılacaktır.

Etkinlik kuralları: Arbitrum'da PancakeSwap Perpetuals V2'de işlem yapan kullanıcılar ödül havuzuna hak kazanır

### Seviye Dağılımı

Her Perşembe 08:00:00 UTC'de, geçen Perşembe 08:00:00 UTC ile bu Perşembe 07:59:59 arasındaki işlem verileri hesaplanır ve ardından Seviye kurallarına göre kullanıcının Seviyesi güncellenir. Seviye kuralları aşağıdaki gibidir (yapılandırma desteklenmektedir):

<table><thead><tr><th width="161">Seviye</th><th width="249.33333333333331">Açıklama</th><th>Ağırlık</th></tr></thead><tbody><tr><td>Elmas</td><td>Dönem işlem hacmi >=1M USD</td><td>5</td></tr><tr><td>Altın</td><td>Dönem işlem hacmi >=500K USD</td><td>3</td></tr><tr><td>Gümüş</td><td>Dönem işlem hacmi >=250K USD</td><td>1</td></tr></tbody></table>

**Not: Seviye kriterleri ve ağırlıkları, havuz likiditesine ve platformdaki genel işlem aktivitesine bağlı olarak değişebilir**

Ödüller, belirli bir seviyeye hak kazanan tüm kullanıcılara eşit olarak dağıtılır

### Trading Ödülleri hesaplama formülü:&#x20;

Her trading ödül döngüsünün sonunda, USDC ödüllerinin ağırlığını ve miktarını belirlemek için kullanıcının o döngüdeki efektif işlem hacmi hesaplanır.

Belirli ödül sayısı formülü şöyledir: r = min{R \* W/Sum(Wi), R \* %20\}, parametreler aşağıdaki gibidir:

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Kullanıcının mevcut dönem için çıkarılacak USDC ödülü miktarı</td></tr><tr><td>R</td><td>Mevcut dönemin ödülü R=(ETH ücretinin USDC değeri + DAI ücretinin USDC değeri + BTC ücretinin USDC değeri + USDC ücreti)*0,25; uzlaşmada %1 Swap ücreti düşülmesi gerekir, örneğin: haftalık ETH ücreti 1 ve ETH fiyatı 2.000 olduğunda, USDC değeri için ETH ücreti = 1 * 2000 * 0,99</td></tr><tr><td>W</td><td>Kullanıcının Seviye düzeyine karşılık gelen ağırlık</td></tr><tr><td>Sum(Wi)</td><td>Tüm kullanıcıların toplam ağırlık puanı. Wi herhangi bir kullanıcının ağırlığını, sum(Wi) ise tüm kullanıcıların toplam ağırlık puanlarını temsil eder.</td></tr></tbody></table>

* Kullanıcı başına maksimum gelir payı, program için ayrılan gelirin %20'si ile sınırlıdır

Hüküm ve Koşullar

* V2'deki her işlem çifti için işlem ücretlerindeki farklılık nedeniyle, efektif işlem hacimleri aynı olsa bile kullanıcıların aldıkları ödüller farklılık gösterebilir.
* Her döngü için dağıtılacak ödüller aşağıdaki sözleşme adresinde saklanacaktır:&#x20;
* PancakeSwap/ApolloX bu etkinlik için nihai yorum hakkını saklı tutar.



Risk Uyarısı: Kripto vadeli işlem ticareti önemli risk taşır. Tüm işlem faaliyetleri kendi takdirine ve riski üstlenmeye hazır olarak gerçekleştirilir. Buradaki bilgiler PancakeSwap/ApolloX'ten finansal veya yatırım tavsiyesi olarak değerlendirilmemelidir. PancakeSwap/ApolloX, PancakeSwap/ApolloX kullanımından kaynaklanabilecek herhangi bir kayıptan sorumlu tutulamaz.

<br>
