---
description: Tek tıklamayla basit likidite sağlama
hidden: true
---

# Zap (V2)

<img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-0.png" alt="" data-size="original">

### Zap Nedir? <a href="#h.lv839zkjvd8q" id="h.lv839zkjvd8q"></a>

Zap, basit likidite sağlamayı mümkün kılar. Manuel takas veya token dengeleme olmaksızın yalnızca bir token ve tek bir tıklamayla likidite ekle.

* Yalnızca bir token ile likidite ekle: İşlem çiftindeki yalnızca bir token'ı kullanarak likidite ekleyebilirsin. Zap, sağladığın bir token'ın yarısını otomatik olarak diğer token ile takas eder ve likidite eklemeden önce işlem çiftini otomatik olarak 50/50 dengeye getirir.
* Dengesiz sayıda token ile likidite ekle: İşlem çiftinde sağladığın token sayısı mevcut havuzun 50:50 ağırlığından farklı olsa bile likidite ekleyebilirsin. Örneğin 30:70. Zap, likidite eklemeden önce token'ları otomatik olarak 50/50 dengeye getirecektir.
* Liküditeyi kaldır ve almak istediğin token'ları seç: Likidite kaldırırken Zap, işlem çiftindeki yalnızca bir token almanı sağlar. Zap, token'larını iade etmeden önce otomatik olarak takas gerçekleştirir.

### Zap'ı Etkinleştir <a href="#h.8q1zrb4afp7i" id="h.8q1zrb4afp7i"></a>

Varsayılan olarak Zap özelliği her kullanıcı için açıktır. Likidite eklerken veya kaldırırken yeni Zap arayüzünü görmüyorsan lütfen ayarlar panelinde etkinleştir. Dişli simgesine tıklayarak ayarlar panelini açabilirsin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-8.png)

{% hint style="warning" %}
Not: Şu anda Zap özelliği beta sürümündedir. Transfer sırasında ücret alan token'lar gibi bazı token'ları desteklemediğini lütfen unutma. Likidite eklerken veya kaldırırken herhangi bir sorunla karşılaşırsan lütfen ayarlar panelinde devre dışı bırak.
{% endhint %}

### Zap İle Gir (Likidite Ekle) <a href="#h.xp3to7fwu7s6" id="h.xp3to7fwu7s6"></a>

[Likidite sayfasını](https://pancakeswap.finance/liquidity) ziyaret et ve "Likidite Ekle"yi seç.

İki giriş token'ı seçerek likidite sağlamak istediğin işlem çiftini seç; daha fazla bilgi için [Likidite kılavuzuna](https://docs.pancakeswap.finance/products/pancakeswap-exchange/liquidity-guide) göz at.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-1.png)

Devam etmek için "Likidite Ekle" butonuna tıkla.

Likidite eklediğin işlem çiftindeki token'ın cüzdanında bakiyesi varsa, o token için onay kutusu otomatik olarak işaretlenecektir. Her iki token için de cüzdanında bakiye varsa, her iki onay kutusu da işaretlenecektir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-6.png)

### Bir token ile Zap kullanma <a href="#h.oc5fxca1vzfj" id="h.oc5fxca1vzfj"></a>

İşlem çiftindeki yalnızca bir token'ı kullanarak likidite ekleyebilirsin. Kullanmak istediğin token için yalnızca bir onay kutusunu işaretle. Zap, işaretlenen token'ların yarısını likidite eklemeden önce işlem çiftindeki diğer token ile otomatik olarak takas eder. Hangi token'ın dönüştürüleceğini belirten bir uyarı mesajı göreceksin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-3.png)

{% hint style="info" %}
Fiyat etkisi çok yüksekse Zap seni Kayma ile koruyacaktır. Tercih edilen limite düşürmek için "TOKEN'ı Azalt"a tıkla.
{% endhint %}

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-7.png)

### Dengesiz miktarlarda iki token ile Zap kullanma <a href="#h.4k2b7plmt9t0" id="h.4k2b7plmt9t0"></a>

Her iki token da işaretliyse ve giriş token miktarları 50/50 dağılımla eşleşmiyorsa Zap dengeleme devreye girecektir. "A Token'ının bir kısmı B Token'ına dönüştürülecek" mesajı göreceksin.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-2.png)

{% hint style="info" %}
Likidite eklemeden önce Zap'ın token sayısını dengelemesini istemiyorsan "Dönüştürme" butonuna tıkla. Bu durumda Zap, takas ve yeniden dengeleme yapmak yerine giriş token sayısını 50/50 dağılıma uyacak şekilde ayarlayacaktır.
{% endhint %}

### Zap ile Devam Et <a href="#h.t4trnmo4dzno" id="h.t4trnmo4dzno"></a>

"Onayla"ya tıkladığında Zap detayları gösterilecek ve onayını bekleyecektir.

Şunları göreceksin:

1. Kaç LP token alacaksın.
2. Giriş token'ları nelerdir ve taahhüt ettiğin token sayısı.
3. 50/50 dağılımı sağlamak için giriş token'larının nasıl takas edildiği.
4. Kullandığın Kayma toleransı.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-4.png)

### Zap İle Çık (Likidite Kaldır) <a href="#h.whuk5lgc371r" id="h.whuk5lgc371r"></a>

Zap ayrıca likidite kaldırırken işlem çiftindeki tek bir token almanı da sağlar.

1. [Likidite sayfasını](https://pancakeswap.finance/swap#/pool) ziyaret et.
2. "Liküditeniz" altında likidite kaldırmak istediğin çifte tıkla.
3. "Kaldır"a tıkla. Yeni bir açılır pencere görünecektir.

"Alacaksın" bölümünde almak istemediğin token'ın işaretini kaldırabilirsin. Zap, likidite kaldırırken getirilerin %100'ünü otomatik olarak işaretli token'a dönüştürür.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/zap-5.png)
