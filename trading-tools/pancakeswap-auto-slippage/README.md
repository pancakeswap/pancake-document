# 🎯 PancakeSwap Auto Slippage

PancakeSwap, işlem yapmayı daha kolay ve verimli hale getirmek için Auto Slippage'ı sundu. Auto Slippage, mevcut piyasa koşullarına göre Kayma toleransını otomatik olarak ayarlayarak başarısız işlemleri önlemeye ve Kayma hatalarından kaynaklanan kayıpları azaltmaya yardımcı olur.

## Kayma Nedir?

**Kayma**, bir işlem için beklediğin fiyat ile işlemin gerçekleştiği fiyat arasındaki farktır. Bu durum çeşitli nedenlerle ortaya çıkabilir:

* Piyasa oynaklığı – Fiyatlar, işlemi yerleştirdiğinde ve onayladığında arasında hızla değişebilir
* Düşük likidite – Beklenen fiyatında yeterince token bulunmayabilir
* Blokzincir gecikmeleri – Onay süreleri, işlem tamamlanmadan önce fiyatın değişmesine neden olabilir

{% hint style="info" %}
Örnek:

100 CAKE'i BNB ile Swap etmeye çalışıyorsun ve 1 CAKE = 0,01 BNB bekliyorsun. Ancak işlem gerçekleştiğinde fiyat değişmiş ve CAKE başına yalnızca 0,0098 BNB alıyorsun. Bu küçük farka Kayma diyoruz.
{% endhint %}

## Kayma Toleransı Nedir?

**Kayma toleransı**, işlemin iptal edilmeden önce kabul etmeye razı olduğun maksimum fiyat farkıdır. Fiyat belirlediğin toleransın ötesine geçerse beklenmedik kayıpları önlemek için işlemin başarısız olur.

{% hint style="info" %}
Örnek:

%1 Kayma toleransı belirlersen ve işlem tamamlanmadan önce fiyat %1'den fazla değişirse işlem gerçekleşmez.
{% endhint %}

## Kayma Toleransım Çok Düşükse Ne Olur?

Kayma toleransın **çok düşük ayarlanmışsa** işlemin başarısız olma ihtimali yüksektir — özellikle şu durumlarda:

* Piyasa oynaklığı yüksek olduğunda
* Düşük likiditeye sahip tokenlar Swap edildiğinde
* Vergi veya karmaşık mekanizmaları olan tokenlar kullanıldığında

{% hint style="warning" %}
Önemli: İşlem başarısız olsa bile deneme için gas ücretlerini harcamış olursun.
{% endhint %}

## Auto Slippage'ı Tanıtalım — Auto Slippage Neden Faydalıdır?

Auto Slippage, Kayma toleransını mevcut piyasa koşullarına göre otomatik olarak ayarlayarak zamandan tasarruf etmeni sağlar ve başarısız işlem riskini azaltır.

**Auto Slippage** ile Kayma toleransını manuel olarak ayarlamana gerek yoktur. Bu, aşağıdaki yaygın sorunların önüne geçer:

* **Kayma toleransını çok düşük ayarlamak**, yürütme sırasında küçük fiyat değişimleri nedeniyle işlemlerin başarısız olmasına neden olabilir.
* **Kayma toleransını çok yüksek ayarlamak**, daha geniş bir fiyat aralığını kabul ettiğinden beklediğinden daha az token almayla sonuçlanabilir.

{% hint style="info" %}
En iyi işlem deneyimini sağlamak için auto slippage **otomatik olarak açıldı**. Manuel bir Kayma toleransı ayarlanmışsa yeni Kayma ayarı uygulanacaktır.
{% endhint %}



## Auto Slippage Nasıl Çalışır?

<pre class="language-html"><code class="lang-html"><strong>Auto Slippage (%) = (Gas Maliyeti USD / Çıktı Token Değeri USD) * %100
</strong></code></pre>

* Gas maliyeti çıktı tokenının değerine kıyasla yüksekse Auto Slippage, işlemin gerçekleşmesini sağlamak için daha yüksek bir Kayma değeri belirler.
* Gas ucuzsa ve çıktı tokenının değeri büyükse daha küçük bir Kayma kullanılır.

Auto Slippage, token ve ağ koşullarına bağlı olarak **%0,5** ile **%5,0** arasında bir değer seçer.



## Auto Slippage Tüm Ağlarda Kullanılabilir mi?

Hayır — Auto Slippage yalnızca BNB Chain, Ethereum gibi Katman 1 (L1) zincirlerde desteklenir.

Katman 2 (L2) zincirlerinde desteklenmez, çünkü:

* Auto Slippage formülü, yararlı bir Kayma ayarı hesaplamak için anlamlı gas maliyet değerlerine dayanır
* L2 gas ücretleri çok düşük olduğundan L2'lerde auto slippage uygulamak işlem başarı oranlarını iyileştirmez

{% hint style="success" %}
Auto Slippage bir ağda **desteklenmiyorsa**:

* Daha önce kullandığın Kayma ayarı uygulanır
* Daha önce bir ayar yapmadıysan varsayılan olarak %0,5 kullanılır
{% endhint %}


