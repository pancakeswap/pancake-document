# Ücretler ve Rotalar

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%2861%29.png" alt=""><figcaption></figcaption></figure>

Exchange V3'te, PancakeSwap Smart Router varsayılan olarak V3, V2, StableSwap (BNB Chain) ile AMM ve piyasa yapıcılarından (BNB Chain ve Ethereum) gelen likiditeyi kullanarak işlemleri gerçekleştirir ve yatırımcılara en iyi fiyatı bulur.

Ancak kullanıcılar, yönlendiricinin hangi likidite kaynaklarını kullanacağını seçerek ve çoklu atlamalar ile bölünmüş yönlendirmeyi etkinleştirip devre dışı bırakarak işlemlerini her zaman özelleştirebilir.

### **Mevcut Swap'a Uygulanan Ücret Oranını ve Ücret Miktarını Kontrol Etme**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28182%29.png)

Mevcut Swap'ında ne kadar işlem ücreti alınacağını görmek için Swap ayrıntılar bölümündeki "Ücret" kısmını incele.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28296%29.png)

İşleminin şu anda hangi havuz türünden ve hangi ücret kademesinden yönlendirildiğini görmek için "Rota" bölümünü incele.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28265%29.png)

Daha fazla ayrıntı için büyüteç simgesine tıklayarak tam işlem rotası görünümünü aç.



### **Likidite kaynaklarını özelleştirme**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28289%29.png)

"Yönlendirmeyi Özelleştir" arayüzünün üst kısmında, yönlendiricinin işlemini yönlendirirken hangi likidite kaynağını kullanacağını seçebilirsin. Bu arayüzü açmak için:

* İşlem rotası görünümünün alt kısmındaki "Yönlendirmeyi Özelleştir" seçeneğine tıkla.
* Swap arayüzündeki çark simgesine tıkla, ardından alt kısımdaki "Yönlendirmeyi Özelleştir" seçeneğine tıkla.

Varsayılan olarak tüm likidite kaynakları etkindir ve Smart Router, PancakeSwap içindeki mevcut tüm likiditelerden tam anlamıyla yararlanır.

Yönlendiricinin işlemleri AMM likidite havuzları ile MM piyasa yapıcıları arasında yönlendirmeyeceğini unutma. İşlemin MM piyasa yapıcıları tarafından gerçekleştirildiğinde, herhangi bir AMM likidite havuzundan geçmeyecektir.

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28199%29.png)

Yapılandırmaları varsayılana sıfırlamak için sağ üst köşedeki "Sıfırla" düğmesine tıklayabilirsin.



### **Yönlendirme tercihlerini özelleştirme**

![](https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28129%29.png)

"Yönlendirmeyi Özelleştir" arayüzünün alt kısmında, çoklu atlamaları ve bölünmüş yönlendirmeyi etkinleştirip devre dışı bırakarak yönlendirme tercihlerini özelleştirebilirsin.

Çoklu atlamalar, token'ların en iyi fiyatı elde etmek için birkaç likidite havuzu arasında birden fazla atlamayla takas edilmesine olanak tanır. Bunu kapatmak, işlemleri doğrudan Swap'larla sınırlandırır; bu durum daha yüksek Kayma'ya hatta fon kaybına neden olabilir.

Bölünmüş yönlendirme, en iyi fiyatı elde etmek için token Swap'larının birden fazla rotaya bölünmesini sağlar. Bunu kapatmak, işlemlerin tek bir rota üzerinden gerçekleştirilmesini kısıtlar; bu durum düşük verimlilik veya daha yüksek Kayma ile sonuçlanabilir.

{% hint style="warning" %}
Özelleştirilmiş bir işlem yapılandırması nedeniyle işlemin gerçekleştirilemediğinde bir uyarı görünecektir. "Ayarlarını kontrol et" seçeneğine tıklayarak "Yönlendirmeyi Özelleştir" arayüzünü hızlıca açabilirsin. Ya da yapılandırmaları hızlıca sıfırlamak için "Varsayılana sıfırla" seçeneğini kullanabilirsin.
{% endhint %}
