# Referans Ajan — Sipariş/Intent Takas Ajanı

> PancakeSwap agregasyonu aracılığıyla tek bir swap-intent Job'u yönlendirerek ve hedef tokeni doğrudan İstemciye teslim ederek gerçekleştiren bir ERC-8183 Provider ajanı.

### 0. ERC-8183 ile nasıl eşleşir

ERC-8183 (Agentic Commerce; Virtuals + Ethereum Foundation), üç rol ve Open → Funded → Submitted → Terminal durumlarına sahip bir **Job** tanımlar. BNB'nin **BNBAgent SDK**'sı canlı uygulamadır.

| Rol                                                      | Bu ajanın içinde                                                                                                                          |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **İstemci** (Agent-A)                                    | Bir swap intent gönderir: "X miktarda token A → token B swap et, ≥ `minOut` teslim et", girişi + bir bahşişi emanete al                  |
| **Sağlayıcı** (Agent-B) — **bu bizim referans ajanımız** | **PancakeSwap agregasyonu** aracılığıyla fiyat teklifi alır ve `minOut`'u karşılayabiliyorsa/geçebiliyorsa swap'ı yürütür ve token B'yi İstemciye teslim eder |
| **Değerlendirici**                                       | İstemcinin token-B miktarı ≥ `minOut` aldığını doğrular; bahşişi serbest bırakır (veya İstemciye iade eder)                              |

Teslim edilebilir nesnel ("İstemci ≥ `minOut` aldı mı?"), bu tam olarak bu ERC-8183'e uyan nedenidir; yeniden dengeleyicinin uymadığı yer.

***

### 1. Amaç ve tek satırlık kapsam

> PancakeSwap agregasyonu aracılığıyla tek bir swap-intent Job'u yönlendirerek ve hedef tokeni doğrudan İstemciye teslim ederek gerçekleştiren bir **Sağlayıcı** ajanı — ve başka bir şey değil.

***

### 2. Ajanın YAPMAYA İZİNLİ olduğu işlemler (yetenek izin listesi)

| # | Yetenek                  | Yüzey                                                         | Notlar                                                                   |
| - | ------------------------ | ------------------------------------------------------------- | ------------------------------------------------------------------------ |
| A | Açık Job'ları keşfet     | BNBAgent SDK (ERC-8183 kayıt defteri)                         | Salt okunur; sunabileceği swap-intent Job'larını filtrele                 |
| B | Bir rota fiyatı al       | **PancakeSwap agregasyonu** (Aggregator API / Smart Router)   | Salt okunur; V3 genelinde en iyi fiyat                                   |
| C | Bir Job'u kabul et       | BNBAgent SDK (Funded → committed)                             | Yalnızca taze fiyat teklifi ≥ `minOut` ve bahşiş ≥ taban ise            |
| D | Swap'ı yürüt             | PancakeSwap router                                            | Girdi Job emanetinden çekilir; **çıktı alıcısı = İstemci**, tek işlemde |
| E | Teslim edilebiliri sun   | BNBAgent SDK (→ Submitted)                                    | Kanıt olarak takas işlem karması                                         |
| F | Bahşişi talep et         | ERC-8183 emaneti / x402                                       | Yalnızca Değerlendirici Job'u Terminal olarak işaretledikten sonra       |

**Her takas çıktısı doğrudan İstemciye gider. Ajanın tek kazancı Job'un bahşişidir.**

***

### 3. Sert güvenlik önlemleri (öne çıkma koşulları)

| Güvenlik Önlemi                   | Kural                                                                                                                                                             |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Yerine getiremeyeceğini kabul etme** | Bir Job'u yalnızca _taze_ fiyat teklifi `minOut`'u geçiyorsa kabul et. Geçemiyorsa Job'u başka bir Sağlayıcı için Funded durumunda bırak.                     |
| **Yürütmede yeniden fiyat teklifi al** | Takas öncesinde hemen yeniden fiyat teklifi al; rota artık `minOut`'u geçemiyorsa iptal et (bayat fiyat teklifi yok).                                         |
| **Atomik takas**                  | Emanetten çek → swap → İstemciye teslim et **tek işlemde**, çıktı alıcısı = İstemci. Ajan, İstemcinin fonlarını başarısız bir adımda hiçbir zaman tutmamalıdır. |
| **Kayma**                         | Yürütme Kayması sınırlı; teslim edilen miktar Kayma sonrasında hâlâ ≥ `minOut` olmalıdır, aksi hâlde işlem geri döner. Asla `amountOutMin = 0` olmamalı.       |
| **Son tarih**                     | Takas işleminde kısa son tarih (≤ 5 dakika); Job'un kendi son tarihine uy.                                                                                       |
| **Min bahşiş / maks değer**       | Bahşiş tabanının altındaki veya Job değeri tavanının üzerindeki Job'ları kabul etme.                                                                             |
| **Token güvenli listesi**         | Yalnızca PancakeSwap token listesindeki tokenlardan oluşan Job'lara hizmet et (honeypot / sahte token önlemi).                                                  |
| **Tek Job eşzamanlılığı (v1)**    | Bir seferde bir Job gerçekleştir; aşırı taahhüt yok.                                                                                                             |
| **Gas ön koşulu**                 | Kabul etmeden önce tam takas için yeterli BNB olduğunu doğrula.                                                                                                  |
| **Idempotent**                    | Zaten Submitted/Terminal olan bir Job'u asla çift gönderme veya yeniden gerçekleştirme.                                                                          |

Herhangi bir kural karşılanamıyorsa **Job'u atla** — asla zorla bir takas yapma.

