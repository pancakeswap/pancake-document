# BscScan ile Farm'lar Nasıl Kullanılır?

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/how-to-yield-farms-bscscan-header.png)

Birden fazla adım gerektirdiğinden PancakeSwap ile Farm'ları kullanmak başta göz korkutucu gelebilir. Bu rehber, BscScan aracılığıyla doğrudan Farm sözleşmesiyle nasıl etkileşim kuracağını adım adım açıklayacak.

{% hint style="warning" %}
BscScan kullanarak sözleşmelerle etkileşim kurmanın yeni başlayanlar için önerilmediğini lütfen anla. Kendini yeterince güvende hissetmiyorsan bunun yerine [Farm'ları Nasıl Kullanırım rehberini](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) kullanmanı tavsiye ederiz.
{% endhint %}

## Farm işlem tanımlayıcısını bulma

Farm akıllı sözleşmesiyle doğru şekilde etkileşim kurmak için LP çiftine karşılık gelen işlem tanımlayıcısına (PID) ihtiyacın olacak. Şu an için bunu bulmanın en kolay yolu GitHub'u kontrol etmektir.

1\. [GitHub'daki PancakeSwap web sitesinin Farm kodunu](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts) aç.

2\. **Control**/**command** + **F** ile proje adı değil, ticker üzerinden çiftini ara. Örneğin 'CAKE-BUSD'.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2871%29.png)

3\. PID numarasını — bu örnekte 389 — daha sonra kolayca erişebileceğin bir yere yaz veya kopyala. Buna daha sonra ihtiyacın olacak.

## BscScan Aracılığıyla LP Token Yatırma

BscScan kullanarak LP Token yatırma işlemine dahil olan birkaç adım var. Takip etmeyi kolaylaştırmak için adımlara böldük.

### Ana Staking Sözleşme adresini alma

Ana staking sözleşmesinin adresi: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

Bunu doğrulamak istiyorsan [PancakeSwap: Ana Staking Sözleşmesi BscScan sayfasını](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) ziyaret et. Adresi sol üstte göreceksin. Panoya kopyalamak için **sayfalar simgesine** tıkla. Yakında buna ihtiyacın olacak.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2877%29.png)

### LP Token sözleşmeni aç

Bir Farm'a harcamadan önce yatırmak istediğin LP Token için akıllı sözleşmeyi onaylaman gerekecek.

### Kaynak koddan

1\. Önce [GitHub'da farms.ts'yi](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts) aç.

2\. **Control**/**command** + **F** ile proje adı değil, ticker üzerinden çiftini ara. Örneğin 'CAKE-BNB'

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28175%29.png)

3\. Aradığın LP çiftinin kodu göründüğünde "56:" sonrasındaki adresi bul. Bu senin sözleşme adresin olacak.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2849%29.png)

### Arayüzden

1\. Önce [PancakeSwap Farm'lar sayfasını](https://pancakeswap.finance/farms) ziyaret et ve sağ üstteki "SEARCH" alanını kullanarak seçtiğin çifti ara. Bu örnekte CAKE-BUSD kullanıyoruz.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2882%29.png)

2\. Daha fazla bilgi görmek için satırı genişletmek üzere **Detaylar**'a tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28236%29.png)

3\. Akıllı sözleşmeyi BscScan'de açmak için **Sözleşmeyi Görüntüle**'ye tıkla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28145%29.png)

### LP Token sözleşmesine izin verme

LP Token sözleşmen BscScan'de açıkken Farm'a LP Token harcamasını onaylayacaksın.

1\. LP Token sözleşme sayfasında **Sözleşme**'ye ve ardından **Sözleşmeye Yaz**'a git.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMask'ı bağlamak için **Web3'e Bağlan**'a tıkla.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Bağlantıyı onayla.

3\. 1. işlev olan "approve" altında "spender:address" göreceksin. Daha önce panoya kopyaladığın Ana Staking Sözleşmesi adresini buraya yapıştır.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28225%29.png)

5\. Sözleşmenin harcayabileceği LP Token miktarını da onaylaman gerekecek. Değer alanına miktarı Wei cinsinden girmen gerekiyor. Miktarını kolayca Wei'ye dönüştürmek için [BscScan Birim Dönüştürücüyü](https://www.bscscan.com/unitconverter) kullanabilirsin. Burada 5 CAKE-BUSD LP Token kullanıyoruz.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28158%29.png)

