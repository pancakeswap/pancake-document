# 📔 Yönetişim

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
[Tokenomics 3.0 güncellemesinin](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3) bir parçası olarak bu sayfa 15 Mayıs 2025 tarihinde güncellendi
{% endhint %}

Oylama, PancakeSwap topluluğuna ses hakkı tanıyarak topluluğun PancakeSwap'ın geleceğini şekillendirmesine katkıda bulunmasını sağlar.

[PancakeSwap'ın yerel oylama portalını](https://pancakeswap.finance/voting) ve [Forum](https://forum.pancakeswap.finance/) sayfamızı incele.

## Oylama Mekanikleri

:notebook\_with\_decorative\_cover:Özet - Ne Değişti ([Tokenomics 3.0 Güncellemesinden](https://pancakeswap.finance/voting/proposal/0x79ef496c9737e48d9677a6e291ff2a549dee6729c9996398e453af8ecbf0ceb3) sonra)

<table><thead><tr><th width="200.6015625">Yönetişim Bileşeni</th><th width="218.01953125">Tokenomics 3.0 Öncesi</th><th width="205.1796875">Tokenomics 3.0 Sonrası</th><th>Durum<select><option value="q1dVFsCri7zA" label="✅ Değişti" color="blue"></option><option value="4AGl26rwjYcI" label="🔁 Değişmedi" color="blue"></option></select></th></tr></thead><tbody><tr><td>Oylama Gücü</td><td>1 veCAKE = 1 oylama gücü</td><td>1 CAKE = 1 oylama gücü</td><td><span data-option="q1dVFsCri7zA">✅ Değişti</span></td></tr><tr><td>Delegasyon</td><td>İzin verilir (veCAKE mekanikleri aracılığıyla)</td><td>Delegasyona izin verilmez</td><td><span data-option="q1dVFsCri7zA">✅ Değişti</span></td></tr><tr><td>Teklif Gönderme Eşiği</td><td>Snapshot için 100B veCAKE gerekli</td><td>Snapshot için 100B CAKE gerekli</td><td><span data-option="q1dVFsCri7zA">✅ Değişti</span></td></tr><tr><td>Temel vs Topluluk Teklifleri</td><td>Her teklif türü için tanımlanmış roller ve amaçlar</td><td>Değişiklik yok</td><td><span data-option="4AGl26rwjYcI">🔁 Değişmedi</span></td></tr><tr><td>Oylama Süresi</td><td>Topluluk: Sabit<br>Temel: Değişken</td><td>Değişiklik yok</td><td><span data-option="4AGl26rwjYcI">🔁 Değişmedi</span></td></tr><tr><td>Snapshot Zamanlaması</td><td>Teklifin yayınlandığı blokta</td><td>Değişiklik yok</td><td><span data-option="4AGl26rwjYcI">🔁 Değişmedi</span></td></tr><tr><td>Çekirdek</td><td>Minimum çekirdek yok</td><td>Değişiklik yok</td><td><span data-option="4AGl26rwjYcI">🔁 Değişmedi</span></td></tr></tbody></table>

### 1. **Oylama Gücü (Değişti)**

* **Tüm CAKE sahipleri doğrudan oy hakkına sahiptir.**
* **Oylama gücü, snapshot sırasında cüzdan adresinde tutulan CAKE miktarıyla doğru orantılıdır**
  * **1 CAKE = 1 oylama gücü**
  * **Syrup Pool'larda stake edilen CAKE**, snapshot anında cüzdan bakiyesinin parçası olmadığı için oylama gücüne **dahil edilmez**
  * Snapshot bakiyesi = Teklifin yayınlandığı blokla aynı
* **Delegasyon artık desteklenmemektedir.** Her CAKE sahibi bireysel olarak oy kullanmalıdır.

### 2. **Teklif Gönderme (Değişmedi)**

* **Teklif Nasıl Gönderilir**
  * [https://pancakeswap.finance/voting/proposal/create](https://pancakeswap.finance/voting/proposal/create) adresinden gönder
  * Şunları içermelidir:
    * Başlık
    * İçerik
    * Açıklama
    * Zincir üzeri aksiyon(lar) (gerekirse)
    * Oylama Süresi
* Teklif Türleri
  1.  Temel Teklifler

      * Yalnızca **PancakeSwap Çekirdek Ekibi** tarafından önerilebilir.
      * CAKE sahiplerinin oylamasını gerektirir.
      * Kabul edilirse PancakeSwap ekibi tarafından uygulanır.

      Örnekler

      1. Protokol ayarlamaları (ürün değişiklikleri, ücret değişiklikleri)
      2. Önceki tekliflerin kapsamadığı Ekosistem Büyüme fonlarının önemli kullanımları
  2. Topluluk Teklifleri
     * **Topluluk** teklifleri, PancakeSwap topluluğu tarafından yayınlanır. Fikir önermek ve topluluğun bakış açısını ifade etmek için kullanılır. Bunlar topluluktan **bağlayıcı olmayan önerilerdir**.
     * **100.000 CAKE (snapshot bakiyesi)** olan herkes gönderebilir.
     * PancakeSwap ekibi güçlü teklifleri gelecekteki Temel Tekliflere dönüştürebilir
     * Topluluk üyeleri ayrıca protokole geri bildirim ve önerilerde bulunmak için [Forumdan](https://forum.pancakeswap.finance/) yararlanabilir.

### **3. Oylama Süresi (Değişmedi)**

* Tüm CAKE sahipleri her teklif için **oylama penceresi süresince** oy kullanabilir.
  * Topluluk teklifi: 3 gün olarak sabit
  * Temel Teklif: PancakeSwap tarafından belirlenen değişken süre
* Oylama gücün, **teklifin yayınlandığı bloktaki CAKE bakiyenin snapshot'ı** ile belirlenir.
* **Teklif yayınlandıktan sonra daha fazla CAKE eklemek**, söz konusu oy için oylama gücünü artırmaz.

Tüm ayrıntılar için [Oylama Rehberine](https://docs.pancakeswap.finance/protocol/voting/voting-guide) bakın.

### **4. Oylama Sonucu (Değişmedi)**

* Sonuç, **kullanılan toplam oylar** (oylama için kullanılan toplam CAKE) temel alınarak belirlenir.
* Bir teklifin geçmesi için şu anda **minimum çekirdek zorunluluğu yoktur**.

## Not: Veto Hakları

Protokolü korumak adına **PancakeSwap Çekirdek Ekibi, kritik durumlarda** — güvenlik tehditleri veya platformun istikrarlı işleyişini etkileyen sorunlar gibi — **topluluk oylaması veya Snapshot anketi gerektirmeksizin müdahale etme hakkını saklı tutar**.

Veto aksiyonu alınan her durumda Çekirdek Ekip, kararın **açık bir açıklamasını kamuoyuyla paylaşacaktır**.

**Olası veto aksiyonları şunları içerebilir:**

1. **Acil hata veya güvenlik açıklarını gidermek için akıllı sözleşmeleri geçici olarak duraklatmak**.
