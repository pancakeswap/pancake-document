# Perpetuals V2 Sözlüğü

**Burada vadeli işlem ticaretine ilişkin tüm terimlerin tanımlarını bulacaksın**

### **Sürekli Trading**

Perpetual'lar, perpetual swap'lar veya kısaca perps; son kullanma tarihi olmayan özel bir vadeli işlem sözleşmesi türüdür.

### **Kaldıraç**

Kaldıraç bir işlem mekanizmasıdır. Traderlar, yatırımın tam tutarından daha azını ödeyerek piyasaya olan maruziyetlerini artırmak için kullanabilir. Basit bir deyişle, yatırımını kaldıraçlamak için borç alırsın.

### Emirler

**Long:** Long emir aç. Bu emirde bir varlık satın alır ve fiyat yükseldiğinde satmak için beklersin. "Al" ve "long" birbirinin yerine kullanılır.

**Short:** Short emir aç. Bu emirde bir varlık ödünç alır, satarsın ve fiyat düştüğünde geri satın almayı umarsın. "Sat" ve "short" birbirinin yerine kullanılır.

**Limit Emri:** Limit emri, belirli bir fiyattan veya daha iyi bir fiyattan alım ya da satımdır. Limit emirlerinin gerçekleşmesi garanti değildir.

**Piyasa Emri:** Piyasa emri, mevcut en iyi fiyattan alım veya satım emridir.

#### Pozisyon Yönetimi

Kullanıcılar, işlem sayfasının alt kısmındaki "Pozisyon" seçeneğine tıklayarak açık pozisyonlarının açılış fiyatı gibi ayrıntılarını kontrol edebilir. Açılış fiyatı, pozisyon sayısı, son fiyat ve zorunlu tasfiye fiyatı gibi ayrıntıları görüntüleyebilirler.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Perp5.png" alt=""><figcaption></figcaption></figure>

**Pozisyon modu**

PancakeSwap, her v2 işlem çifti için izole kaldıraç modunu kullanacak. Çiftler bağımsız olarak çalışır:&#x20;

* Her işlem çifti izole bir pozisyondur; kullanıcılar birden fazla izole pozisyon açabilir.
* Her pozisyon (işlem çifti) bağımsız olarak çalışır. Kullanıcıların marjlarını tamamlamaları gerekirse, diğer ayrı pozisyonlarda kullanılabilir varlıkları olsa bile bunu manuel olarak yapmaları gerekecektir (ApolloX gelecekte otomatik tamamlamayı destekleyecek).
* Her izole işlem pozisyonunun kendi risk oranı ve tasfiye fiyatı olacak ve bireysel olarak kapatılacak.
* Tasfiye riski her işlem çifti için izole edilmiştir. Bir pozisyon tasfiye edilirse, diğer pozisyonlar etkilenmez.

**Pozisyonu kapatma**

Kullanıcılar "Pozisyonu Kapat" seçeneğine tıklayarak pozisyonlarını kapatabilir.

#### Ücretler ve Kayma

Ücretler hakkında daha fazla bilgi için lütfen [Aster'ın sayfasını](https://docs.asterdex.com/product/asterex-simple/fees-and-slippage) ziyaret edin.
