# Degen Mode Dinamik Ücret

PancakeSwap Perpetuals Degen Mode, dinamik bir ücret modeli kullanır. Bu ücret, ücretleri K&Z'a göre hesaplamak ve kullanıcıları kayıplardan korumak amacıyla tasarlanmıştır.\
**Nasıl çalışır?**

$$
\text{closeFeeRate} = \max\left(\frac{\text{pnl} \cdot \text{shareRate}}{\text{notional}}, \text{closeMinRate}\right)
$$

burada:

* Pnl, pozisyondaki kâr veya zarardır.
* shareRate, paylaşım oranıdır; ücretler olarak ödenen nominal değerin yüzdesidir (varsayılan olarak %15).
* Notional, pozisyonu açmak için kullanılan para miktarıdır.
* closeMinRate, minimum kapanış ücreti oranıdır; bir pozisyonu kapatmak için ödeyebileceğiniz en düşük miktardır (varsayılan olarak %0,03).

\
**Örnek:**

100 $ kâr, %15 paylaşım oranı ve 600 $ nominal değerli bir pozisyonunuz varsa kapanış ücreti oranı şöyle olur:

Kapanış ücreti oranı = Max(100 \* %15 / 600, %0,03) = %0,03

Bu durumda kapanış ücreti oranı, minimum kapanış ücreti oranı olan %0,03 olur.<br>

Not:

İşlem gerçekleştirme ücreti yalnızca bir pozisyon açıldığında alınır. BNB Chain için 0,3 USD / Arbitrum için 0,2 USD / opBNB için 0,01 USD / Base için 0,3 USD olarak belirlenmiştir; klasik sürekli işlem çiftlerinde alınan ücretle aynıdır. Pozisyon açma ücreti yoktur.

Tasfiye durumunda, %90 likidite kayıp oranı kapanış ücretini içerir.
