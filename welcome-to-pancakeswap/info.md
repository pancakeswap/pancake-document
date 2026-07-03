# 📈 Analitik (Bilgi Sayfası)

## Bilgi Sayfası&#x20;

PancakeSwap'in yerleşik analitik sitesini buradan görüntüle: [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Tüm temel metrik verileri PCS dahili İndeksleyici'den alınır; bu indeksleyici de sözleşme çağrıldığında tetiklenen olaylardan verileri toplar.&#x20;

PancakeSwap'in dahili indeksleyicisindeki tarih boyutu için günlük istatistiklerde uluslararası standart saat dilimini (UTC) kullanıyoruz. Bu nedenle Gösterge Paneli'nin yatay ekseninde bir tarih göründüğünde, bu tarihin uluslararası standart saat dilimini (UTC) temsil ettiğini unutma.<br>

## Temel Metrikler

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Hacim (İşlem Hacmi):** Her işlem çifti için günlük verileri ve her token için günlük işlem verilerini takip ediyoruz. Günlük işlem hacmi, gün içindeki her tokenın işlem hacminin fiyatıyla çarpılmasıyla hesaplanır.

**Toplam Kilitli Değer:** Dahili İndeksleyici'den tüm havuzları alır ve her havuzdan reserve\_usd veya total\_value\_locked\_usd değerini okur.&#x20;

**Fiyat:** PCS Dahili İndeksleyici'de, USD ile ilgili fiyatları hesaplamak için birkaç temel havuz kullanıyoruz. Birincil havuz, temel havuz olarak en yüksek hacimli işlem havuzunu kullandığımız ve işlem hacmi ağırlığına göre sabit coinin USD fiyatını hesapladığımız sabit coin işlem havuzudur. Ayrıca, USD fiyatı sağlamak amacıyla zincirin sabit coinini temel token'ın işlem havuzu da temel havuz olarak değerlendirilir.

_Beyaz listeye alınmamış veya beyaz listedeki token'larla eşleştirilmemiş token'lar bu hesaplamaların dışında tutulur._

<br>
