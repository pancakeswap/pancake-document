# SSS

### CAKE'imi kilitledi ya da CAKE havuzu pozisyonumu taşıdım. Neden hâlâ 0 payım var? <a href="#cae64522-4729-43a2-8fa8-6bbd2567dcea" id="cae64522-4729-43a2-8fa8-6bbd2567dcea"></a>

Paylar, her Perşembe UTC 00:00'da gerçekleşen haftalık dağıtımda güncellenir.

Ödüller, tam bir epoch boyunca staking yaptığında birikmeye başlar.&#x20;

Epoch'lar, her Perşembe UTC 00:00'da başlayan 7 günlük dönemlerdir. Örneğin Salı günü stake yaparsan ilk epoch'un Perşembe başlar. Bir sonraki Perşembeye kadar staking yaptıktan sonra bu Perşembeden sonraki Perşembeye kadar olan epoch 1'in ödüllerini talep edebilirsin.

Güncellenmiş ödül rakamları için her Perşembe tekrar kontrol et.

### Aktif bir staking pozisyonum olmasına rağmen neden paylarım/ödüllerim 0? <a href="#9f2843b7-1a26-4248-8c3e-f5343b2de92e" id="9f2843b7-1a26-4248-8c3e-f5343b2de92e"></a>

Ödüller hesaplanırken kalan kilit süresi haftalara yuvarlanır. Bu nedenle pay almak için staking pozisyonunun en erken bir sonraki Perşembe UTC 00:00'da açılması gerekir.

Örneğin, 1. hafta 1 Ocak Perşembe UTC 00:00'da başlıyorsa ve 1. hafta dağıtımı için ödül almak istiyorsan:

* 1 Ocak UTC 00:00'dan önce katılman
* 15 Ocak UTC 00:00'da veya daha sonra açılan aktif bir veCAKE staking pozisyonuna sahip olman gerekiyor. (3. hafta Perşembe)

Staking pozisyonun 8 Ocak Perşembe UTC 00:00'da (2. hafta Perşembe) açılıyorsa veCAKE bakiyen 8 Ocak UTC 00:00'da sıfıra döneceğinden 1. hafta için yine 0 ödül alacağını unutma.

### Hafta ortasında bir dağıtım dönemine katılabilir miyim? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Hayır, belirtildiği üzere ödüller ancak epoch başladığında zaten staking yapıyor olman durumunda birikmeye başlar. Epoch her hafta Perşembe UTC 00:00'da başlar.&#x20;

### Nasıl daha fazla ödül alabilirim? <a href="#db254eef-09b7-41d7-bb56-310c77ce976b" id="db254eef-09b7-41d7-bb56-310c77ce976b"></a>

Havuzlardaki payların, bir sonraki Perşembe UTC 00:00'daki dağıtım anındaki veCAKE bakiyene göre hesaplandığından, daha fazla ödül almak için veCAKE bakiyeni şu şekillerde artırabilirsin:

* veCAKE staking pozisyonuna daha fazla CAKE kilitle
* Staking pozisyonunu yenile

CAKE ekledikten veya süreyi uzattıktan sonra paylarının yalnızca bir sonraki epoch başlangıcında, yani yaklaşan Perşembe UTC 00:00'da güncelleneceğini unutma.

### Neden haftalık enjekte edilen ödüller çeşitli takip araçlarında (Info sayfası gibi) gösterilen işlem hacmiyle tam olarak örtüşmüyor? Neden haftalık CAKE havuzu ödülleri gauges oylama sonuçlarıyla tam olarak eşleşmiyor?

Haftalık enjekte edilen CAKE ödüllerinin sayısı, çeşitli takip araçlarında gösterilen hacimden hesaplanan rakamlarla tam olarak örtüşmeyebilir. Dönüştürülebilecek CAKE ödülü miktarını etkileyen birden fazla dış etken bulunabilir:

* İşlem ücreti dönüştürülüp işlenirken CAKE token fiyatı
* İşlem ücreti dönüştürülüp işlenirken temel varlık fiyatları
* Gas ve operasyon maliyetlerini düşürmek için BNB Chain dışındaki blok zincirlerden elde edilen gelirler aylık işlenir. Bu gelirler haftalık ortalama ile bir ay gecikmeli olarak enjekte edilir.
* Bazı işlem çiftlerinin işlem ücreti işlenirken yetersiz likiditesi olabilir.
* Bazı işlem çiftleri, ücretlerinin işlenmesini engelleyen özel mantığa sahip token'lar içerebilir.
* Altyapı ve destek sistem performansından kaynaklanan işlem gecikmeleri.

Şefler, üretilen daha fazla işlem ücretinin işlenip CAKE'e dönüştürülebilmesi için araçlar ve uygulamalar geliştirmek adına yoğun çalışmaktadır.
