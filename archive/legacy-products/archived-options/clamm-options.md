# CLAMM Options

{% hint style="danger" %}
\[ARŞİVLENDİ] Options – 11 Mart 2025 itibarıyla\
Hâlâ çekilecek likiditenin varsa lütfen https://www.stryke.xyz/en/trade adresini ziyaret ederek bunu hemen yap.
{% endhint %}

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/trading-campaign.jpg" alt=""><figcaption></figcaption></figure>



CLAMM Options, zincir üzeri opsiyon ticaretine yeni bir yaklaşım sunar; likidite sağlayıcılara PancakeSwap üzerindeki v3 likiditesinden yararlanmaları için bir platform sağlar. Bu sayede likiditeyi hem v3 Likidite Havuzları hem de opsiyon satışı için kullanarak standart AMM işlem ücretleri, opsiyon primleri ve ek ödüller kazanabilirler; yatırımcılar ise bu likiditeden yararlanarak çeşitli tokenlar üzerinde Amerikan tarzı opsiyon satın alabilir.

Stryke (eski adıyla Dopex) ekibi tarafından hazırlanan CLAMM options protokolü, opsiyon yatırımcıları (alıcılar) ve PancakeSwap v3 havuzları için verimli bir çift likidite sağlama sistemi sunar.

CLAMM Options'ın işleyişine ilişkin yapısal bir özet:

1. CLAMM options'a likidite ekleyen LP'ler, seçtikleri fiyat aralığında belirlenen PancakeSwap v3 havuzuna da eş zamanlı katkıda bulunur.
2. Bir opsiyon yatırımcısı (alıcı) pozisyon başlattığında likidite, opsiyon satışını kolaylaştırmak üzere v3 havuzundan çekilir. İlgili LP böylece bir opsiyon satıcısı konumuna geçer ve bir prim alır.
3. Opsiyon alıcıları tarafından kullanılmayan likidite PancakeSwap v3 havuzunda kalır ve işlem ücreti kazanabilir.
4. Opsiyon satmaktan ve bir v3 havuzunda likidite sağlamaktan elde edilen kazanım, aynı kalıcı kayıpla örtüşür; bu da kullanıcıların v3 havuzlarına likidite eklemenin standart yöntemiyle kıyaslandığında artan bir riskle karşılaşmadığını garanti eder.
5. LP'ler bazı risklerle karşı karşıyadır; çünkü likidite, düşük opsiyon alım talebi nedeniyle kullanılmadan kalabilir. Ayrıca likidite etkin olmayan bir aralıkta havuza eklendiğinden herhangi bir ücret kazanılmayabilir.

PancakeSwap'ın Amerikan tarzı CLAMM options'ları, 1 saat ile 24 saat arasında çeşitli vade süreleri sunarak Arbitrum zincirinde piyasaya çıkacak.

| **Piyasalar**         | ARB/USDC, ETH/USDC ve wBTC/USDC     |
| --------------------- | ----------------------------------- |
| **Opsiyon Türleri**   | Alım (Call) ve Satım (Put)          |
| **Kullanım Fiyatları**| v3 havuz tick'lerine dayalı         |
| **Vade Süreleri**     | 1S, 2S, 6S, 12S ve 24S              |

**Kullanım Koşulları:** Kullanıcılar, kâr içinde sona eren opsiyonların değersiz bitmesini önlemek için kapanıştan önce pozisyonlarını kullanabilir. Vade sonunda kârları otomatik olarak realize etmek, başka bir aksiyon gerektirmeksizin otomatik kullanım etkinleştirilebilir.

### Adım adım rehber

PancakeSwap CLAMM Options'ı kullanma adım adım rehberi aşağıdadır.

**Yatırımcılar için:** [https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap](https://blog.pancakeswap.finance/articles/how-to-trade-options-on-pancake-swap) \
**LP'ler için:** [https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options](https://blog.pancakeswap.finance/articles/how-to-provide-liquidity-on-pancake-swap-s-clamm-options)
