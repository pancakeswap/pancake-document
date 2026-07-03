# Cüzdan Oluştur (Monad)

### 1. **Neden Cüzdana İhtiyacın Var**

**Monad'da PancakeSwap** kullanmak için bir **kripto cüzdanına** ihtiyacın var — bu, dijital varlıkların için kişisel kasandır ve DeFi dünyasına açılan pasaportunudur. Cüzdan olmadan şunları yapamazsın:

* Monad'da token **Swap et**
* PancakeSwap'ın **V2 ve V3 Havuzlarına** **Likidite sağla**
* Monad'da herhangi bir dApp ile etkileşime gir veya token sakla

***

### 2. **Cüzdan Kurulumunun Temelleri (Önce Güvenlik!)**

Kripto cüzdanları, varlıkların üzerinde tam kontrol sağlar — ancak büyük güç, büyük sorumluluk getirir. Cüzdanını güvende tutmak için şu en iyi uygulamaları takip et:

| ✅ Yapılacaklar                                                                     | ❌ Yapılmayacaklar                                                    |
| ---------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| ✅ **Resmi kaynaklardan indir** (uygulama mağazaları, doğrulanmış web siteleri)     | ❌ Rastgele bağlantılardan veya DM'lerden yükleme                     |
| ✅ Kurulum talimatlarını **dikkatlice takip et**                                    | ❌ Yedekleme sürecini aceleye getirme veya atlama                     |
| ✅ **Kurtarma ifadesini yedekle** ve çevrimdışı bir yerde sakla                    | ❌ Ekran görüntüsü alma veya telefonunda/bilgisayarında saklama       |
| ✅ **İfadeni gizli tut** — erişimi geri kazanmanın tek yolu bu                     | ❌ Biri "destek" olduğunu iddia etse bile asla paylaşma              |
| ✅ Kurtarma ifadesini yalnızca **cüzdan uygulaması içinde** gir                   | ❌ Web sitelerine, pop-up'lara veya başka uygulamalara asla girme    |

> 🧠 Kurtarma ifaden = cüzdanına erişim

***

### 3. **Cüzdan Seçimi: Mobil mi, Masaüstü mü?**

Hangi cüzdan türünü kullanacağından emin değil misin? İşte tarzına uygun seçim yapabilmen için mobil ile masaüstü/web cüzdanlarını karşılaştıran hızlı bir özet:

| Özellik           | **Mobil Cüzdanlar**                  | **Tarayıcı/Masaüstü Cüzdanlar**            |
| ----------------- | ------------------------------------ | ------------------------------------------ |
| **Kullanım amacı** | Hareket halindeyken Swap ve takip    | Çoklu görev veya derin dApp kullanımı için |
| **Kullanım kolaylığı** | Sezgisel, yeni başlayan dostu   | Hafif eklentiler, hızlı erişim             |
| **Güvenlik**      | Telefon güvenliğine bağlı            | Daha kolay donanım cüzdanı entegrasyonu    |
| **Pratiklik**     | Hepsi bir arada uygulama             | Daha manuel, ama güçlü                     |
| **En iyisi...**   | Sıradan kullanıcılar, mobil işlemciler | Masaüstü kullanıcıları, daha gelişmiş akışlar |

> 📱 Mobil cüzdanlar işlem yapmak, portföy yönetmek ve NFT'lere göz atmak için daha akıcı bir deneyim sunabilir — hepsi telefonundan.

***

{% hint style="success" %}
**Monad ekosistemi için kullanabileceğin bazı popüler** [**cüzdanlar**](https://docs.monad.xyz/tooling-and-infra/wallets/software-wallets)**!**
{% endhint %}

***

#### 🔌 **WalletConnect Uyumlu Seçenekler**

**WalletConnect** kullanarak cüzdanları Monad'daki PancakeSwap'a bağlayabilirsin — masaüstünden veya mobilden doğrudan:

* **Leap wallet**
* **Bitget wallet**
* **HaHa wallet**
* **Backpack** ve daha fazlası

> WalletConnect üzerinden PancakeSwap arayüzünde bağlanırken desteklenen cüzdanların tam listesini göreceksin.

***

### 4. **Genel Cüzdan Kurulum Adımları (Hızlı Rehber)**

Hangi cüzdanı seçersen seç, süreç genel olarak benzerdir:

1. Cüzdan uygulamasını veya tarayıcı eklentisini **resmi kaynağından** **indir**
2. Uygulamayı başlat ve **"Create a new wallet"**'a dokun
   * (Ya da zaten birine sahipsen **"Import"**'u seç)
3. Güçlü bir **şifre veya PIN** belirle (gerekiyorsa)
4.  Sana bir **kurtarma ifadesi** (12 veya 24 kelime) gösterilecek —

    → **Yaz ve çevrimdışı güvenli bir yerde sakla**
5. Kurulumu tamamlamak için **kurtarma ifadesini onayla**
6.  **Cüzdanına MON yükle**

    → PancakeSwap'ta Swap yaparken veya likidite eklerken gas ücretlerini ödemek için **MON**'a ihtiyacın olacak
7. Varlıklarını Monad'a taşımak için bu [cross-chain bridge'i](https://monadbridge.com/) kullanabilirsin