{% hint style="warning" %}
Sınırsız harcama onayı vermek için değer olarak `-1` de kullanabilirsin. Bu varsayılan olarak her şeyi harcayacağın anlamına gelmez; yalnızca bu sözleşmeyi kullanan herhangi bir büyüklükteki işlemin cüzdanın tarafından onaylanacağı anlamına gelir.
{% endhint %}

6\. **Yaz**'a tıkla ve MetaMask cüzdanındaki aksiyonu kabul et. Artık onayladığın miktara kadar LP Token yatırabilirsin.

### Ana Staking Sözleşme akıllı sözleşmesiyle LP Token Yatırma

Ana Staking Sözleşmesi artık LP Token'larını harcamak için onaylandığına göre yatırma zamanı geldi.

1\. [PancakeSwap: Ana Staking Sözleşmesi BscScan sayfasına](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) geri dön, **Sözleşme**'ye ve ardından **Sözleşmeye Yaz**'a git.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMask'ı bağlamak için **Web3'e Bağlan**'a tıkla.

3\. 2. işlev olan "deposit"e kaydır ve PID'ini "\_pid" alanına gir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2884%29.png)

PID'ini daha önce kopyalamadıysan bu sayfanın yukarısındaki **Farm işlem tanımlayıcısını bulma** bölümünden nasıl alacağını öğrenebilirsin.

4\. \_pid'in altında "\_amount" göreceksin. Daha önce onayladığın LP sözleşmesi için harcamak istediğin miktarı gir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28257%29.png)

5\. Bilgileri kontrol et ve **Yaz**'a tıkla. MetaMask'ta aksiyonunu onayla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **İşlemini Görüntüle**'ye tıklayarak yatırmanın çalıştığını onaylayabilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## Bir Pool'dan Para Çekme

LP Token'larını bir Pool'dan çekmek, yatırma işlemine çok benzer. Fark, hangi işlevle etkileşime geçeceğindedir.

1\. [PancakeSwap: Ana Staking Sözleşmesi BscScan sayfasına](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract) geri dön, **Sözleşme**'ye ve ardından **Sözleşmeye Yaz**'a git.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMask'ı bağlamak için **Web3'e Bağlan**'a tıkla.

3\. 15. işlev olan "withdraw"a kaydır ve PID'ini "\_pid" alanına gir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28166%29.png)

PID'ini daha önce kopyalamadıysan bu sayfanın yukarısındaki **Farm işlem tanımlayıcısını bulma** bölümünden nasıl alacağını öğrenebilirsin.

4\. \_pid'in altında "\_amount" göreceksin. Pool'dan çekmek istediğin LP miktarını gir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2837%29.png)

5\. Bilgileri kontrol et ve **Yaz**'a tıkla. MetaMask'ta aksiyonunu onayla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **İşlemini Görüntüle**'ye tıklayarak para çekmenin çalıştığını onaylayabilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)

## **Acil para çekme işlemi yapma**

‌Acil para çekme işlevi, başka hiçbir yol işe yaramadığında tüm fonlarını bir pool'dan çekmenizi sağlar.

{% hint style="danger" %}
**Acil para çekme işlevini kullanmak CAKE ödüllerinden vazgeçmene neden olur!**

PancakeSwap ekibi, bu işlevi yalnızca PancakeSwap ekibi tarafından resmi olarak tavsiye edildiğinde veya akıllı sözleşmelerle etkileşim konusunda çok rahatsanız ve temel kodu anlıyorsanız kullanmanı önerir.
{% endhint %}

‌1. [PancakeSwap: Ana Staking Sözleşmesi BscScan sayfasında](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), **Sözleşme**'ye ve ardından **Sözleşmeye Yaz**'a git.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28304%29.png)

2\. MetaMask'ı bağlamak için **Web3'e Bağlan**'a tıkla.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. 4. işlev olan "emergencyWithdraw"a kaydır ve PID'ini "\_pid" alanına gir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28275%29.png)

PID'ini daha önce kopyalamadıysan bu sayfanın yukarısındaki **Farm işlem tanımlayıcısını bulma** bölümünden nasıl alacağını öğrenebilirsin.

5\. Bilgileri kontrol et ve **Yaz**'a tıkla. MetaMask'ta aksiyonunu onayla.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2857%29.png)

6\. **İşlemini Görüntüle**'ye tıklayarak para çekmenin çalıştığını onaylayabilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28190%29.png)
