# Tahmin SSS

{% hint style="info" %}
Sorularının cevaplarını hızlıca bulmak için yan çubuğu kullan!
{% endhint %}

## A) Genel Sorular

### **1. Ücretler nedir?**

Her turun toplam potunun %3'ü hazineye gider; bunun %100'ü CAKE geri alımı ve yakımı için kullanılır.

### 2. Ödeme nasıl hesaplanır?

* YUKARI Havuzu için Ödeme Oranı = Her İki Havuzun Toplam Değeri ÷ YUKARI Havuzunun Değeri
* AŞAĞI Havuzu için Ödeme Oranı = Her İki Havuzun Toplam Değeri ÷ AŞAĞI Havuzunun Değeri

**Örnek - 2 BNB "AŞAĞI" bahsi, sonuç = "AŞAĞI":**

* AŞAĞI taraf = 15 BNB, toplam ödül havuzu = 150 BNB&#x20;
* AŞAĞI ödeme oranı = 150 BNB / 15 BNB = 10x
* Ödeme Miktarı = Ödeme Oranı × Pozisyon × (1 - Hazine Ücreti)
  * AŞAĞI'ya 2 BNB bahis koyarsan ödeme = (2 × 10) × (1 − 0,03) = 19,4 BNB
* Kâr = 19,4 − 2 = 17,4 BNB

### 3. Kazançlarımı toplamak için zaman sınırı var mı?

Hayır, kazançlarını gelecekte istediğin zaman toplayabilirsin.

### 4. PancakeSwap Tahmin sözleşmesinin adresi nedir?

**BNB Chain**

