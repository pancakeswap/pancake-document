# Perpetuals V1 Sözlüğü

**Burada vadeli işlem ticaretine ilişkin tüm terimlerin tanımlarını bulacaksın**

### **Sürekli Trading**

Perpetual'lar, perpetual swap'lar veya kısaca perps; son kullanma tarihi olmayan özel bir vadeli işlem sözleşmesi türüdür.



### **Kaldıraç**

Kaldıraç bir işlem mekanizmasıdır. Traderlar, yatırımın tam tutarından daha azını ödeyerek piyasaya olan maruziyetlerini artırmak için kullanabilir. Basit bir deyişle, yatırımını kaldıraçlamak için borç alırsın.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **Marj**

Kaldıraçlı pozisyonların teminatıdır. İki farklı modda kullanılabilir:

* Çapraz Marj Modu: Aynı marj varlığı altındaki tüm çapraz pozisyonlar aynı varlık çapraz marj bakiyesini paylaşır. Tasfiye durumunda, varlıklarının tüm marj bakiyesi ve varlık altındaki açık pozisyonlar müsadere edilebilir.
* İzole Marj Modu: Her pozisyona ayrılan marj miktarını kısıtlayarak bireysel pozisyonlardaki riskinizi yönet. Bir pozisyonun marj oranı %100'e ulaştığında, pozisyon tasfiye edilir. Bu modda pozisyonlara marj eklenebilir veya çıkarılabilir.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Marj Oranı**: Marj Oranı = Bakım Marjı / Marj Bakiyesi. Marj Oranı %100'e ulaştığında pozisyonların tasfiye edilir.

**Bakım Oranı**: Açık pozisyonları korumak için gereken minimum marj bakiyesi miktarı.

**Marj Bakiyesi** = Cüzdan Bakiyesi + Gerçekleşmemiş PNL. Marj Bakiyesi <= Bakım Marjı olduğunda pozisyonların tasfiye edilir.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XbMw0LFJbqt4EJDkb7FNXnuK7r_BFnDvvwJcZ5BCkRLMbA91nkAYH2KTaKJCodDl4B_Tv3Aq53BkS)

### Varlıklar:

**Yatır**: Fonlarını vadeli işlemler hesabına yatır.

**Çek**: Fonlarını vadeli işlemler hesabından cüzdanına çek.

**Bakiye**: Cüzdan Bakiyesi = Toplam Net Transfer + Toplam Gerçekleşen Kâr + Toplam Net Fonlama Ücreti - Toplam Komisyon.

**Gerçekleşmemiş PNL**: Bu pozisyondaki gerçekleşmemiş kâr ve zarar, İşaret Fiyatı esas alınarak hesaplanır; özkaynak getirisi yüzdesidir.

**Modlar:**&#x20;

* Tek Varlık Modu: Yalnızca sembolün tek marj varlığını kullanarak USDⓈ-M Vadeli İşlemler ticaretini destekler. Aynı marj varlığı pozisyonlarının PNL'si mahsup edilebilir. Çapraz Marj Modunu ve İzole Marj Modunu destekler.
* Çoklu Varlık Modu: Birden fazla marj varlığında USDⓈ-M Vadeli İşlemler ticareti. PNL, farklı marj varlığı pozisyonları arasında mahsup edilebilir. Yalnızca Çapraz Marj Modunu destekler.

{% hint style="info" %}
Not: USDⓈ-M Vadeli İşlemler'de açık pozisyon veya açık emir varsa Çoklu Varlık Modu etkinleştirilemez. Çoklu Varlık Modu yalnızca USDⓈ-M Vadeli İşlemler için geçerlidir. Çoklu Varlık Modunu etkinleştirmeden önce, bu modu kullanırken USDⓈ-M Vadeli İşlemler hesap riskini daha iyi yönetmek amacıyla kılavuzu ayrıntılı olarak okuyun.<br>
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Emirler

**Al/Long:** Long emir aç. Bu emirde bir varlık satın alır ve fiyat yükseldiğinde satmak için beklersin. "Al" ve "long" birbirinin yerine kullanılır.

**Sat/Short:** Short emir aç. Bu emirde bir varlık ödünç alır, satarsın ve fiyat düştüğünde geri satın almayı umarsın. "Sat" ve "short" birbirinin yerine kullanılır.

**Limit Emri:** Limit emri, belirli bir fiyattan veya daha iyi bir fiyattan alım ya da satım emridir. Limit emirlerinin gerçekleşmesi garanti değildir.

**Piyasa Emri:** Piyasa emri, mevcut en iyi fiyattan alım veya satım emridir. Emir defterinde daha önce yerleştirilen limit emirlerine karşı gerçekleştirilir. Piyasa emri verirken piyasa alıcısı (taker) olarak ücret ödersin.

**Stop Limit Emri:** Stop limit emrini anlamanın en kolay yolu, onu stop fiyatı ve limit fiyatına ayırmaktır. Stop fiyatı, limit emrini tetikleyen fiyattır; limit fiyatı ise tetiklenen limit emrinin fiyatıdır. Bu, stop fiyatına ulaşıldığında limit emrinin emir defterine anında yerleştirileceği anlamına gelir.

**Stop Piyasa Emri:** Stop limit emrine benzer şekilde, stop piyasa emri de tetikleyici olarak bir stop fiyatı kullanır. Ancak stop fiyatına ulaşıldığında, limit emri yerine bir piyasa emri tetiklenir.

**İzleyen Stop:** İzleyen stop, bir işlem lehine hareket ederken kâr kilitleyen veya zararı sınırlayan bir emir türüdür. İzleyen stoplar yalnızca fiyat lehine hareket ettiğinde hareket eder. Kâr kilitlemek veya zararı azaltmak için hareket ettiğinde, diğer yönde geri dönmez.

**Yalnızca Gönder (Post Only):** Post-only Modu, Traderlerin yalnızca Emir Defterine Piyasa Yapıcı (Maker) Emir olarak gönderilecekse emir verebileceği anlamına gelir. Piyasa Alıcısı (Taker) Emri olarak gönderilecek emirler reddedilir. Piyasa Emri verilemez ve hiçbir emir gerçekleştirilmez. Post-only modunda bekleyen emirler iptal edilebilir.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**Yalnızca Azalt (Reduce Only):** Yalnızca Azalt emri, pozisyonunu yalnızca azaltır, artırmaz.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF talimatları**, emirlerinin gerçekleştirilmeden veya sona ermeden önce ne kadar süre aktif kalacağını belirlemenizi sağlar. TIF talimatları için şu seçeneklerden birini seçebilirsin:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_ui7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

* **GTC** (İptal Edilene Kadar Geçerli): Emir, gerçekleşene veya iptal edilene kadar aktif kalır.&#x20;
* **IOC** (Anlık Veya İptal): Emir hemen gerçekleştirilir (tamamen veya kısmen). Yalnızca kısmen gerçekleşirse, emrin gerçekleşmeyen kısmı iptal edilir.&#x20;
* **FOK** (Tamamen Gerçekleş veya İptal Et): Emir derhal tamamen gerçekleştirilmelidir. Aksi takdirde hiç gerçekleştirilmez.
