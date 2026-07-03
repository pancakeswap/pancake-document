# Pancake Gifts SSS

Bu SSS, Pancake Gifts'in arka planda nasıl çalıştığını, farklı senaryolarda neler bekleyeceğini ve belirli tasarım tercihlerinin neden yapıldığını ele alır.

***

## 1. 🔐 Hediye Kodu Davranışı ve Erişim

### **1.1 Hediye kodu neden saklanmıyor?**

Hediye kodunu **kasıtlı olarak** şunlarda saklamıyoruz:

* Ön uç yerel depolama
* Arka uç veritabanları

Bu şunları korur:

* Kullanıcı gizliliği
* Cihaz güvenliğine karşı güvenlik
* Kazara veya kötü niyetli hediye talepleri

### **1.2 Hediye kodunu daha sonra yeniden oluşturabilir veya alabilir miyim?**

Hayır. Hediye kodu:

* Oluşturma sırasında **yalnızca bir kez** gösterilir
* Oluşturulan **bağlantıya** veya **QR koduna** yerleştirilir
* Arayüzde veya geçmişte **tekrar gösterilmeyecek**

{% hint style="warning" %}
Kod kaybolursa ve bağlantıyı veya QR'ı kaydetmediysen hediye manuel olarak talep edilemez. Bunun yerine, hediye miktarını almak için manuel olarak iptal edebilirsin.
{% endhint %}

### **1.3 Hediye kodu yine de paylaşım bağlantısına veya QR'a yerleştirilecek mi?**

Evet:

* Paylaşım bağlantısı hediye kodunu içerir (örn. `pancakeswap.finance/gift#code=xxxx`)
* QR kodu da hediye kodunu içerir, ancak **daha sonra yeniden oluşturulamaz.**&#x20;

{% hint style="success" %}
**İpucu:** Oluşturulduğunda resmi indir
{% endhint %}

* Manuel talepler gerçek hediye kodunu gerektirir — bağlantı/QR kaybolursa yedek yol yoktur

## 2. 🎁 Hediye Durumu ve Son Kullanma

### **2.1 Hediyenin talep edilip edilmediğini, iptal edilip edilmediğini veya süresinin dolup dolmadığını görebilir miyim?**

Evet. **Hediye Geçmişi** bölümü şunları gösterir:

* Durum: Beklemede / Talep Edildi / İptal Edildi / Süresi Doldu / Talep Edilemez
* Hediye ayrıntıları (token, miktar, tür, zincir, zaman damgaları)

### **2.2 Hediyenin süresi dolduğunda ne olur?**

Hediye varsayılan **7 günlük süre** içinde talep edilmezse:

* **Tüm hediye miktarı** oluşturucunun cüzdanına iade edilir
* Sabit **talep gas ücreti (\~0,05 $) iade edilmez**

## 3. 🧠 Talep Mantığı ve Sınırlamalar

### **3.1 Kullanıcılar bir hediyeyi oluşturulduğundan farklı bir zincirde talep edebilir mi?**

Hayır. Hediye **zincire bağlıdır**:

* **BSC** üzerinde oluşturulan bir hediye **BSC** üzerinde talep edilmelidir
* Cross-chain hediyeleşme şu anda desteklenmiyor

## 4. ⛽ Gas Ücretleri ve Tasarım

### **4.1 Hediye oluşturma için sabit gas miktarı nasıl belirleniyor?**

Mevcut BNB Chain koşullarına göre sabit bir gas fiyatı belirliyoruz (\~mevcut önerilen Gas miktarının 5 katı).

Bu tampon:

* Ani gas artışlarına karşı koruma sağlar
* Normal volatilite altında hediyelerin talep edilebilir kalmasını sağlar

\
Örnek

* **Mevcut öneri: 0,1 Gwei** (bkz: [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Dolayısıyla, Sabit gas talep ücreti = 0,1 Gwei x 5 = 0,5 Gwei**


