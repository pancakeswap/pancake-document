# Solana SSS

### V3 Havuzları – Sıkça Sorulan Sorular (SSS)

#### 1. Hangi ücret kademeleri mevcut?

**Desteklenen Ücret Kademeleri:**\
V3 (yoğunlaştırılmış likidite) havuzları için aşağıdaki ücret kademeleri mevcuttur:

`0.01%, 0.02%, 0.03%, 0.04%, 0.05%, 0.1%, 0.15%, 0.16%, 0.18%, 0.2%, 0.25%, 0.4%, 0.6%, 0.8%, 1%, 2%, 3%, 4%`

**Ücret Dağılımı (tüm ücret kademeleri için geçerlidir):**

* %84 likidite sağlayıcılara (LP)
* %16 protokole
  * %8 yakılır
  * %8 protokol hazinesine gider

#### 2. Herkes havuz oluşturabilir mi?

Evet. Havuz oluşturma birkaç istisna dışında izinsizdir:

* Belirli bir **token çifti + ücret kademesi** kombinasyonu için yalnızca bir havuz var olabilir (örn. aynı anda yalnızca bir SOL<> USDC %0,1 havuzu olabilir)
* Şu anda yalnızca **SPL token'ları** ve seçili **Token-2022** token'ları desteklenmektedir.

#### 3. Yeni oluşturulan bir havuzun görünmesi ne kadar sürer?

* Havuzlar genellikle oluşturulduktan yaklaşık **5 dakika** sonra havuz listesinde görünür.
* Görünmezse:
  * Manüel olarak bulmak için **arama çubuğunu** kullan.
  * Havuzlar **düşük TVL** nedeniyle listeden filtrelenmiş olabilir.

#### 4. Havuzumun APR veya TVL'si neden hâlâ sıfır gösteriyor?

Bu, yeni bir havuz oluşturulduğunda beklenen bir durumdur:

* APR ve TVL verileri yalnızca havuzda **en az bir Swap** gerçekleştikten sonra görünecektir.
* Bir Swap gerçekleştikten sonra bu metrikler yaklaşık **15 dakika** içinde gösterilmeye başlar.

#### 5. Havuz oluşturmak için özel bir token nasıl eklenir?

Yeni bir token eklemek için:

* Havuz oluşturma arayüzünde token seçicisini aç.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28410%29.png" alt="" width="248"><figcaption></figcaption></figure>

* Token'ın adresini arama çubuğuna yapıştır.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28411%29.png" alt="" width="247"><figcaption></figcaption></figure>

* **"Add Token"**'a tıkla.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28414%29.png" alt="" width="251"><figcaption></figcaption></figure>

* Token artık listede aranabilir olacak.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28412%29.png" alt="" width="249"><figcaption></figcaption></figure>

* Token'ları yönetmek için:
  * **"View Token List"**'e tıkla.
  * Manüel olarak eklenen token'ları içeren **Kullanıcı Eklenen Token Listesi** de dahil olmak üzere farklı listeleri açıp kapatabilirsin.

      <figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28413%29.png" alt="" width="247"><figcaption></figcaption></figure>

#### 6. Solana'daki ilk işlemim neden daha pahalı görünüyor?

Solana, her cüzdan için token bakiyelerini yönetmek amacıyla **İlişkili Token Hesapları (ATA)** kullanır. Bir token ile ilk kez etkileşime girerken cüzdanın bir ATA oluşturmalıdır; bu da tek seferlik bir başlangıç maliyeti (SOL cinsinden) gerektirir.

* Bu ATA oluşturma ücreti Solana protokolü tarafından zorunlu kılınmakta olup PancakeSwap'a özgü değildir.
* ATA daha sonra kapatılırsa, **başlangıçta kullanılan SOL iade alınabilir**.