* **BNBUSD**: [0x18b2a687610328590bc8f2e5fedde3b582a49cda](https://bscscan.com/address/0x18b2a687610328590bc8f2e5fedde3b582a49cda)
* **BTCUSD**: [0x48781a7d35f6137a9135Bbb984AF65fd6AB25618](https://bscscan.com/address/0x48781a7d35f6137a9135Bbb984AF65fd6AB25618#code)
* **ETHUSD**: [0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5](https://bscscan.com/address/0x7451F994A8D510CBCB46cF57D50F31F188Ff58F5#code)



## B) Pozisyonlar ve Sonuçlar

### 1. **Pozisyonumu değiştirebilir veya kaldırabilir miyim?**

Hayır. Bir pozisyona girdiğinde yönü DEĞİŞTİREMEZ, pozisyona ekleme YAPAMASsın veya pozisyonunu KALDIRAMASSSIN. Pozisyon kilitlendiğinden onaylamadan önce pozisyon yönünden %100 emin olduğundan emin ol.&#x20;

### 2. Piyasalar ne zaman iptal edilir? O zaman ne olur?

* **Ne zaman:** Oracle veya arka uç hizmet arızası ya da diğer olağandışı durumlar.
* **Sonuç:** Kullanıcılar orijinal bahis miktarlarının %100'ünü talep edebilir (ücret yok).

### 3. Tur sona erdikten sonra sonuç değişti! Neden?

Bazen bir tur kapandıktan sonra nihai sonuç, tur canlıyken gösterilen son sonuçtan farklı olabilir. Bir turun "AŞAĞI" ile sona erdiğini izlersen birkaç saniye sonra "YUKARI"ya döndüğü görünebilir.

Bunun nedeni, bir turun nihai sonucunu belirlemek için Oracle fiyat akışını kullanmamızdır. Bir turun sonu ile bir sonrakinin başlangıcı arasındaki süre 30 saniyedir, ancak Oracle her 20 saniyede bir yenilenir. Bu kısa süre içinde Oracle, sonraki turu başlatmak için gereken işlem üretilirken bir güncelleme gönderebilir. Bu durum önceki turun sonucunun "ters çevrilmiş" gibi görünmesine neden olabilir.

### 4. Kilit Fiyatı ve Kapanış Fiyatı nedir?

* **Kilit Fiyatı:** CANLI aşamasının başındaki fiyat.
* **Kapanış Fiyatı:** Turun sonundaki fiyat; kazananları belirlemek için kullanılır.

**Örnek – Tur 400 (BNB Tahmini):**

1. **12:00–12:05:** Bahis Yap → Kullanıcı 0,1 BNB ile "YUKARI" bahsi yapar
2. **12:05–12:10:** Kilit Aşaması → Kilit Fiyatı = 850 $
3. **12:10:** Kapanış Aşaması → Kapanış Fiyatı = 860 $
4. **Sonuç: "YUKARI"** bahsi kazanır

**Notlar:**

* Oracle fiyatı güncellemesi 20 saniyeye kadar sürebilir.
* Eve kazanır: Tüm bahisler eve gider

### 5. HANGİ durumlar EV KAZANCI olarak değerlendirilir?

**Senaryolar:**

1. Karşıt bahis yoksa ve kullanıcı kaybederse (örneğin, yalnızca bir kullanıcı YUKARI bahis yapar ve sonuç = AŞAĞI)
2. Kilit Fiyatı = Kapanış Fiyatı

**Ne olur:**

* PancakeSwap havuzun %100'ünü alır; tüm fonlar CAKE yakımına gider.
* Her iki taraftaki kullanıcılar ilk bahis miktarlarını kaybeder.

**Örnek - Karşıt bahis yok:**

* Kullanıcı A YUKARI bahis yapar, AŞAĞI bahis yok, sonuç = AŞAĞI → Kullanıcı A kaybeder; fonların %100'ü hazineye gider.
* Kullanıcı B YUKARI bahis yapar, AŞAĞI bahis yok, sonuç = YUKARI → Kullanıcı B yatırdığının %97'sini geri alır.



## C) Piyasa Duraklamaları

### 1. Piyasaların duraklatılması ne anlama gelir?

Piyasalar, sözleşmenin güvenilirliğini etkileyen koşullar oluştuğunda duraklatılır. Piyasaların duraklatılması, hiçbir turda bahis kabul edilmeyeceği anlamına gelir.

### 2. PancakeSwap Tahmin piyasasının duraklamasına ne yol açar?

Tahmin piyasası aşağıdaki koşullarda duraklar:

1. Tahmin sözleşmesi, tur sona erdiğinde oracle'ın fiyatı henüz yayınlamamış olması nedeniyle ChainLink oracle'dan fiyat alamamışsa.
2. Tahmin sözleşmesi, işlemin 15 bloktan uzun süre bellek havuzunda beklemesi nedeniyle bir eylemi (bir turu sona erdirme veya oracle'dan fiyat alma) yürütemediyse.
3. PancakeSwap, söz konusu piyasa / varlık için tahmini durdurmaya karar verdiyse.

### 3. Piyasa duraklandığında açık pozisyonum ne olur?

Canlı bir pozisyonun varken piyasalar duraklatılırsa, kazançlarını normalde talep ettiğin gibi fonlarını geri talep edebilirsin.

Fonları geri almak için biraz gas ücreti ödemen gerekir. Gas ücretleri için seni tazmin edemeyiz; bu nedenle lütfen katılmadan önce bu küçük riski göz önünde bulundur.

### 4. Piyasalar duraklatıldıktan sonra ne zaman yeniden başlar?

Piyasalar, bir yönetici (şeflerden biri) piyasayı manuel olarak yeniden başlattığında devam eder.



## D) Sorun Giderme ve Talepler

### 1. BNB Chain'deki CAKEUSD piyasasındaki geçmiş kazançlarımı nasıl talep ederim?&#x20;

* [https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc](https://pancakeswap.finance/prediction?token=CAKE\&chain=bsc) adresine git
* Geçmiş tur kazançları için geçmiş sekmesini kontrol et

### 2. Kazançlarımı neden cüzdanımda göremiyorum?

Kazançlarını topladığında, bunlar genellikle cüzdanının işlem günlüklerinde görünmeyebilir.\
Bunun nedeni farklı bir işlem türü kullanmalarıdır: Dahili işlemler.\
BscScan'de cüzdan adresini gir, ardından ulaştıklarını doğrulamak için "Internal Txns" sekmesini kontrol et.\
![](https://lh5.googleusercontent.com/9NoIvK-oztyEaizCfgrj-poPIP_uWeFDYsa0_nxN3sKUiIwFdACy_BemrtRLJn-ZkyW3LprfRn4s9lL24BOGb-I-t1vHoh5wkuTx7bObHQl5sS7xPmuZEOTVPUXr7LPNAfPfqr12)

### 3. Turun sonuçları neden gösterilmiyor?

Her turda 15 blokluk bir tampon süresi vardır; bu durum turun sona ermesinden sonra 45 saniyeye kadar gecikmelere neden olabilir.\
Bu tampon süresi, bir fiyatı güvenilir şekilde çekip bir turu hemen bitiremeyebileceğimiz gerçeğini göz önünde bulundurmak içindir: çeşitli blok zinciri faktörleri ağda işlemlerin onaylanma hızını etkiler.

### 4. Kazançlarımı toplayamıyorum, ne yapmalıyım?

Cüzdanında gas ücretlerini ödemek için yeterli BNB olduğundan emin ol. Akıllı sözleşmeyi tetiklemek için biraz BNB'ye ihtiyacın var.

### **5. Web sitesinden kazançlarımı talep edemiyorsam ne yapmalıyım?**

Kazançlarını doğrudan sözleşmeden talep edebilirsin. Aşağıdaki 3 sekmedeki adımları takip et.

{% tabs %}
{% tab title="Check rounds you played" %}
Oynadığın turların geçmişini nasıl kontrol edersin

1. [Tahmin sözleşmesinin](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) BscScan sayfasına git (örn. BNBUSD).
2. "8. getUserRounds" bölümüne kaydır.
3. "user(address)" altına cüzdan adresini yaz.
4. "cursor(uint256)" değerini 0, "size(uint256)" değerini 1000 olarak ayarla.
5. "Query"ye tıkla
6. Girdiğin turlar ilk satırda aşağıda gösterilecek. ("uint256\[]:" sonrasında)
{% endtab %}

{% tab title="Check if you can claim" %}
Önce, oynadığın turdan gerçekten talep edebilip edemeyeceğini kontrol et.

1. [Tahmin sözleşmesinin](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) BscScan sayfasına git (örn. BNBUSD) ve Okuma sekmesine git
2. "4. claimable" bölümüne kaydır.
3. Kontrol etmek istediğin tur kimliğini "epoch(uint256)" altına yaz.
4. Cüzdan adresini "user(address)" altına yaz.
5. "Query"ye tıkla
6. Bir tur talep edilebilirse "true" görünür.
7. Sonuç "false" ise, lütfen yukarıdaki adımları tekrarlayarak "19. refundable" ile dene.&#x20;
8. Not: ⬆️ Bir turun hem "4. claimable" hem de "19. refundable" için "false" döndürdüğünü ama web sitesinde göründüğünü görürsen muhtemelen çoktan talep edilmiştir ve web sitesi geride kalmıştır.
{% endtab %}

{% tab title="Claim from a round" %}
Talep etme yöntemi

1. [Tahmin sözleşmesinin](https://bscscan.com/address/0x0E3A8078EDD2021dadcdE733C6b4a86E51EE8f07#readContract) BscScan sayfasına git (örn. BNBUSD) ve Yazma sekmesine git
2. "🔴 Connect to Web3"e tıkla
3. Bağlanmak için MetaMask veya WalletConnect kullan.
4. "3. claim" bölümüne kaydır
5.  Talep etmek istediğin tur numarasını şu biçimde gir, \[] köşeli parantezler dahil: `[12345]`&#x20;

    Birden fazla turdan aynı anda talep etmek istiyorsan turları şu şekilde virgülle ayır: `[12345,12346,12347]`
6. "Write"a tıkla
7. Cüzdanda onayla&#x20;
{% endtab %}
{% endtabs %}
