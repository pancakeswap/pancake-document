# 🎁 Pancake Gifts

### 🎯 Pancake Gifts Nedir?

**Pancake Gifts**, herkese yalnızca bir **bağlantı** veya **QR kodu** kullanarak arkadaşlarına, kullanıcılara veya topluluklara isteğe bağlı gas dahil token göndermesini sağlar. Alıcı için basit, güvenli ve gassız bir deneyimdir.

Kripto dünyasına girişi bir mesaj göndermek kadar kolay hale getirecek şekilde tasarlandı — cüzdan finansmanı, Bridge veya ön ücret gerekmez.

### 🤝 Pancake Gifts'i Neden Geliştirdik

Web3'e katılmak hâlâ pek çok engel içeriyor. Yeni kullanıcılar çoğunlukla başlamadan bile pes ediyor; bunun nedenleri:

* **Cüzdanda gas yok** → Zincir üzerinde hiçbir işlem yapılamıyor
* **Doğru zincirde fon yok** → dApp'leri kullanmadan önce Bridge gerekiyor
* **Başlamak için kripto satın almak gerekiyor** → CEX kaydı veya fiat girişi zorunlu

Pancake Gifts bu engelleri şu şekilde ortadan kaldırıyor:

* ✅ Alıcıların anında etkileşim kurabilmesi için hediyeye **yerel gas tokenları dahil**
* ✅ **Gas ücretini önceden sponsorla** (gönderici küçük bir ücret öder)
* ✅ **Basit bir bağlantı veya QR ile talep et** — karmaşık ekleme süreci yok



Hem şunlar için bir araçtır:

* Zincir üzerinde başlamak isteyen yeni kullanıcılar
* **Benimsemeyi artırmak, kullanıcıları ödüllendirmek veya kampanyaları daha dostane bir şekilde yürütmek** isteyen Web3-yerli topluluklar

***

### ⚙️ Özellik Özeti

| Özellik                       | Açıklama                                                                           |
| ----------------------------- | ---------------------------------------------------------------------------------- |
| **Zincir Desteği**            | BNB Chain (ilk lansman)                                                            |
| **Hediye Kodu Türleri**       | Bağlantı **veya** QR Kodu                                                          |
| **Tek Kullanımlık**           | Her kod yalnızca bir kez talep edilebilir                                          |
| **Token Desteği**             | Maksimum 2 token: 1 BEP-20 (zorunlu), 1 yerel gas tokeni (isteğe bağlı)           |
| **Özel Miktarlar**            | Token başına farklı değerler ayarla                                                |
| **Hediye Talep Gas Ücreti**   | Gönderici gas'ı önceden öder (\~BNB cinsinden 0,05 $)                             |
| **Hediye Geçmişi**            | Kullanıcılar gönderilen tüm hediyeleri, talep durumunu, son kullanma tarihini görebilir |
| **Güvenlik Kontrolleri**      | Transfer ücreti olan ve karmaşık mantıklı tokenlar engellenir                     |

### 🚫 Sınırlamalar

1. **Kod başına bir hediye** — Toplu hediye henüz desteklenmiyor.
2. **Hediyeler yeniden devreye alınamaz** — İptal edildikten veya süresi dolduktan sonra yeniden kullanılamaz.
3. **Desteklenmeyen tokenlar engellenir** — Transfer ücreti veya özel mantığı olan tokenlar oluşturulurken hata gösterecek.
4. **Başarısız talepler yeniden denenir** — Arka uç birkaç kez yeniden dener. Hâlâ başarısız olursa hediye **talep edilemez** olarak işaretlenir ve fonları almak için manuel olarak iptal edilmesi gerekir.
5. **Hediye aynı zincirde talep edilmelidir** — Örneğin ETH hediyesi Ethereum'da talep edilmelidir. Cross-chain talep henüz desteklenmiyor.

***

### 🕒 İptal ve Son Kullanma Mantığı

Hediyeler duruma ve zamana göre tanımlanmış bir yaşam döngüsünü izler:

#### Manuel İptal

* **Oluşturucu**, hâlâ **talep edilmemiş** ve **son kullanma penceresi içinde** olan herhangi bir hediyeyi iptal edebilir.
* Tokenlar (ilk Hediye Talep Gas Ücreti eksi) göndericiye iade edilir.
* İptal edilen hediyeler **yeniden etkinleştirilemez** veya yeniden kullanılamaz.

#### Otomatik Son Kullanma

* Hediyeler, kullanıcı tanımlı bir süre sonra **otomatik olarak sona erer** (varsayılan: 7 gün).
* Talep edilmemiş tokenlar göndericinin cüzdanına **otomatik olarak iade edilir**.
* Süresi dolan hediyeler de yeniden kullanılamaz.

***

### 🔄 Hediye Durumları ve Anlamları

| Durum              | Açıklama                                                                            |
| ------------------ | ----------------------------------------------------------------------------------- |
| **Beklemede**      | Hediye oluşturuldu ve talep edilmesi bekleniyor                                    |
| **Talep Edildi**   | Hediye bir alıcı tarafından başarıyla talep edildi                                  |
| **İptal Edildi**   | Hediye gönderici tarafından manuel olarak iptal edildi                              |
| **Süresi Doldu**   | Hediye talep edilmeden son kullanma süresini geçti                                  |
| **Talep Edilemez** | Yeniden deneme sayısı aşıldı; fonları almak için hediyenin iptal edilmesi gerekiyor |

***

### ⚠️ Hata İşleme ve Uç Durumlar

1. **Desteklenmeyen Token**
   * Transfer ücreti veya özel mantığı olan tokenlar için hediye oluşturma engellenir.
2. **Gas Uyuşmazlığı**
   * **Gerçek talep gas maliyeti ≥** göndericinin önceden ödediği ücret ise aşırı kullanımı önlemek için talep otomatik olarak başarısız olur. Gas ücret seviyeleri aralıkta olduğunda yeniden denecektir.
3. **Başarısız Talep Girişimleri**
   * İlk başarısız talpete yeniden deneme yapılacaktır.
   * Hâlâ başarısız olursa:
     * Alıcı "Talep Edilemez" görür
     * Gönderici fonları almak için hediyeyi manuel olarak iptal etmeli; alıcının yeni bir hediye kodu talep etmesi veya alması gerekecektir.
