---
description: Ethereum ve BNB Chain gibi EVM'ler arasında Bridge yap
---

# Nasıl Bridge Yapılır – EVM'ler Arası

{% hint style="success" %}
**EVM'ler:** EVM zincirleri, Ethereum uyumlu akıllı sözleşmeleri ve dApp'leri çalıştırmak için Ethereum Sanal Makinesi'ni kullanan blokchaинlerdir. Ethereum, BNB Smart Chain vb. bunlara örnek verilebilir.
{% endhint %}

1. [https://pancakeswap.finance/bridge](https://pancakeswap.finance/bridge) adresine git
2. Cüzdanının bağlı olduğundan emin ol

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%281%29%20%283%29.png" alt=""><figcaption></figcaption></figure>

3. Ağ seçiciler aracılığıyla **kaynak** ve **hedef** zincirlerini seç

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%282%29%20%283%29.png" alt="" width="375"><figcaption></figcaption></figure>

4. Göndermek istediğin miktarı gir ve açılır listeden token'ı seç

* **İpucu:** Göndermeden önce token sözleşme adresini her zaman iki kez kontrol et!

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%283%29.png" alt="" width="374"><figcaption></figcaption></figure>

5. **Alınacak token'ı** seç – Token sembollerinin aynı olduğu durumlarda (örn. USDC / USDT) aralarından seçim yapabileceğin varyantlar görünecektir

* **İpucu:** Token adını ve adresini doğrulamak için token'ın üzerine gel veya bağlantıya tıkla

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%284%29%20%282%29.png" alt="" width="375"><figcaption><p>USDC</p></figcaption></figure>

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%285%29%20%282%29.png" alt="" width="375"><figcaption><p>USDC (Wormhole)</p></figcaption></figure>

6. Tüm detayların doğru olduğunu onaylamak için "Alacaksın" bölümünü incele

* PancakeSwap, kaynak ve hedef zincirlerine göre birden fazla Bridge sağlayıcısı arasından seçim yapar.
* Sağlayıcılar ücretler, işlem süreleri ve olası kısıtlamalar bakımından farklılık gösterir; bunlar açıkça gösterilecektir.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%28385%29.png" alt=""><figcaption></figcaption></figure>

* Etiketler rotaları karşılaştırmanı kolaylaştırır:
  * **En İyi Getiri** = en yüksek alınan miktar
  * **En Hızlı** = en kısa transfer süresi

İhtiyaçlarına göre hız ve değeri dengelemek için bu etiketleri kullan.

{% hint style="warning" %}
Bir Bridge sağlayıcısıyla **ilk işleminde** token transferini onaylaman istenecektir (bu tek seferlik bir işlemdir)

* **İkinci işleminde** yalnızca "Gönder"e tıkla, Bridge transferin başlayacaktır
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%286%29%20%281%29.png" alt=""><figcaption></figcaption></figure>

7. Arkanı yasla ve rahatla! Bridge transferlerinin büyük çoğunluğu yalnızca birkaç dakika içinde tamamlanır. İşlem tamamlandığında token'ların Ethereum adresinde görünecektir.