***

### 4. Kapsam dışı — ajan YAPMAMALI

1. **İstemci fonlarını belirtilen swap dışında herhangi bir şey için kullanma.** Çıktı alıcısı her zaman İstemcidir.
2. **Kendi envanterinden öne çıkma / ana para riski alma.** v1 **yalnızca emanetten çekme** — İstemcinin emanete alınan girdisini yönlendirir; kendi bakiyesinden doldurmaz.
3. **PancakeSwap dışı veya doğrulanmamış sözleşmeler üzerinden yönlendirme** veya PancakeSwap agregasyonu dışında takas yapma.
4. **Güvenli listede olmayan tokenlardan oluşan Job'lara hizmet etme** veya (v1) scaled-UI / RWA tokenı içeren herhangi bir Job'a hizmet etme (§5).
5. **Kaldıraç, perp, marjin veya borçlanma kullanma.**
6. **Gerçekten gerçekleştirmediği bir teslimi sunma** (sahte kanıt yok) veya **kendi Job'larını değerlendirme** (çıkar çatışması).
7. **PancakeSwap veya ERC-8183 sözleşmeleri üzerindeki herhangi bir owner/admin işlevini çağırma.**
8. **Tek bir takas ötesinde sürekli token onayları tutma**; onayları Job miktarına kapsama al.

***

### 5. PancakeSwap'a özgü mantık (uygulama doğruluğu)

* **PancakeSwap agregasyonu üzerinden yönlendir**, tek bir havuz değil — V2 / V3 / Stable genelinde en iyi yürütme tüm değer teklifini oluşturur ("en iyi fiyat bahşişi kazanır").
* Router'ın `recipient`'ını İstemci adresine ayarlayarak **atomik olarak İstemciye teslim et**; asla "kendine swap et, sonra aktar" şeklinde iki adımlı bir yöntem kullanma.
* **Fiyat teklifi tazeliği** — Zincir üstü fiyat keşif ile takas arasında değişir; yürütmede yeniden fiyat teklifi al (güvenlik önlemi §3).
* **`minOut` ham birimlerdir.** **Scaled-UI / ERC-8056 tokenları** (Binance Hisse Tokenları / RWA hisseleri) için ham ≠ görüntülenen; yanlış işlem sessizce yanlış teslimata yol açar. **Scaled-UI tokenlarını v1'den hariç tut** — mühendislik ham birim işlemini uçtan uca doğrulayana kadar.
* Takas işlemindeki **Kayma minimumu**, teslim edilen miktar ≥ `minOut` olacak şekilde türetilmeli; bahşiş/ücret bölümünü hesaba katarak.

***

### 6. Başarısızlık ve kurtarma davranışı

* **Yürütmede fiyat teklifi `minOut`'u karşılamıyor** → emanet çekmeden önce/atomik olarak iptal et; Job başka bir Sağlayıcı için Funded durumunda kalır. Kısmi durum yok.
* **Zaten Submitted/Terminal** → atla (idempotent).
* **Takas işlemi geri döndü** → Job başkaları tarafından talep edilebilir kalır; ajan başarısızlığı kaydedip devam eder.
* **Bir Job üzerinde tekrarlanan başarısızlıklar** → yeniden deneme döngüsü yerine söz konusu Job'u yerel olarak kara listeye al ve uyar.

***

### 7. Entegrasyon noktaları (BNB / ERC-8183 tarafı)

Bunlar BNB Agent Studio / BNBAgent SDK tarafından sağlanır, PancakeSwap tarafından oluşturulmaz — ancak spec bunlara bağımlıdır:

* **Job yaşam döngüsü** (Open'ı keşfet → Funded'ı kabul et → Submitted → talep et) BNBAgent SDK aracılığıyla.
* **Sağlayıcı kimliği** ERC-8004 aracılığıyla.
* **Emanet + ödeme** ERC-8183 emaneti / x402 aracılığıyla.
* **Değerlendirici** — kriter "İstemcinin token-B bakiyesi ≥ `minOut` arttı" olmalıdır. **Değerlendiriciyi kimin çalıştırdığını** (tarafsız/protokol vs. İstemci) ve kriterin zincir üzerinde uygulanabilir olup olmadığını BNB ile doğrula.

***

### 8. Önerilen v1 tutumu ve açık kararlar

1. **Yalnızca emanetten çekme, tek seferde tek Job, yalnızca token güvenli listesi, scaled-UI tokenı yok.** Lansmanda öne çıkmak için en küçük güvenli yüzey.
2. **PancakeSwap swap arayüzünü doğrula** — **Aggregator (`aggr`) HTTP API** vs. **Smart Router SDK**. Jerry'nin notu "pcs aggr api kullan" diyor; ajanın hangisini çağırdığını doğrulama gerekiyor; bu entegrasyonu değiştirir (ve rehberin bir agregasyon bölümüne ihtiyaç duyup duymadığını).
3. **Emanet mekanizmasını** BNB ile doğrula — Sağlayıcı swap'ı yönlendirmek için İstemcinin emanete alınan girdisini çekebilir mi ve İstemciye teslimat, teslim edilebilir olarak uygulanabilir mi?
4. **Değerlendirici sahibini ve kriterini** doğrula (§7).

> Öne çıkmadan önce mühendislik onayı: atomik emanetten çekme → swap → İstemciye teslim yönlendirmesi; yürütmede yeniden fiyat teklifi; `minOut`-Kayma-sonrası matematiği; güvenli liste uygulaması; idempotent Job işlemi.
