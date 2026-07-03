# Social Login SSS

{% hint style="info" %}
Daha fazla bilgi için: [https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction](https://docs.privy.io/security/wallet-infrastructure/architecture#wallet-transaction)
{% endhint %}

### 🔍 Genel Bakış

**1. PancakeSwap'ın social login özelliği nedir ve neden kullanmalıyım?**

Social login, **Google**, **X (Twitter)**, **Discord** veya **Telegram** hesabınla PancakeSwap'a erişmeni sağlar — cüzdan eklentisine veya tohum ifadesine gerek yok. Arka planda kendi gözetiminde bir cüzdan oluşturulur; böylece, özellikle zamana duyarlı anlarda küçük miktarlarla bile DeFi'yi hemen deneyimleyebilirsin. Bu, giriş engelini önemli ölçüde düşürür.

**2. Social login hangi zincirleri destekler?**

Social login cüzdanın, PancakeSwap tarafından desteklenen tüm zincirlerde çalışır:

* **BNB Chain**
* **Ethereum**
* **Base**
* **Arbitrum**
* **Linea**
* **opBNB**

Tüm cüzdanlar **EVM uyumludur** ve PancakeSwap üzerinden bu ağlarda doğal olarak kullanılabilir. Diğer zincirlerin (EVM olmayanlar dahil) desteklenmesini istiyorsan bize bildirin!

**3. Social login cüzdanını nerede kullanabilirim?**

PancakeSwap web uygulaması aracılığıyla herhangi bir masaüstü veya mobil **tarayıcıda** doğrudan kullanabilirsin. Harici cüzdan uygulamaları veya dApp tarayıcılarıyla **uyumlu değildir**.



### 🛠️ Cüzdan Kurulumu ve Kullanımı

**4. Cüzdan nasıl oluşturulur ve güvence altına alınır?**

Cüzdanın, giriş yapıldığında otomatik olarak oluşturulur ve **2-of-2 anahtar payı sistemiyle** güvence altına alınır. Anahtarı yeniden oluşturmak ve imza üretmek için her iki pay da gereklidir.

Pay şifrelemesi hakkında daha fazla bilgi için:

* [https://docs.privy.io/security/wallet-infrastructure/architecture](https://docs.privy.io/security/wallet-infrastructure/architecture)
* [https://privy.io/blog/how-privy-embedded-wallets-work](https://privy.io/blog/how-privy-embedded-wallets-work)

**5. Kaç cüzdan oluşturabilirim?**

Sosyal hesap başına dApp başına **bir cüzdan** oluşturulur. Örneğin, Privy kullanan başka bir uygulamada da Google girişini kullanırsan ayrı bir cüzdan oluşturulur.



### 🔐 Güvenlik ve Gizlilik

**6. Biri cihazımı çalsa cüzdanıma erişebilir mi?**

Hayır. Biri cihazına erişim sağlasa bile hem **social login** hem de (ayarlanmışsa) **kurtarma parolana** ihtiyaç duyar.

**7. PancakeSwap veya Privy hangi verileri saklar?**

* PancakeSwap, cüzdanla ilgili herhangi bir anahtar payını **saklamaz**.
* Privy, **şifrelenmiş Auth Share ve Kurtarma Share'ini (kurtarma akışı ayarlanmamışsa)** saklar.

> Kurtarma kurulumunu tamamlamadıysan Kurtarma Share'in varsayılan olarak Privy'de saklanır. Daha fazla bilgi için: [https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share](https://docs.privy.io/security/wallet-infrastructure/advanced/user-device#securing-the-recovery-share)
>
>

### 🔄 Kurtarma ve Oturum Yönetimi

**8. Aynı cüzdanı farklı bir cihazda veya tarayıcıda kullanabilir miyim?**

Evet! Aynı sosyal hesapla giriş yap. Yeni bir cihazsa kurtarma parolanı kullanarak (ayarlandıysa) kurtarma sürecinden geçersin.

**9. Cihaz değiştirirsem ne olur?**

Sosyal hesabınla yeniden giriş yapman ve kurtarma akışından (parola kurulumu) geçmen istenir. Kurtarma parolası ayarlamadıysan sosyal hesap girişi yeterlidir.

**10. Hem social login'ime hem de kurtarma yöntemime erişimi kaybedersem ne olur?**

Hem sosyal hesabına hem de kurtarma yöntemine erişimi kaybedersen **cüzdanın kurtarılamaz**. Tohum ifadesi yedek seçeneği yoktur ve özel anahtar dışa aktarma şu anda desteklenmemektedir.

> ⚠️ Unutma: Özel anahtarını dışa aktarmak, ileride etkinleştirilirse, cüzdanının tam kontrolünü anahtara sahip olan herkese verir — son derece dikkatli ol.

**11. Aktif oturumlar ne kadar sürer?**

Oturumlar 30 **gün** sürer. Sonrasında **yeniden giriş yapman** ve (gerekirse) kurtarma bilgilerini tekrar girmen istenir. Aktif bir oturum süresince her işlem için manuel onay vermene gerek yoktur.



### ⚙️ Uyumluluk ve Sınırlamalar

**12. Cüzdanı dışa veya içe aktarabilir miyim?**

* **Dışa aktarma**: Güvenlik nedeniyle varsayılan olarak desteklenmez. Gelecekteki güncellemelerde değişebilir.
* **İçe aktarma**: Desteklenmez. MetaMask veya Phantom gibi harici cüzdanları içe aktaramazsın.

**13. Bu cüzdanı WalletConnect ile diğer dApp'lere bağlayabilir miyim?**

Şu an için hayır. Gömülü cüzdan **yalnızca PancakeSwap ile sınırlıdır**. Daha geniş kullanım ilginizi çekiyorsa bize bildirin — gelecekte genişleme mümkündür.



### 🚀 Gelişmiş Özellikler

**14. Social login cüzdanı Hesap Soyutlamasını destekliyor mu?**

Evet. Biconomy gibi entegrasyonlar aracılığıyla işlem gruplama ve **gas sponsorluğu** gibi **Hesap Soyutlama özelliklerini** destekler.

**15. İmzasız işlemler nasıl etkinleştirilir?**

* Girişin ardından oturumun 30 **güne** kadar aktif kalır. Bu süre zarfında PancakeSwap, oturum bilgilerini kullanarak Privy'den senin adına işlem imzalamasını isteyebilir.
* Her işlem için bir cüzdan açılır penceresi görmezsin — her şey arka planda yönetilir. 30 günün ardından bu imzasız deneyimi kullanmaya devam etmek için yeniden giriş yapman gerekir.
