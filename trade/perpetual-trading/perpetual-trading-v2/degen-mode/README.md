---
hidden: true
---

# Degen Mode

Degen Trading Modu, traderlar'a geleneksel işlem yöntemlerine kıyasla alternatif bir işlem yolu sunar. Piyasayı analiz etmek için ekran başında daha az zaman geçirmeyi tercih eden ve daha az müdahaleci bir yaklaşım benimseyen traderlar bu işlem modunu seçebilir. Yüksek volatilite dönemlerinde, traderlar 0 kayma, yüksek kaldıraç ve son derece düşük ücretlerle kazançlarını maksimize edebilir. Düşük volatilitede ise traderlar küçük fiyat hareketleri üzerine spekülasyon yapabilir.

Başlangıçta Degen Trading Modu, long ve short piyasa emirleri için maksimum 1001x kaldıraç desteğiyle yalnızca BTCUSD için kullanılabilecektir. Traderlar, sıfır kayma ile pozisyon açmadan önce anapara (teminat miktarı) girmelidir.

Degen Mode, Perpetuals V2'de hem BNB Chain, Arbitrum, opBNB hem de Base zincirinde kullanılabilir.

### Degen Mode Formatı

Degen modu, sürekli trading yapanlara aşağıdaki oynanış özelliklerini ve avantajlarını sunar:

**Yüksek Kaldıraç, Daha Az Peşin Teminat —** 1001x gibi yüksek kaldıraç sayesinde kullanıcılar Degen Mode aracılığıyla işlem stratejilerini uygulayabilir ve güçlendirebilir. Kullanıcılar artık önemli miktarda peşin teminat yatırmadan daha yüksek kazanç potansiyeline sahip olabilir.

**Daha Düşük Ücretler —** Sıfır kaymalı işlemler sayesinde kullanıcılar daha iyi bir işlem deneyiminin keyfini çıkarabilir. Kullanıcılardan pozisyon açma ücreti alınmaz. Bu durum, pozisyon açma ücretlerinin artık teminat olarak kullanılabilmesiyle kullanıcıların işlem kazanç potansiyelini artırır.

**Dinamik Ücret Yapısı —** Degen Modu'na özgü olarak tasarlanan Dinamik Ücret Yapısı, kapanış pozisyonları için ücretleri Kâr ve Zarara (K&Z) dayalı olarak hesaplamak üzere titizlikle tasarlanmıştır. Dinamik ücret yapısı hakkında daha fazla bilgi için [buraya](degen-mode-dynamic-fee.md) bakın.

**Çift Teklifleri —** Degen Mode, BNB Chain, Arbitrum, opBNB ve Base zincirinde BTCUSD için kullanılabilir.

### Nasıl çalışır

1. [https://perp.pancakeswap.finance/en/futures/v2/](https://perp.pancakeswap.finance/en/futures/v2/) adresine git veya ana sayfamızda "Perpetuals" seçeneğini seç.
2. Ekranın sağ üst kısmında "Long" veya "Short" pozisyonunu seç ve 1001x kaldıraç seçmek için kaldıraç düzenleyicisine tıkla.
3. Miktarı ve uygun kaldıracı seç.
4. Kâr al miktarını (%50 ile %300 arasında) seç ve **pozisyon aç**'a tıkla.
5. Pozisyonun ekranın alt kısmındaki "pozisyonlar" sekmesinde görünecektir.
6. Pozisyonu kapatmak için pozisyonun yanındaki "kapat" butonuna bas. Aksi takdirde Degen Mode kapanışı, kâr al veya tasfiye süresinde otomatik olarak gerçekleştirilecektir. Daha fazla bilgi için lütfen [perpetuals-glossary.md](../perpetuals-glossary.md "mention") ve [perpetual-trading-faq](../perpetual-trading-faq/ "mention") sayfalarına bakın.
